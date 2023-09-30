
# Break the big project into many smaller apps to try with different test approaches.

<img width="738" alt="Screenshot 2023-09-30 at 11 23 07" src="https://github.com/lebronjamesuit/sub-spring-test-project/assets/11584601/b481273f-d9fe-4c0f-b62f-5f5115bf5878">

Note

  - @SpringBootApplication  is a convenience annotation that adds all of the following:

  - @Configuration: Tags the class as a source of bean definitions for the application context.

  - @EnableAutoConfiguration: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.

  - @EnableWebMvc: Flags the application as a web application and activates key behaviors, such as setting up a DispatcherServlet. Spring Boot adds it automatically when it sees spring-webmvc on the classpath.

  - @ComponentScan: Tells Spring to look for other components, configurations, and services in the the com.example.testingweb package, letting it find the HelloController class.

  - The @SpringBootTest annotation tells Spring Boot to look for a main configuration class (one with @SpringBootApplication, for instance) and use that to start a Spring application context.


In this test, the full Spring application context is started but without the server. We can narrow the tests to only the web layer by using @WebMvcTest.

  - @WebMvcTest

The test assertion is the same as in the previous case. However, in this test, Spring Boot instantiates only the web layer rather than the whole context. In an application with multiple controllers, you can even ask for only one to be instantiated by using, for example, @WebMvcTest(YourClass.class).

# Next challenge:

Implement "Test containers" which has Unit tests with real dependencies
