Limelight CDN Media Proxy
====================================

This is a node.js application that serves as a media proxy for Limelight CDN.  This basically takes
the following URL and maps it to the actual media download.

```
http://localhost:4000/0011aee4e21d4b84aecc342960eb876a
```

Where ```0011aee4e21d4b84aecc342960eb876a``` is the Limelight CDN media ID.  When this application
is running on a server, you can then just navigate to that URL and it will download the file directly
from Limelight CDN.

You can also use this with the ```<video>``` and ```<audio>``` tags.

```
<video src="http://localhost:4000/0011aee4e21d4b84aecc342960eb876a" controls />
```

Installation
---------------------------------

You can install this module using NPM.

```
sudo npm install -g limelight_proxy
```

Usage
----------------------------------
To run the proxy on your server or computer, you can run with the following parameters.

```
limelight_proxy --organization 12345678 --secret abcd1234 --access_key zyx987 --port 4000
```

Pipe vs. Redirect
-----------------------------------
This library allows you to either retrieve your media via http pipe, or via redirect.  By default,
it will pipe the remote file to the request.  However, you can change this to use a redirect by
using the ```redirect``` parameter as follows.

```
limelight_proxy --organization 12345678 --secret abcd1234 --access_key zyx987 --port 4000 --redirect 1
```
