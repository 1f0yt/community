--workspace.FallenPartsDestroyHeight = -900000000000000000000
--[[
                                      __                          __  
                                    |\ | /  \ \  /  /\     |__| |  | |__) 
                                    | \| \__/  \/  /~~\    |  | \__/ |__) 
                                      
                                            -- NOVA HUB SOURCE --
                                           NOVA HUB COPYRIGHT CLAIM
    Please read this disclaimer carefully before using NOVA HUB,
    operated by us. The content displayed on the website is the intellectual property of the NOVA HUB Community. You may not reuse, republish, or reprint such content without our permission.
    All information posted is merely for educational and informational purposes. It is not intended
    as a substitute for professional advice. Should you decide to act upon any information on this website, you do so at your own risk.
    While the information on this website has been verified to the best of our abilities, we cannot guarantee that there are no mistakes or errors.
    We reserve the right to change this policy at any given time, of which you will be promptly
    updated. If you want to make sure that you are up to date with the latest changes, we advise
    you to frequently visit this page.
    
    - Dev Notes
    Some of our code are not made by us because sometimes we are lazy, but most of them are made by us.
    If you need help with your script contact us: len#7343
    Nova Hub will continue to update and will be open source every update.
    You must be a developer to understand all of this, if you do not understand contact us: len#7343
    - https://discord.gg/kWvgRuruhn, Our Discord

    - NOVA HUB© 2022

    - Hub by len#7343, Mouad#4819, TheSamuel#9008, probly#5848, hailhydra_12#0915, Demogorgon#7727


    btw this was beautified so codes can be easier to look at

    codes that are not mine should have notes above it now
]]










--[[
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
    !!PLEASE READ ABOVE BEFORE CHECKING THE CODE!!
]]






































































































-- not my notification lib
local t = tick()
local NotificationHolder =
    loadstring(game:HttpGet("https://raw.githubusercontent.com/BocusLuke/UI/main/STX/Module.Lua"))()
local Notification = loadstring(game:HttpGet("https://raw.githubusercontent.com/BocusLuke/UI/main/STX/Client.Lua"))()
local skyids = {
    "rbxassetid://4922990751"
}
for i, v in pairs(getgc(true)) do
    if typeof(v) == "table" and rawget(v, "getIsBodyMoverCreatedByGame") then
        v.getIsBodyMoverCreatedByGame = function(gg)
            return true
        end
    end
    if typeof(v) == "table" and rawget(v, "kick") then
        v.kick = function()
            return wait(9e9)
        end
    end
    if typeof(v) == "table" and rawget(v, "randomDelayKick") then
        v.randomDelayKick = function()
            return wait(9e9)
        end
    end
    if typeof(v) == "table" and rawget(v, "connectCharacter") then
        v.connectCharacter = function(gg)
            return wait(9e9)
        end
    end
    if typeof(v) == "table" and rawget(v, "Remote") then
        v.Remote.Name = v.Name -- simple remote naming (tbh i could have used another method)
        -- i sticked to this method because i used it on the first and forgor to replace it :Skull:
        -- contact me for better method
    end
end
local oldnamecall -- anti kick because cw kicks u after u rename the remotes
oldnamecall =
    hookmetamethod(
    game,
    "__namecall",
    function(self, ...)
        local args = {...}
        local method = getnamecallmethod()

        if (method == "Kick" or method == "kick") and self == game.Players.LocalPlayer then
            return
        end

        return oldnamecall(self, unpack(args))
    end
)
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local flyKeyDown
local flyKeyUp
local events = game:GetService("ReplicatedStorage").Communication.Events
local functions = game:GetService("ReplicatedStorage").Communication.Functions
for i = 1, 25 do -- inf jump bypass
    events.StartFastRespawn:FireServer()
    functions.CompleteFastRespawn:FireServer()
    wait()
end

-- anim table & tables
local weapon_anims = {}
local killsays = { -- found by cheese
    "你是垃圾，菜鸟可以做得更好。",
    "imagine dying 😅😅😅 LLLL",
    "Oops i forgot you were there, oh wait you actually dont exist anyways.",
    "ez ez you got clapped by a low level haha!",
    "🤓: you cant just exploit in here!!111!!111 its illegal!!!!",
    "why are you dying to me bro fr fr",
    "clapped by nova hub user :skull:",
    "bro got clapped lol",
    "'🤓: imagine being fatherless'  where are yours then go check 😁😁😁",
    "sorry did my kill aura hit you? if so then youre trash 😅",
    "bro got skill issues 😅😅😅",
    "bozo cant even beat me",
    "fr fr nova on top",
    "What's up 'Hackle cheatle' here guys, I have been arresting due to multiple crimes including cheating.",
    "wdym touch grass i have one of those on my feet",
    "fortnite 19$ gift card who wants it!!!??",
    ".gg/gswH7FGxyb <-- join for cool scripts (!!! real no fake !!!)",
    "ez bozo",
    "your dad never came back from the milk store for a reason",
    "damn bro did your mother drop you when youre born",
    "Who are you talking to? a kill say bot? 😅",
    "damn bro you really need a therapist 😅😅",
    "🤓: stop hacking!!!! its against the rules!!!",
    "wenomechainsama tumajarbisaun",
    "you should go back to kindergarden bro 😂",
    "im just better than you!!!!!",
    "nova hub better than you smh smh smh 😅"
}
for i, v in pairs(game:GetService("ReplicatedStorage").Shared.Assets.Melee:GetDescendants()) do
    if v:IsA("Animation") then
        if v.Name:find("Slash") or v.Name:find("Swing") then
            table.insert(weapon_anims, v.AnimationId)
        end
    end
