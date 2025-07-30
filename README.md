# SHADOW-RUB-- SHADOW HUB by ChatGPT - Seguro e Limpo
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local mouse = player:GetMouse()

-- Image ID da bolinha (sua foto)
local imageId = "https://p77-sign-va.tiktokcdn.com/tos-maliva-avt-0068/ca747922311e6d59ccaf315fd7e6a2cd~tplv-tiktokx-cropcenter:1080:1080.jpeg"

-- Criar ScreenGui
local gui = Instance.new("ScreenGui", game.CoreGui)
gui.Name = "ShadowHub"

-- Bolinha com sua imagem
local icon = Instance.new("ImageButton", gui)
icon.Size = UDim2.new(0, 60, 0, 60)
icon.Position = UDim2.new(0, 20, 0, 20)
icon.Image = imageId
icon.BackgroundTransparency = 1
icon.Name = "OpenMenuButton"
icon.Visible = true
icon.ZIndex = 10

-- Janela do menu
local frame = Instance.new("Frame", gui)
frame.Size = UDim2.new(0, 250, 0, 320)
frame.Position = UDim2.new(0, 100, 0, 100)
frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
frame.BorderSizePixel = 0
frame.Visible = false
frame.Name = "MainMenu"
frame.ZIndex = 5

-- Título
local title = Instance.new("TextLabel", frame)
title.Size = UDim2.new(1, 0, 0, 40)
title.BackgroundTransparency = 1
title.Text = "🔥 SHADOW HUB 🔥"
title.TextColor3 = Color3.fromRGB(255, 0, 0)
title.Font = Enum.Font.GothamBlack
title.TextSize = 20

-- Função para criar botões
local function createButton(name, callback, posY)
	local btn = Instance.new("TextButton", frame)
	btn.Size = UDim2.new(1, -20, 0, 35)
	btn.Position = UDim2.new(0, 10, 0, posY)
	btn.Text = name
	btn.BackgroundColor3 = Color3.fromRGB(40, 0, 0)
	btn.TextColor3 = Color3.new(1, 1, 1)
	btn.Font = Enum.Font.GothamBold
	btn.TextSize = 16
	btn.MouseButton1Click:Connect(callback)
end

-- Funções (simples, você pode editar com o que quiser depois)
createButton("🏃‍♂ Modo Superman", function()
	local char = player.Character or player.CharacterAdded:Wait()
	char.Humanoid.WalkSpeed = 100
	char.Humanoid.JumpPower = 120
end, 50)

createButton("🔍 Auto Inspecionar", function()
	-- Aqui você coloca sua lógica de patch God/Secreto
	print("Inspecionando patches automaticamente...")
end, 90)

createButton("🏠 Voar pra Base", function()
	local char = player.Character or player.CharacterAdded:Wait()
	if char:FindFirstChild("HumanoidRootPart") then
		char.HumanoidRootPart.CFrame = CFrame.new(0, 300, 0) -- exemplo, edite pro local da base
	end
end, 130)

createButton("🧲 Auto Coletar", function()
	-- Simulação de coleta automática
	print("Coleta automática ativada.")
end, 170)

createButton("👯 Twin Pet", function()
	print("Pegando pet e voando...")
end, 210)

createButton("🧟 Fugir do Brainrot", function()
	print("Brainrot detectado. Fugindo...")
end, 250)

-- Clique na bolinha abre/fecha o menu
icon.MouseButton1Click:Connect(function()
	frame.Visible = not frame.Visible
end)
