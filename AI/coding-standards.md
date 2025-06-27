This file is a list of instructions for writing code for this project.

# Coding Standards
- All code should follow these standards
- All naming conventions should be followed.
- All Library requirements should be followed.
- All src Code standards should be followed for src projects.
- All Test code standards should be followed for test projects.

# Naming Conventions
- Fields should begin with `_`.  i.e. `_field`;
- Microsoft's C# naming conventions should be followed.

# Library Requirements
- Every library should have one of the following licenses:
  - MIT
  - Apache 2.0
  - GNU GPL v2+

# src Code
- All projects should be contained in the src folder.
- All projects follow the naming convention of `yato.[Project purpose]`.  E.g. `yato.Web` or `yato.Model`
- Source code should be separated into projects based on best practices.
- Public, protected and internal interfaces, classes, methods and priorities should have the `///` annotations populated.
  - It is alright to inherit from an interface's annotation provided the interfaces' annotation:
    - Is not contradicted
    - Sufficiently explains what the concrete implementation is doing.
    - Wouldn't be confusing if read in the context of the Concrete implementation.

# Test Code
- Tests should follow all the src Code rules, except where overridden below.
- Tests should be created as though TDD.
- All test projects must be created in the test solution folder.
- Test Project naming convention is: `[name of project under test].Tests.[Type of testing]` where the type of testing is
likely either Unit or Integration.
- Where possible, there needs to be both unit tests and integration tests, where the integration tests check at least
flows through the project under test.
- If possible, create integration tests between projects following process flows.
- Tests must be written in XUnit3, with FluentAssertions (Version 7.2 as this is the last one with the Apache license)
and must use NSubstitute
- Tests must use Arrange, Act, Assert and use comments to delineate these sections.
- Tests names must follow the following format `[MethodName]_Should[DoSomething]_When[Criteria]`, where the values
inside the `[]` are those we change.
   - Constructor-based tests use `Constructor` as the method name.
   - If a method is overloaded the name of the method becomes `[MethodName<DataType of each parameter]` e.g.
```csharp
// This signature
public string GetMessage(int id, string[] attributes);

// becomes
[Fact] 
public void GetMessageIntStringArr_ShouldDoSomething_WhenCriteria();
```
- Tests do not need `///` annotations.