end
-- inf yield fly stuff ignore
FLYING = false
iyflyspeed = 1
vehicleflyspeed = 1
-- inf fly i modified it a bit
function sFLY(vfly, ragdoll, platform)
    if flyKeyDown or flyKeyUp then
        flyKeyDown:Disconnect()
        flyKeyUp:Disconnect()
    end
    local T = LocalPlayer.Character.HumanoidRootPart
    local CONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
    local lCONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
    local SPEED = 0

    local function FLY()
        FLYING = true
        local BG = Instance.new("BodyGyro")
        local BV = Instance.new("BodyVelocity")
        BG.P = 9e4
        BG.Parent = T
        BV.Parent = T
        BG.maxTorque = Vector3.new(9e9, 9e9, 9e9)
        BG.cframe = T.CFrame
        BV.velocity = Vector3.new(0, 0, 0)
        BV.maxForce = Vector3.new(9e9, 9e9, 9e9)
        task.spawn(
            function()
                repeat
                    wait()
                    if LocalPlayer.Character.Humanoid:FindFirstChild("RagdollRemoteEvent") ~= nil then
                        if ragdoll then
                            LocalPlayer.Character.Humanoid:FindFirstChild("RagdollRemoteEvent"):FireServer(true)
                        end
                    end
                    for i, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                        if v:IsA("BallSocketConstraint") then
                            v.TwistLowerAngle = 0
                            v.TwistUpperAngle = 0
                            v.UpperAngle = 0
                            v.Radius = 0
                            if v.Parent.Name == "Right Arm" or v.Parent.Name == "Left Arm" then
                                v.TwistLowerAngle = 0
                                v.TwistUpperAngle = 0
                                v.UpperAngle = 90
                                v.Radius = 90
                            end
                        end
                    end
                    if not vfly and LocalPlayer.Character:FindFirstChildOfClass("Humanoid") then
                        LocalPlayer.Character:FindFirstChildOfClass("Humanoid").PlatformStand = platform
                    end
                    if CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0 or CONTROL.Q + CONTROL.E ~= 0 then
                        SPEED = 50
                    elseif
                        not (CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0 or CONTROL.Q + CONTROL.E ~= 0) and
                            SPEED ~= 0
                     then
                        SPEED = 0
                    end
                    if (CONTROL.L + CONTROL.R) ~= 0 or (CONTROL.F + CONTROL.B) ~= 0 or (CONTROL.Q + CONTROL.E) ~= 0 then
                        BV.velocity =
                            ((workspace.CurrentCamera.CoordinateFrame.lookVector * (CONTROL.F + CONTROL.B)) +
                            ((workspace.CurrentCamera.CoordinateFrame *
                                CFrame.new(
                                    CONTROL.L + CONTROL.R,
                                    (CONTROL.F + CONTROL.B + CONTROL.Q + CONTROL.E) * 0.2,
                                    0
                                ).p) -
                                workspace.CurrentCamera.CoordinateFrame.p)) *
                            SPEED
                        lCONTROL = {F = CONTROL.F, B = CONTROL.B, L = CONTROL.L, R = CONTROL.R}
                    elseif
                        (CONTROL.L + CONTROL.R) == 0 and (CONTROL.F + CONTROL.B) == 0 and (CONTROL.Q + CONTROL.E) == 0 and
                            SPEED ~= 0
                     then
                        BV.velocity =
                            ((workspace.CurrentCamera.CoordinateFrame.lookVector * (lCONTROL.F + lCONTROL.B)) +
                            ((workspace.CurrentCamera.CoordinateFrame *
                                CFrame.new(
                                    lCONTROL.L + lCONTROL.R,
                                    (lCONTROL.F + lCONTROL.B + CONTROL.Q + CONTROL.E) * 0.2,
                                    0
                                ).p) -
                                workspace.CurrentCamera.CoordinateFrame.p)) *
                            SPEED
                    else
                        BV.velocity = Vector3.new(0, 0, 0)
                    end
                    BG.cframe = workspace.CurrentCamera.CoordinateFrame
                until not FLYING
                CONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
                lCONTROL = {F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0}
                SPEED = 0
                BG:Destroy()
                BV:Destroy()
                if LocalPlayer.Character:FindFirstChildOfClass("Humanoid") then
                    LocalPlayer.Character:FindFirstChildOfClass("Humanoid").PlatformStand = false
                end
            end
        )
    end
    flyKeyDown =
        Mouse.KeyDown:Connect(
        function(KEY)
            if KEY:lower() == "w" then
                CONTROL.F = (vfly and vehicleflyspeed or iyflyspeed)
            elseif KEY:lower() == "s" then
                CONTROL.B = -(vfly and vehicleflyspeed or iyflyspeed)
            elseif KEY:lower() == "a" then
                CONTROL.L = -(vfly and vehicleflyspeed or iyflyspeed)
            elseif KEY:lower() == "d" then
                CONTROL.R = (vfly and vehicleflyspeed or iyflyspeed)
            elseif QEfly and KEY:lower() == "e" then
                CONTROL.Q = (vfly and vehicleflyspeed or iyflyspeed) * 2
            elseif QEfly and KEY:lower() == "q" then
                CONTROL.E = -(vfly and vehicleflyspeed or iyflyspeed) * 2
            end
            pcall(
                function()
                    workspace.CurrentCamera.CameraType = Enum.CameraType.Track
                end
            )
        end
    )
    flyKeyUp =
        Mouse.KeyUp:Connect(
        function(KEY)
            if KEY:lower() == "w" then
                CONTROL.F = 0
            elseif KEY:lower() == "s" then
                CONTROL.B = 0
            elseif KEY:lower() == "a" then
                CONTROL.L = 0
            elseif KEY:lower() == "d" then
                CONTROL.R = 0
            elseif KEY:lower() == "e" then
                CONTROL.Q = 0
            elseif KEY:lower() == "q" then
                CONTROL.E = 0
            end
        end
    )
    FLY()
end -- skidded from inf yield cuz im too lazy again also the random fly i found sometimes anti cheat u

invisfling = function() -- changed to loadstring because it was so messy
    loadstring(game:HttpGet'https://raw.githubusercontent.com/SussyImposterRed/Scripts/main/NoIdentityFling')()
end
local library = loadstring(game:HttpGet("https://pastebin.com/raw/xB6h23QX"))() -- not my lib

menu = library.new('<font color="rgb(38, 55, 189)">nova</font>.xyz', "novasaves\\")
local tabs = {
    menu.new_tab("http://www.roblox.com/asset/?id=7300477598"),
    menu.new_tab("http://www.roblox.com/asset/?id=7300535052"),
    menu.new_tab("http://www.roblox.com/asset/?id=7300480952"),
    menu.new_tab("http://www.roblox.com/asset/?id=7300486042"),
    menu.new_tab("http://www.roblox.com/asset/?id=7300489566")
}

function parry()
    game:GetService("ReplicatedStorage").Communication.Events.Parry:FireServer()
end

function getChance(v) -- from cheese
    local chance = math.floor(Random.new().NextNumber(Random.new(),0,1) * 100) / 100
    return chance <= math.floor(v) / 100
