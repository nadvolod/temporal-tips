
## Error

`io.temporal.worker.TypeAlreadyRegisteredException`

## Description

By default, the Java SDK generates an Activity Type name from the method name in your @ActivityInterface, with the first letter capitalized. If you have two different interfaces that both contain a method named analyze, they will both resolve to the Activity Type "Analyze", causing a collision

## Solution

```java
@ActivityInterface(namePrefix = "DataService_")
public interface DataActivities {
    @ActivityMethod(name = "Analyze")
    void analyze();
}
```
