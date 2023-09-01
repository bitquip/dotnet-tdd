# Mocking and Stubbing

## Mastering Unit Testing with Test Doubles

As we deepen our understanding of Test-Driven Development (TDD), it's important to address the challenge of testing code that depends on external components, such as databases or web services. Test doubles, like mocks and stubs, allow us to isolate and control these dependencies during unit testing.

### Introducing Test Doubles

Test doubles are objects that stand in for real components in our tests. They help us control the behavior of dependencies and focus on the unit under test.

#### Step 14: Using Test Doubles

1. In scenarios where you need to test code with external dependencies, use test doubles such as mocks and stubs.

2. Let's consider an example where our `Gear` class needs to fetch data from a database. We'll use a mock object to simulate database behavior and ensure our tests are isolated and reliable.

### Writing Tests with Mocks

Let's illustrate the concept of using a mock object by considering a scenario where the `Gear` class interacts with a database.

#### Step 15: Writing Tests with Mocks

1. In the `GearTests.cs` file located in the `Tests` folder of your test project, let's create a test that uses a mock to simulate database behavior:

```csharp
using Moq;

// ...

[Fact]
public void CalculateGearRatio_FromDatabase_ReturnsCorrectValue()
{
    // Arrange
    var mockDatabase = new Mock<IDatabaseService>();
    mockDatabase.Setup(db => db.FetchGearRatio()).Returns(0.75);
    
    var gear = new Gear(mockDatabase.Object);

    // Act
    var result = gear.CalculateGearRatioFromDatabase();

    // Assert
    Assert.Equal(0.75, result);
}
```

In this test, we're using the Moq library to create a mock of the `IDatabaseService` interface. We set up the mock to return a specific value when the `FetchGearRatio` method is called. This allows us to isolate the `Gear` class and test its behavior without relying on a real database.

### Implementing Code with Mocked Dependencies

Now, let's implement the `CalculateGearRatioFromDatabase` method in the `Gear` class, which fetches the gear ratio from the database.

#### Step 16: Implementing Code with Mocked Dependencies

1. Open the `Program.cs` file located in the root directory of your project.

2. Implement the `CalculateGearRatioFromDatabase` method in the `Gear` class:

```csharp
public class Gear
{
    private readonly IDatabaseService _databaseService;

    public Gear(IDatabaseService databaseService)
    {
        _databaseService = databaseService;
    }

    public double CalculateGearRatioFromDatabase()
    {
        return _databaseService.FetchGearRatio();
    }
}
```

By injecting the `IDatabaseService` interface into the `Gear` class constructor, we've decoupled it from the actual database implementation.

### Embracing Isolation with Test Doubles

Through the use of test doubles like mocks, you can isolate code from its dependencies, ensuring focused and reliable unit tests. As you encounter scenarios with external dependencies, leverage test doubles to maintain the integrity of your tests and the quality of your application.

---

**Hell Yeah!** 

You've gained a valuable skill in using test doubles to improve the effectiveness of your unit tests. By mastering the art of isolating dependencies, you're enhancing the reliability of your codebase.

Stay engaged as we delve into more advanced topics in TDD and further explore the depths of .NET development!
