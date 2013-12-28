tomcat-common
=============




## Building from source


### check out sources
`git clone https://github.com/basmussen/tomcat-common.git`

### Maven build
`mvn clean install`


### copy lib to TOMCAT_HOME/lib
`cp tomcat-common-0.0.1.jar TOMCAT_HOME/lib`


## Tomcat configuration

Edit your context.xml
`vi TOMCAT_HOME/context.xml`

Add your resource to file

<Context>
  <Resource auth="Container" factory="com.benasmussen.jndi.url.URLFactory" name="url/MyUrl" type="java.net.URL"    url="file:///your/path/to/file"/>
</Context>



## Webapplication configuration


## Spring 3 configuration





## Staying in touch
Follow me [@BenAsmussen][] on Twitter. 

## License
The project is released under  the [MIT Licence][].



