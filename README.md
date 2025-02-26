-- VERSÃO PRA EU
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/Kiwilegazin/Orion-mobile-v2/refs/heads/main/README.md')))()

-- LA ELE RECEBA CASCA DE BALA 
local Window = OrionLib:MakeWindow({
    Name = "🎩RED BLACK HUB V6🎩",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionTest",
    IntroEnabled = false
})

-- NOSAAA
local Tab1 = Window:MakeTab({
    Name = "👨‍💻SCRIPTS👨‍💻",
    Icon = "rbxassetid://138553129773125",
    PremiumOnly = false
})

-- AI MEU CU
Tab1:AddTextbox({
    Name = "🤑COLOCA A MERDA DO SCRIPT LOGO🤑",
    Default = "",
    TextDisappear = false,
    Callback = function(text)
        _G.scriptCode = text
    end
})

-- BRUH
Tab1:AddButton({
    Name = "📄EXECUTAR O SCRIPT QUE TU COLOCOU NA MERDA DA TEXT BOX📄",
    Callback = function()
        if _G.scriptCode and _G.scriptCode ~= "" then
            local func = loadstring(_G.scriptCode)
            if func then
                func()
            else
                print("Erro ao carregar o script.")
            end
        else
            print("Por favor, insira um script válido na TextBox.")
        end
    end
})

-- SCRIPTS FICA NESSE CARALHO

Tab1:AddButton({
    Name = "🤑ESP RED BLACK🤑",
    Callback = function()
        loadstring(game:HttpGet('https://rawscripts.net/raw/Universal-Script-ESP-VERIFICADOR-DE-PLAYERS-V5-27937'))()
    end
})

Tab1:AddButton({
    Name = "🕹️SANDER X🕹️",
    Callback = function()
        loadstring(game:HttpGet('https://rawscripts.net/raw/Brookhaven-RP-Sander-X-Hub-Latest-Version-3-16718'))()
    end
})

Tab1:AddButton({
    Name = "✈️FLY GUI✈️",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Brookhaven-andx1F3E1RP-Fly-Gui-15924"))()
    end
})

Tab1:AddButton({
    Name = "💰WALK FLING(SOMENTE EM MAPAS COM COLISÃO DE PLAYERS)💰",
    Callback = function()
       loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Walk-Fling-Script-18573"))()
    end
})

Tab1:AddButton({
    Name = "📄INFINITE YIELD📄",
    Callback = function()
       loadstring(game:HttpGet("https://rawscripts.net/raw/Infinite-Yield_500"))()
    end
})

Tab1:AddButton({
    Name = "🌐TROLL GUI🌐",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Troll-Gui-3874"))()
    end
})

-- PEGA NO MEU PAL
local Tab2 = Window:MakeTab({
    Name = "🥳LAG SERVER/TOOLS🥳",
    Icon = "rbxassetid://127522669208877",
    PremiumOnly = false
})

Tab2:AddButton({
    Name = "🍖Equipar Todos os Itens🍖",
    Callback = function()
        equipAllItems()
    end
})
Tab2:AddButton({
    Name = "👨‍🔬TELEPORT TOOL👨‍🔬",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Teleport-Tool-27419"))()
    end
})

Tab2:AddButton({
    Name = "🤑TELEKINIS🤑",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Fe-Telekinesis-V5-21542"))()
    end
})

Tab2:AddButton({
    Name = "🔥LAG SERVER🔥",
    Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(500, 50, 500)
        local clickDetector = Instance.new("ClickDetector")
        for i = 1, 5 do
            local basketball = Instance.new("Tool", game.Players.LocalPlayer.Backpack)
            basketball.Name = "Basketball " .. i
            clickDetector.Parent = basketball
        end
        print("Multiplicando basketball até 5 tools")
    end
})

local Tab3 = Window:MakeTab({
    Name = "🤣TROLL🤣",
    Icon = "rbxassetid://111501435575860",
    PremiumOnly = false
})

