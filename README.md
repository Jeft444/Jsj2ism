-- JeftXz Hub - Transformação em Monstro Gigante
local Players = game:GetService("Players")
local lp = Players.LocalPlayer
local char = lp.Character or lp.CharacterAdded:Wait()

-- Aguarda o personagem carregar
if not char:FindFirstChild("Humanoid") then
	char:WaitForChild("Humanoid")
end

-- Aumenta o tamanho do personagem
for _, part in pairs(char:GetDescendants()) do
	if part:IsA("BasePart") then
		part.Size = part.Size * 4
		part.Material = Enum.Material.Neon
		part.BrickColor = BrickColor.new("Really red")
	elseif part:IsA("Accessory") then
		part:Destroy()
	end
end

-- Aumenta o personagem visualmente (escala)
if char:FindFirstChild("Humanoid") then
	char.Humanoid.BodyDepthScale.Value = 4
	char.Humanoid.BodyHeightScale.Value = 4
	char.Humanoid.BodyWidthScale.Value = 4
	char.Humanoid.HeadScale.Value = 4
end

-- Adiciona efeito sonoro de monstro
