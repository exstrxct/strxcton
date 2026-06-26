# Strxcton UI Library
UI Library made by some fuckass furry
<br>
I've always wanted to make my own UI library for my exploiting needs, so i decided to just make this LOL

## Note
A few things:
* There is no dragging yet
* You can toggle the UI with `F2`
* This is still in alpha stages, don't whine in my ear about certain features not working or not existing. **I'm working on it**

## Building
There are **2** versions of Strxcton, if you'd like to use the stable version of strxcton, please use the following loadstring
```lua
local strxcton = loadstring(game:HttpGet("https://raw.githubusercontent.com/exstrxct/strxcton/refs/heads/main/rel/stable.luau"))()
```

As for the dev version, this will include features that we have not yet added, it may be unstable at times.
```lua
local strxcton = loadstring(game:HttpGet("https://raw.githubusercontent.com/exstrxct/strxcton/refs/heads/main/rel/dev.luau"))()
```

After loading, use `strxcton.new()`

```lua
-- Code snippet
local strxcton = loadstring(game:HttpGet("https://raw.githubusercontent.com/exstrxct/strxcton/refs/heads/main/rel/stable.luau"))()

local UI = strxcton.new()
```

From here you can start using the library!

## Usage

### `UI:SetTitle(title: string)`
Sets the title of the UI, usually visible at the topbar

*Example*
```lua
UI:SetTitle("Strxcton - Work at a Pizza Place")
```
`Returns nil`

<br>

---

### `UI:Notify(title: string, text: string, duration: number)`
Sends a simple notification to the player

*Example*
```lua
UI:Notify("Error", "Unable to find victim 'Noob12345' in Workspace")
```
`Returns nil`

<br>

---

### `UI:Label(text: string)`
Adds a `TextLabel` instance to the UI, text customizable with the first parameter.

*Example*
```lua
local Label = UI:Label("Teleportation")
```
`Returns TextLabel: TextLabel`
<br>

---

### `UI:Button(text: string, callback: function)`
Adds a `TextButton` to the UI. You can add a `MouseButton1Click` connection using the `callback` parameter.

*Example*
```lua
local Button = UI:Button("Click to get 500000 money", function()
    game:GetService("ReplicatedStorage").MoneyRemote:FireServer(500000)
end)
```
`Returns TextButton: TextButton`

<br>

---

### `UI:TextBox(placeholder: string, callback: function)`
Adds a `TextBox` to the UI. You can add a `FocusLost` connection using the `callback` parameter, it will fire when `EnterPressed` is true.

*Example*
```lua
local Box = UI:TextBox("Enter WalkSpeed", function()
    local Player = game.Players.LocalPlayer
    local Character = Player.Character
    local Humanoid = Character:FindFirstChild("Humanoid")

    if not Character then return end
    if not Humanoid then return end
    
    Humanoid.WalkSpeed = Box.Text
end)
```
`Returns TextBox: TextBox`

<br>

---

### `UI:Divide()`
Allows you to divide sections of your UI. This essentially creates a invisible frame to make viewing the UI objects easier.

*Example*
```lua
UI:Label("Teleportation")
local Button = UI:Button("Very cool button", function() end)

UI:Divide()

UI:Label("Money Givers")
local Button2 = UI:Button("Button that has nothing to do with the first button", function() end)
```
`Returns nil`

<br>


## Additional
I would really appreciate it if you didn't act like a skid and claim you made this UI library. I created the UI and the script with little to no free time.

## Credits

### - Izzy (exstrxct)
* [GitHub](https://github.com/exstrxct)
* [YouTube](https://www.youtube.com/@exstrxct)
