# What is Xevolver XML Framework ?
>"XevXml is a framework for user-defined code transformations based on XML. XevXml provides interconversion between an abstract syntax tree (AST) of a C/Fortran code and an XML document. The XML document is exposed to users. Hence, the users can use any XML tools for user-defined AST transformations, and then generate a transformed version of the C/Fortran code. [(***https://github.com/xevolver/xevxml***)](https://github.com/xevolver/xevxml)"

---

# about this image
* CentOS 6.9 where Xevolver XML Framework installed  
* Xevolver XML Framework installed @ `/opt/xevxml`  
 Apache Xerces C++ installed @ `/opt/xerces-c`  
* Apache Xalan C++ installed @ `/opt/xalan-c`  
* PicoJSON @ `/opt/picojson`  
* ROSE compiler installed @ `/opt/rose`  
* Boost installed @ `/opt/boost-1.54`  
* Environment variable setting file @ `/opt/rose/setPATH.sh`
* Common server environment variable setting file @ `/etc/profile.d/rose.sh , xevxml.sh`  

###### /opt/rose/setPATH.sh  
```
   export JAVA_HOME=`readlink /etc/alternatives/java_sdk_openjdk`
   export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/opt/rose/lib:/opt/boost-1.54/lib:${JAVA_HOME}/lib:${JAVA_HOME}/jre/lib/amd64/server
   export C_INCLUDE_PATH=$C_INCLUDE_PATH:/opt/rose/include/rose:/opt/boost-1.54/include
   export CPLUS_INCLUDE_PATH=$CPLUS_INCLUDE_PATH:/opt/rose/include/rose:/opt/boost-1.54/include
   export PATH=$PATH:/opt/rose/bin
```

###### /etc/profile.d/rose.sh
```
   source /opt/rose/setPATH.sh  
```  

###### /etc/profile.d/xevxml.sh
```
   source /opt/xevxml/bin/xevxml_vars.sh
```  

---

# Notes
## build  
```sh:console
 sudo docker build -t sin1/xevolver .  
```

## run
```sh:console
 sudo docker run -itd --name xevxml sin1/xevolver
```

---

# Software dependencies
| Software component | version |
|:-----------|:------------|
|xevolver |       xevolver/xevxml : commit [267e35898203d53b495c70956ac58396fd5e3edc](https://github.com/xevolver/xevxml/commit/267e35898203d53b495c70956ac58396fd5e3edc) |
|xalan_c  |       1.11 |
|xerces-c |       3.1.1 |
|picojson |       kazuho/picojson : commit [1ebfc7b998fed25c48b4c14c0907bda74ead42c5](https://github.com/kazuho/picojson/commit/1ebfc7b998fed25c48b4c14c0907bda74ead42c5) |
|cmake    |       3.1.1 |
|rose compiler |    xevolver/rose-xev  (based ROSE ver.0.9.7.20) |
|               | [commit e4bd48887e23a8f0f8910f1f6fb88dc6d7302b56](https://github.com/xevolver/rose-xev/commit/e4bd48887e23a8f0f8910f1f6fb88dc6d7302b56) |
|git           |  1.7.1|
|wget       |     1.12|
|gcc        |     4.4.7|
|autoconf   |     2.69|
|automake |       1.15.1|
|libtool        | 2.4.6|
|flex           | 2.5.35|
|bison        |   2.4.1|
|yacc         |   1.9|
|jdk            |java-1.7.0-openjdk-1.7.0.141.x86_64|
|python      |    2.6.6|
|boost        |   1_54_0|
|bzip2        |   1.0.6|
|zlib           | 1.2.11|
|ghostscript |    8.70|
|doxygen     |    1.6.1 |
|graphviz     |   2.26 |
|CentOS | Mounted from [library/centos:6.9](https://github.com/CentOS/sig-cloud-instance-images/blob/4f329fe087b0152df26344cecee9ba30b03b1a7b/docker/Dockerfile) |

---

# References
* Xevolver CREST-- http://xev.arch.is.tohoku.ac.jp/ja/software/
* xevolver/xevxml -- https://github.com/xevolver/xevxml
* Apache Xerces C++ 3.1.1 -- http://xerces.apache.org/
* Apache Xalan C++ 1.0 -- http://xml.apache.org/xalan-c/
* PicoJSON -- https://github.com/kazuho/picojson
* ROSE compiler infrastructure -- http://rosecompiler.org/
* Boost C++ Libraries -- http://www.boost.org/