end
-- Not my config
do
    local _menu = tabs[5].new_section("menu") -->> Simple config system

    local all_cfgs

    local configs = _menu.new_sector("configs")
    local text
    local list =
        configs.element(
        "Scroll",
        "config list",
        {options = {"none"}},
        function(State)
            text:set_value({Text = State.Scroll})
        end
    )
    text = configs.element("TextBox", "config name")
    configs.element(
        "Button",
        "save",
        nil,
        function()
            if menu.values[5].menu.configs["config name"].Text ~= "none" then
                menu.save_cfg(menu.values[5].menu.configs["config name"].Text)
            end
        end
    )
    configs.element(
        "Button",
        "load",
        nil,
        function()
            if menu.values[5].menu.configs["config name"].Text ~= "none" then
                menu.load_cfg(menu.values[5].menu.configs["config name"].Text)
            end
        end
    )
    configs.element(
        "Button",
        "rejoin",
        nil,
        function()
            game:GetService "TeleportService":TeleportToPlaceInstance(game.PlaceId, game.JobId, LocalPlayer)
        end
    )
    configs.element("Toggle", "kill say")
    configs.element("Button","clear local appearance", nil, function()
        LocalPlayer:ClearCharacterAppearance()
    end)
    configs.element("Button","load chat bypass", nil, function()
        local newT = tick()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/SussyImposterRed/Scripts/main/chatbypass'))()
        Notification:Notify(
            {Title = "Nofitication", Description = "Loaded Chat Bypass from github in " .. tick() - newT .. "s (seconds)"},
            {OutlineColor = Color3.fromRGB(80, 80, 80), Time = 5, Type = "default"}
        )
    end)
    configs.element("Button","unload chat bypass", nil, function()
        game:GetService("TextChatService").OnIncomingMessage = function(L)end
    end)
    for i,v in pairs(getgc(true)) do
        if typeof(v) == 'table' then
            if rawget(v,'removeKillFeedIdx') then
                oldrender = v.render
                v.render = function(gg)
                    if gg.props then
                        local whoDied = gg.props.killfeedItemInfo.playerThatDied
                        local whoKilled = gg.props.killfeedItemInfo.playerThatKilled
                        if (menu.values[5].menu.configs["kill say"].Toggle and tostring(whoKilled) == LocalPlayer.Name and tostring(whoDied) ~= LocalPlayer.Name) then
                            game:GetService("TextChatService").TextChannels.RBXGeneral:SendAsync(
                                tostring(whoDied)..", "..killsays[math.random(1, #killsays)]
                            )
                        end
                    end
                    return oldrender(gg)
                end
            end
        end
    end

    local function update_cfgs()
        all_cfgs = listfiles("novasaves\\")
        for _, cfg in next, all_cfgs do
            all_cfgs[_] = string.gsub(string.gsub(cfg, "novasaves\\", ""), ".txt", "")
            list:add_value(all_cfgs[_])
        end
    end
    update_cfgs()

    task.spawn(
        function()
            while true do
                wait(1)
                update_cfgs()
            end
        end
    )
end

do
    local rage = tabs[1].new_section("rage")
    local combat = rage.new_sector("combat")
    local Autos = rage.new_sector("Autos", "Right")
    local Misc = rage.new_sector("Misc", "Right")
    local Spins = rage.new_sector("Spins","Right")
    local parrying = false
    local PTBL = {}
    for i,v in pairs(Players:GetPlayers()) do
        table.insert(PTBL,v.Name)
    end
    Misc.element("Toggle", "BHop")
    Autos.element("Toggle", "Auto Equip")
    Autos.element("Toggle", "Auto Revive")
    Autos.element("Toggle", "Fast Respawn")
    combat.element("Toggle", "Kill Aura")
    combat.element("Slider", "Kill Aura Distance", {default = {min = 0, max = 12, default = 12}})
    combat.element("Toggle", "Custom Kill Aura Distance")
    combat.element("Slider", "Custom Distance", {default = {min = 0, max = 1000, default = 600}})
    combat.element("Toggle", "Whitelist Friends")
    combat.element("Combo", "Whitelist Players",{options = PTBL})
    combat.element("Toggle", "Teleport Behind (for kill aura)")
    combat.element("Slider", "Teleport Distance", {default = {min = 0, max = 5, default = 5}})
    combat.element("Toggle", "Stomp Aura")
    combat.element("Slider", "Stomp Aura Distance", {default = {min = 0, max = 25, default = 25}})
    combat.element("Toggle", "Custom Stomp Aura Distance")
    combat.element("Slider", "Custom Stomp Distance", {default = {min = 0, max = 1000, default = 600}})
    Spins.element("Toggle", "Spin")
    Spins.element("Slider", "Spin Power", {default = {min = 0, max = 50, default = 50}})
    Autos.element("Toggle", "Auto Parry")
    Autos.element("Slider", "Auto Parry Distance", {default = {min = 0, max = 25, default = 10}})
    Autos.element("Slider", "Auto Parry Chance", {default = {min = 0, max = 100, default = 100}})
    Autos.element("Toggle", "Anti Parry")
    Autos.element("Button", "Fix Anti Parry (if u cant damage)",nil,function()
        parrying = false
    end)
    -- DEVFORUM GETCLOSEST (i love this one, i use it almost on all of my scripts)
    local function GetClosest(Distance)
        local Character = LocalPlayer.Character
        local HumanoidRootPart = Character and Character:FindFirstChild("HumanoidRootPart")
        if not (Character or HumanoidRootPart) then
            return
        end

        local TargetDistance = Distance
        local Target

        for i, v in ipairs(Players:GetPlayers()) do
            if (v ~= LocalPlayer and v.Character and v.Character:FindFirstChild("HumanoidRootPart") and not table.find(menu.values[1].rage.combat["Whitelist Players"].Combo,v.Name) and not v:IsFriendsWith(LocalPlayer.UserId)) then
                local TargetHRP = v.Character.HumanoidRootPart
                local mag = (HumanoidRootPart.Position - TargetHRP.Position).magnitude
                if mag < TargetDistance then
                    TargetDistance = mag
                    Target = v
                end
            end
        end

        return Target
    end
    task.spawn(function()
        function updatePlrList()
            local NewPTBL = {}
            for i,v in pairs(Players:GetPlayers()) do
                table.insert(NewPTBL,v.Name)
            end
            
            if #NewPTBL ~= 1 then
                menu.values[1].rage.combat["Whitelist Players"].Combo:set_value(NewPTBL,false)
            end
        end
        
        while true do
            pcall(updatePlrList)
            wait(1)
        end
    end)
    task.spawn(function()
        local Sounds = {
            "1",
            "2",
            "3",
            "4",
            "5",
            "6",
            "7",
            "8",
            "9",
            "10"
        }
        
        workspace.PlayerCharacters.DescendantAdded:Connect(function(e)
            if (e:IsA("Sound") and e.Parent.Name == "Hitbox") then
                task.spawn(function()
                    for i,v in pairs(Sounds) do
                        if e.Parent.Parent.Parent.Parent.Name == LocalPlayer.Name then
                            if menu.values[1].rage.combat["Kill Aura"].Toggle then
                                if e.Name == v then
                                    spawn(function()
                                        print('destroying')
                                        e:Destroy()
                                    end)
                                end
                            end
                            break
                        end
                        if e.Name == v and e.Parent.Parent.Parent.Parent.Name ~= LocalPlayer.Name then
                            local Character = LocalPlayer.Character
                            if (Character and Character:FindFirstChild("HumanoidRootPart")) then
                                local distance = (Character.HumanoidRootPart.Position-e.Parent.Position).Magnitude
                                if menu.values[1].rage.Autos["Auto Parry Chance"].Slider >= 90 then
                                    if distance <= menu.values[1].rage.Autos["Auto Parry Distance"].Slider then 
                                        parry()
                                    end
                                elseif getChance(menu.values[1].rage.Autos["Auto Parry Chance"].Slider) then
                                    if distance <= menu.values[1].rage.Autos["Auto Parry Distance"].Slider then 
                                        parry()
                                    end
                                end
                            end
                            break
                        end
                    end
                end)
            end
            pcall(function()
                if (e:IsA("Sound") and e.SoundId == "rbxassetid://211059855") then
                    if e.Parent.Parent.Name ~= LocalPlayer.Name then
                        local p = (e.Parent and e.Parent)
                        if (LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")) then
                            local distance = (LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude
                            if (distance <= 10 and menu.values[1].rage.Autos["Anti Parry"].Toggle) then
                                parrying = true
                                task.spawn(function()
                                    while p.Transparency ~= 1 do
                                        task.wait()
                                    end
                                    task.wait(.1)
                                    parrying = false
                                end)
                            end
                        end
                    end
                end
            end)
        end)
    end)
    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        if menu.values[1].rage.combat["Kill Aura"].Toggle then
                            local Closest
                            if menu.values[1].rage.combat["Custom Kill Aura Distance"].Toggle then
                                Closest = GetClosest(menu.values[1].rage.combat["Custom Distance"].Slider)
                            else
                                Closest = GetClosest(menu.values[1].rage.combat["Kill Aura Distance"].Slider)
                            end
                            if Closest then
                                if Closest.Character:FindFirstChild("Humanoid").Health == 0 then
                                else
                                    if menu.values[1].rage.combat["Teleport Behind (for kill aura)"].Toggle then
                                        if not menu.values[1].rage.combat["Custom Kill Aura Distance"].Toggle then
                                            LocalPlayer.Character.HumanoidRootPart.CFrame =
                                                Closest.Character.HumanoidRootPart.CFrame *
                                                CFrame.new(0, 0, menu.values[1].rage.combat["Teleport Distance"].Slider)
                                        end
                                    end
                                    local Weapon
                                    for i, v in pairs(LocalPlayer.Character:GetChildren()) do
                                        if v:IsA("Tool") then
                                            if v:FindFirstChild("Hitboxes") ~= nil then
                                                Weapon = v
                                            end
                                        end
                                    end
                                    if not Weapon then
                                    else
                                        if menu.values[1].rage.combat["Custom Kill Aura Distance"].Toggle then
                                            for i, v in pairs(Weapon:GetDescendants()) do
                                                if v:IsA "BasePart" then
                                                    v.CFrame = Closest.Character.HumanoidRootPart.CFrame
                                                    v.Velocity = Vector3.new(100000, 100000, 100000)
                                                    v.CanCollide = false
                                                    v.Massless = true
                                                    --v.Anchored = true
                                                    if v:FindFirstChild "BodyVelocity" == nil then
                                                        local boopyve = Instance.new("BodyVelocity")
                                                        boopyve.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
                                                        boopyve.P = math.huge
                                                        boopyve.Velocity = Vector3.new(100000, 100000, 100000)
                                                        boopyve.Parent = v
                                                    end
                                                end
                                                if v:IsA("Motor6D") then
                                                    if v.Parent.Name == "Motor6Ds" then
                                                        v:Destroy()
                                                    end
                                                end
                                            end
                                        end

                                        local rayOrigin = LocalPlayer.Character.HumanoidRootPart.Position
                                        local rayDirection = Vector3.new(0, 0, 5)
                                        local raycastParams = RaycastParams.new()
                                        raycastParams.IgnoreWater = true
                                        raycastParams.FilterType = Enum.RaycastFilterType.Blacklist
                                        local raycastResult = workspace:Raycast(rayOrigin, rayDirection, raycastParams)
                                        local args1 = {
                                            [1] = Weapon,
                                            [2] = math.random(1, 4)
                                        }

                                        events.MeleeSwing:FireServer(unpack(args1))
                                        task.wait(0.2)

                                        local args = {
                                            [1] = Weapon,
                                            [2] = Closest.Character.Head,
                                            [3] = Weapon.Hitboxes.Hitbox,
                                            [4] = Closest.Character.Head.Position,
                                            [5] = Closest.Character.Head.CFrame:ToObjectSpace(
                                                CFrame.new(Closest.Character.Head.Position)
                                            ),
                                            [6] = raycastResult
                                        }
                                        if Closest.Character:FindFirstChild("SemiTransparentShield").Transparency == 1 then
                                            events.MeleeDamage:FireServer(unpack(args))

                                            events.MeleeDamage:FireServer(unpack(args))
                                        else
                                            return
                                        end
                                    end
                                end
                            elseif Closest == nil then
                                for i, v in pairs(Weapon:GetDescendants()) do
                                    if v:IsA "BasePart" then
                                        v.CFrame = LocalPlayer.Character.HumanoidRootPart.CFrame
                                        v.Velocity = Vector3.new(100000,100000,100000)
                                        v.CanCollide = false
                                    end
                                end
                            end
                        end
                    end
                )
            end
        end
    )

    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        if menu.values[1].rage.combat["Stomp Aura"].Toggle then
                            local Closest
                            if menu.values[1].rage.combat["Custom Stomp Aura Distance"].Toggle then
                                Closest = GetClosest(menu.values[1].rage.combat["Custom Stomp Distance"].Slider)
                            else
                                Closest = GetClosest(menu.values[1].rage.combat["Stomp Aura Distance"].Slider)
                            end
                            if Closest then
                                if Closest.Character:FindFirstChild("Humanoid").Health == 0 then
                                else
                                    local Weapon = LocalPlayer.Character.Stomp
                                    if not Weapon then
                                    else
                                        if Closest.Character.Humanoid.Health <= 15 then
                                            if menu.values[1].rage.combat["Custom Stomp Aura Distance"].Toggle then
                                                for i, v in pairs(Weapon:GetDescendants()) do
                                                    if v:IsA "BasePart" then
                                                        v.CFrame = Closest.Character.HumanoidRootPart.CFrame
                                                        v.Velocity = Vector3.new(100000,100000,100000)
                                                        v.CanCollide = false
                                                        v.Massless = true
                                                        --v.Anchored = true
                                                        if v:FindFirstChild "BodyVelocity" == nil then
                                                            local boopyve = Instance.new("BodyVelocity")
                                                            boopyve.MaxForce =
                                                                Vector3.new(math.huge, math.huge, math.huge)
                                                            boopyve.P = math.huge
                                                            boopyve.Velocity = Vector3.new(100000,100000,100000)
                                                            boopyve.Parent = v
                                                        end
                                                    end
                                                    if v:IsA("Motor6D") then
                                                        if v.Parent.Name == "Motor6Ds" then
                                                            v:Destroy()
                                                        end
                                                    end
                                                end
                                            end

                                            local rayOrigin = LocalPlayer.Character.HumanoidRootPart.Position
                                            local rayDirection = Vector3.new(0, 0, 5)
                                            local raycastParams = RaycastParams.new()
                                            raycastParams.IgnoreWater = true
                                            raycastParams.FilterType = Enum.RaycastFilterType.Blacklist
                                            local raycastResult =
                                                workspace:Raycast(rayOrigin, rayDirection, raycastParams)
                                            local args1 = {
                                                [1] = Weapon,
                                                [2] = math.random(1, 4)
                                            }

                                            events.MeleeSwing:FireServer(unpack(args1))
                                            task.wait(0.2)

                                            local args = {
                                                [1] = Weapon,
                                                [2] = Closest.Character.Head,
                                                [3] = Weapon.Hitboxes.RightLegHitbox,
                                                [4] = Closest.Character.Head.Position,
                                                [5] = Closest.Character.Head.CFrame:ToObjectSpace(
                                                    CFrame.new(Closest.Character.Head.Position)
                                                ),
                                                [6] = raycastResult
                                            }

                                            events.MeleeDamage:FireServer(unpack(args))

                                            events.MeleeDamage:FireServer(unpack(args))
                                        end
                                    end
                                end
                            elseif Closest == nil then
                                for i, v in pairs(Weapon:GetDescendants()) do
                                    if v:IsA "BasePart" then
                                        v.CFrame = LocalPlayer.Character.HumanoidRootPart.CFrame
                                        v.Velocity = Vector3.new(100000,100000,100000)
                                        v.CanCollide = false
                                    end
                                end
                            end
                        end
                    end
                )
            end
        end
    )

    task.spawn(
        function()
            game:GetService("RunService").RenderStepped:Connect(
                function()
                    pcall(
                        function()
                            for i, v in pairs(LocalPlayer.Backpack:GetChildren()) do
                                if v:IsA("Tool") then
                                    if v:FindFirstChild("Hitboxes") ~= nil then
                                        if menu.values[1].rage.Autos["Auto Equip"].Toggle then
                                            v.Parent = LocalPlayer.Character
                                        end
                                    end
                                end
                            end
                        end
                    )
                end
            )
        end
    )

    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        if menu.values[1].rage.Autos["Auto Revive"].Toggle then
                            if LocalPlayer.Character.Humanoid.Health <= 15 then
                                events.SelfReviveStart:FireServer()
                                events.SelfRevive:FireServer()
                            end
                        end
                    end
                )
            end
        end
    )

    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        if menu.values[1].rage.Autos["Fast Respawn"].Toggle then
                            if LocalPlayer.Character.Humanoid.Health == 0 then
                                events.StartFastRespawn:FireServer()
                                functions.CompleteFastRespawn:FireServer()
                            end
                        end
                    end
                )
            end
        end
    )

    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function() -- originally from outliers old source but i removed it and wrote a new one it kinda looks like the same but its a different one
                        if menu.values[1].rage.Spins["Spin"].Toggle then
                            if LocalPlayer.Character.HumanoidRootPart:FindFirstChild("spin") == nil then
                                local Spin = Instance.new("BodyAngularVelocity")
                                Spin.Name = "spin"
                                Spin.Parent = LocalPlayer.Character.HumanoidRootPart
                                Spin.MaxTorque = Vector3.new(0, math.huge, 0)
                                for i, v in (LocalPlayer.Character:GetChildren()) do
                                    if v:IsA("BasePart") then
                                        v.Massless = true
                                        v.Velocity = Vector3.new(0, 0, 0)
                                    end
                                end
                            else
                                if LocalPlayer.Character.HumanoidRootPart:FindFirstChild("spin") ~= nil then
                                    LocalPlayer.Character.HumanoidRootPart.spin.AngularVelocity =
                                        Vector3.new(0, menu.values[1].rage.Spins["Spin Power"].Slider, 0)
                                end
                            end
                        else
                            if LocalPlayer.Character.HumanoidRootPart:FindFirstChild("spin") ~= nil then
                                LocalPlayer.Character.HumanoidRootPart.spin:Destroy()
                            end
                        end
                    end
                )
            end
        end
    )

    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        if menu.values[1].rage.Misc["BHop"].Toggle then
                            if LocalPlayer.Character.Humanoid.FloorMaterial ~= Enum.Material.Air then
                                LocalPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
                            end
                        end
                    end
                )
            end
        end
    )

    local old
    old = hookmetamethod(game, "__namecall", function(self, ...)
        local args = {...}
        if not checkcaller() and self == events.MeleeDamage and getnamecallmethod() == "FireServer" and parrying == true then
            return
        end 
        return old(self, ...)
    end)
