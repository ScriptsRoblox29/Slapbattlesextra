local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
 
 
local Window = Rayfield:CreateWindow({
    Name = "Slap Battles But Bad",
    Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
    LoadingTitle = "Loading...",
    LoadingSubtitle = "by isssacque1234",
    Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
    ConfigurationSaving = {
       Enabled = true,
       FolderName = skibidi, -- Create a custom folder for your hub/game
       FileName = "skibidi script"
    },
 
 
    KeySystem = true, -- Set this to true to use our key system
    KeySettings = {
       Title = "Key",
       Subtitle = "Key System",
       Note = "Dm for key (Tiktok: Mega_cat_studios)", -- Use this to tell the user how to get a key
       FileName = "skibidi key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Key_9120"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
 }) 
 
 
 local Aimbot = loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/Aimbot-V3/main/src/Aimbot.lua"))()
 local chams = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Roblox-Chams-Highlight/refs/heads/main/Highlight.lua"))()
 local targethud = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Lua-TargetHud/refs/heads/main/targethud.lua"))()
 local speed = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Lua-Speed/refs/heads/main/speed.lua"))()
 
 
 
 
 local aimbotTab = Window:CreateTab("Main", "crosshair")
 
 local Section = aimbotTab:CreateSection("Main")
 
 
 
 
 local Button = aimbotTab:CreateButton({
   Name = "Anti-Void",
   Callback = function()
       local part = Instance.new("Part")
       part.Size = Vector3.new(2048, 2, 2048)
       part.Position = Vector3.new(5.28387451, 189.407303, -188.988602)
       part.Transparency = 0.35
       part.Anchored = true
       part.CanCollide = true
       part.Parent = workspace
   end,
})

 
 local visualsTab = Window:CreateTab("Visuals", "crosshair")
 
 local Section = visualsTab:CreateSection("This is visual, meaning it doesn't appear to the entire server, just you.")
 
 
 local Toggle = visualsTab:CreateToggle({
    Name = "ESP players",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().chams.enabled = Value
    end,
 })
 

local playerTab = Window:CreateTab("Player", "crosshair")
 
 local Section = playerTab:CreateSection("I think you already know")


local Toggle = playerTab:CreateToggle({
    Name = "activate Speed",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().speed.enabled = Value
    end,
 })
 
 
  local Slider = playerTab:CreateSlider({
    Name = "Speed",
    Range = {0, 250},
    Increment = 1,
    Suffix = "Speed",
    CurrentValue = 0,
    Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        getgenv().speed.speed = Value
    end,
 })

 
 
 getgenv().speed = {
    enabled = false,       -- Enable or disable the speed boost
    speed = 16,          -- Desired walk speed
    control = false, -- Enable enhanced control
    friction = 2.0,       -- Custom friction factor for more control
    keybind = Enum.KeyCode.KeypadDivide -- yes.. i put it as divide.. on the keypad
})


local creditTab = Window:CreateTab("Credits", "crosshair")
 
 local Section = playerTab:CreateSection("credits")


 local Label = creditTab:CreateLabel("Creator of script: isssacque1234", 4483362458, Color3.fromRGB(255, 255, 255), false) -- Title, Icon, Color, IgnoreTheme

 local Label = creditTab:CreateLabel("taught me how to make a script: @stratxgydev", 4483362458, Color3.fromRGB(255, 255, 255), false) -- Title, Icon, Color, IgnoreTheme
 

 local tpTab = Window:CreateTab("Teleport", "crosshair")
 
 local Section = playerTab:CreateSection("teleport to places")

 
 Rayfield:Notify({
    Title = "Ready!",
    Content = "Script loaded.",
    Duration = 6.5,
    Image = 4483362458,
 })