Tab3:AddButton({
    Name = "🥵FLING RED BLACK🥵",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/kiwi541/Mr-red-Black-V4/refs/heads/main/README.md'))()
    end
})

Tab3:AddButton({
    Name = "🤑PEGAR SOFÁ🤑",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(-82, 19, -130)
            print("Teletransportado para as coordenadas: X: -82, Y: 19, Z: -130")
        else
            print("Não foi possível teletransportar.")
        end
    end
})

local Tab4 = Window:MakeTab({
    Name = "😈TROLL VERSION V3😈",
    Icon = "rbxassetid://118477128531489",
    PremiumOnly = false
})

local Tab5 = Window:MakeTab({
    Name = "💀 EXIBIÇÕES/REJOIN💀",
    Icon = "rbxassetid://88858899538480",
    PremiumOnly = false
})

Tab5:AddButton({
    Name = "⚠️REJOIN⚠️",
    Callback = function()
        game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
    end
})

Tab5:AddButton({
    Name = "🌐COORDENADAS🌐",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            local pos = player.Character.HumanoidRootPart.Position
            setclipboard(string.format("X: %d, Y: %d, Z: %d", pos.X, pos.Y, pos.Z))
            print("Coordenadas copiadas para a área de transferência: ", pos)
        else
            print("Não foi possível obter as coordenadas.")
        end
    end
})

local showModels = true

Tab5:AddButton({
    Name = "🏠Mostrar Modelos🏠",
    Callback = function()
        showModels = not showModels
        if showModels then
            for _, model in pairs(workspace:GetChildren()) do
                if model:IsA("Model") then
                    print("Modelo: " .. model.Name .. " - Criador: " .. tostring(model.Creator))
                end
            end
        else
            print("Exibição de modelos desligada")
        end
    end
})

local Tab6 = Window:MakeTab({
    Name = "🧠CORPO🧠",
    Icon = "rbxassetid://83307165845406",
    PremiumOnly = false
})

local spinning = false

Tab6:AddButton({
    Name = "🌀Ativar Spin🌀",
    Callback = function()
        spinning = true
        while spinning do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(0, math.rad(10), 0)
            wait(0.1)
        end
        print("Spin ativado")
    end
})

Tab6:AddButton({
    Name = "💣Desativar Spin💣",
    Callback = function()
        spinning = false
        print("Spin desativado")
    end
})

local speed = 16
local jumpPower = 50

Tab6:AddTextbox({
    Name = "Velocidade",
    Default = tostring(speed),
    TextDisappear = false,
    Callback = function(text)
        local newSpeed = tonumber(text)
        if newSpeed then
            speed = newSpeed
            game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = speed
            print("Velocidade alterada para: " .. speed)
        else
            print("Por favor, insira um valor numérico válido para a velocidade.")
        end
    end
})

-- Botão Anti Sit
Tab6:AddButton({
    Name = "🪑ANTI SIT🪑",
    Callback = function()
        local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid.Sit = false
            humanoid.Changed:Connect(function(property)
                if property == "Sit" then
                    humanoid.Sit = false
                end
            end)
            print("Anti Sit ativado")
        end
    end
})

-- Botão para voltar a conseguir sentar
Tab6:AddButton({
    Name = "🪑VOLTAR A CONSEGUIR SENTAR🪑",
    Callback = function()
        local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid.Changed:Connect(function() end) -- Para remover o bloqueio de sentar
            print("Agora você pode sentar novamente")
        end
    end
})

Tab6:AddTextbox({
    Name = "Pulo",
    Default = tostring(jumpPower),
    TextDisappear = false,
    Callback = function(text)
        local newJumpPower = tonumber(text)
        if newJumpPower then
            jumpPower = newJumpPower
            game.Players.LocalPlayer.Character.Humanoid.JumpPower = jumpPower
            print("Pulo alterado para: " .. jumpPower)
        else
            print("Por favor, insira um valor numérico válido para o pulo.")
        end
    end
})

