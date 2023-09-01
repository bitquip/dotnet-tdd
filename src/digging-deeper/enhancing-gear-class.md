# Enhancing Gear Class Through Testing

As we continue our exploration of Test-Driven Development (TDD), let's extend our tests to cover additional functionalities of the `Gear` class. Through systematic testing and incremental development, we build a solid foundation for our code.

### Testing Pitch Diameter Calculation

Next, we'll write tests to validate the accuracy of the `PitchDiameter` calculation in the `Gear` class.

#### Step 6: Writing Tests for Pitch Diameter Calculation

1. In the `GearTests.cs` file located in the `Tests` folder of your test project, add the following test method:

```csharp
[Theory]
[InlineData(1.5, 10, 20, 15.0)]
[InlineData(2.0, 20, 30, 40.0)]
[InlineData(0.8, 15, 45, 12.0)]
public void GetPitchDiameter_WithModuleAndTeeth_ReturnsCorrectValue(double module, int teeth, double pressureAngle, double expectedPitchDiameter)
{
    // Arrange
    var gear = new Gear(module, teeth, pressureAngle);

    // Act
    var result = gear.PitchDiameter;

    // Assert
    Assert.Equal(expectedPitchDiameter, result, 10);
}
```

Here, we're using the **Theory** attribute again with **InlineData** to test the `PitchDiameter` property with different input values. The test checks whether the calculated pitch diameter matches the expected pitch diameter within a specified tolerance.

### Implementing More Gear Class Functionality

With our new test in place, let's proceed to implement the `PitchDiameter` property in the `Gear` class.

#### Step 7: Implementing the `PitchDiameter` Property

1. Open the `Program.cs` file located in the root directory of your project.

2. Add the implementation for the `PitchDiameter` property in the `Gear` class:

```csharp
public class Gear
{
    // ...

    public double PitchDiameter
    {
        get { return Module * Teeth; }
    }
}
```

Now, the `PitchDiameter` property is calculated as the product of `Module` and `Teeth`.

### Completing the Red-Green-Refactor Cycle

With the implementation in place, let's run our tests again to complete the red-green-refactor cycle.

#### Step 8: Running the Tests Again

1. Navigate back to the root directory of your project (if you are in the `GearCalculator.Tests` folder, use `cd ..`).

2. Run the tests using the following command:

```bash
dotnet test
```

As the tests pass, we have successfully implemented the `PitchDiameter` property using the TDD approach.

---

**You're making great progress!**

By systematically writing tests and implementing code, you're creating a robust application with well-defined functionalities. 

Our journey into TDD and .NET development continues as we explore more aspects of the `Gear` class.

> Moving onward!
