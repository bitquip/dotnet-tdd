# Parameterizing Tests

## Efficient Testing with Parameterized Tests

As we advance in our Test-Driven Development (TDD) journey, we often encounter situations where we need to test the same functionality with multiple input scenarios. Parameterized tests allow us to achieve this efficiently and maintainable.

### Introducing Parameterized Tests

Parameterized tests enable us to write a single test method that can be executed with multiple sets of input data. This approach helps us validate the behavior of our code across different scenarios.

#### Step 17: Writing Parameterized Tests

1. In the `GearTests.cs` file located in the `Tests` folder of your test project, let's create a parameterized test to validate gear calculations with various input data:

```csharp
[Theory]
[InlineData(1.0, 10, 20.0, 4.0808206181339193)]
[InlineData(1.5, 15, 30.0, 7.539822368615503)]
[InlineData(2.0, 20, 45.0, 12.566370614359172)]
public void GearCalculations_ReturnCorrectValues(double module, int teeth, double pressureAngle, double expectedValue)
{
    // Arrange
    var gear = new Gear(module, teeth, pressureAngle);

    // Act
    var baseDiameter = gear.BaseDiameter;
    var pitch = gear.Pitch;
    var pitchDiameter = gear.PitchDiameter;

    // Assert
    Assert.Equal(expectedValue, baseDiameter, 10);
    Assert.Equal(expectedValue, pitch, 10);
    Assert.Equal(expectedValue, pitchDiameter, 10);
}
```

In this parameterized test, we're using the **InlineData** attribute to provide different sets of input data for the `module`, `teeth`, `pressureAngle`, and `expectedValue` parameters. The test method will be executed for each set of data, and the test assertions will validate the calculations.

### Achieving Comprehensive Testing with Efficiency

Parameterized tests allow us to achieve comprehensive testing with minimal code duplication. By testing a wide range of scenarios using a single test method, we ensure the robustness of our codebase.

---

**Yeahhhh!** 

You've unlocked the power of parameterized tests, enabling you to efficiently test your code across various scenarios. By writing tests that cover a multitude of cases, you're increasing the reliability of your application.

Stay engaged as we explore more advanced TDD concepts and dive deeper into .NET development!