function equipAllItems()
    local character = game.Players.LocalPlayer.Character
    if character and character:FindFirstChildOfClass("Humanoid") then
        local humanoid = character:FindFirstChildOfClass("Humanoid")
        for i, tool in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
            if tool:IsA("Tool") then
                humanoid:EquipTool(tool)
                print("Item equipado: " .. tool.Name)
            end
        end
    else
        print("Personagem não encontrado ou não possui um Humanoid.")
    end
end

local Tab7 = Window:MakeTab({
    Name = "🤳TIK TOK🤳",
    Icon = "rbxassetid://133426623974922",
    PremiumOnly = false
})

Tab7:AddButton({
    Name = "👨‍💻TIK TOK DO MR RED BLACK👨‍💻",
    Callback = function()
        setclipboard("THE_MR_RED_BLACK_OFC")
    end
})

Tab7:AddButton({
    Name = "🤪POLICE BROOKHAVEN OFC🤪",
    Callback = function()
        setclipboard("policebrookhavenofficial")
    end
})

Tab7:AddButton({
    Name = "👨‍💻MR POLICE👨‍💻",
    Callback = function()
        setclipboard("policebrookhaven99")
    end
})

local Tab8 = Window:MakeTab({
    Name = "👨‍💻OWNER SCRIPT👨‍💻",
    Icon = "rbxassetid://108619014641303",
    PremiumOnly = false
})

Tab8:AddLabel("🎩THE MR RED BLACK OWNER🎩")
Tab8:AddLabel("💀MOLENGA COM CASPA💀")
Tab8:AddLabel("🥵MR POLICE🥵")
Tab8:AddLabel("👨‍🔬SR NESCAU👨‍🔬")
Tab8:AddLabel("👨‍💻FRAGIOTA👨‍💻")
Tab8:AddLabel("🤖BING AI🤖")

local Tab9 = Window:MakeTab({
    Name = "⚙️CONFIGURAÇÕES⚙️",
    Icon = "rbxassetid://79994606808372",
    PremiumOnly = false
})

local TabChat = Window:MakeTab({
    Name = "💬CHAT💬",
    Icon = "rbxassetid://83068331479571",
    PremiumOnly = false
})

TabChat:AddButton({
    Name = "💬CHAT BY PASS💬",
    Callback = function()
        -- Executa o script fornecido
        loadstring(game:HttpGet('https://raw.githubusercontent.com/Gazer-Ha/bruh/refs/heads/main/ImBadd1'))()
        print("Script do tutorial executado")
    end
})

TabChat:AddButton({
    Name = "💬PLACA GIGANTE 1💬",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(-238, 88, -549)
            print("Teletransportado para as coordenadas: X: -238, Y: 88, Z: -549")
        else
            print("Não foi possível teletransportar.")
        end
    end
})

TabChat:AddButton({
    Name = "💬PLACA GIGANTE 2💬",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(443, 63, 513)
            print("Teletransportado para as coordenadas: X: 443, Y: 63, Z: 513")
        else
            print("Não foi possível teletransportar.")
        end
    end
})

TabChat:AddButton({
    Name = "💬PLACA GIGANTE 3💬",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(-633, 25, 361)
            print("Teletransportado para as coordenadas: X: -633, Y: 25, Z: 361")
        else
            print("Não foi possível teletransportar.")
        end
    end
})

local Tab = Window:MakeTab({
    Name = "👮‍♂️PRISON LIFE HUB👮‍♂️",
    Icon = "rbxassetid://74896161958894",
    PremiumOnly = false
})

local Tab = Window:MakeTab({
    Name = "🤫MURDER MYSTERY HUB🤫",
    Icon = "rbxassetid://126420106112541",
    PremiumOnly = false
})
