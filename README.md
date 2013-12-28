Tomcat Common
=============

Enables JNDI URL support for Tomcat. You can configure your applications for different environments like local dev, tests server, integration tests and production. This was tested with Tocmat 7.


## Building from source


### Check out sources
`git clone https://github.com/basmussen/tomcat-common.git`

### Maven build
`mvn clean install`


### Copy the lib to your tomcat instance
`cp PROJECT/target/tomcat-common-0.0.1.jar TOMCAT_HOME/lib`

## Tomcat configuration

Edit your tomcat context.xml
`vi TOMCAT_HOME/context.xml`

Add the resource element to your context file

```
<Context>
  ...
  <Resource auth="Container" factory="com.benasmussen.jndi.url.URLFactory" 
  name="url/MyUrl" type="java.net.URL" url="file:///your/path/to/file"/>
  ...
</Context>
```

## Spring 3

```
<beans xmlns="http://www.springframework.org/schema/beans" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
xmlns:jee="http://www.springframework.org/schema/jee"
xsi:schemaLocation="
http://www.springframework.org/schema/jee http://www.springframework.org/schema/jee/spring-jee.xsd
http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
```

```
<jee:jndi-lookup id="myUrl" jndi-name="java:comp/env/url/MyUrl" expected-type="java.net.URL" />
```


## Staying in touch
Follow me [@BenAsmussen][] on Twitter. 

## License
The project is released under the [MIT License][].


[MIT License]: http://opensource.org/licenses/MIT
[@BenAsmussen]: https://twitter.com/BenAsmussen

