# dirty-get
A simple utility package abstracting the native `http.get` with a promise.


**DO NOT** use this when you expect lengthy body contents. This puts the **entirety** of the body in memory.  
Make actual use of streams.

If you need contents of an `https:` URL, use [dirty-sec-get](<https://github.com/Phoenix35/dirty-sec-get>).  
There will be no merge of the two packages to accept both protocols. Make your own or use a library.

## How-to
```js
const httpGet = require("@phoenix35/dirty-get");
```
```js
const someText = await httpGet("http://skateipsum.com/get/1/0/text");
```

As it uses the native `http` module, `url` can be a string, an object accepted by [`http.get`](<https://nodejs.org/api/http.html#http_http_get_url_options_callback>), or an URL instance.

### When expecting binary data
The function returns an UTF-8 encoded string by default.  
You can switch to a buffer representation by passing `null` as the second argument.
```js
const someIcon = await httpGet("http://skateipsum.com/favicon.ico", null);
```

## Licensing
    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
