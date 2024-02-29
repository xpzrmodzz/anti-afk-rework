-- Supprimer les anciens GUI s'ils existent
local existingGui = game.CoreGui:FindFirstChild("AntiAFKGui")
if existingGui then
    existingGui:Destroy()
end

-- Variable pour contrôler la visibilité du GUI
getgenv().visualizer = false -- Changez cette valeur en true pour rendre le GUI visible

-- Fonction pour mettre à jour la visibilité du GUI
local function updateVisibility()
    ba.Enabled = getgenv().visualizer
end

-- Fonction pour créer le GUI
local function createGui()
    -- Créer l'interface utilisateur
    ba = Instance.new("ScreenGui")
    ba.Parent = game.CoreGui
    ba.Enabled = true -- Par défaut, le GUI est actif
    ba.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
    
    ca = Instance.new("TextLabel")
    ca.Parent = ba
    ca.Active = true
    ca.BackgroundColor3 = Color3.new(0, 0, 0)
    ca.Draggable = true
    ca.Position = UDim2.new(0.698610067, 0, 0.098096624, 0)
    ca.Size = UDim2.new(0, 370, 0, 52)
    ca.Font = Enum.Font.SourceSansSemibold
    ca.Text = "Anti AFK Script"
    ca.TextColor3 = Color3.new(255, 255, 255)
    ca.TextSize = 22

    da = Instance.new("Frame")
    da.Parent = ca
    da.BackgroundColor3 = Color3.new(0, 0, 0)
    da.Position = UDim2.new(0, 0, 1.0192306, 0)
    da.Size = UDim2.new(0, 370, 0, 107)

    _b = Instance.new("TextLabel")
    _b.Parent = da
    _b.BackgroundColor3 = Color3.new(0, 0, 0)
    _b.Position = UDim2.new(0, 0, 0.800455689, 0)
    _b.Size = UDim2.new(0, 370, 0, 21)
    _b.Font = Enum.Font.Arial
    _b.Text = "by C.N"
    _b.TextColor3 = Color3.new(255, 255, 255)
    _b.TextSize = 20

    ab = Instance.new("TextLabel")
    ab.Parent = da
    ab.BackgroundColor3 = Color3.new(0, 0, 0)
    ab.Position = UDim2.new(0, 0, 0.158377, 0)
    ab.Size = UDim2.new(0, 370, 0, 44)
    ab.Font = Enum.Font.ArialBold
    ab.Text = "wait C.N best scripter?"
    ab.TextColor3 = Color3.new(255, 255, 255)
    ab.TextSize = 20

    -- Mettre à jour la visibilité initiale
    updateVisibility()
end

-- Appeler la fonction pour créer le GUI
createGui()

-- Capturer le service VirtualUser et connecter la fonction d'inactivité
local bb = game:GetService('VirtualUser')
game:GetService('Players').LocalPlayer.Idled:Connect(function()
    -- Capturer le contrôleur et cliquer sur un bouton
    bb:CaptureController()
    bb:ClickButton2(Vector2.new())

    -- Mettre à jour le texte après une période d'inactivité
    ab.Text = "LOL you sus bro"
    wait(2)
    ab.Text = "C.N ON TOP"
end)