end

-- not my esp :Skull:

do
    local players = tabs[3].new_section("players")

    local esp = players.new_sector("ESP")
    esp.element("Toggle", "Enabled"):add_keybind()
    esp.element("Slider", "Max Distance", {default = {min = 250, max = 5000, default = 5000}})

    local Playere = players.new_sector("Player")
    Playere.element("Toggle", "Box"):add_color({Color = Color3.fromRGB(255, 255, 255)})
    Playere.element("Toggle", "Name"):add_color({Color = Color3.fromRGB(255, 255, 255)})
    Playere.element("Toggle", "Health"):add_color({Color = Color3.fromRGB(0, 255, 0)})
    Playere.element("Toggle", "Indicators"):add_color({Color = Color3.fromRGB(255, 255, 255)})
    Playere.element("Combo", "Types", {options = {"Tool", "Distance"}})

    local oof = players.new_sector("Out Of FOV", "Right")
    oof.element("Toggle", "Enabled"):add_color({Color = Color3.fromRGB(255, 255, 255)})
    oof.element("Slider", "Size", {default = {min = 10, max = 15, default = 15}})
    oof.element("Slider", "Offset", {default = {min = 100, max = 700, default = 400}})
    oof.element("Combo", "Settings", {options = {"Outline", "Blinking"}})
