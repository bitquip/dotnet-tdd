# Writing More Robust Tests

In our pursuit of Test-Driven Development (TDD), we'll build on the foundation we've established by writing tests for more features of the `Gear` class.

By thoroughly testing our code, we ensure its reliability and robustness.

### Testing Pitch Calculation

Let's move forward by testing the `Pitch` calculation in the `Gear` class. The pitch of a gear is a significant parameter, and we want to validate its accuracy.

#### Step 3: Writing a Test for Pitch Calculation

1. In the `GearTests.cs` file located in the `Tests` folder of your test project, add the following test method:

```csharp
[Theory]
[InlineData(1.5, 10, 20, 4.7123889803846897)]
[InlineData(2.0, 20, 30, 6.2831853071795862)]
[InlineData(0.8, 15, 45, 2.5132741228718345)]
public void GetPitch_WithModule_ReturnsCorrectValue(double module, int teeth, double pressureAngle, double expectedPitch)
{
    // Arrange
    var gear = new Gear(module, teeth, pressureAngle);

    // Act
    var result = gear.Pitch;

    // Assert
    Assert.Equal(expectedPitch, result, 10);
}
```

In this test, we've used the **Theory** attribute along with **InlineData** to test the `Pitch` property with different input values. The test method will be executed for each set of data provided in **InlineData**.

The test checks whether the calculated pitch matches the expected pitch within a specified tolerance.

### Implementing the Gear Class Functionality

With our test in place, let's move on to implement the functionality of the `Gear` class to make the tests pass.

#### Step 4: Implementing the `Gear` Class

1. Open the `Program.cs` file located in the root directory of your project.

2. Modify the `Gear` class constructor to store the provided values:

```csharp
public class Gear
{
    public Gear(double module, int teeth, double pressureAngle)
    {
        Module = module;
        Teeth = teeth;
        PressureAngle = pressureAngle;
    }
    // ...
}
```

With this change, the `Gear` class constructor now takes the `module`, `teeth`, and `pressureAngle` parameters and assigns them to the corresponding properties.

3. Implement the `Pitch` property calculation in the `Gear` class:

```csharp
public class Gear
{
    Module = module;
    Teeth = teeth;
    PressureAngle = pressureAngle;

    // ADD THIS!
    public double Pitch
    {
        get { return Math.PI * Module; }
    }
}
```

The `Pitch` property now calculates the pitch using the formula `Math.PI * Module`.

### The Red-Green-Refactor Cycle Continues

With the implementation complete, it's time to run our tests and witness the magic of TDD in action. By running the tests, we aim to transition from the **Red** (failing test) phase to the **Green** (passing test) phase.

#### Step 5: Running the Tests

1. Navigate back to the root directory of your project (if you are in the `GearCalculator.Tests` folder, use `cd ..`).

2. Run the tests using the following command:

```bash
dotnet test
```

If all goes well, you should see that the tests pass, indicating that the `Gear` class functionality is correctly implemented.

---

**Congratulations!**

 By following the Test-Driven Development approach, you've ensured that your code is thoroughly tested and functional. 

You've embraced the red-green-refactor cycle and witnessed how it guides you in creating reliable software.

In the upcoming sections, we'll continue to write tests, implement code, and refine our application. Stay engaged as we journey further into the world of TDD in .NET development!
