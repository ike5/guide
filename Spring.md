# How to package Spring Boot Project

> $ ./mvnw package


## Simple REST Controller

`
@RestController
public class GreetingController {

    private static final String template = "Hello, %s!";
    private final AtomicLong counter = new AtomicLong(); // way to set id for greeting

    // /greeting?name=Dan
    @GetMapping("/greeting")
    public Greeting greeting(@RequestParam(value = "name", defaultValue = "World") String name) {
        return new Greeting(counter.incrementAndGet(), String.format(template, name));
    }
}
`java
