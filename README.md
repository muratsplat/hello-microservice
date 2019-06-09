# Hello Microservice

This is simple  hello world application on microservice based. This app uses Spring-Boot framework.


## Requritmments
* Java >=8 
* Gradle >=5.0


Firstly clone this repository via git command like this:
```sh
$ git cone git@github.com:muratsplat/hello-microservice.git
```

This project includes two application. These are:
* Gateway
* Book

`Gateway` application works as reverse proxy. Book is simple micro service. Also you can add new your service.

## How to run

### To run Book microservice
```sh
$ cd book
$ gradle  bootRun
```

### To run Book microservice
```sh
$ cd gateway
$ gradle  bootRun
```

The gateway listen to `8080` port to handle HTTP request. And Book service also listen to `8090` port.

### How to test the gateway
```sh
$ curl -v  localhost:8080/books/available
*   Trying ::1...
* TCP_NODELAY set
* Connected to localhost (::1) port 8080 (#0)
> GET /books/available HTTP/1.1
> Host: localhost:8080
> User-Agent: curl/7.54.0
> Accept: */*
>
< HTTP/1.1 200
< X-Application-Context: application:8080
< Date: Sun, 09 Jun 2019 15:34:52 GMT
< Content-Type: text/plain;charset=UTF-8
< Transfer-Encoding: chunked
<
* Connection #0 to host localhost left intact
Spring in Action%
```

Also you can access to Book service directly.
```sh
curl -v  localhost:8090/available
*   Trying ::1...
* TCP_NODELAY set
* Connected to localhost (::1) port 8090 (#0)
> GET /available HTTP/1.1
> Host: localhost:8090
> User-Agent: curl/7.54.0
> Accept: */*
>
< HTTP/1.1 200
< Content-Type: text/plain;charset=UTF-8
< Content-Length: 16
< Date: Sun, 09 Jun 2019 15:37:05 GMT
<
* Connection #0 to host localhost left intact
Spring in Action%
```


Well done, we have tried to create new microservice based services by using Spring Boot. 

## Resources
* https://spring.io/guides/gs/routing-and-filtering/
