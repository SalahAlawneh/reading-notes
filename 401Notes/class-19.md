# Spring and Sockets
![](img/19a.png)
- the socket can make sending messages between the server and cleint side possible.
- socket is a thin layer beyond the transmission control protocol.
- we can use subprotocol in socket, and here we will use STOMP sub-protocol
- the general steps to make a socket:
   - initialize the spring with needed dependencies
   - create resource representational class
   - create messaging handling controller
   - configure STOMP for messaging
   - make the application able to run
   - test the app
- the depencies in `build.gradle` => 
```
plugins {
	id 'org.springframework.boot' version '2.4.3'
	id 'io.spring.dependency-management' version '1.0.11.RELEASE'
	id 'java'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '1.8'

repositories {
	mavenCentral()
}

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-websocket'
	implementation 'org.webjars:webjars-locator-core'
	implementation 'org.webjars:sockjs-client:1.0.2'
	implementation 'org.webjars:stomp-websocket:2.3.3'
	implementation 'org.webjars:bootstrap:3.3.7'
	implementation 'org.webjars:jquery:3.1.1-1'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

test {
	useJUnitPlatform()
}

```

====> in general the socket as i found is straitforward thing if you follow the steps in the provided source, and this an additional source for socket in spring framework [baeldung](https://www.baeldung.com/websockets-spring)