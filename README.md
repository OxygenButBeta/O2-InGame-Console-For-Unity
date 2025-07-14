# O2 InGame Console

**O2 Console** is an in-game, attribute-driven debug console for Unity that allows developers to easily define and execute commands. Built on Unity's **Reflection API**, it dynamically discovers scene objects and registers command methods at runtime, providing a flexible and powerful tool for real-time game interaction and debugging.

---

## Features

- **Command Attribute System**  
  Use `[ConsoleCommand("CommandKey")]` to mark methods, properties, or fields as console commands. The system auto-registers them.

- **Reflection-Based Registration**  
  Scans methods, properties, and fields (both public and private) on scene objects during initialization.

- **Single Parameter Support**  
  Supports commands with up to one parameter. Multiple parameters support may be added in the future.

- **Dynamic Command Execution**  
  Execute commands directly from the in-game console interface.

- **Supports Static and Instance Members**  
  Works with static and instance methods, properties, and fields alike.

- **Scene Discovery on Initialization**  
  Automatically discovers objects present when the scene loads. Runtime-instantiated objects require manual subscription.

- **Parameter Passing and Conversion**  
  Converts console input strings to match command method parameters automatically.

- **Exception Handling and Logging**  
  Automatically catches exceptions and logs errors to the console.

- **Built-in Commands**  
  Includes commands like `/Clear` to clear logs and others to interact with the game or engine.

---

## User Interface

![O2 Console Screenshot](Console%20UI%20Images/ConsoleIM%20(5).png)

### Additional Screenshots

- [Screenshot 1](Console%UI%Images/ConsoleIM%(2).png)  
- [Screenshot 2](Console%UI%Images/ConsoleIM%(4).png)  
- [Screenshot 3](Console%UI%Images/ConsoleIM%(6).png)

---

## Getting Started

### Installation

1. Clone or download the **O2 Console** repository or Unity package.
2. Import the O2 Console scripts into your Unity project.
3. Add the provided console prefab into your scene. It contains the input field and log window.
4. Optionally, set a hotkey (e.g., `~`) to toggle the console visibility.

### Usage

Mark any method, property, or field you want to expose as a console command with `[ConsoleCommand("CommandKey")]`. The console will automatically register it.

#### Example: Properties and Fields
```csharp
    [ConsoleCommand("GetValue")]
    public int Value {get; set;}

    [ConsoleCommand("GetStaticValue")]
    public static int StaticValue {get; set;}

    [ConsoleCommand("GetPrivateValue")]
    private int PrivateValue;
```````
Instance & Static Method Example
```csharp

    [ConsoleCommand("InstanceMethod")]
    public void InstanceMethod()
    {
        // Do Something
    }
    
    [ConsoleCommand("SomeFunction")]
    static string SomeFunction()
    {
       return // Do Something
    }
```````
