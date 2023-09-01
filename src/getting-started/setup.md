# Getting Started

Before we dive into writing code, let's make sure we have everything set up correctly. In this section, we'll cover the prerequisites, set up our project, and get familiar with the provided code.

### Prerequisites

Before we begin, ensure you have the following installed on your development machine:

- [.NET SDK](https://dotnet.microsoft.com/download) - This is the core development platform for building .NET applications. Make sure you have the .NET SDK installed for your platform.

### Setting Up the Project

#### Step 1: Create a New Project Folder

Let's start by creating a dedicated folder for our project. Open your terminal or command prompt and navigate to the directory where you want to create the project folder.

```bash
mkdir GearCalculator
cd GearCalculator
```

#### Step 2: Create the .NET Console Application

Now that we have our project folder ready, let's create a .NET Console Application project. Run the following command:

```bash
dotnet new console -n GearCalculator
```

This command creates a new .NET Console Application project named "GearCalculator" within our project folder.

#### Step 3: Navigate to the Project Directory

Navigate into the newly created project directory:

```bash
cd GearCalculator
```

#### Setup the Gear class

```csharp
using System;

namespace GearCalculator
{
    public class Gear
    {
        // Properties
        public double Module { get; }
        public int Teeth { get; }
        public double PressureAngle { get; }

        // Constructor
        public Gear(double module, int teeth, double pressureAngle)
        {
            Module = module;
            Teeth = teeth;
            PressureAngle = pressureAngle;
        }

        // Methods to calculate properties will be added later
    }

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello GearCalculator!");
        }
    }
}
```

### Understanding the Provided Code

Our project structure is now set up, and we're ready to dive into the code. Let's take a closer look at the provided code and understand its components.

#### The Gear Class

The `Gear` class is the heart of our application. It represents a single gear and contains properties to store essential information about the gear. These properties include:

- `Module`: The gear's module, which defines the size of the teeth.
- `Teeth`: The number of teeth on the gear.
- `PressureAngle`: The pressure angle of the gear's teeth.

In addition to the properties, the `Gear` class also has methods to calculate various properties of the gear, such as `BaseDiameter`, `Pitch`, and `PitchDiameter`.

#### The Program Class

The `Program` class serves as the entry point for our console application. Currently, it contains a basic `Main` method that prints a simple message. We'll be adding more functionality to this class as we progress through the tutorial.

### Conclusion

In this section, we've prepared our development environment by setting up the necessary prerequisites and creating a .NET Console Application project. We've also explored the provided code and gained an understanding of the `Gear` and `Program` classes.

In the next section, we'll dive into the exciting world of Test-Driven Development (TDD) by writing our first set of tests for the `Gear` class. We'll follow the TDD process to ensure that our code is thoroughly tested and functional.

Now that we have a clear understanding of the project setup and the provided code, it's time to start implementing the Test-Driven Development (TDD) approach. TDD is a powerful methodology that guides us in creating robust and reliable code by writing tests before implementing the actual functionality.
