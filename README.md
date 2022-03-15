# jnlp
simple jnlp app

1. create keystore with the command

  ``keytool -genkey -keyalg RSA -alias jnlpstore -keystore src/main/resources/jnlp.jks -storepass password -validity 360``

2. Produce and sign jar file with

   ``mvn  -Djarsigner.storepass=password -Djarsigner.keypass=password -Dgithub-user clean package``
   
3. To update version change version in pom.xml and jnlp file

``
    <jar href="jnlp.jar" main="true" version="1.0-SNAPSHOT"/>``
    
4. change code base in jnlp file

``
<jnlp spec="1.0+"
      codebase="https://github.com/fercp/jnlp/raw/master/src/main/resources/">    
``

5. change href in index.html

``
<a href="https://github.com/fercp/jnlp/raw/master/src/main/resources/test.jnlp">Launch the example</a>
``
      
      
    
