Understood! Let's create a structured documentation for your `imgui` Roblox UI library, modeled after the style of the Orion UI Library documentation. This will provide users with clear guidance on how to utilize your library effectively.

---

# 📘 **imgui UI Library Documentation**

A lightweight and modular UI library for Roblox, designed for exploit scripts and custom interfaces.

---

## 🔧 **Getting Started**

To begin using the `imgui` library, load it into your script:

```lua
local engine = loadstring(game:HttpGet("https://raw.githubusercontent.com/Singularity5490/rbimgui-2/main/rbimgui-2.lua"))()
```

This initializes the `engine` object, which serves as the entry point for creating windows and UI elements.

---

## 🪟 **Creating a Window**

Create a new window with the following syntax:

```lua
local window = engine.new({
    text = "Window Title",
    size = UDim2.new(0, 300, 0, 200),
})
window.open()
```

- `text`: Title displayed on the window.
- `size`: Dimensions of the window using `UDim2`.

---

## 📑 **Adding Tabs**

Add tabs to organize your UI elements:

```lua
local tab = window.new({
    text = "Tab Name",
})
```

- `text`: Label for the tab.

---

## 🧩 **UI Elements**

### 🔹 **Label**

Displays static text.

```lua
local label = tab.new("label", {
    text = "This is a label",
    color = Color3.new(1, 0, 0), -- Optional text color
})
```

### 🔘 **Button**

Clickable button that triggers an event.

```lua
local button = tab.new("button", {
    text = "Click Me",
})
button.event:Connect(function()
    print("Button clicked!")
end)
```

### 🔄 **Switch**

Toggle switch for boolean values.

```lua
local switch = tab.new("switch", {
    text = "Enable Feature",
})
switch.set(true) -- Set initial state
switch.event:Connect(function(state)
    print("Switch state:", state)
end)
```

### 🎚️ **Slider**

Adjustable slider for numerical input.

```lua
local slider = tab.new("slider", {
    text = "Volume",
    min = 0,
    max = 100,
    value = 50,
    rounding = 0, -- Decimal places
})
slider.event:Connect(function(value)
    print("Slider value:", value)
end)
slider.set(75) -- Set slider value
```

### 🎨 **Color Picker**

Select a color value.

```lua
local colorPicker = tab.new("color", {
    text = "Pick a Color",
    color = Color3.new(0, 0, 1), -- Initial color
})
colorPicker.event:Connect(function(color)
    print("Selected color:", color)
end)
```

### 📂 **Dropdown**

Dropdown menu for selecting options.

```lua
local dropdown = tab.new("dropdown", {
    text = "Choose an Option",
})
dropdown.new("Option 1")
dropdown.new("Option 2")
dropdown.event:Connect(function(selected)
    print("Selected:", selected)
end)
```

### 🧱 **Dock**

Container for grouping elements horizontally.

```lua
local dock = tab.new("dock")

local dockButton = dock.new("button", {
    text = "Docked Button",
})
dockButton.event:Connect(function()
    print("Docked button clicked")
end)

local dockSlider = dock.new("slider", {
    size = 100,
})
dockSlider.event:Connect(function(value)
    print("Docked slider value:", value)
end)
```

### 📁 **Folder**

Collapsible section for organizing elements.

```lua
local folder = tab.new("folder", {
    text = "Settings",
})
folder.open() -- Expand folder

local folderButton = folder.new("button", {
    text = "Apply Settings",
})
folderButton.event:Connect(function()
    print("Settings applied")
end)
```

---

## 🧪 **Example Usage**

```lua
local engine = loadstring(game:HttpGet("https://raw.githubusercontent.com/Singularity5490/rbimgui-2/main/rbimgui-2.lua"))()

local window = engine.new({
    text = "Demo Window",
    size = UDim2.new(0, 300, 0, 200),
})
window.open()

local tab = window.new({ text = "Main Tab" })

local label = tab.new("label", {
    text = "Welcome to imgui!",
    color = Color3.new(0, 1, 0),
})

local button = tab.new("button", {
    text = "Click Me",
})
button.event:Connect(function()
    print("Button clicked!")
end)
```

---

## 📝 **Notes**

- All UI elements are created using the `tab.new` method with the element type and configuration table.
- Events are connected using the `.event:Connect(function)` pattern.
- Use `.set(value)` to programmatically set the state of switches and sliders.

---

If you need further assistance or examples, feel free to ask! 
