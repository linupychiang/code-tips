1. 在使用ipython，可以使用?做提示
```python
import requests
request?
```
回车后，发现会有相关提示
```shell
In [2]: requests?
Type:        module
String form: <module 'requests' from 'd:\\softs\\python\\python37\\lib\\site-packages\\requests\\__init__.py'>
File:        d:\softs\python\python37\lib\site-packages\requests\__init__.py
Docstring:
Requests HTTP Library
~~~~~~~~~~~~~~~~~~~~~

Requests is an HTTP library, written in Python, for human beings.
Basic GET usage:

   >>> import requests
   >>> r = requests.get('https://www.python.org')
   >>> r.status_code
   200
   >>> b'Python is a programming language' in r.content
   True

... or POST:

   >>> payload = dict(key1='value1', key2='value2')
   >>> r = requests.post('https://httpbin.org/post', data=payload)
   >>> print(r.text)
   {
     ...
     "form": {
       "key1": "value1",
       "key2": "value2"
     },
     ...
   }

The other HTTP methods are supported - see `requests.api`. Full documentation
is at <https://requests.readthedocs.io>.

:copyright: (c) 2017 by Kenneth Reitz.
:license: Apache 2.0, see LICENSE for more details.
```
```shell
In [3]: requests.get?
Signature: requests.get(url, params=None, **kwargs)
Docstring:
Sends a GET request.

:param url: URL for the new :class:`Request` object.
:param params: (optional) Dictionary, list of tuples or bytes to send
    in the query string for the :class:`Request`.
:param \*\*kwargs: Optional arguments that ``request`` takes.
:return: :class:`Response <Response>` object
:rtype: requests.Response
File:      d:\softs\python\python37\lib\site-packages\requests\api.py
Type:      function
```
2. ipython tab键，同样可以代码提示
```python
In [4]: requests.  (tab键)
       adapters                   ConnectTimeout             logging                    Request                    structures
       api                        cookies                    models                     request()                  Timeout
       auth                       delete()                   NullHandler                RequestException           TooManyRedirects
       certs                      DependencyWarning          options()                  RequestsDependencyWarning  urllib3
       chardet_version            exceptions                 packages                   Response                   URLRequired
       charset_normalizer_version FileModeWarning            patch()                    Session                    utils
       check_compatibility()      get()                      post()                     session()                  warnings
       codes                      head()                     PreparedRequest            sessions
       compat                     hooks                      put()                      ssl
       ConnectionError            HTTPError                  ReadTimeout                status_codes
```
3. requests 返回内容编码
requests 内部使用了chardet
还可以使用响应头的`Content-Type: text/html;charset=utf-8`来判断