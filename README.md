local Library = loadstring(Game:HttpGet("https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wizard"))()

local PhantomForcesWindow = Library:NewWindow("By Yay = Get Huge thx")
-- New Teleport Section
local TeleportSection = PhantomForcesWindow:NewSection("Teleport")

-- Booster Toggle
TeleportSection:CreateToggle("booster2xSuperMarcket", function(value)
    if value then
        local player = game.Players.LocalPlayer
        local character = player.Character
        local part = workspace:FindFirstChild("Radioactive")
        
        if character and part then
            local humanoidRoot = character:FindFirstChild("HumanoidRootPart")
            if humanoidRoot then
                humanoidRoot.CFrame = part.CFrame
            end
        end
    end
end)

-- Vertical Slider
TeleportSection:CreateSlider("Height Control", 0, 100, 0, false, function(value)
    local player = game.Players.LocalPlayer
    local character = player.Character
    
    if character then
        local humanoidRoot = character:FindFirstChild("HumanoidRootPart")
        if humanoidRoot then
            local pos = humanoidRoot.Position
            pos.Y = value * 10  -- Multiply by 10 for better height control
            humanoidRoot.Position = pos
        end
    end
end)
