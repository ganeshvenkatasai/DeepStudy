# Spring Boot

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
