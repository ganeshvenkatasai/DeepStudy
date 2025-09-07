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

## Spring Boot Annotations

**@SpringBootApplication** - Main class annotation combining @Configuration, @EnableAutoConfiguration, and @ComponentScan

**@EnableAutoConfiguration** - Enables Spring Boot's auto-configuration mechanism based on classpath

**@Configuration** - Marks class as source of bean definitions and configuration

**@ComponentScan** - Tells Spring where to search for components (@Controller, @Service, @Repository)

**@SpringBootConfiguration** - Alternative to @Configuration for Spring Boot applications

## Component Annotations

**@Component** - Generic Spring-managed component

**@Service** - Specialization of @Component for service layer business logic

**@Repository** - Specialization of @Component for data access objects (DAOs)

**@Controller** - Specialization of @Component for Spring MVC controllers

**@RestController** - Combines @Controller and @ResponseBody for RESTful web services

## Dependency Injection Annotations

**@Autowired** - Injects dependencies automatically by type

**@Qualifier** - Specifies which bean to inject when multiple beans of same type exist

**@Primary** - Marks bean as primary when multiple beans of same type exist

**@Bean** - Declares a bean definition in @Configuration class

**@Value** - Injects property values from application.properties or application.yml

**@PropertySource** - Loads properties from external file

## Web MVC and REST Annotations

**@RequestMapping** - Maps HTTP requests to controller methods

**@GetMapping** - Maps HTTP GET requests to controller methods

**@PostMapping** - Maps HTTP POST requests to controller methods

**@PutMapping** - Maps HTTP PUT requests to controller methods

**@DeleteMapping** - Maps HTTP DELETE requests to controller methods

**@PatchMapping** - Maps HTTP PATCH requests to controller methods

**@RequestBody** - Binds HTTP request body to method parameter

**@ResponseBody** - Binds method return value to HTTP response body

**@PathVariable** - Binds URI template variables to method parameters

**@RequestParam** - Binds HTTP request parameters to method arguments

**@RequestHeader** - Binds HTTP request headers to method parameters

**@RequestAttribute** - Binds request attributes to method parameters

**@CookieValue** - Binds HTTP cookie values to method parameters

**@CrossOrigin** - Enables Cross-Origin Resource Sharing (CORS)

## JPA/Data Annotations

**@Entity** - Marks class as JPA entity mapped to database table

**@Table** - Specifies database table name and properties

**@Id** - Marks field as primary key

**@GeneratedValue** - Specifies primary key generation strategy

**@Column** - Specifies database column mapping and properties

**@Transient** - Excludes field from database persistence

**@OneToOne** - Defines one-to-one relationship between entities

**@OneToMany** - Defines one-to-many relationship between entities

**@ManyToOne** - Defines many-to-one relationship between entities

**@ManyToMany** - Defines many-to-many relationship between entities

**@JoinColumn** - Specifies foreign key column

**@JoinTable** - Specifies join table for many-to-many relationships

## Validation Annotations

**@Valid** - Enables validation on method parameters or fields

**@Validated** - Spring-specific validation annotation supporting validation groups

**@NotNull** - Validates that field is not null

**@NotEmpty** - Validates that field is not null and not empty

**@NotBlank** - Validates that string field is not null, empty, or whitespace

**@Size** - Validates field size within specified range

**@Min** - Validates minimum numeric value

**@Max** - Validates maximum numeric value

**@Email** - Validates email format

**@Pattern** - Validates field matches specified regex pattern

**@Past** - Validates date is in the past

**@Future** - Validates date is in the future

## Security Annotations

**@EnableWebSecurity** - Enables Spring Security web security configuration

**@PreAuthorize** - Method-level security based on expression evaluation before method execution

**@PostAuthorize** - Method-level security based on expression evaluation after method execution

**@Secured** - Method-level security based on roles

**@RolesAllowed** - JSR-250 annotation for role-based method security

**@AuthenticationPrincipal** - Injects current authenticated user into method parameter

