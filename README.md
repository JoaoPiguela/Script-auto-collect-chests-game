-- Script para coletar todos os baús em Blox Fruits

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

-- Função para coletar baús
function collectChests()
    for _, chest in pairs(workspace:GetChildren()) do
        if chest:IsA("Model") and chest:FindFirstChild("Chest") then
            humanoidRootPart.CFrame = chest.Chest.CFrame
            wait(0.5) -- Espera meio segundo para garantir a coleta
        end
    end
end

-- Loop para coletar baús continuamente
while true do
    collectChests()
    wait(10) -- Espera 10 segundos antes de procurar novamente
end
