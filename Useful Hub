local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Create Window

local Window = Rayfield:CreateWindow({
    Name = "Useful Hub",
    LoadingTitle = "Loading...",
    LoadingSubtitle = "By Midas93939",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = "Useful Hub", -- <-- changed folder name
        FileName = "MyUI"
    },
    Discord = { Enabled = false },
    KeySystem = false
})

-- Create a main tab
local MainTab = Window:CreateTab("Main", 4483362458)

-- Variables for toggle/slider
local toggleRunning = false
local loopThread
local sliderValue = 5

-- Toggle: starts/stops repeating action
MainTab:CreateToggle({
    Name = "Auto Action",
    CurrentValue = false,
    Flag = "AutoToggle",
    Callback = function(Value)
        toggleRunning = Value

        if toggleRunning then
            loopThread = task.spawn(function()
                while toggleRunning do
                    print("Action running! Slider value:", sliderValue)
                    -- Example safe action: you can replace this
                    task.wait(1)
                end
            end)
        else
            print("Action stopped.")
        end
    end,
})

-- Slider: changes a variable dynamically

-- Button 1: Safe action example
MainTab:CreateButton({
    Name = "Auto Fire Proximity",
    Callback = function()
        print("Button pressed: Doing something!")
        -- Auto-activate any ProximityPrompt when it appears (becomes visible)
for _, prompt in pairs(game:GetDescendants()) do
    if prompt:IsA("ProximityPrompt") then
        prompt.Triggered:Connect(function() end) -- prevent errors

        prompt.PromptShown:Connect(function()
            fireproximityprompt(prompt)
        end)
    end
end

-- Detect any new prompts added later
game.DescendantAdded:Connect(function(v)
    if v:IsA("ProximityPrompt") then
        v.PromptShown:Connect(function()
            fireproximityprompt(v)
        end)
    end
end)

        -- Replace this with any safe action in your Studio project
    end,
})

-- Button 2: Another safe action
MainTab:CreateButton({
    Name = "Instant Proximity",
    Callback = function()
        print("Button pressed: Another action triggered!")
        -- Another example safe action
        -- Make all ProximityPrompts fire instantly
local function setProximityHoldToZero(parent)
    for _, obj in pairs(parent:GetDescendants()) do
        if obj:IsA("ProximityPrompt") then
            obj.HoldDuration = 0
        end
    end
end

-- Apply to the whole workspace
setProximityHoldToZero(game.Workspace)

-- Optional: continuously update newly added ProximityPrompts
game.Workspace.DescendantAdded:Connect(function(descendant)
    if descendant:IsA("ProximityPrompt") then
        descendant.HoldDuration = 0
    end
end)

    end,
})

local SlotTab = Window:CreateTab("Slot", 4483362458)

-- Example toggle on Slot tab
SlotTab:CreateToggle({
    Name = "Slot Toggle",
    CurrentValue = false,
    Flag = "SlotToggle",
    Callback = function(Value)
        print("Slot Toggle is now:", Value)
    end
})

-- Example slider on Slot tab
SlotTab:CreateSlider({
    Name = "Slot Slider",
    Range = {0, 100},
    Increment = 5,
    Suffix = "%",
    CurrentValue = 50,
    Flag = "SlotSlider",
    Callback = function(Value)
        print("Slot Slider set to:", Value)
    end
})

-- Example button on Slot tab
SlotTab:CreateButton({
    Name = "Slot Action",
    Callback = function()
        print("Slot Action button pressed!")
    end
})


