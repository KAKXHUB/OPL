local DiscordLib =
    loadstring(game:HttpGet "https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/discord")()

local win = DiscordLib:Window("KAK HUB ")

local serv = win:Server("One Piece Legendary", "")

local drops = serv:Channel("Players")

players = {}

for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
end

local drop =
    drops:Dropdown(
    "players",
    players,
    function(bool)
        Select = bool
    end
)

drops:Button(
    "Teleport",
    function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select].Character.HumanoidRootPart.CFrame
    end
)

drops:Toggle(
    "Auto Teleport",
    false,
    function(bool)
SpamTeleport1g = bool
    end
)

spawn(function()
while wait() do
if SpamTeleport1g then
pcall(function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select].Character.HumanoidRootPart.CFrame * CFrame.new(0,30,0)
end)
end
end
end)

drops:Toggle(
    "Bring Player",
    false,
    function(bool)
SpamTeleport2g = bool
    end
)

spawn(function()
while wait() do
if SpamTeleport2g then
pcall(function()
game.Players[Select].Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-3)
end)
end
end
end)

local Missions = serv:Channel("Mission")

NPC = {}

for i,v in pairs(game:GetService("Workspace").Merchants:GetChildren()) do
   table.insert(NPC,v.Name)
end

local drop =
    Missions:Dropdown(
    "NPC",
    NPC,
    function(bool)
        Select = bool
    end
)

Missions:Button(
    "Teleport",
    function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Merchants[Select].HumanoidRootPart.CFrame
    end
)

Missions:Button(
    "TP TO The Expert",
    function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Merchants.ExpertiseMerchant.HumanoidRootPart.CFrame
    end
)

Missions:Toggle(
    "Auto get Package",
    false,
    function(bool)
SpamTeleport1g = bool
    end
)

spawn(function()
while wait() do
if SpamTeleport1g then
pcall(function()
workspace.Merchants.QuestFishMerchant.Clickable.Retum:FireServer()
end)
end
end
end)

local FarmBeri = serv:Channel("FarmBeri")

FarmBeri:Button(
    "TP Boss Sniper",
    function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1099.3090820312, 278, 1703.5080566406)
    end
)

FarmBeri:Button(
    "Kill Boss Sniper",
    function()
        game:GetService("Workspace").Enemies["Lv8000 Gunner Captain"].Humanoid.Health = 0
        game:GetService("Workspace").Enemies["Lv500 Bucky"].Humanoid.Health = 0
        game:GetService("Workspace").Enemies["Lv360 Bruno"].Humanoid.Health = 0
        game:GetService("Workspace").Enemies["Lv440 Buster"].Humanoid.Health = 0
    end
)

FarmBeri:Toggle(
    "Auto Kill Boss",
    false,
    function(bool)
_G.Farm = bool;
while _G.Farm do wait()
        game:GetService("Workspace").Enemies["Lv8000 Gunner Captain"].Humanoid.Health = 0
        game:GetService("Workspace").Enemies["Lv500 Bucky"].Humanoid.Health = 0
        game:GetService("Workspace").Enemies["Lv360 Bruno"].Humanoid.Health = 0
        game:GetService("Workspace").Enemies["Lv440 Buster"].Humanoid.Health = 0
        wait(.1)
        end
    end
)

