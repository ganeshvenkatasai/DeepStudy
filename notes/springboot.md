# Spring Boot

If you have ever created a Spring Boot application, you have seen the following code in the main method:

```java
@SpringBootApplication
public class MyApplication {
    public static void main(String[] args) {
        SpringApplication.run(MyApplication.class, args);
    }
}
```

At first glance, it looks like a simple static method call, but behind the scenes, `SpringApplication.run()` does a lot of heavy lifting.


---

![Logs](https://raw.githubusercontent.com/ganeshvenkatasai/DeepStudy/refs/heads/main/assets/img/logs.png)

---


### Key Observations from Application Logs

Some important points we can deduce from logs:
- Spring Boot Application Process ID is 90279
- Spring Boot Application is launching Tomcat on port 8080

## Lifecycle of SpringApplication.run()

Let's understand what happens behind the scenes:

### 1. Creating the SpringApplication Instance

```java
SpringApplication app = new SpringApplication(MyApplication.class);
SpringApplication.run(MyApplication.class, args);
```

- Identifies if it's a Servlet-based, Reactive or Non-web application
- Chooses the right ApplicationContext type:
  - `AnnotationConfigServletWebServerApplicationContext` → MVC apps

### 2. Preparing the Environment

Loads configuration from multiple sources:
- `application.properties` or `application.yaml`
- Command-line arguments
- Environment variables
- Determine active profile (Dev, test, prod)
- Makes all values available through the Environment abstraction

### 3. Creating the ApplicationContext

- Initializing the Spring container
- Register beans annotated with `@Component`, `@Service`, `@Repository`, `@Configuration`
- Prepares auto-configuration (`@EnableAutoConfiguration`)

### 4. Refreshing the Context

- Calls `context.refresh()`
- Triggers bean instantiation and dependency injection
- Applies lifecycle callbacks (`@PostConstruct`, InitializingBeans)

### 5. Starting the Embedded Server (for web apps)

- Starts Tomcat, Jetty, or Undertow
- Deploys your controllers so the app can start handling requests

### 6. Load Application Properties

Spring Boot allows you to set configuration properties (like database connection or port number) in files like `application.properties` or `application.yml`.

The run method loads these configurations and applies them, so your app behaves according to the settings you have defined.

### 7. Run Initializers and Listeners

**Initializers**: Pieces of code that run before the application starts, and they allow you to perform setup tasks.

**Listeners**: Objects that listen for specific events during the application lifecycle and respond to them, such as when the app starts or shuts down.

### 8. Manage Command-Line Arguments


### 9. Launch the Application

---

## Core Concepts
- `SpringApplication` → Main entry point for Spring Boot apps  
- `Auto-configuration` → Automatically configures Spring based on dependencies  
- `Starters` → Predefined dependency descriptors (spring-boot-starter-*)  

## Dependency Injection
- `@Component` → Base stereotype for Spring-managed beans  
- `@Service` → Business service layer stereotype  
- `@Repository` → Data access layer stereotype  
- `@Autowired` → Injects dependencies automatically  

## Web Layer
- `@RestController` → Combines @Controller and @ResponseBody  
- `@RequestMapping` → Maps web requests to handler methods  
- `@GetMapping` → Shortcut for GET request mapping  
- `@PostMapping` → Shortcut for POST request mapping  

## Data Access
- `Spring Data JPA` → Simplifies JPA-based repositories  
- `CrudRepository` → Provides CRUD operations  
- `JpaRepository` → JPA-specific repository extension  
- `@Entity` → Marks class as JPA entity  
- `@Transactional` → Defines transaction boundaries  

## Configuration
- `application.properties` → Default configuration file  
- `@Configuration` → Marks class as configuration source  
- `@Bean` → Indicates method produces a Spring bean  
- `@Value` → Injects property values  

## Exception Handling
- `@ControllerAdvice` → Global exception handler  
- `@ExceptionHandler` → Handles specific exceptions  
- `ResponseEntity` → Wrapper for HTTP response  

## Security
- `Spring Security` → Authentication/authorization framework  
- `@EnableWebSecurity` → Enables web security configuration  
- `UserDetailsService` → Core interface for user data  

## Testing
- `@SpringBootTest` → Full context integration testing  
- `@WebMvcTest` → Focused web layer testing  
- `@DataJpaTest` → Repository layer testing  
- `MockMvc` → Mock MVC testing framework  

## Actuator
- `spring-boot-actuator` → Production-ready monitoring  
- `/health` → Application health endpoint  
- `/metrics` → Application metrics endpoint  

## Profiles
- `@Profile` → Conditionally enables beans  
- `application-{profile}.properties` → Profile-specific config  

## Logging
- `Logback` → Default logging implementation  
- `logging.level` → Sets package-specific log levels  

## Caching
- `@EnableCaching` → Enables Spring caching  
- `@Cacheable` → Caches method results  
- `@CacheEvict` → Removes cache entries  

## Async
- `@Async` → Marks method as asynchronous  
- `@EnableAsync` → Enables async processing  

## Validation
- `@Valid` → Triggers bean validation  
- `@NotNull` → Validates field not null  
- `@Size` → Validates string/collection size  

## REST Clients
- `RestTemplate` → Synchronous REST client  
- `WebClient` → Reactive REST client  

## Scheduling
- `@Scheduled` → Marks method for periodic execution  
- `@EnableScheduling` → Enables scheduling  

## Messaging
- `JMS` → Java Message Service support  
- `@JmsListener` → Listens to JMS destinations  

## AOP
- `@Aspect` → Declares aspect class  
- `@Before` → Advice that runs before method  
- `@After` → Advice that runs after method  

## Actuator Endpoints
- `/info` → Application information  
- `/beans` → Lists all Spring beans  
- `/mappings` → Displays URL mappings  

## Spring Boot CLI
- `spring run` → Runs Groovy scripts  
- `spring jar` → Creates executable jar  

## Deployment
- `Executable JAR` → Self-contained deployment  
- `Docker` → Containerization support  

## Monitoring
- `Micrometer` → Application metrics facade  
- `Prometheus` → Monitoring system integration  