end

local PlayerDrawings = {}
local Settings = {
    Line = {
        Thickness = 1,
        Color = Color3.fromRGB(0, 255, 0)
    },
    Text = {
        Size = 13,
        Center = true,
        Outline = true,
        Font = Drawing.Fonts.Plex,
        Color = Color3.fromRGB(255, 255, 255)
    },
    Square = {
        Thickness = 1,
        Color = menu.values[3].players.Player["$Box"].Color,
        Filled = false
    },
    Triangle = {
        Color = Color3.fromRGB(255, 255, 255),
        Filled = true,
        Visible = false,
        Thickness = 1
    }
}

function New(Type, Outline, Name)
    local drawing = Drawing.new(Type)
    for i, v in pairs(Settings[Type]) do
        drawing[i] = v
    end
    if Outline then
        drawing.Color = Color3.new(0, 0, 0)
        drawing.Thickness = 3
    end
    return drawing
end

function Add(Player)
    if not PlayerDrawings[Player] then
        PlayerDrawings[Player] = {
            Offscreen = New("Triangle", nil, "Offscreen"),
            Name = New("Text", nil, "Name"),
            Tool = New("Text", nil, "Tool"),
            Distance = New("Text", nil, "Distance"),
            BoxOutline = New("Square", true, "BoxOutline"),
            Box = New("Square", nil, "Box"),
            HealthOutline = New("Line", true, "HealthOutline"),
            Health = New("Line", nil, "Health")
        }
    end
end

for _, Player in pairs(Players:GetPlayers()) do
    if Player ~= LocalPlayer then
        Add(Player)
    end
end
Players.PlayerAdded:Connect(Add)
Players.PlayerRemoving:Connect(
    function(Player)
        if PlayerDrawings[Player] then
            for i, v in pairs(PlayerDrawings[Player]) do
                if v then
                    v:Remove()
                end
            end

            PlayerDrawings[Player] = nil
        end
    end
)

function NOFLY()
    FLYING = false
    if flyKeyDown or flyKeyUp then
        flyKeyDown:Disconnect()
        flyKeyUp:Disconnect()
    end
    if LocalPlayer.Character:FindFirstChildOfClass("Humanoid") then
        LocalPlayer.Character:FindFirstChildOfClass("Humanoid").PlatformStand = false
    end
    LocalPlayer.Character.Humanoid.RagdollRemoteEvent:FireServer(false)
    for i = 1, 5 do
        LocalPlayer.Character.Humanoid.RagdollRemoteEvent:FireServer(false)
        wait(.1)
    end
    pcall(
        function()
            workspace.CurrentCamera.CameraType = Enum.CameraType.Custom
        end
    )
end

local Noclipping
local Clip = false
-- Inf yield noclip, I said it once that it wasnt mine so :shrug:
function NoclipLoop()
    if menu.values[4].misc2.misc["Noclip"].Toggle and Clip == false and LocalPlayer.Character ~= nil then
        for _, child in pairs(LocalPlayer.Character:GetDescendants()) do
            if child:IsA("BasePart") and child.CanCollide == true and child.Name ~= floatName then
                child.CanCollide = false
            end
        end
    end
end

