Use Python version 3 to complete these exercises

#Exercise 1

Create a class `HttpRequestBuilder`, which can be used to construct an HTTP request to be sent.
You can read about the HTTP request format [here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages).

The class should have the following signature:

```python
class HttpRequestBuilder:
    def set_uri(self, uri):
        pass

    def add_header(self, name, value):
        pass

    def set_method(self, method):
        pass

    def to_string(self):
        pass
```

The following snippet demonstrates usage of the class:

```python
builder = HttpRequestBuilder()
builder.set_method('GET')
builder.set_uri('/')
builder.add_header('User-Agent', 'My own client')
builder.to_string() == '''\
GET / HTTP/1.1
User-Agent: My own client


'''
```

Read [this](http://www.diveintopython3.net/native-datatypes.html) to find out more about
fundamental data types in Python which will be useful for constructing your class.
Read [this](http://www.diveintopython3.net/iterators.html#defining-classes) for information 
on classes in Python.


To send the message over a socket, a HTTP request has to be transformed into the
byte array representing the request string encoded as ASCII characters.

Add a new method, `to_bytes` which returns a `bytes` object representing the request.

Read [this](http://www.diveintopython3.net/strings.html#byte-arrays) 
For information on characters and bytes in Python 3.