**@EnableGlobalMethodSecurity** - Enables method-level security

## Transaction Annotations

**@Transactional** - Enables declarative transaction management

**@EnableTransactionManagement** - Enables transaction management configuration

**@Rollback** - Forces transaction rollback in test methods

**@Commit** - Forces transaction commit in test methods

## Caching Annotations

**@EnableCaching** - Enables Spring's annotation-driven cache management

**@Cacheable** - Caches method results for subsequent calls with same parameters

**@CachePut** - Updates cache without interfering with method execution

**@CacheEvict** - Removes entries from cache

**@Caching** - Groups multiple cache operations on single method

**@CacheConfig** - Shares common cache-related settings at class level

## Testing Annotations

**@SpringBootTest** - Loads complete Spring application context for integration testing

**@WebMvcTest** - Tests Spring MVC controllers with minimal context

**@DataJpaTest** - Tests JPA repositories with in-memory database

**@MockBean** - Creates mock beans in Spring application context

**@SpyBean** - Creates spy beans in Spring application context

**@TestConfiguration** - Provides additional configuration for tests

**@ActiveProfiles** - Specifies active profiles for test execution

**@Sql** - Executes SQL scripts during test execution

**@Rollback** - Controls transaction rollback for test methods

**@Commit** - Forces transaction commit for test methods

**@WithMockUser** - Provides mock user for security testing

## Conditional Annotations

**@ConditionalOnClass** - Conditional bean creation based on class presence

**@ConditionalOnMissingClass** - Conditional bean creation based on class absence

**@ConditionalOnBean** - Conditional bean creation based on bean presence

**@ConditionalOnMissingBean** - Conditional bean creation based on bean absence

**@ConditionalOnProperty** - Conditional bean creation based on property values

**@ConditionalOnResource** - Conditional bean creation based on resource presence

**@ConditionalOnWebApplication** - Conditional for web applications

**@ConditionalOnNotWebApplication** - Conditional for non-web applications

**@ConditionalOnExpression** - Conditional based on SpEL expression evaluation

**@ConditionalOnJava** - Conditional based on Java version

## Lifecycle and Configuration Annotations

**@PostConstruct** - Method executed after dependency injection

**@PreDestroy** - Method executed before bean destruction

**@Lazy** - Lazy initialization of beans

**@Scope** - Defines bean scope (singleton, prototype, session, request)

**@Profile** - Conditional bean creation based on active profiles

**@Import** - Imports additional configuration classes

**@ImportResource** - Imports XML configuration files

**@DependsOn** - Specifies bean initialization order

**@Order** - Defines execution order for components

**@EventListener** - Marks method as event listener

**@Async** - Enables asynchronous method execution

**@EnableAsync** - Enables asynchronous processing support

**@Scheduled** - Schedules method execution at fixed intervals

**@EnableScheduling** - Enables scheduled task execution

## Actuator Annotations

**@Endpoint** - Creates custom actuator endpoint

**@ReadOperation** - Defines read operation for actuator endpoint

**@WriteOperation** - Defines write operation for actuator endpoint

**@DeleteOperation** - Defines delete operation for actuator endpoint

## Boot-specific Annotations

**@ConfigurationProperties** - Binds external configuration properties to Java objects

**@EnableConfigurationProperties** - Enables @ConfigurationProperties support

**@ConditionalOnCloudPlatform** - Conditional based on cloud platform detection

**@RefreshScope** - Enables configuration refresh at runtime

## Additional Utility Annotations

**@JsonIgnore** - Excludes field from JSON serialization/deserialization

**@JsonProperty** - Specifies JSON property name

**@JsonFormat** - Specifies JSON date/time formatting

**@AliasFor** - Creates aliases for annotation attributes

**@Lookup** - Method injection for prototype beans

**@Resource** - JSR-250 annotation for dependency injection by name

**@Required** - Marks bean property as required (deprecated in Spring 5+)

