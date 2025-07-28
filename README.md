# .m--- Cria GUI principal
local player = game.Players.LocalPlayer
local gold = 0

-- Função para criar um botão
local function createButton(parent, text, pos, size)
    local btn = Instance.new("TextButton")
    btn.Parent = parent
    btn.Text = text
    btn.Position = pos
    btn.Size = size
    btn.BackgroundColor3 = Color3.new(1, 0.7, 0.2)
    btn.TextScaled = true
    btn.Font = Enum.Font.GothamBold
    btn.TextColor3 = Color3.new(0,0,0)
    btn.AutoButtonColor = true
    return btn
end

-- Cria ScreenGui
local gui = Instance.new("ScreenGui")
gui.Parent = player:WaitForChild("PlayerGui")
gui.Name = "HotGoldMenu"

-- Botão HOT
local hotBtn = createButton(gui, "HOT", UDim2.new(0.05,0,0.8,0), UDim2.new(0.2,0,0.1,0))

-- Label do ouro
local goldLabel = Instance.new("TextLabel")
goldLabel.Parent = gui
goldLabel.Text = "Ouro: 0"
goldLabel.Position = UDim2.new(0.05,0,0.7,0)
goldLabel.Size = UDim2.new(0.2,0,0.08,0)
goldLabel.BackgroundTransparency = 1
goldLabel.TextScaled = true
goldLabel.Font = Enum.Font.GothamSemibold
goldLabel.TextColor3 = Color3.new(1,1,0)

-- Botão MENU
local menuBtn = createButton(gui, "Menu", UDim2.new(0.28,0,0.8,0), UDim2.new(0.15,0,0.1,0))

-- Menu Frame
local menuFrame = Instance.new("Frame")
menuFrame.Parent = gui
menuFrame.Position = UDim2.new(0.5, -100, 0.5, -90)
menuFrame.Size = UDim2.new(0,200,0,180)
menuFrame.BackgroundColor3 = Color3.new(0.15, 0.15, 0.15)
menuFrame.Visible = false

-- Opções do menu
local renasBtn = createButton(menuFrame, "100000000000× Renascimento", UDim2.new(0,10,0,10), UDim2.new(0,180,0,40))
local sorteBtn = createButton(menuFrame, "1000× de Sorte", UDim2.new(0,10,0,60), UDim2.new(0,180,0,40))
local afkBtn = createButton(menuFrame, "Antik AFK", UDim2.new(0,10,0,110), UDim2.new(0,180,0,40))

-- Fecha menu ao clicar fora
local closeBtn = createButton(menuFrame, "Fechar", UDim2.new(0,10,0,150), UDim2.new(0,180,0,20))

-- Função do botão HOT
hotBtn.MouseButton1Click:Connect(function()
    gold = gold + 1
    goldLabel.Text = "Ouro: " .. tostring(gold)
end)

-- Abre menu
menuBtn.MouseButton1Click:Connect(function()
    menuFrame.Visible = true
end)

-- Fecha menu
closeBtn.MouseButton1Click:Connect(function()
    menuFrame.Visible = false
end)

-- Funções das opções do menu
renasBtn.MouseButton1Click:Connect(function()
    print("Renascimento multiplicado por 100000000000!")
end)

sorteBtn.MouseButton1Click:Connect(function()
    print("Sorte multiplicada por 1000!")
end)

afkBtn.MouseButton1Click:Connect(function()
    print("Antik AFK ativado!")
end)
