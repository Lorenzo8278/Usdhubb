-- ✅ USD HUB LOADING + MAIN GUI FUNCIONAL (Delta-safe)

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Remove GUIs antigas
pcall(function()
	if playerGui:FindFirstChild("USDLoadingGui") then playerGui.USDLoadingGui:Destroy() end
	if playerGui:FindFirstChild("USDMainGui") then playerGui.USDMainGui:Destroy() end
end)

-- GUI de carregamento
local loadingGui = Instance.new("ScreenGui")
loadingGui.Name = "USDLoadingGui"
loadingGui.ResetOnSpawn = false
loadingGui.IgnoreGuiInset = true
loadingGui.Parent = playerGui

-- Imagem de fundo (LOADING...)
local loadingImage = Instance.new("ImageLabel")
loadingImage.Parent = loadingGui
loadingImage.Size = UDim2.new(1, 0, 1, 0)
loadingImage.Position = UDim2.new(0, 0, 0, 0)
loadingImage.Image = "rbxassetid://17447123781" -- 🖼️ ID do "LOADING"
loadingImage.BackgroundTransparency = 1
loadingImage.ScaleType = Enum.ScaleType.Stretch

-- Texto "BEM VINDO AO USD HUB"
local loadingText = Instance.new("TextLabel")
loadingText.Parent = loadingGui
loadingText.Size = UDim2.new(1, 0, 0.1, 0)
loadingText.Position = UDim2.new(0, 0, 0.85, 0)
loadingText.Text = "BEM VINDO AO USD HUB"
loadingText.TextScaled = true
loadingText.Font = Enum.Font.GothamBold
loadingText.TextColor3 = Color3.fromRGB(0, 255, 255)
loadingText.TextStrokeTransparency = 0.2
loadingText.BackgroundTransparency = 1

-- Aguarda 5 segundos, depois troca para o MAIN
task.delay(5, function()
	loadingGui:Destroy()

	local mainGui = Instance.new("ScreenGui")
	mainGui.Name = "USDMainGui"
	mainGui.ResetOnSpawn = false
	mainGui.IgnoreGuiInset = true
	mainGui.Parent = playerGui

	local mainImage = Instance.new("ImageLabel")
	mainImage.Parent = mainGui
	mainImage.Size = UDim2.new(1, 0, 1, 0)
	mainImage.Position = UDim2.new(0, 0, 0, 0)
	mainImage.Image = "rbxassetid://17447166434" -- 🖼️ ID da imagem do "MAIN" (Kaká)
	mainImage.BackgroundTransparency = 1
	mainImage.ScaleType = Enum.ScaleType.Stretch
end)
