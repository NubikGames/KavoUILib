# KavoUILib
Kavo UI Library by xHeptc Documentation but in GitHub.

[[Kavo UI Library by xHeptc]]
[Documentation]

Getting Loadstring:
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

Creating UI Library Window:
local Window = Library.CreateLib("TITLE", "DarkTheme")
Themes:
    LightTheme
    DarkTheme
    GrapeTheme
    BloodTheme
    Ocean
    Midnight
    Sentinel
    Synapse

Creating Tabs:
local Tab = Window:NewTab("TabName")

Creating Section:
local Section = Tab:NewSection("Section Name")

Update Section:
Section:UpdateSection("Section New Title")

Creating Labels:
Section:NewLabel("LabelText")

Update Label:
label:UpdateLabel("New Text")

Creating Buttons:
Section:NewButton("ButtonText", "ButtonInfo", function()
    print("Clicked")
end)

Update Button:
Make sure your button is local when updating it.

button:UpdateButton("New Text")

Creating Toggles:
Section:NewToggle("ToggleText", "ToggleInfo", function(state)
    if state then
        print("Toggle On")
    else
        print("Toggle Off")
    end
end)

Updating Toggles:
getgenv().Toggled = false

local toggle = Section:NewToggle("Toggle", "Info", (state)
    getgenv().Toggled = state
end)

game:GetService("RunService").RenderStepped:Connect(function()
	if getgenv().Toggled then
		toggle:UpdateToggle("Toggle On")
	else
		toggle:UpdateToggle("Toggle Off")
	end
end)

Creating Sliders:
Section:NewSlider("SliderText", "SliderInfo", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

Creating Textboxes:
Section:NewTextBox("TextboxText", "TextboxInfo", function(txt)
	print(txt)
end)

Creating Keybinds:
Section:NewKeybind("KeybindText", "KeybindInfo", Enum.KeyCode.F, function()
	print("You just clicked the bind")
end)

Toggling UI with Keybinds:
Section:NewKeybind("KeybindText", "KeybindInfo", Enum.KeyCode.F, function()
	Library:ToggleUI()
end)

Creating Dropdowns:
Section:NewDropdown("DropdownText", "DropdownInf", {"Option 1", "Option 2", "Option 3"}, function(currentOption)
    print(currentOption)
end)

Dropdown Refresh:
local oldList = {
  "2019",
  "2020"
}
local newList = {
  "2021",
  "2022"
}
local dropdown = Section:NewDropdown("Dropdown","Info", oldList, function()

end)
Section:NewButton("Update Dropdown", "Refreshes Dropdown", function()
  dropdown:Refresh(newList)
end)

Creating Color Pickers:
Section:NewColorPicker("Color Text", "Color Info", Color3.fromRGB(0,0,0), function(color)
    print(color)
    -- Second argument is the default color
end)

This is end of Kavo UI Library documentation.