do
    fonts = {
        "Legacy",
        "Arial",
        "ArialBold",
        "SourceSans",
        "SourceSansBold",
        "SourceSansSemibold",
        "SourceSansLight",
        "SourceSansItalic",
        "Bodoni",
        "Garamond",
        "Cartoon",
        "Code",
        "Highway",
        "SciFi",
        "Arcade",
        "Fantasy",
        "Antique",
        "Gotham",
        "GothamSemibold",
        "GothamBold",
        "GothamBlack",
        "AmaticSC",
        "Bangers",
        "Creepster",
        "DenkOne",
        "Fondamento",
        "FredokaOne",
        "GrenzeGotisch",
        "IndieFlower",
        "JosefinSans",
        "Jura",
        "Kalam",
        "LuckiestGuy",
        "Merriweather",
        "Michroma",
        "Nunito",
        "Oswald",
        "PatrickHand",
        "PermanentMarker",
        "Roboto",
        "RobotoCondensed",
        "RobotoMono",
        "Sarpanch",
        "SpecialElite",
        "TitilliumWeb",
        "Ubuntu"
    }
    local misc1 = tabs[4].new_section("misc")
    local misc2 = tabs[4].new_section("misc2")
    local miscsector = misc2.new_sector("misc")
    --local stuff = menu.values[4]["custom chat"].Fun
    local player = misc1.new_sector("player")
    local utility = misc1.new_sector("utility")
    miscsector.element(
        "Button",
        "No Identity fling",
        nil,
        function()
            invisfling()
        end
    )
    utility.element("Toggle", "No Utility Damage (expect bombs)")
    player.element("Toggle", "Auto Airdrop-Claimer")
    miscsector.element(
        "Toggle",
        "Velocity Fly",
        nil,
        function(state)
            if menu.values[4].misc2.misc["Velocity Fly"].Toggle then
                sFLY(false, false, false)
            else
                NOFLY()
            end
        end
    )
    miscsector.element(
        "Toggle",
        "Fly",
        nil,
        function(state)
            if menu.values[4].misc2.misc["Fly"].Toggle then
                sFLY(false, true, true)
                LocalPlayer.Character.Humanoid.RagdollRemoteEvent:FireServer(true)
            else
                NOFLY()
                LocalPlayer.Character.Humanoid.RagdollRemoteEvent:FireServer(false)
            end
        end
    )
    miscsector.element(
        "Toggle",
        "Noclip",
        nil,
        function(state)
            if menu.values[4].misc2.misc["Noclip"].Toggle then
                Clip = false
            else
                Clip = true
            end
        end
    )
    player.element("Toggle", "Walk On Air (Q,E)")
    player.element("Toggle", "Jesus")
    player.element("Toggle", "No Fall Damage")
    player.element("Toggle", "No Ragdoll")
    player.element("Toggle", "No Dash Cooldown")
    player.element("Toggle", "Infinite Stamina")
    player.element("Toggle", "Infinite Air")
    player.element("Toggle", "Infinite Jump")
    player.element("Toggle", "No Jump Cooldown")
    player.element("Toggle", "Jump Whenever")
    miscsector.element("Toggle", "Kill Feed Spam")
    miscsector.element("Toggle", "Free Emotes")
    miscsector.element("Toggle", "Hide Name")
    player.element("Toggle", "Walk Speed")
    player.element("Slider", "Speed", {default = {min = 0, max = 150, default = 75}})
    player.element("Toggle", "Jump Power")
    player.element("Slider", "Power", {default = {min = 0, max = 500, default = 150}})
    Noclipping = game:GetService "RunService".Stepped:Connect(NoclipLoop)
    local Airdrops = game:GetService("Workspace").Airdrops
    task.spawn(
        function()
            Airdrops.ChildAdded:Connect(
                function(o)
                    if menu.values[4].misc.player["Auto Airdrop-Claimer"].Toggle then
                        local Airdrop = o
                        LocalPlayer.Character.HumanoidRootPart.CFrame = Airdrop:WaitForChild "Crate".Base.CFrame
                        wait(.2)
                        fireproximityprompt(Airdrop:WaitForChild "Crate".Hitbox.ProximityPrompt)
                    end
                end
            )
        end
    )
    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        if LocalPlayer.Character.Humanoid:FindFirstChildOfClass "RemoteEvent" ~= nil then
                            if menu.values[4].misc.player["No Ragdoll"].Toggle then
                                LocalPlayer.Character.Humanoid.RagdollRemoteEvent:FireServer(false)
                            end
                        end
                    end
                )
            end
        end
    )
    task.spawn(
        function()
            while task.wait() do
                pcall(
                    function()
                        for i, v in pairs(
                            getconnections(LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("WalkSpeed"))
                        ) do
                            v:Disable()
                        end
                        for i, v in pairs(
                            getconnections(LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("JumpPower"))
                        ) do
                            v:Disable()
                        end
                        if menu.values[4].misc.player["Walk Speed"].Toggle then
                            LocalPlayer.Character.Humanoid.WalkSpeed = menu.values[4].misc.player["Speed"].Slider
                            if menu.values[4].misc.player["Speed"].Slider > 75 then
                                LocalPlayer.Character.HumanoidRootPart.Anchored = true
                                task.wait(0.0001)
                                LocalPlayer.Character.HumanoidRootPart.Anchored = false
                            end
                            if LocalPlayer.Character:FindFirstChild("Float") ~= nil then
                                LocalPlayer.Character:FindFirstChild("Float"):Destroy()
                            end
                        else
                            task.wait()
                            if LocalPlayer.Character.Humanoid.WalkSpeed > 30 then
                                LocalPlayer.Character.Humanoid.WalkSpeed = 16
                            end
                            LocalPlayer.Character.HumanoidRootPart.Anchored = false
                        end

                        if menu.values[4].misc.player["Jump Power"].Toggle then
                            LocalPlayer.Character.Humanoid.JumpPower = menu.values[4].misc.player["Power"].Slider
                        else
                            LocalPlayer.Character.Humanoid.JumpPower = 50
                        end
                    end
                )
            end
        end
    )
    task.spawn(
        function()
            game:GetService "RunService".RenderStepped:Connect(
                function()
                    if menu.values[4].misc2.misc["Hide Name"].Toggle then
                        events.UpdateIsCrouching:FireServer(true)
                    end
                end
            )
        end
    )

    task.spawn(
        function()
            game:GetService "RunService".RenderStepped:Connect(
                function()
                    if menu.values[4].misc.player["Walk On Air (Q,E)"].Toggle then
                        if not menu.values[4].misc.player["Walk Speed"].Toggle then
                            events.UpdateIsParkouring:FireServer(true)
                        end
                    end
                end
            )
        end
    )

    task.spawn(
        function()
            game:GetService("RunService").RenderStepped:Connect(
                function()
                    if menu.values[4].misc.player["Jesus"].Toggle then
                        if workspace.Map:FindFirstChildOfClass "Model" ~= nil then
                            workspace.Map:FindFirstChildOfClass "Model".MapConfiguration.WaterAreas.WaterArea.CanCollide =
                                true
                        end
                    else
                        if workspace.Map:FindFirstChildOfClass "Model" ~= nil then
                            workspace.Map:FindFirstChildOfClass "Model".MapConfiguration.WaterAreas.WaterArea.CanCollide =
                                false
                        end
                    end
                end
            )
        end
    )

    local UIS = game:GetService("UserInputService")

    UIS.InputBegan:Connect(
        function(k, j)
            if j then
                return
            end
            if k.KeyCode == Enum.KeyCode.Space then
                if menu.values[4].misc.player["Infinite Jump"].Toggle then
                    pcall(
                        function()
                            LocalPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
                        end
                    )
                end
            end
        end
    )
    -- Infinite Yield Float (too lazy to make one myself)
    local FloatValue = -3.1
    qUp =
        Mouse.KeyUp:Connect(
        function(KEY)
            if KEY == "q" then
                FloatValue = FloatValue + 0.5
            end
        end
    )
    eUp =
        Mouse.KeyUp:Connect(
        function(KEY)
            if KEY == "e" then
                FloatValue = FloatValue - 0.5
            end
        end
    )
    qDown =
        Mouse.KeyDown:Connect(
        function(KEY)
            if KEY == "q" then
                FloatValue = FloatValue - 0.5
            end
        end
    )
    eDown =
        Mouse.KeyDown:Connect(
        function(KEY)
            if KEY == "e" then
                FloatValue = FloatValue + 0.5
            end
        end
    )
    local runService =
        game:GetService "RunService".RenderStepped:Connect(
        function()
            if
                (menu.values[4].misc.player["Walk On Air (Q,E)"].Toggle and
                    not menu.values[4].misc.player["Walk Speed"].Toggle)
             then
                if LocalPlayer.Character:FindFirstChild("Float") == nil then
                    local Float = Instance.new("Part")
                    Float.Name = "Float"
                    Float.Parent = LocalPlayer.Character
                    Float.Transparency = 1
                    Float.Size = Vector3.new(2, 0.2, 1.5)
                    Float.Anchored = true
                else
                    LocalPlayer.Character:FindFirstChild("Float").CFrame =
                        LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0, FloatValue, 0)
                end
            elseif
                not menu.values[4].misc.player["Walk On Air (Q,E)"].Toggle and
                    LocalPlayer.Character:FindFirstChild("Float") ~= nil
             then
                LocalPlayer.Character:FindFirstChild("Float"):Destroy()
                events.UpdateIsParkouring:FireServer(false)
                FloatValue = -3.1
            end
            -- epic kill feed spammer
            if menu.values[4].misc2.misc["Kill Feed Spam"].Toggle then
                events.StartFastRespawn:FireServer()
                functions.CompleteFastRespawn:FireServer()
            end
        end
    )

    local newindex

    newindex =
        hookmetamethod(
        game,
        "__namecall",
        function(self, ...)
            local howcalledomg = getnamecallmethod()
            local whataretheargs = {...}

            if
                not checkcaller() and self.Name == "GotHitRE" and
                    menu.values[4].misc.utility["No Utility Damage (expect bombs)"].Toggle and
                    howcalledomg == "FireServer"
             then
                return wait(9e9)
            end
            if
                not checkcaller() and self.Name == "RagdollRemoteEvent" and
                    menu.values[4].misc.player["No Ragdoll"].Toggle and
                    howcalledomg == "FireServer"
             then
                return wait(9e9)
            end
            if
                not checkcaller() and self.Name == "StartFallDamage" or
                    self.Name == "TakeFallDamage" and menu.values[4].misc.player["No Fall Damage"].Toggle and
                        howcalledomg == "FireServer"
             then
                return wait(9e9)
            end
            if
                not checkcaller() and self.Name == "UpdateIsCrouching" and menu.values[4].misc2.misc["Hide Name"].Toggle and
                    howcalledomg == "FireServer"
             then
                return
            elseif
                not checkcaller() and self.Name == "UpdateIsCrouching" and
                    not menu.values[4].misc2.misc["Hide Name"].Toggle
             then
                return newindex(self, ...)
            end

            if
                not checkcaller() and self.Name == "UpdateIsParkouring" and
                    menu.values[4].misc.player["Walk On Air (Q,E)"].Toggle and
                    howcalledomg == "FireServer"
             then
                return
            elseif
                not checkcaller() and self.Name == "UpdateIsParkouring" and
                    not menu.values[4].misc.player["Walk On Air (Q,E)"].Toggle and
                    howcalledomg == "FireServer"
             then
                return newindex(self, ...)
            end

            return newindex(self, ...)
        end
    )

    for i, v in pairs(getgc(true)) do
        if type(v) == "table" and rawget(v, "AIR_TO_ADD_PER_SECOND_WHILE_SWIMMING") then
            local old = v.AIR_TO_ADD_PER_SECOND_WHILE_SWIMMING

            task.spawn(
                function()
                    while true do
                        if menu.values[4].misc.player["Infinite Air"].Toggle then
                            v.AIR_TO_ADD_PER_SECOND_WHILE_SWIMMING = 99999999999999999999999999999
                        else
                            v.AIR_TO_ADD_PER_SECOND_WHILE_SWIMMING = old
                        end
                        task.wait()
                    end
                end
            )
        end
        if typeof(v) == "table" and rawget(v, "getCanJump") then
            local old = v.getCanJump

            v.getCanJump = function()
                if menu.values[4].misc.player["Jump Whenever"].Toggle then
                    return true
                else
                    return old()
                end
            end
        end

        if typeof(v) == "table" and rawget(v, "JUMP_DELAY_ADD") then
            local old = v.JUMP_DELAY_ADD

            task.spawn(
                function()
                    while true do
                        if menu.values[4].misc.player["No Jump Cooldown"].Toggle then
                            v.JUMP_DELAY_ADD = 0.5
                        else
                            v.JUMP_DELAY_ADD = old
                        end
                        task.wait()
                    end
                end
            )
        end

        if typeof(v) == "table" and rawget(v, "_setStamina") then
            local old = v._setStamina

            v._setStamina = function(gg, gg2)
                if menu.values[4].misc.player["Infinite Stamina"].Toggle then
                    gg._stamina = math.huge
                    gg._staminaChangedSignal:Fire(150)
                else
                    return old(gg, gg2)
                end
            end
        end
        
        if typeof(v) == "table" and rawget(v, "toggleRagdoll") then
            local old = v.toggleRagdoll
            
            v.toggleRagdoll = function(gg, gg2, gg3)
                if menu.values[4].misc.player["No Ragdoll"].Toggle then
                    return
                else
                    return old(gg, gg2, gg3)
                end
            end
        end

        if typeof(v) == "table" and rawget(v, "DASH_COOLDOWN") then
            local old = v.DASH_COOLDOWN

            task.spawn(
                function()
                    while true do
                        if menu.values[4].misc.player["No Dash Cooldown"].Toggle then
                            v.DASH_COOLDOWN = -500
                        else
                            v.DASH_COOLDOWN = old
                        end
                        task.wait()
                    end
                end
            )
        end

        if typeof(v) == "table" and rawget(v, "gamepassIdRequired") then
            task.spawn(
                function()
                    while true do
                        if menu.values[4].misc2.misc["Free Emotes"].Toggle then
                            if v.gamepassIdRequired == "danceEmotes" then
                                v.gamepassIdRequired = nil
                            elseif v.gamepassIdRequired == "toxicEmotes" then
                                v.gamepassIdRequired = nil
                            elseif v.gamepassIdRequired == "respectEmotes" then
                                v.gamepassIdRequired = nil
                            end
                        else
                            if v.gamepassIdRequired == nil then
                                v.gamepassIdRequired = "danceEmotes"
                            end
                        end
                        task.wait()
                    end
                end
            )
        end
    end
