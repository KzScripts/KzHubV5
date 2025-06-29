-- KZ HUB - VERSÃO CORRIGIDA
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local Workspace = game:GetService("Workspace")
local LocalPlayer = Players.LocalPlayer

-- Aguarda o jogador carregar completamente
if not LocalPlayer.Character then
    LocalPlayer.CharacterAdded:Wait()
end

wait(1) -- Aguarda um pouco mais para garantir carregamento

-- LOADING SCREEN
do
    local screenGui = Instance.new("ScreenGui")
    screenGui.Name = "KzHubLoading"
    screenGui.IgnoreGuiInset = true
    screenGui.ResetOnSpawn = false
    screenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")
    
    local mainFrame = Instance.new("Frame")
    mainFrame.Size = UDim2.new(1, 0, 1, 0)
    mainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
    mainFrame.BorderSizePixel = 0
    mainFrame.Parent = screenGui
    
    local logoImage = Instance.new("ImageLabel")
    logoImage.Size = UDim2.new(0, 96, 0, 96)
    logoImage.Position = UDim2.new(0.5, -48, 0.25, 0)
    logoImage.BackgroundTransparency = 1
    logoImage.ImageTransparency = 1
    logoImage.Image = "rbxassetid://71567579053009"
    logoImage.Parent = mainFrame
    
    local imageCorner = Instance.new("UICorner")
    imageCorner.CornerRadius = UDim.new(0.5, 0)
    imageCorner.Parent = logoImage
    
    local titleLabel = Instance.new("TextLabel")
    titleLabel.Size = UDim2.new(1, 0, 0, 70)
    titleLabel.Position = UDim2.new(0, 0, 0.42, 0)
    titleLabel.BackgroundTransparency = 1
    titleLabel.Text = "Logando Como Admin"
    titleLabel.Font = Enum.Font.GothamBlack
    titleLabel.TextSize = 42
    titleLabel.TextColor3 = Color3.new(1, 1, 1)
    titleLabel.TextStrokeTransparency = 0.2
    titleLabel.TextXAlignment = Enum.TextXAlignment.Center
    titleLabel.TextYAlignment = Enum.TextYAlignment.Center
    titleLabel.TextTransparency = 1
    titleLabel.Parent = mainFrame
    
    local subtitleLabel = Instance.new("TextLabel")
    subtitleLabel.Size = UDim2.new(1, 0, 0, 30)
    subtitleLabel.Position = UDim2.new(0, 0, 0.56, 0)
    subtitleLabel.BackgroundTransparency = 1
    subtitleLabel.Text = "Bem Vindo Ao Kz Hub "
    subtitleLabel.Font = Enum.Font.GothamBold
    subtitleLabel.TextSize = 22
    subtitleLabel.TextColor3 = Color3.new(1, 1, 1)
    subtitleLabel.TextStrokeTransparency = 0.25
    subtitleLabel.TextXAlignment = Enum.TextXAlignment.Center
    subtitleLabel.TextYAlignment = Enum.TextYAlignment.Center
    subtitleLabel.TextTransparency = 1
    subtitleLabel.Parent = mainFrame
    
    local creditLabel = Instance.new("TextLabel")
    creditLabel.Size = UDim2.new(1, 0, 0, 26)
    creditLabel.Position = UDim2.new(0, 0, 0.62, 0)
    creditLabel.BackgroundTransparency = 1
    creditLabel.Text = "Dev Team KzHub"
    creditLabel.Font = Enum.Font.Gotham
    creditLabel.TextSize = 19
    creditLabel.TextColor3 = Color3.new(1, 1, 1)
    creditLabel.TextStrokeTransparency = 0.35
    creditLabel.TextXAlignment = Enum.TextXAlignment.Center
    creditLabel.TextYAlignment = Enum.TextYAlignment.Center
    creditLabel.TextTransparency = 1
    creditLabel.Parent = mainFrame
    
    -- Função de animação
    local function tweenElement(element, property, value, duration)
        local tween = TweenService:Create(element, TweenInfo.new(duration, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {[property] = value})
        tween:Play()
        return tween
    end
    
    -- Animações de entrada
    tweenElement(logoImage, "ImageTransparency", 0, 0.7)
    wait(0.3)
    tweenElement(titleLabel, "TextTransparency", 0, 0.7)
    wait(0.1)
    tweenElement(subtitleLabel, "TextTransparency", 0, 0.6)
    wait(0.05)
    tweenElement(creditLabel, "TextTransparency", 0, 0.6)
    wait(2.1)
    wait(1.2)
    
    -- Animações de saída
    tweenElement(logoImage, "ImageTransparency", 1, 0.6)
    tweenElement(titleLabel, "TextTransparency", 1, 0.6)
    tweenElement(subtitleLabel, "TextTransparency", 1, 0.6)
    tweenElement(creditLabel, "TextTransparency", 1, 0.6)
    wait(0.65)
    screenGui:Destroy()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/KzScripts/KzHubV6/refs/heads/main/KzHubAdmin.lua"))()
end

