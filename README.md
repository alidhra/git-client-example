

Design Assumptions:
==================
* Using standard spring boot rest API project structure.  
* Not using lombok, so we can use json format annotation for the getter and setter.  
* As it was not a requirement, we are not using authentication when interacting with Git to avoid the 'Rate Limit' error.  
* The service will return an HTTP status code of 404 when the user is not found.  
* The service uses the default spring boot error handling.  
* Does not have any license headers as this is meant for use by myself and
  few individuals given explicity invite. It is meant to be deleted after a short time.  
* Swagger UI is provided for manual test.  
  In real world scenario, it would not be included or be secured.  
  Or we would not include it in the final build.
  
* Tests were limited to happy-path and user-not-found scenarios due to time constraint.  
* No negative test cases beyond user not found.   
* The negative test for 'Rate Limit' error is there but not enabled.  
* Not using mocks for testing.  



Build
=====
##### Default
`mvn clean install`  
#### Enable debug messages to see the cache kick in and the calls to Git.
`mvn clean install -Dspring.profiles.active=debug` 
##### Skip tests
`mvn clean install -DskipTests`  

Run
===
##### Default
`java -jar target/git-user-lookup-example-0.0.1-SNAPSHOT.jar`

##### See debug logs
`java -jar target/git-user-lookup-example-0.0.1-SNAPSHOT.jar --spring.profiles.active=debug`


Manual Test
===========
Navigate to the following URL in your browser  
`http://localhost:8081/swagger-ui/index.html#/git-user-info-controller/lookupUser`
