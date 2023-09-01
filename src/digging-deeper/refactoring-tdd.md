# Evolving Code Through Test-Driven Refactorings

As we progress in our Test-Driven Development (TDD) journey, we'll encounter situations where our code needs improvement. Test-Driven Refactorings allow us to enhance our codebase while maintaining its functionality and ensuring the existing tests still pass.

### Testing New Functionality: Gear Ratio

To demonstrate this concept, we'll add a new functionality to the `Gear` class: calculating the gear ratio. We'll write tests for this new feature and then refactor the code to accommodate it.

#### Step 9: Writing Tests for Gear Ratio Calculation

1. In the `GearTests.cs` file located in the `Tests` folder of your test project, add the following test method:

```csharp
[Theory]
[InlineData(1.5, 10, 20, 0.5)]
[InlineData(2.0, 20, 30, 0.6666666666666666)]
[InlineData(0.8, 15, 45, 0.3333333333333333)]
public void GetGearRatio_WithModuleAndTeeth_ReturnsCorrectValue(double module, int teeth, double pressureAngle, double expectedGearRatio)
{
    // Arrange
    var gear = new Gear(module, teeth, pressureAngle);

    // Act
    var result = gear.GearRatio;

    // Assert
    Assert.Equal(expectedGearRatio, result, 15);
}
```

In this test, we're introducing a new `GearRatio` property and testing its calculation for various inputs using the **Theory** attribute and **InlineData**.

#### Step 10: Implementing the `GearRatio` Property

1. Open the `Program.cs` file located in the root directory of your project.

2. Add the implementation for the `GearRatio` property in the `Gear` class:

```csharp
public class Gear
{
    // ...

    public double GearRatio
    {
        get { return (double)Teeth / Module; }
    }
}
```

The `GearRatio` is calculated as the ratio of `Teeth` to `Module`.

### Test-Driven Refactoring

With the new functionality in place, let's take a moment to perform a test-driven refactoring. This ensures that we maintain our code quality while enhancing its capabilities.

#### Step 11: Running Tests and Refactoring

1. Navigate back to the root directory of your project (if you are in the `GearCalculator.Tests` folder, use `cd ..`).

2. Run the tests using the following command:

```bash
dotnet test
```

Ensure that all tests pass, confirming the correctness of the newly added functionality.

3. Now, let's refine the code to improve readability. In the `Gear` class, update the `GearRatio` property implementation to use a clearer variable name:

```csharp
public double GearRatio
{
    get { return (double)Teeth / Module; }
}
```

With this refactor, we're making the code more understandable and maintaining its functionality.

---

**Congratulations!**

You've successfully evolved your codebase through test-driven refactorings. By adhering to TDD principles, you've ensured that your application remains reliable while accommodating new features.

Stay engaged as we continue to explore advanced TDD concepts and delve deeper into .NET development!