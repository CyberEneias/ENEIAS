-- LocalScript

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Informações da experiência
local experienceName = game.Name
local executionDate = os.date("%d/%m/%Y - %H:%M:%S")

-- Estados
local autofarmEnabled = false
local killAuraEnabled = false

-- Criando GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "TestGUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = playerGui

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 300, 0, 200)
frame.Position = UDim2.new(0, 20, 0, 20)
frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
frame.Parent = screenGui

local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 10)
corner.Parent = frame

-- Título (nome da experiência)
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, -10, 0, 30)
title.Position = UDim2.new(0, 5, 0, 5)
title.BackgroundTransparency = 1
title.Text = experienceName
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.TextScaled = true
title.Font = Enum.Font.GothamBold
title.Parent = frame

-- Data
local dateLabel = Instance.new("TextLabel")
dateLabel.Size = UDim2.new(1, -10, 0, 20)
dateLabel.Position = UDim2.new(0, 5, 0, 40)
dateLabel.BackgroundTransparency = 1
dateLabel.Text = executionDate
dateLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
dateLabel.TextScaled = true
dateLabel.Font = Enum.Font.Gotham
dateLabel.Parent = frame

-- Função para criar botões toggle
local function createToggle(text, positionY, callback)
	local button = Instance.new("TextButton")
	button.Size = UDim2.new(1, -20, 0, 35)
	button.Position = UDim2.new(0, 10, 0, positionY)
	button.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
	button.Text = text .. ": OFF"
	button.TextColor3 = Color3.fromRGB(255, 255, 255)
	button.Font = Enum.Font.Gotham
	button.TextScaled = true
	button.Parent = frame

	local enabled = false

	button.MouseButton1Click:Connect(function()
		enabled = not enabled
		button.Text = text .. (enabled and ": ON" or ": OFF")
		callback(enabled)
	end)
end

-- Toggle Autofarm
createToggle("Autofarm", 70, function(state)
	autofarmEnabled = state
end)

-- Toggle Kill Aura
createToggle("Kill Aura", 115, function(state)
	killAuraEnabled = state
end)

-- Loop do Autofarm (exemplo genérico)
task.spawn(function()
	while true do
		task.wait(1)

		if autofarmEnabled then
			-- EXEMPLO:
			-- Mover o personagem
			-- Coletar moedas
			-- Disparar RemoteEvent

			print("Autofarm ativo...")
		end
	end
end)

-- Loop do Kill Aura (exemplo genérico)
task.spawn(function()
	while true do
		task.wait(0.3)

		if killAuraEnabled then
			-- EXEMPLO:
			-- Detectar inimigos próximos
			-- Reduzir vida / atacar via RemoteEvent

			print("Kill Aura ativa...")
		end
	end
end)
