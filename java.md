# Java & Spring Boot Interview Questions

## Java – Interview Questions & Answers

### 1) What is the difference between `==` and `equals()` in Java?
**Answer:**
- `==` compares references (memory address).
- `equals()` compares content (if overridden properly).

```java
String a = new String("hi");
String b = new String("hi");

System.out.println(a == b);      // false
System.out.println(a.equals(b)); // true
```

### 2) Why is `String` immutable in Java?
**Answer:**
- Improves security (used in class loading, URLs, DB credentials).
- Makes strings thread-safe.
- Enables string pooling and performance optimizations.
- Allows hash code caching.

### 3) Difference between `ArrayList` and `LinkedList`
**Answer:**

| Feature | ArrayList | LinkedList |
|---|---|---|
| Access | Fast (`O(1)`) | Slow (`O(n)`) |
| Insert in middle | Costly | Better |
| Memory | Less | More (node pointers) |

### 4) What is `HashMap` and how does it work internally?
**Answer:**
- Uses hashing to store key-value pairs.
- Flow: key -> hash -> bucket.
- On collisions, uses linked list/tree (tree from Java 8+ in high-collision buckets).
- Relies on both `hashCode()` and `equals()`.

### 5) Why must we override both `equals()` and `hashCode()`?
**Answer:**
- Contract: if two objects are equal by `equals()`, they must have the same `hashCode()`.
- Otherwise, hash-based collections (`HashMap`, `HashSet`) behave incorrectly.

### 6) Difference between `final`, `finally`, and `finalize()`
**Answer:**
- `final`: used for constants, methods that cannot be overridden, or classes that cannot be inherited.
- `finally`: block that executes after `try-catch` (typically for cleanup).
- `finalize()`: old GC hook, deprecated and should be avoided.

### 7) What is synchronization in Java?
**Answer:**
- Prevents multiple threads from entering a critical section at the same time.

```java
synchronized void update() {
        // critical section
}
```

### 8) Difference between `Comparable` and `Comparator`
**Answer:**
- `Comparable`: defines natural ordering inside the class.
- `Comparator`: defines custom ordering outside the class.

### 9) What is `Optional` in Java?
**Answer:**
- A container object used to reduce `NullPointerException` risk and express absence explicitly.

```java
Optional<String> name = Optional.ofNullable(str);
```

### 10) What is Stream API?
**Answer:**
- Enables functional-style processing of collections.

```java
list.stream()
        .filter(x -> x > 10)
        .map(x -> x * 2)
        .toList();
```

---

## Spring Boot – Interview Questions & Answers

### 1) What is Spring Boot?
**Answer:**
Spring Boot is an opinionated framework that:
- reduces manual configuration,
- provides auto-configuration,
- runs apps with an embedded server.

### 2) Difference between Spring and Spring Boot
**Answer:**

| Spring | Spring Boot |
|---|---|
| Manual configuration | Auto configuration |
| External server setup | Embedded server |
| More setup effort | Less setup effort |

### 3) What is Auto-Configuration?
**Answer:**
- Spring Boot automatically configures beans based on classpath, dependencies, and properties.
- Commonly enabled via `@SpringBootApplication`.

### 4) What does `@SpringBootApplication` contain?
**Answer:**
It combines:
- `@Configuration`
- `@EnableAutoConfiguration`
- `@ComponentScan`

### 5) Difference between `@Component`, `@Service`, and `@Repository`
**Answer:**
- All register beans in the Spring container.
- `@Component`: generic bean.
- `@Service`: service layer semantic.
- `@Repository`: DAO layer semantic + exception translation.

### 6) What is Dependency Injection?
**Answer:**
- The framework provides object dependencies automatically.

```java
@Autowired
private UserService service;
```

### 7) Difference between `@Controller` and `@RestController`
**Answer:**
- `@Controller`: returns views (e.g., HTML templates).
- `@RestController`: returns response body data (usually JSON).

### 8) What is Spring Bean lifecycle?
**Answer:**
Typical flow:
1. Bean instantiated
2. Dependencies injected
3. `@PostConstruct` callback
4. Bean ready for use
5. `@PreDestroy` callback before shutdown

### 9) How do you handle exceptions globally?
**Answer:**
- Use `@ControllerAdvice` with `@ExceptionHandler` methods.

### 10) What is Spring Data JPA?
**Answer:**
- Reduces boilerplate for database access using repository abstractions.

```java
public interface UserRepo extends JpaRepository<User, Long> { }
```

### 11) Difference between `findById()` and `getById()`
**Answer:**
- `findById()`: fetches immediately, returns `Optional<T>`.
- `getById()`: may return a lazy proxy (behavior depends on JPA provider/version).

### 12) What is Actuator?
**Answer:**
- Provides production-ready endpoints such as:
    - `/actuator/health`
    - `/actuator/metrics`
    - `/actuator/info`

### 13) How does Spring Boot connect to a database?
**Answer:**
- Configure datasource properties:

```properties
spring.datasource.url=...
spring.datasource.username=...
spring.datasource.password=...
```

- Auto-configuration typically creates:
    - `DataSource`
    - `EntityManager`
    - `TransactionManager`

### 14) Difference between `@RequestParam` and `@PathVariable`
**Answer:**
- `@PathVariable`: value comes from URL path (e.g., `/users/{id}`).
- `@RequestParam`: value comes from query parameters (e.g., `?page=1`).

### 15) What is the default embedded server in Spring Boot?
**Answer:**
- Tomcat (by default).