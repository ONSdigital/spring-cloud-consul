################################################################
# To build
################################################################
mvn clean install


################################################################
# To run
################################################################
- with default profile:
    - java -jar target/spring-cloud-consul-0.1.0.jar

- with prod profile:
    - java -jar -Dspring.profiles.active=prod target/spring-cloud-consul-0.1.0.jar


################################################################
# To test the app itself
################################################################
- curl http://localhost:8281/mgmt/health -v -X GET
200 {"description":"Spring Cloud Consul Discovery Client","status":"UP"}


- curl http://localhost:8181 -v -X GET
200 Greetings from Spring Boot: Key is prodKey and Template is prodTemplate


################################################################
# To test the service discovery
################################################################
- see testServiceDiscovery.txt


################################################################
# To test the service discovery
################################################################
- see testApplicationProperties.txt
