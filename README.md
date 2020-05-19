# Play with docker javascript SDK

This is the client side JS of PWD that allows to run terminals and attach them to your site


## Using the SDK

Here's a minimal example of the SDK usage:


```html
<html>
    <head>
        <title>PWD SDK Demo</title>
    </head>
    <body>
    <div id="myTerm" style="width 500px; height: 500px;"></div>
    <link rel="stylesheet" href="./dist/styled.css" /> 
    <script src="./dist/pwd.js"></script>
    <script>
        pwd = new PWD();
        pwd.newSession([{selector: '#myTerm'}]);
    </script>                                                                         
    </body>
</html>
```
If you are running [Play with Docker](https://github.com/play-with-docker/play-with-docker) locally (which saves resources on our production machines) create the new session with an additional option:

```
pwd.newSession([{selector: '#myTerm'}], {baseUrl: 'http://localhost'});
```

You can easily test your page with the SDK by running the following from the root directory of this project on Linux or Mac:

```
docker run --name sdktest -v $PWD:/usr/share/nginx/html:ro -d -it -p 8080:80 nginx
```
and then browse to [localhost:8080](http://localhost:8080).


## Building the SDK

Clone this repo and run `npm install && npm run build`