end
-- !!NOT MY ESP!!
local Camera = workspace.CurrentCamera

local ESPLoop =
    game:GetService("RunService").RenderStepped:Connect(
    function()
        for _, Player in pairs(Players:GetPlayers()) do
            local PlayerDrawing = PlayerDrawings[Player]
            if not PlayerDrawing then
                continue
            end

            for _, Drawing in pairs(PlayerDrawing) do
                Drawing.Visible = false
            end

            if not menu.values[3].players.ESP.Enabled.Toggle or not menu.values[3].players.ESP["$Enabled"].Active then
                continue
            end
            local Character = Player.Character
            local RootPart, Humanoid =
                Character and Character:FindFirstChild("HumanoidRootPart"),
                Character and Character:FindFirstChildOfClass("Humanoid")
            if not Character or not RootPart or not Humanoid then
                continue
            end

            local DistanceFromCharacter = (Camera.CFrame.Position - RootPart.Position).Magnitude
            if menu.values[3].players.ESP["Max Distance"].Slider < DistanceFromCharacter then
                continue
            end

            local Pos, OnScreen = Camera:WorldToViewportPoint(RootPart.Position)
            if not OnScreen then
                local VisualTable = menu.values[3].players["Out Of FOV"]

                local RootPos = RootPart.Position
                local CameraVector = Camera.CFrame.Position
                local LookVector = Camera.CFrame.LookVector

                local Dot = LookVector:Dot(RootPart.Position - Camera.CFrame.Position)
                if Dot <= 0 then
                    RootPos = (CameraVector + ((RootPos - CameraVector) - ((LookVector * Dot) * 1.01)))
                end

                local ScreenPos, OnScreen = Camera:WorldToScreenPoint(RootPos)
                if not OnScreen then
                    local Drawing = PlayerDrawing.Offscreen
                    local FOV = 800 - menu.values[3].players["Out Of FOV"].Offset.Slider
                    local Size = menu.values[3].players["Out Of FOV"].Size.Slider

                    local Center = (Camera.ViewportSize / 2)
                    local Direction = (Vector2.new(ScreenPos.X, ScreenPos.Y) - Center).Unit
                    local Radian = math.atan2(Direction.X, Direction.Y)
                    local Angle = (((math.pi * 2) / FOV) * Radian)
                    local ClampedPosition =
                        (Center +
                        (Direction *
                            math.min(
                                math.abs(((Center.Y - FOV) / math.sin(Angle)) * FOV),
                                math.abs((Center.X - FOV) / (math.cos(Angle)) / 2)
                            )))
                    local Point =
                        Vector2.new(
                        math.floor(ClampedPosition.X - (Size / 2)),
                        math.floor((ClampedPosition.Y - (Size / 2) - 15))
                    )

                    local function Rotate(point, center, angle)
                        angle = math.rad(angle)
                        local rotatedX =
                            math.cos(angle) * (point.X - center.X) - math.sin(angle) * (point.Y - center.Y) + center.X
                        local rotatedY =
                            math.sin(angle) * (point.X - center.X) + math.cos(angle) * (point.Y - center.Y) + center.Y

                        return Vector2.new(math.floor(rotatedX), math.floor(rotatedY))
                    end

                    local Rotation = math.floor(-math.deg(Radian)) - 47
                    Drawing.PointA = Rotate(Point + Vector2.new(Size, Size), Point, Rotation)
                    Drawing.PointB = Rotate(Point + Vector2.new(-Size, -Size), Point, Rotation)
                    Drawing.PointC = Rotate(Point + Vector2.new(-Size, Size), Point, Rotation)
                    Drawing.Color = VisualTable["$Enabled"].Color
                    Drawing.Filled =
                        not table.find(menu.values[3].players["Out Of FOV"].Settings.Combo, "Outline") and true or false
                    if table.find(menu.values[3].players["Out Of FOV"].Settings.Combo, "Blinking") then
                        Drawing.Transparency = (math.sin(tick() * 5) + 1) / 2
                    else
                        Drawing.Transparency = 1
                    end

                    if VisualTable.Enabled.Toggle then
                        Drawing.Visible = true
                    else
                        Drawing.Visible = false
                    end
                end
            else
                local VisualTable = menu.values[3].players.Player

                local Size =
                    (Camera:WorldToViewportPoint(RootPart.Position - Vector3.new(0, 3, 0)).Y -
                    Camera:WorldToViewportPoint(RootPart.Position + Vector3.new(0, 2.6, 0)).Y) /
                    2
                local BoxSize = Vector2.new(math.floor(Size * 1.5), math.floor(Size * 1.9))
                local BoxPos = Vector2.new(math.floor(Pos.X - Size * 1.5 / 2), math.floor(Pos.Y - Size * 1.6 / 2))

                local Name = PlayerDrawing.Name
                local Tool = PlayerDrawing.Tool
                local Distance = PlayerDrawing.Distance
                local Box = PlayerDrawing.Box
                local BoxOutline = PlayerDrawing.BoxOutline
                local Health = PlayerDrawing.Health
                local HealthOutline = PlayerDrawing.HealthOutline

                if VisualTable.Box.Toggle then
                    Box.Size = BoxSize
                    Box.Position = BoxPos
                    Box.Visible = true
                    Box.Color = VisualTable["$Box"].Color
                    BoxOutline.Size = BoxSize
                    BoxOutline.Position = BoxPos
                    BoxOutline.Visible = true
                end

                if VisualTable.Health.Toggle then
                    Health.From = Vector2.new((BoxPos.X - 5), BoxPos.Y + BoxSize.Y)
                    Health.To =
                        Vector2.new(Health.From.X, Health.From.Y - (Humanoid.Health / Humanoid.MaxHealth) * BoxSize.Y)
                    Health.Color = VisualTable["$Health"].Color
                    Health.Visible = true

                    HealthOutline.From = Vector2.new(Health.From.X, BoxPos.Y + BoxSize.Y + 1)
                    HealthOutline.To = Vector2.new(Health.From.X, (Health.From.Y - 1 * BoxSize.Y) - 1)
                    HealthOutline.Visible = true
                end

                if VisualTable.Name.Toggle then
                    Name.Text = Player.Name
                    Name.Position = Vector2.new(BoxSize.X / 2 + BoxPos.X, BoxPos.Y - 16)
                    Name.Color = VisualTable["$Name"].Color
                    Name.Font = 1
                    Name.Visible = true
                end

                if VisualTable.Indicators.Toggle then
                    local BottomOffset = BoxSize.Y + BoxPos.Y + 1
                    if table.find(VisualTable.Types.Combo, "Tool") then
                        local Equipped =
                            Player.Character:FindFirstChildOfClass("Tool") and
                            Player.Character:FindFirstChildOfClass("Tool").Name or
                            "None"
                        Equipped = Equipped
                        Tool.Text = Equipped
                        Tool.Position = Vector2.new(BoxSize.X / 2 + BoxPos.X, BottomOffset)
                        Tool.Color = VisualTable["$Indicators"].Color
                        Tool.Font = 1
                        Tool.Visible = true
                        BottomOffset = BottomOffset + 15
                    end
                    if table.find(VisualTable.Types.Combo, "Distance") then
                        Distance.Text = math.floor(DistanceFromCharacter) .. "m"
                        Distance.Position = Vector2.new(BoxSize.X / 2 + BoxPos.X, BottomOffset)
                        Distance.Color = VisualTable["$Indicators"].Color
                        Distance.Font = 1
                        Distance.Visible = true

                        BottomOffset = BottomOffset + 15
                    end
                end
            end
        end
    end
)

Notification:Notify(
    {Title = "Nofitication", Description = "Nova Hub Loaded in " .. tick() - t .. "s (seconds)"},
    {OutlineColor = Color3.fromRGB(80, 80, 80), Time = 5, Type = "default"}
)
