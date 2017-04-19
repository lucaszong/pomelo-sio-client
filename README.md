# pomelo client
pomeol client，基于socket.io-client

## Getting Start

```
npm install 
```

## scripts

```
var pomelo = require('pomelo-client');
var pomeloclient = new pomelo({"debug":true});
pomeloclient.init({ "host": host, "port": port,"reconnectionAttempts":3 }, function (socket) {
        pomeloclient.request("chat.userHandler.addUser", args,
            function (data) {
                pomeloclient.disconnect();
                
                console.log(data);
            });
    });

pomeloclient.on("error", function (err) {
    pomeloclient.disconnect();
    console.log(err);
});

```



### pomelo(opts:Object)

  opts.debug:true/false  console.log
  
### init(opts:Object,cb:Function)

  opts.host: host name
  opts.port: port
  opts.reconnectionAttempts: (Number) number of reconnection attempts before giving up (Infinity)