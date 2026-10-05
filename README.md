loadstring(game:HttpGet("https://raw.githubusercontent.com/sara_Y1780/main/autofarm.lua"))()
local Players = game:GetService("Players")
local player = Players.LocalPlayer

print("AutoFarm system loaded for " .. player.Name)

-- Apne game ke NPC folder ka naam
local enemies = workspace:FindFirstChild("Enemies")

if not enemies then
    warn("Enemies folder nahi mila!")
    return
end

while task.wait(1) do
    for _, enemy in ipairs(enemies:GetChildren()) do
        local humanoid = enemy:FindFirstChildOfClass("Humanoid")

        if humanoid and humanoid.Health > 0 then
            print("Target:", enemy.Name)
            -- Yahan tumhare own game's attack system ko call karna hoga.
        end
    end
end
