# 🎮 O2 InGame Console

**O2 Console** is an in-game, attribute-driven debug console for Unity that lets developers **easily define and execute commands** at runtime. Built using Unity’s powerful **Reflection API**, it dynamically discovers scene objects and registers command methods, providing a flexible and robust tool for live debugging and interaction.

---

## ✨ Features

- 🏷️ **Command Attribute System**  
  Mark methods, properties, or fields with `[ConsoleCommand("CommandKey")]` and the console automatically registers them as commands.

- 🔍 **Reflection-Based Registration**  
  Scans all public and private methods, properties, and fields on scene objects during initialization.

- 🔢 **Single Parameter Support**  
  Supports commands with up to one parameter (multi-parameter support coming soon!).

- ⚡ **Dynamic Command Execution**  
  Execute commands directly from the in-game console UI.

- 🧩 **Supports Static & Instance Members**  
  Works seamlessly with static and instance methods, properties, and fields.

- 🎯 **Scene Discovery on Load**  
  Automatically discovers objects present when the scene loads; runtime-created objects require manual registration.

- 🔄 **Parameter Passing & Conversion**  
  Converts input strings from the console to the correct method parameter types automatically.

- 🛡️ **Exception Handling & Logging**  
  Captures exceptions and logs errors cleanly in the console for easier debugging.

- 🚀 **Built-in Commands**  
  Includes handy commands like `/Clear` to clear logs and others for interacting with your game or engine.

---

## 🎨 User Interface

![O2 Console Screenshot](Console%20UI%20Images/ConsoleIM%20(5).png)

### Additional Screenshots  
- ![Screenshot 1](Console%UI%Images/ConsoleIM%(2).png)  
- ![Screenshot 2](Console%UI%Images/ConsoleIM%(4).png)  
- ![Screenshot 3](Console%UI%Images/ConsoleIM%(6).png)  

---

## 🚀 Getting Started

### Installation

1. Clone or download the **O2 Console** repository or Unity package.  
2. Import the console scripts into your Unity project.  
3. Drag and drop the provided console prefab into your scene (includes input field & log display).  
4. Optionally, set a hotkey (e.g., `~`) to toggle the console during play mode.

---

### Usage

To expose a command to the console, simply decorate methods, properties, or fields with the `[ConsoleCommand("CommandKey")]` attribute. The console will auto-register them.

#### Example: Properties & Fields
```csharp
[ConsoleCommand("GetValue")]
public int Value { get; set; }

[ConsoleCommand("GetStaticValue")]
public static int StaticValue { get; set; }

[ConsoleCommand("GetPrivateValue")]
private int PrivateValue;

[ConsoleCommand("InstanceMethod")]
public void InstanceMethod()
{
    // Your code here
}

[ConsoleCommand("SomeFunction")]
static string SomeFunction()
{
    return "Hello from static function!";
}
