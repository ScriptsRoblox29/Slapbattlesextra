local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
 
 
local Window = Rayfield:CreateWindow({
    Name = "Slap Battles Extra",
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
 
 
    KeySystem = false, -- Set this to true to use our key system
    KeySettings = {
       Title = "Key",
       Subtitle = "Key System",
       Note = "Dm for key (Tiktok: Mega_cat_studios)", -- Use this to tell the user how to get a key
       FileName = "skibidi key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Key_9120", "Key_4045"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
 }) 
 
 
 local Aimbot = loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/Aimbot-V3/main/src/Aimbot.lua"))()
 local chams = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Roblox-Chams-Highlight/refs/heads/main/Highlight.lua"))()
 local targethud = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Lua-TargetHud/refs/heads/main/targethud.lua"))()
 local speed = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stratxgy/Lua-Speed/refs/heads/main/speed.lua"))()
 
 
 
 
 local aimbotTab = Window:CreateTab("Main", "crosshair")
 
 local Section = aimbotTab:CreateSection("Main")
 
 
 
 local Button = aimbotTab:CreateButton({
   Name = "get all the Slapples",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart

       local locations = {
           Vector3.new(-224.98114013671875, 6126.7158203125, 484.705810546875),
           Vector3.new(-312.94866943359375, 6186.44775390625, -394.93756103515625),
           Vector3.new(-224.68707275390625, 6175.63427734375, 593.5723876953125),
           Vector3.new(-189.69598388671875, 6171.33349609375, 594.4552612304688),
           Vector3.new(-174.95452880859375, 6125.9990234375, 564.5806884765625),
           Vector3.new(-161.24725341796875, 6135.458984375, 504.67755126953125),
           Vector3.new(-261.95635986328125, 6126.3330078125, 555.8439331054688),
           Vector3.new(-267.85931396484375, 6126.4677734375, 518.296142578125),
           Vector3.new(-537.5476684570312, 6186.4140625, -311.90362548828125),
           Vector3.new(-531.8552856445312, 6186.00244140625, -293.7408447265625),
           Vector3.new(-412.51519775390625, 6185.228515625, -486.0479736328125),
           Vector3.new(-169.58807373046875, 6132.755859375, 512.9716186523438),
           Vector3.new(-219.95013427734375, 6166.21533203125, 572.8008422851562),
           Vector3.new(-261.95672607421875, 6145.9375, 542.096923828125),
           Vector3.new(-211.42474365234375, 6126.5859375, 599.59912109375),
           Vector3.new(-194.39923095703125, 6173.8564453125, 575.3776245117188)
       }

       task.spawn(function()
           for _, pos in ipairs(locations) do
               humanoidRootPart.CFrame = CFrame.new(pos)
               task.wait(0.1)
           end
       end)
   end,
})


 local Button = aimbotTab:CreateButton({
   Name = "security part",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart

       local position = Vector3.new(-874.9923095703125, 6228.69921875, -1030.2723388671875)

       local part = Instance.new("Part")
       part.Size = Vector3.new(50, 2, 50)
       part.Position = position
       part.Anchored = true
       part.CanCollide = true
       part.Parent = workspace

       humanoidRootPart.CFrame = CFrame.new(position.X, position.Y + 3, position.Z) -- Teleporta 3 studs acima
   end,
})


local Button = aimbotTab:CreateButton({
   Name = "Remove Mod call of all (no work more)",
   Callback = function()
       for _, player in ipairs(game.Players:GetPlayers()) do
           if player:FindFirstChild("PlayerGui") then
               local playerGui = player.PlayerGui
               local mainGui = playerGui:FindFirstChild("MainGui")
               if mainGui then
                   local buttons = mainGui:FindFirstChild("Buttons")
                   if buttons then
                       local reportFrame = buttons:FindFirstChild("ReportFrame")
                       if reportFrame and reportFrame:IsA("TextLabel") then
                           reportFrame:Destroy()
                       end
                   end
               end
           end
       end
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


 local Button = visualsTab:CreateButton({
   Name = "Delete Lava",
   Callback = function()
       local islands = workspace:FindFirstChild("Islands")
       if not islands then return end

       local volcanoIsland = islands:FindFirstChild("Volcano Island")
       if not volcanoIsland then return end

       for _, obj in ipairs(volcanoIsland:GetDescendants()) do
           if obj:IsA("Part") and obj.Name == "Lava" then
               obj:Destroy()
           end
       end
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
    Range = {0, 259},
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
}


 local gloveTab = Window:CreateTab("Glove", "crosshair")
 
 local Section = gloveTab:CreateSection("change your glove idk")


 local Button = gloveTab:CreateButton({
   Name = "Slap Aura (support on some gloves)",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character then return end

       local glovesList = {
           "Default", "OVERKILL", "ZZZZZZZ", "Diamond", "Brick", "Snow", 
           "Dice", "Stun", "Flash", "Replica", "Reverse", "Defense", 
           "MEGAROCK", "Rocky", "Reaper", "Blocked", "God's Hand", 
           "The Flex", "Exploit", "Weakness", "Builder", "Dual", "Troll", 
           "Box","Glove"
       }

       for _, tool in ipairs(player.Character:GetChildren()) do
           if tool:IsA("Tool") and table.find(glovesList, tool.Name) then
               for _, obj in ipairs(tool:GetDescendants()) do
                   if obj:IsA("MeshPart") and obj.Name == "Hand" then
                       obj.Size = Vector3.new(75, 75, 75)
                       obj.Material = Enum.Material.ForceField
                       obj.Color = Color3.fromRGB(0, 255, 0)
                   end
               end
           end
       end
   end,
})


 local usefulTab = Window:CreateTab("useful", "crosshair")
 
 local Section = usefulTab:CreateSection("this will help")


 local Button = usefulTab:CreateButton({
   Name = "Anti-Void",
   Callback = function()
       local part = Instance.new("Part")
       part.Size = Vector3.new(2048, 2, 2048)
       part.Position = Vector3.new(-37.72334671020508, 6074.17431640625, 83.17035675048828)
       part.Anchored = true
       part.CanCollide = true
       part.Transparency = 0.25
       part.Parent = workspace
   end,
})


local Toggle = usefulTab:CreateToggle({
    Name = "Slapple Farm",
    CurrentValue = false,
    Flag = "TeleportToggle",
    Callback = function(Value)
        getgenv().teleportEnabled = Value
        
        if Value then
            task.spawn(function()
                local player = game.Players.LocalPlayer
                if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

                local humanoidRootPart = player.Character.HumanoidRootPart
                local locations = {
                    Vector3.new(-224.98114013671875, 6126.7158203125, 484.705810546875),
                    Vector3.new(-312.94866943359375, 6186.44775390625, -394.93756103515625),
                    Vector3.new(-224.68707275390625, 6175.63427734375, 593.5723876953125),
                    Vector3.new(-189.69598388671875, 6171.33349609375, 594.4552612304688),
                    Vector3.new(-174.95452880859375, 6125.9990234375, 564.5806884765625),
                    Vector3.new(-161.24725341796875, 6135.458984375, 504.67755126953125),
                    Vector3.new(-261.95635986328125, 6126.3330078125, 555.8439331054688),
                    Vector3.new(-267.85931396484375, 6126.4677734375, 518.296142578125),
                    Vector3.new(-537.5476684570312, 6186.4140625, -311.90362548828125),
                    Vector3.new(-531.8552856445312, 6186.00244140625, -293.7408447265625),
                    Vector3.new(-412.51519775390625, 6185.228515625, -486.0479736328125),
                    Vector3.new(-169.58807373046875, 6132.755859375, 512.9716186523438),
                    Vector3.new(-219.95013427734375, 6166.21533203125, 572.8008422851562),
                    Vector3.new(-261.95672607421875, 6145.9375, 542.096923828125),
                    Vector3.new(-211.42474365234375, 6126.5859375, 599.59912109375),
                    Vector3.new(-194.39923095703125, 6173.8564453125, 575.3776245117188)
                }

                while getgenv().teleportEnabled do
                    for _, pos in ipairs(locations) do
                        if not getgenv().teleportEnabled then return end
                        humanoidRootPart.CFrame = CFrame.new(pos)
                        task.wait(0.05)
                    end
                end
            end)
        else
            getgenv().teleportEnabled = false
        end
    end,
})


local Toggle = usefulTab:CreateToggle({
    Name = "Slap Farm (use slap aura to be more useful)",
    CurrentValue = false,
    Flag = "MoveToggle",
    Callback = function(Value)
        getgenv().moveToPlayers = Value

        if Value then
            task.spawn(function()
                local player = game.Players.LocalPlayer
                if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

                local humanoidRootPart = player.Character.HumanoidRootPart

                while getgenv().moveToPlayers do
                    for _, targetPlayer in pairs(game.Players:GetPlayers()) do
                        if targetPlayer ~= player then
                            local targetChar = targetPlayer.Character
                            if targetChar and targetChar:FindFirstChild("HumanoidRootPart") then
                                local targetPosition = targetChar.HumanoidRootPart.Position
                                local currentPosition = humanoidRootPart.Position
                                
                                local direction = (targetPosition - currentPosition).unit
                                
                                local moveSpeed = 250
                                local newPosition = currentPosition + direction * moveSpeed * 0.1
                                
                                humanoidRootPart.CFrame = CFrame.new(newPosition)
                                task.wait(0.05)
                            end
                        end
                    end
                end
            end)
        else
            getgenv().moveToPlayers = false
        end
    end
})


local Button = usefulTab:CreateButton({
    Name = "Become invisible",
    Callback = function()
        local player = game.Players.LocalPlayer
        if not player or not player.Character then return end

        for _, part in pairs(player.Character:GetChildren()) do
            if part:IsA("BasePart") or part:IsA("MeshPart") then
                part.Transparency = 1
            elseif part:IsA("Accessory") and part:FindFirstChild("Handle") then
                part.Handle.Transparency = 1
            end
        end

        local head = player.Character:FindFirstChild("Head")
        if head then
            local faceDecal = head:FindFirstChildWhichIsA("Decal")
            if faceDecal then
                faceDecal.Transparency = 1
            end
        end
    end,
})


local tpTab = Window:CreateTab("Teleport", "crosshair")
 
 local Section = tpTab:CreateSection("teleports")


 local Button = tpTab:CreateButton({
   Name = "TP to lobby",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart
       humanoidRootPart.CFrame = CFrame.new(-550.1726684570312, 6313.1767578125, -2.789579153060913)
   end,
})


local Button = tpTab:CreateButton({
   Name = "TP to area",
   Callback = function()
       local player = game.Players.LocalPlayer
       if not player or not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

       local humanoidRootPart = player.Character.HumanoidRootPart
       humanoidRootPart.CFrame = CFrame.new(-29.6503849029541, 6082.54638671875, 85.0864028930664) -- teleport.
   end,
})
 
 
 Rayfield:Notify({
    Title = "Ready!",
    Content = "Script loaded.",
    Duration = 6.5,
    Image = 4483362458,
 })

Rayfield:Notify({
    Title = "important warning!",
    Content = "This game has moderation so if you have any staff on your server, LEAVE.",
    Duration = 10,
    Image = 4483362458,
 })
 
