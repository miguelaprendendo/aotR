
-- Configurações básicas
local targetNPCs = {"Titan", "Abnormal"} -- Nomes dos NPCs a serem eliminados

-- Função para encontrar e atacar NPCs
functionattackAllNPCs ()
for _, npc in pairs(game.Workspace:GetChildren()) do
if table.find(targetNPCs, npc.Name) and npc:FindFirstChild("HumanoidRootPart") then
-- Move o jogador para perto do NPC e ataca
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = npc.HumanoidRootPart.CFrame * CFrame.new(0, 0, -5)
game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool"):Activate()
end
end
end
-- Loop principal para eliminar NPCs
game:GetService("RunService").RenderStepped:Connect(function()
attackAllNPCs()
end)
