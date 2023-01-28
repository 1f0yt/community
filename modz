if not game:IsLoaded() then 
    repeat game.Loaded:Wait()
    until game:IsLoaded() 
end
repeat wait(1)
    pcall(function()
        if game:GetService("Players").LocalPlayer.PlayerGui.Main:FindFirstChild("ChooseTeam") then
            if game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Visible == true then
                if _G.Team == "Marines" then
                    for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                        v.Function()
                    end
                else
                    for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                        v.Function()
                    end
                end
            end
        end
    end)
until game.Players.localPlayer.Neutral == false
if _G.Fast_Delay == nil then
	_G.Fast_Delay = 0.3
end
spawn(function()
    while true do wait()
        getgenv().rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(Kick)
            if not _G.TP_Ser and _G.Rejoin then
                if Kick.Name == 'ErrorPrompt' and Kick:FindFirstChild('MessageArea') and Kick.MessageArea:FindFirstChild("ErrorFrame") then
                    game:GetService("TeleportService"):Teleport(game.PlaceId)
                    wait(50)
                end
            end
        end)
    end
end)

local VirtualUser=game:service'VirtualUser'
game:service'Players'.LocalPlayer.Idled:connect(function()
	VirtualUser:CaptureController()
	VirtualUser:ClickButton2(Vector2.new())
end)

spawn(function()
	while wait(3) do
		game:GetService'VirtualUser':CaptureController()
	end
end)

Old_World = false
New_World = false
Three_World = false
local placeId = game.PlaceId
if placeId == 2753915549 then
    Old_World = true
elseif placeId == 4442272183 then
    New_World = true
elseif placeId == 7449423635 then
    Three_World = true
end
_G.Color = Color3.fromRGB(68, 202, 186)

_G.Setting_table = {
    Auto_Farm = false,
    FastAttack = true,
	Auto_Buso = true,
	Auto_Ken = true,
	Show_Damage = true,
	NoClip = true,
	Save_Member = true,
	Melee_A = true,
	Defense_A = true,
	SkillZ = true,
	Rejoin = true,
	Anti_AFK = true,
	K_MAX = 50,
	Chest_Lock = 50,
	Delay_C = 15
}

_G.Check_Save_Setting = "CheckSaveSetting"

getgenv()['JsonEncode'] = function(msg)
    return game:GetService("HttpService"):JSONEncode(msg)
end
getgenv()['JsonDecode'] = function(msg)
    return game:GetService("HttpService"):JSONDecode(msg)
end
getgenv()['Check_Setting'] = function(Name)
    if not _G.Dis and not isfolder('Switch Hub BF Premium') then
        makefolder('Switch Hub BF Premium')
    end
    if not _G.Dis and not isfile('Switch Hub BF Premium/'..Name..'.json') then
        writefile('Switch Hub BF Premium/'..Name..'.json',JsonEncode(_G.Setting_table))
    end
end
getgenv()['Get_Setting'] = function(Name)
    if not _G.Dis and isfolder('Switch Hub BF Premium') and isfile('Switch Hub BF Premium/'..Name..'.json') then
        _G.Setting_table = JsonDecode(readfile('Switch Hub BF Premium/'..Name..'.json'))
        return _G.Setting_table
	elseif not _G.Dis then
        Check_Setting(Name)
    end
end
getgenv()['Update_Setting'] = function(Name)
    if not _G.Dis and isfolder('Switch Hub BF Premium') and isfile('Switch Hub BF Premium/'..Name..'.json') then
        writefile('Switch Hub BF Premium/'..Name..'.json',JsonEncode(_G.Setting_table))
	elseif not _G.Dis then
        Check_Setting(Name)
    end
end

Check_Setting(_G.Check_Save_Setting)
Get_Setting(_G.Check_Save_Setting)

if _G.Setting_table.Save_Member then
	getgenv()['MyName'] = game.Players.LocalPlayer.Name
	print("Save Member")
elseif _G.Setting_table.Save_All_Member then
	getgenv()['MyName'] = "AllMember"
	print("Save All Member")
else
	getgenv()['MyName'] = "None"
	_G.Dis = true
end

Check_Setting(getgenv()['MyName'])
Get_Setting(getgenv()['MyName'])

_G.Setting_table.Key = _G.wl_key
Update_Setting(getgenv()['MyName'])

if type(_G.Setting_table.Weapon) ~= 'string' then
	for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
		if tostring(v2.ToolTip) == "Melee" then
			_G.Setting_table.Weapon = v2.Name
		end
	end
end


function Text(value)
    game.StarterGui:SetCore("SendNotification", {
        Title = "MODZ Notification", 
        Text = tostring(value),
        Icon = "http://www.roblox.com/asset/?id=9606070311",
        Duration = 10
    })
end
function Com()
    game.StarterGui:SetCore("SendNotification", {
        Title = "MODZ Notification", 
        Text = "✅  Complete",
        Icon = "http://www.roblox.com/asset/?id=9606070311",
        Duration = 5
    })
end

function TelePBoss(p)
	if (p.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude >= 2000 and not Auto_Raid and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
		if NameQuest == "FishmanQuest" then
			_G.Stop_Tween = true
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			wait(.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			_G.Stop_Tween = nil
		elseif Ms == "God's Guard [Lv. 450]"  then
			_G.Stop_Tween = true
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			wait(.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			_G.Stop_Tween = nil
		elseif NameQuest == "SkyExp1Quest" then
			_G.Stop_Tween = true
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			wait(.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
			_G.Stop_Tween = nil
		elseif NameQuest == "ShipQuest1" then
			_G.Stop_Tween = true
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			wait(.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
			_G.Stop_Tween = nil
		elseif NameQuest == "ShipQuest2" then
			_G.Stop_Tween = true
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			wait(.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
			_G.Stop_Tween = nil
		elseif NameQuest == "FrostQuest" then
			_G.Stop_Tween = true
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			wait(.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
			_G.Stop_Tween = nil
		else
			Mix_Farm = true
			_G.Stop_Tween = true
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
			repeat wait(.5)
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p
				wait()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
			until (p.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 and game.Players.LocalPlayer.Character.Humanoid.Health > 0
			wait(.5)
			_G.Stop_Tween = nil
			Mix_Farm = nil
		end
	end
end

function CheckQuestBoss()
	-- Old World
		if _G.SelectBoss == "Saber Expert [Lv. 200] [Boss]" then
			MsBoss = "Saber Expert [Lv. 200] [Boss]"
			NameBoss = "Saber Expert"
			CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
		elseif _G.SelectBoss == "The Saw [Lv. 100] [Boss]" then
			MsBoss = "The Saw [Lv. 100] [Boss]"
			NameBoss = "The Saw"
			CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
		elseif _G.SelectBoss == "Greybeard [Lv. 750] [Raid Boss]" then
			MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
			NameBoss = "Greybeard"
			CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
		elseif _G.SelectBoss == "The Gorilla King [Lv. 25] [Boss]" then
			MsBoss = "The Gorilla King [Lv. 25] [Boss]" 
			NameBoss = "The Gorilla King"
			NameQuestBoss = "JungleQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Bobby [Lv. 55] [Boss]" then
			MsBoss = "Bobby [Lv. 55] [Boss]"
			NameBoss = "Bobby"
			NameQuestBoss = "BuggyQuest1"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Yeti [Lv. 110] [Boss]" then
			MsBoss = "Yeti [Lv. 110] [Boss]"
			NameBoss = "Yeti"
			NameQuestBoss = "SnowQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
			CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Mob Leader [Lv. 120] [Boss]" then
			MsBoss = "Mob Leader [Lv. 120] [Boss]"
			NameBoss = "Mob Leader"
			CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
		elseif _G.SelectBoss == "Vice Admiral [Lv. 130] [Boss]" then
			MsBoss = "Vice Admiral [Lv. 130] [Boss]"
			NameBoss = "Vice Admiral"
			NameQuestBoss = "MarineQuest2"
			QuestLvBoss = 2
			CFrameQBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
			CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Warden [Lv. 220] [Boss]" then
			MsBoss = "Warden [Lv. 220] [Boss]"
			NameBoss = "Warden"
			NameQuestBoss = "ImpelQuest"
			QuestLvBoss = 1
			CFrameQBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Chief Warden [Lv. 230] [Boss]" then
			MsBoss = "Chief Warden [Lv. 230] [Boss]"
			NameBoss = "Chief Warden"
			NameQuestBoss = "ImpelQuest"
			QuestLvBoss = 2
			CFrameQBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Swan [Lv. 240] [Boss]" then
			MsBoss = "Swan [Lv. 240] [Boss]"
			NameBoss = "Swan"
			NameQuestBoss = "ImpelQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Magma Admiral [Lv. 350] [Boss]" then
			MsBoss = "Magma Admiral [Lv. 350] [Boss]"
			NameBoss = "Magma Admiral"
			NameQuestBoss = "MagmaQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
			CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Fishman Lord [Lv. 425] [Boss]" then
			MsBoss = "Fishman Lord [Lv. 425] [Boss]"
			NameBoss = "Fishman Lord"
			NameQuestBoss = "FishmanQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
			CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
			if (CFrameQBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			end
		elseif _G.SelectBoss == "Wysper [Lv. 500] [Boss]" then
			MsBoss = "Wysper [Lv. 500] [Boss]"
			NameBoss = "Wysper"
			NameQuestBoss = "SkyExp1Quest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
			CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
			if (CFrameQBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			end
		elseif _G.SelectBoss == "Thunder God [Lv. 575] [Boss]" then
			MsBoss = "Thunder God [Lv. 575] [Boss]"
			NameBoss = "Thunder God"
			NameQuestBoss = "SkyExp2Quest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
			CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Cyborg [Lv. 675] [Boss]" then
			MsBoss = "Cyborg [Lv. 675] [Boss]"
			NameBoss = "Cyborg"
			NameQuestBoss = "FountainQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
			CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
			TelePBoss(CFrameBoss)
		-- New World
		elseif _G.SelectBoss == "Diamond [Lv. 750] [Boss]" then
			MsBoss = "Diamond [Lv. 750] [Boss]"
			NameBoss = "Diamond"
			NameQuestBoss = "Area1Quest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Jeremy [Lv. 850] [Boss]" then
			MsBoss = "Jeremy [Lv. 850] [Boss]"
			NameBoss = "Jeremy"
			NameQuestBoss = "Area2Quest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Fajita [Lv. 925] [Boss]" then
			MsBoss = "Fajita [Lv. 925] [Boss]"
			NameBoss = "Fajita"
			NameQuestBoss = "MarineQuest3"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Don Swan [Lv. 1000] [Boss]" then
			MsBoss = "Don Swan [Lv. 1000] [Boss]"
			NameBoss = "Don Swan"
			CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Smoke Admiral [Lv. 1150] [Boss]" then
			MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
			NameBoss = "Smoke Admiral"
			NameQuestBoss = "IceSideQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
			CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
			MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
			NameBoss = "Cursed Captain"
			CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
		elseif _G.SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
			MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
			NameBoss = "Darkbeard"
			CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
		elseif _G.SelectBoss == "Order [Lv. 1250] [Raid Boss]" then
			MsBoss = "Order [Lv. 1250] [Raid Boss]"
			NameBoss = "Order"
			CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
		elseif _G.SelectBoss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
			MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
			NameBoss = "Awakened Ice Admiral"
			NameQuestBoss = "FrostQuest"
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
			CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Tide Keeper [Lv. 1475] [Boss]" then
			MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
			NameBoss = "Tide Keeper"
			NameQuestBoss = "ForgottenQuest"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
			CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
			TelePBoss(CFrameBoss)
		-- Thire World
		elseif _G.SelectBoss == "Stone [Lv. 1550] [Boss]" then
			MsBoss = "Stone [Lv. 1550] [Boss]"
			NameBoss = "Stone"
			NameQuestBoss = "PiratePortQuest"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-290, 44, 5577)
			CFrameBoss = CFrame.new(-1085, 40, 6779)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Island Empress [Lv. 1675] [Boss]" then
			MsBoss = "Island Empress [Lv. 1675] [Boss]"
			NameBoss = "Island Empress"
			NameQuestBoss = "AmazonQuest2"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(5443, 602, 752)
			CFrameBoss = CFrame.new(5659, 602, 244)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Kilo Admiral [Lv. 1750] [Boss]" then
			MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
			NameBoss = "Kilo Admiral"
			NameQuestBoss = "MarineTreeIsland"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(2178, 29, -6737)
			CFrameBoss =CFrame.new(2846, 433, -7100)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Captain Elephant [Lv. 1875] [Boss]" then
			MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
			NameBoss = "Captain Elephant"
			NameQuestBoss = "DeepForestIsland"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-13232, 333, -7631)
			CFrameBoss = CFrame.new(-13221, 325, -8405)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Beautiful Pirate [Lv. 1950] [Boss]" then
			MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
			NameBoss = "Beautiful Pirate"
			NameQuestBoss = "DeepForestIsland2"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-12686, 391, -9902)
			CFrameBoss = CFrame.new(5182, 23, -20)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
			MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
			NameBoss = "rip_indra True Form"
			CFrameBoss = CFrame.new(-5359, 424, -2735)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Longma [Lv. 2000] [Boss]" then
			MsBoss = "Longma [Lv. 2000] [Boss]"
			NameBoss = "Longma"
			CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
			MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
			NameBoss = "Soul Reaper"
			CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
			TelePBoss(CFrameBoss)
		elseif _G.SelectBoss == "Cake Queen [Lv. 2175] [Boss]" then
			MsBoss = "Cake Queen [Lv. 2175] [Boss]"
			NameBoss = "Cake Queen"
			NameQuestBoss = "IceCreamIslandQuest"             
			QuestLvBoss = 3
			CFrameQBoss = CFrame.new(-821.267456, 65.9448776, -10964.3994, 0.814093888, -3.67296735e-08, -0.58073324, 3.30765637e-08, 1, -1.6879099e-08, 0.58073324, -5.46748513e-09, 0.814093888)
			CFrameBoss = CFrame.new(-715.467102, 381.69104, -11019.8896, 0.955998719, -1.07319993e-08, -0.293370903, 5.00311881e-09, 1, -2.02781667e-08, 0.293370903, 1.7918131e-08, 0.955998719)
			TelePBoss(CFrameBoss)
		end
	end

		function CheckLevel()
			local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
			if Old_World then
				if Lv == 1 or Lv <= 9 or SelectMonster == "Bandit [Lv. 5]" then -- Bandit
					Ms = "Bandit [Lv. 5]"
					NameQuest = "BanditQuest1"
					QuestLv = 1
					NameMon = "Bandit"
					CFrameQ = CFrame.new(1060.9383544922, 16.455066680908, 1547.7841796875)
					CFrameMon = CFrame.new(1038.5533447266, 41.296249389648, 1576.5098876953)
				elseif Lv == 10 or Lv <= 14 or SelectMonster == "Monkey [Lv. 14]" then -- Monkey
					Ms = "Monkey [Lv. 14]"
					NameQuest = "JungleQuest"
					QuestLv = 1
					NameMon = "Monkey"
					CFrameQ = CFrame.new(-1601.6553955078, 36.85213470459, 153.38809204102)
					CFrameMon = CFrame.new(-1448.1446533203, 50.851993560791, 63.60718536377)
				elseif Lv == 15 or Lv <= 29 or SelectMonster == "Gorilla [Lv. 20]" then -- Gorilla
					Ms = "Gorilla [Lv. 20]"
					NameQuest = "JungleQuest"
					QuestLv = 2
					NameMon = "Gorilla"
					CFrameQ = CFrame.new(-1601.6553955078, 36.85213470459, 153.38809204102)
					CFrameMon = CFrame.new(-1142.6488037109, 40.462348937988, -515.39227294922)
				elseif Lv == 30 or Lv <= 39 or SelectMonster == "Pirate [Lv. 35]" then -- Pirate
					Ms = "Pirate [Lv. 35]"
					NameQuest = "BuggyQuest1"
					QuestLv = 1
					NameMon = "Pirate"
					CFrameQ = CFrame.new(-1140.1761474609, 4.752049446106, 3827.4057617188)
					CFrameMon = CFrame.new(-1201.0881347656, 40.628940582275, 3857.5966796875)
				elseif Lv == 40 or Lv <= 59 or SelectMonster == "Brute [Lv. 45]" then -- Brute
					Ms = "Brute [Lv. 45]"
					NameQuest = "BuggyQuest1"
					QuestLv = 2
					NameMon = "Brute"
					CFrameQ = CFrame.new(-1140.1761474609, 4.752049446106, 3827.4057617188)
					CFrameMon = CFrame.new(-1387.5324707031, 24.592035293579, 4100.9575195313)
				elseif Lv == 60 or Lv <= 74 or SelectMonster == "Desert Bandit [Lv. 60]" then -- Desert Bandit
					Ms = "Desert Bandit [Lv. 60]"
					NameQuest = "DesertQuest"
					QuestLv = 1
					NameMon = "Desert Bandit"
					CFrameQ = CFrame.new(896.51721191406, 6.4384617805481, 4390.1494140625)
					CFrameMon = CFrame.new(984.99896240234, 16.109552383423, 4417.91015625)
				elseif Lv == 75 or Lv <= 89 or SelectMonster == "Desert Officer [Lv. 70]" then -- Desert Officer
					Ms = "Desert Officer [Lv. 70]"
					NameQuest = "DesertQuest"
					QuestLv = 2
					NameMon = "Desert Officer"
					CFrameQ = CFrame.new(896.51721191406, 6.4384617805481, 4390.1494140625)
					CFrameMon = CFrame.new(1547.1510009766, 14.452038764954, 4381.8002929688)
				elseif Lv == 90 or Lv <= 99 or SelectMonster == "Snow Bandit [Lv. 90]" then -- Snow Bandit
					Ms = "Snow Bandit [Lv. 90]"
					NameQuest = "SnowQuest"
					QuestLv = 1
					NameMon = "Snow Bandit"
					CFrameQ = CFrame.new(1386.8073730469, 87.272789001465, -1298.3576660156)
					CFrameMon = CFrame.new(1356.3028564453, 105.76865386963, -1328.2418212891)
				elseif Lv == 100 or Lv <= 119 or SelectMonster == "Snowman [Lv. 100]" then -- Snowman
					Ms = "Snowman [Lv. 100]"
					NameQuest = "SnowQuest"
					QuestLv = 2
					NameMon = "Snowman"
					CFrameQ = CFrame.new(1386.8073730469, 87.272789001465, -1298.3576660156)
					CFrameMon = CFrame.new(1218.7956542969, 138.01184082031, -1488.0262451172)
				elseif Lv == 120 or Lv <= 149 or SelectMonster == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
					Ms = "Chief Petty Officer [Lv. 120]"
					NameQuest = "MarineQuest2"
					QuestLv = 1
					NameMon = "Chief Petty Officer"
					CFrameQ = CFrame.new(-5035.49609375, 28.677835464478, 4324.1840820313)
					CFrameMon = CFrame.new(-4931.1552734375, 65.793113708496, 4121.8393554688)
				elseif Lv == 150 or Lv <= 174 or SelectMonster == "Sky Bandit [Lv. 150]" then -- Sky Bandit
					Ms = "Sky Bandit [Lv. 150]"
					NameQuest = "SkyQuest"
					QuestLv = 1
					NameMon = "Sky Bandit"
					CFrameQ = CFrame.new(-4842.1372070313, 717.69543457031, -2623.0483398438)
					CFrameMon = CFrame.new(-4955.6411132813, 365.46365356445, -2908.1865234375)
				elseif Lv == 175 or Lv <= 249 or SelectMonster == "Dark Master [Lv. 175]" then -- Dark Master
					Ms = "Dark Master [Lv. 175]"
					NameQuest = "SkyQuest"
					QuestLv = 2
					NameMon = "Dark Master"
					CFrameQ = CFrame.new(-4842.1372070313, 717.69543457031, -2623.0483398438)
					CFrameMon = CFrame.new(-5148.1650390625, 439.04571533203, -2332.9611816406)
				elseif Lv == 250 or Lv <= 274 or SelectMonster == "Toga Warrior [Lv. 250]" then -- Toga Warrior
					Ms = "Toga Warrior [Lv. 250]"
					NameQuest = "ColosseumQuest"
					QuestLv = 1
					NameMon = "Toga Warrior"
					CFrameQ = CFrame.new(-1577.7890625, 7.4151420593262, -2984.4838867188)
					CFrameMon = CFrame.new(-1872.5166015625, 49.080215454102, -2913.810546875)
				elseif Lv == 275 or Lv <= 299 or SelectMonster == "Gladiator [Lv. 275]" then -- Gladiator
					Ms = "Gladiator [Lv. 275]"
					NameQuest = "ColosseumQuest"
					QuestLv = 2
					NameMon = "Gladiator"
					CFrameQ = CFrame.new(-1577.7890625, 7.4151420593262, -2984.4838867188)
					CFrameMon = CFrame.new(-1521.3740234375, 81.203170776367, -3066.3139648438)
				elseif Lv == 300 or Lv <= 329 or SelectMonster == "Military Soldier [Lv. 300]" then -- Military Soldier
					Ms = "Military Soldier [Lv. 300]"
					NameQuest = "MagmaQuest"
					QuestLv = 1
					NameMon = "Military Soldier"
					CFrameQ = CFrame.new(-5316.1157226563, 12.262831687927, 8517.00390625)
					CFrameMon = CFrame.new(-5369.0004882813, 61.24352645874, 8556.4921875)
				elseif Lv == 330 or Lv <= 374 or SelectMonster == "Military Spy [Lv. 325]" then -- Military Spy
					Ms = "Military Spy [Lv. 325]"
					NameQuest = "MagmaQuest"
					QuestLv = 2
					NameMon = "Military Spy"
					CFrameQ = CFrame.new(-5316.1157226563, 12.262831687927, 8517.00390625)
					CFrameMon = CFrame.new(-5984.0532226563, 82.14656829834, 8753.326171875)
				elseif Lv == 375 or Lv <= 399 or SelectMonster == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior 
					_G.FM = true
					Ms = "Fishman Warrior [Lv. 375]"
					NameQuest = "FishmanQuest"
					QuestLv = 1
					NameMon = "Fishman Warrior"
					CFrameQ = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
					CFrameMon = CFrame.new(60844.10546875, 98.462875366211, 1298.3985595703)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
					end
				elseif Lv == 400 or Lv <= 449 or SelectMonster == "Fishman Commando [Lv. 400]" then -- Fishman Commando
					_G.FM = true
					Ms = "Fishman Commando [Lv. 400]"
					NameQuest = "FishmanQuest"
					QuestLv = 2
					NameMon = "Fishman Commando"
					CFrameQ = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
					CFrameMon = CFrame.new(61738.3984375, 64.207321166992, 1433.8375244141)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
					end
				elseif Lv == 450 or Lv <= 474 or SelectMonster == "God's Guard [Lv. 450]" then -- God's Guard
					_G.FM = false
					Ms = "God's Guard [Lv. 450]"
					NameQuest = "SkyExp1Quest"
					QuestLv = 1
					NameMon = "God's Guard"
					CFrameQ = CFrame.new(-4721.8603515625, 845.30297851563, -1953.8489990234)
					CFrameMon = CFrame.new(-4628.0498046875, 866.92877197266, -1931.2352294922)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
					end
				elseif Lv == 475 or Lv <= 524 or SelectMonster == "Shanda [Lv. 475]" then -- Shanda
					_G.FM = false
					Ms = "Shanda [Lv. 475]"
					NameQuest = "SkyExp1Quest"
					QuestLv = 2
					NameMon = "Shanda"
					CFrameQ = CFrame.new(-7863.1596679688, 5545.5190429688, -378.42266845703)
					CFrameMon = CFrame.new(-7685.1474609375, 5601.0751953125, -441.38876342773)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
					end
				elseif Lv == 525 or Lv <= 549 or SelectMonster == "Royal Squad [Lv. 525]" then -- Royal Squad
					Ms = "Royal Squad [Lv. 525]"
					NameQuest = "SkyExp2Quest"
					QuestLv = 1
					NameMon = "Royal Squad"
					CFrameQ = CFrame.new(-7903.3828125, 5635.9897460938, -1410.923828125)
					CFrameMon = CFrame.new(-7654.2514648438, 5637.1079101563, -1407.7550048828)
				elseif Lv == 550 or Lv <= 624 or SelectMonster == "Royal Soldier [Lv. 550]" then -- Royal Soldier
					Ms = "Royal Soldier [Lv. 550]"
					NameQuest = "SkyExp2Quest"
					QuestLv = 2
					NameMon = "Royal Soldier"
					CFrameQ = CFrame.new(-7903.3828125, 5635.9897460938, -1410.923828125)
					CFrameMon = CFrame.new(-7760.4106445313, 5679.9077148438, -1884.8112792969)
				elseif Lv == 625 or Lv <= 649 or SelectMonster == "Galley Pirate [Lv. 625]" then -- Galley Pirate
					Ms = "Galley Pirate [Lv. 625]"
					NameQuest = "FountainQuest"
					QuestLv = 1
					NameMon = "Galley Pirate"
					CFrameQ = CFrame.new(5258.2788085938, 38.526931762695, 4050.044921875)
					CFrameMon = CFrame.new(5557.1684570313, 152.32717895508, 3998.7758789063)
				elseif Lv >= 650 or SelectMonster == "Galley Captain [Lv. 650]" then -- Galley Captain
					Ms = "Galley Captain [Lv. 650]"
					NameQuest = "FountainQuest"
					QuestLv = 2
					NameMon = "Galley Captain"
					CFrameQ = CFrame.new(5258.2788085938, 38.526931762695, 4050.044921875)
					CFrameMon = CFrame.new(5677.6772460938, 92.786109924316, 4966.6323242188)
				end
			end
			if New_World then
				if Lv == 700 or Lv <= 724 or SelectMonster == "Raider [Lv. 700]" then -- Raider
					Ms = "Raider [Lv. 700]"
					NameQuest = "Area1Quest"
					QuestLv = 1
					NameMon = "Raider"
					CFrameQ = CFrame.new(-427.72567749023, 72.99634552002, 1835.9426269531)
					CFrameMon = CFrame.new(68.874565124512, 93.635643005371, 2429.6752929688)
				elseif Lv == 725 or Lv <= 774 or SelectMonster == "Mercenary [Lv. 725]" then -- Mercenary
					Ms = "Mercenary [Lv. 725]"
					NameQuest = "Area1Quest"
					QuestLv = 2
					NameMon = "Mercenary"
					CFrameQ = CFrame.new(-427.72567749023, 72.99634552002, 1835.9426269531)
					CFrameMon = CFrame.new(-864.85009765625, 122.47104644775, 1453.1505126953)
				elseif Lv == 775 or Lv <= 799 or SelectMonster == "Swan Pirate [Lv. 775]" then -- Swan Pirate
					Ms = "Swan Pirate [Lv. 775]"
					NameQuest = "Area2Quest"
					QuestLv = 1
					NameMon = "Swan Pirate"
					CFrameQ = CFrame.new(635.61151123047, 73.096351623535, 917.81298828125)
					CFrameMon = CFrame.new(1065.3669433594, 137.64012145996, 1324.3798828125)
				elseif Lv == 800 or Lv <= 874 or SelectMonster == "Factory Staff [Lv. 800]" then -- Factory Staff
					Ms = "Factory Staff [Lv. 800]"
					NameQuest = "Area2Quest"
					QuestLv = 2
					NameMon = "Factory Staff"
					CFrameQ = CFrame.new(635.61151123047, 73.096351623535, 917.81298828125)
					CFrameMon = CFrame.new(533.22045898438, 128.46876525879, 355.62615966797)
				elseif Lv == 875 or Lv <= 899 or SelectMonster == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant
					Ms = "Marine Lieutenant [Lv. 875]"
					NameQuest = "MarineQuest3"
					QuestLv = 1
					NameMon = "Marine Lieutenant"
					CFrameQ = CFrame.new(-2440.9934082031, 73.04190826416, -3217.7082519531)
					CFrameMon = CFrame.new(-2489.2622070313, 84.613594055176, -3151.8830566406)
				elseif Lv == 900 or Lv <= 949 or SelectMonster == "Marine Captain [Lv. 900]" then -- Marine Captain
					Ms = "Marine Captain [Lv. 900]"
					NameQuest = "MarineQuest3"
					QuestLv = 2
					NameMon = "Marine Captain"
					CFrameQ = CFrame.new(-2440.9934082031, 73.04190826416, -3217.7082519531)
					CFrameMon = CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406)
					if Lv >= 925 then
						_G.SelectBoss = "Fajita [Lv. 925] [Boss]"
					end
				elseif Lv == 950 or Lv <= 974 or SelectMonster == "Zombie [Lv. 950]" then -- Zombie
					Ms = "Zombie [Lv. 950]"
					NameQuest = "ZombieQuest"
					QuestLv = 1
					NameMon = "Zombie"
					CFrameQ = CFrame.new(-5494.3413085938, 48.505931854248, -794.59094238281)
					CFrameMon = CFrame.new(-5536.4970703125, 101.08577728271, -835.59075927734)
				elseif Lv == 975 or Lv <= 999 or SelectMonster == "Vampire [Lv. 975]" then -- Vampire
					Ms = "Vampire [Lv. 975]"
					NameQuest = "ZombieQuest"
					QuestLv = 2
					NameMon = "Vampire"
					CFrameQ = CFrame.new(-5494.3413085938, 48.505931854248, -794.59094238281)
					CFrameMon = CFrame.new(-5806.1098632813, 16.722528457642, -1164.4384765625)
				elseif Lv == 1000 or Lv <= 1049 or SelectMonster == "Snow Trooper [Lv. 1000]" then -- Snow Trooper
					Ms = "Snow Trooper [Lv. 1000]"
					NameQuest = "SnowMountainQuest"
					QuestLv = 1
					NameMon = "Snow Trooper"
					CFrameQ = CFrame.new(607.05963134766, 401.44781494141, -5370.5546875)
					CFrameMon = CFrame.new(535.21051025391, 432.74209594727, -5484.9165039063)
				elseif Lv == 1050 or Lv <= 1099 or SelectMonster == "Winter Warrior [Lv. 1050]" then -- Winter Warrior
					Ms = "Winter Warrior [Lv. 1050]"
					NameQuest = "SnowMountainQuest"
					QuestLv = 2
					NameMon = "Winter Warrior"
					CFrameQ = CFrame.new(607.05963134766, 401.44781494141, -5370.5546875)
					CFrameMon = CFrame.new(1234.4449462891, 456.95419311523, -5174.130859375)
				elseif Lv == 1100 or Lv <= 1124 or SelectMonster == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate
					Ms = "Lab Subordinate [Lv. 1100]"
					NameQuest = "IceSideQuest"
					QuestLv = 1
					NameMon = "Lab Subordinate"
					CFrameQ = CFrame.new(-6061.841796875, 15.926671981812, -4902.0385742188)
					CFrameMon = CFrame.new(-5720.5576171875, 63.309471130371, -4784.6103515625)
				elseif Lv == 1125 or Lv <= 1174 or SelectMonster == "Horned Warrior [Lv. 1125]" then -- Horned Warrior
					Ms = "Horned Warrior [Lv. 1125]"
					NameQuest = "IceSideQuest"
					QuestLv = 2
					NameMon = "Horned Warrior"
					CFrameQ = CFrame.new(-6061.841796875, 15.926671981812, -4902.0385742188)
					CFrameMon = CFrame.new(-6292.751953125, 91.181983947754, -5502.6499023438)
				elseif Lv == 1175 or Lv <= 1199 or SelectMonster == "Magma Ninja [Lv. 1175]" then -- Magma Ninja
					Ms = "Magma Ninja [Lv. 1175]"
					NameQuest = "FireSideQuest"
					QuestLv = 1
					NameMon = "Magma Ninja"
					CFrameQ = CFrame.new(-5429.0473632813, 15.977565765381, -5297.9614257813)
					CFrameMon = CFrame.new(-5461.8388671875, 130.36347961426, -5836.4702148438)
				elseif Lv == 1200 or Lv <= 1249 or SelectMonster == "Lava Pirate [Lv. 1200]" then -- Lava Pirate
					Ms = "Lava Pirate [Lv. 1200]"
					NameQuest = "FireSideQuest"
					QuestLv = 2
					NameMon = "Lava Pirate"
					CFrameQ = CFrame.new(-5429.0473632813, 15.977565765381, -5297.9614257813)
					CFrameMon = CFrame.new(-5251.1889648438, 55.164535522461, -4774.4096679688)
				elseif Lv == 1250 or Lv <= 1274 or SelectMonster == "Ship Deckhand [Lv. 1250]" then -- Ship Deckhand
					Ms = "Ship Deckhand [Lv. 1250]"
					NameQuest = "ShipQuest1"
					QuestLv = 1
					NameMon = "Ship Deckhand"
					CFrameQ = CFrame.new(1040.2927246094, 125.08293151855, 32911.0390625)
					CFrameMon = CFrame.new(921.12365722656, 125.9839553833, 33088.328125)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				elseif Lv == 1275 or Lv <= 1299 or SelectMonster == "Ship Engineer [Lv. 1275]" then -- Ship Engineer
					Ms = "Ship Engineer [Lv. 1275]"
					NameQuest = "ShipQuest1"
					QuestLv = 2
					NameMon = "Ship Engineer"
					CFrameQ = CFrame.new(1040.2927246094, 125.08293151855, 32911.0390625)
					CFrameMon = CFrame.new(886.28179931641, 40.47790145874, 32800.83203125)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				elseif Lv == 1300 or Lv <= 1324 or SelectMonster == "Ship Steward [Lv. 1300]" then -- Ship Steward
					Ms = "Ship Steward [Lv. 1300]"
					NameQuest = "ShipQuest2"
					QuestLv = 1
					NameMon = "Ship Steward"
					CFrameQ = CFrame.new(971.42065429688, 125.08293151855, 33245.54296875)
					CFrameMon = CFrame.new(943.85504150391, 129.58183288574, 33444.3671875)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				elseif Lv == 1325 or Lv <= 1349 or SelectMonster == "Ship Officer [Lv. 1325]" then -- Ship Officer
					Ms = "Ship Officer [Lv. 1325]"
					NameQuest = "ShipQuest2"
					QuestLv = 2
					NameMon = "Ship Officer"
					CFrameQ = CFrame.new(971.42065429688, 125.08293151855, 33245.54296875)
					CFrameMon = CFrame.new(955.38458251953, 181.08335876465, 33331.890625)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				elseif Lv == 1350 or Lv <= 1374 or SelectMonster == "Arctic Warrior [Lv. 1350]" then -- Arctic Warrior
					Ms = "Arctic Warrior [Lv. 1350]"
					NameQuest = "FrostQuest"
					QuestLv = 1
					NameMon = "Arctic Warrior"
					CFrameQ = CFrame.new(5668.1372070313, 28.202531814575, -6484.6005859375)
					CFrameMon = CFrame.new(5935.4541015625, 77.26016998291, -6472.7568359375)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
					end
				elseif Lv == 1375 or Lv <= 1424 or SelectMonster == "Snow Lurker [Lv. 1375]" then -- Snow Lurker
					Ms = "Snow Lurker [Lv. 1375]"
					NameQuest = "FrostQuest"
					QuestLv = 2
					NameMon = "Snow Lurker"
					CFrameQ = CFrame.new(5668.1372070313, 28.202531814575, -6484.6005859375)
					CFrameMon = CFrame.new(5628.482421875, 57.574996948242, -6618.3481445313)
				elseif Lv == 1425 or Lv <= 1449 or SelectMonster == "Sea Soldier [Lv. 1425]" then -- Sea Soldier
					Ms = "Sea Soldier [Lv. 1425]"
					NameQuest = "ForgottenQuest"
					QuestLv = 1
					NameMon = "Sea Soldier"
					CFrameQ = CFrame.new(-3054.5827636719, 236.87213134766, -10147.790039063)
					CFrameMon = CFrame.new(-3185.0153808594, 58.789089202881, -9663.6064453125)
				elseif Lv >= 1450 or SelectMonster == "Water Fighter [Lv. 1450]" then -- Water Fighter
					Ms = "Water Fighter [Lv. 1450]"
					NameQuest = "ForgottenQuest"
					QuestLv = 2
					NameMon = "Water Fighter"
					CFrameQ = CFrame.new(-3054.5827636719, 236.87213134766, -10147.790039063)
					CFrameMon = CFrame.new(-3262.9301757813, 298.69036865234, -10552.529296875)
				end
			end
			if Three_World then
				if Lv == 1500 or Lv <= 1524 or SelectMonster == "Pirate Millionaire [Lv. 1500]" then -- Pirate Millionaire
					Ms = "Pirate Millionaire [Lv. 1500]"
					NameQuest = "PiratePortQuest"
					QuestLv = 1
					NameMon = "Pirate Millionaire"
					CFrameQ = CFrame.new(-289.61752319336, 43.819011688232, 5580.0903320313)
					CFrameMon = CFrame.new(-435.68109130859, 189.69866943359, 5551.0756835938)
				elseif Lv == 1525 or Lv <= 1574 or SelectMonster == "Pistol Billionaire [Lv. 1525]" then -- Pistol Billoonaire
					Ms = "Pistol Billionaire [Lv. 1525]"
					NameQuest = "PiratePortQuest"
					QuestLv = 2
					NameMon = "Pistol Billionaire"
					CFrameQ = CFrame.new(-289.61752319336, 43.819011688232, 5580.0903320313)
					CFrameMon = CFrame.new(-236.53652954102, 217.46676635742, 6006.0883789063)
				elseif Lv == 1575 or Lv <= 1599 or SelectMonster == "Dragon Crew Warrior [Lv. 1575]" then -- Dragon Crew Warrior
					Ms = "Dragon Crew Warrior [Lv. 1575]"
					NameQuest = "AmazonQuest"
					QuestLv = 1
					NameMon = "Dragon Crew Warrior"
					CFrameQ = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
					CFrameMon = CFrame.new(6301.9975585938, 104.77153015137, -1082.6075439453)
				elseif Lv == 1600 or Lv <= 1624 or SelectMonster == "Dragon Crew Archer [Lv. 1600]" then -- Dragon Crew Archer
					Ms = "Dragon Crew Archer [Lv. 1600]"
					NameQuest = "AmazonQuest"
					QuestLv = 2
					NameMon = "Dragon Crew Archer"
					CFrameQ = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
					CFrameMon = CFrame.new(6831.1171875, 441.76708984375, 446.58615112305)
				elseif Lv == 1625 or Lv <= 1649 or SelectMonster == "Female Islander [Lv. 1625]" then -- Female Islander
					Ms = "Female Islander [Lv. 1625]"
					NameQuest = "AmazonQuest2"
					QuestLv = 1
					NameMon = "Female Islander"
					CFrameQ = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
					CFrameMon = CFrame.new(5792.5166015625, 848.14392089844, 1084.1818847656)
				elseif Lv == 1650 or Lv <= 1699 or SelectMonster == "Giant Islander [Lv. 1650]" then -- Giant Islander
					Ms = "Giant Islander [Lv. 1650]"
					NameQuest = "AmazonQuest2"
					QuestLv = 2
					NameMon = "Giant Islander"
					CFrameQ = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
					CFrameMon = CFrame.new(5009.5068359375, 664.11071777344, -40.960144042969)
				elseif Lv == 1700 or Lv <= 1724 or SelectMonster == "Marine Commodore [Lv. 1700]" then -- Marine Commodore
					Ms = "Marine Commodore [Lv. 1700]"
					NameQuest = "MarineTreeIsland"
					QuestLv = 1
					NameMon = "Marine Commodore"
					CFrameQ = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
					CFrameMon = CFrame.new(2198.0063476563, 128.71075439453, -7109.5043945313)
				elseif Lv == 1725 or Lv <= 1774 or SelectMonster == "Marine Rear Admiral [Lv. 1725]" then -- Marine Rear Admiral
					Ms = "Marine Rear Admiral [Lv. 1725]"
					NameQuest = "MarineTreeIsland"
					QuestLv = 2
					NameMon = "Marine Rear Admiral"
					CFrameQ = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
					CFrameMon = CFrame.new(3294.3142089844, 385.41125488281, -7048.6342773438)
				elseif Lv == 1775 or Lv <= 1799 or SelectMonster == "Fishman Raider [Lv. 1775]" then -- Fishman Raide
					Ms = "Fishman Raider [Lv. 1775]"
					NameQuest = "DeepForestIsland3"
					QuestLv = 1
					NameMon = "Fishman Raider"
					CFrameQ = CFrame.new(-10582.759765625, 331.78845214844, -8757.666015625)
					CFrameMon = CFrame.new(-10553.268554688, 521.38439941406, -8176.9458007813)
				elseif Lv == 1800 or Lv <= 1824 or SelectMonster == "Fishman Captain [Lv. 1800]" then -- Fishman Captain
					Ms = "Fishman Captain [Lv. 1800]"
					NameQuest = "DeepForestIsland3"
					QuestLv = 2
					NameMon = "Fishman Captain"
					CFrameQ = CFrame.new(-10583.099609375, 331.78845214844, -8759.4638671875)
					CFrameMon = CFrame.new(-10789.401367188, 427.18637084961, -9131.4423828125)
				elseif Lv == 1825 or Lv <= 1849 or SelectMonster == "Forest Pirate [Lv. 1825]" then -- Forest Pirate
					Ms = "Forest Pirate [Lv. 1825]"
					NameQuest = "DeepForestIsland"
					QuestLv = 1
					NameMon = "Forest Pirate"
					CFrameQ = CFrame.new(-13232.662109375, 332.40396118164, -7626.4819335938)
					CFrameMon = CFrame.new(-13489.397460938, 400.30349731445, -7770.251953125)
				elseif Lv == 1850 or Lv <= 1899 or SelectMonster == "Mythological Pirate [Lv. 1850]" then -- Mythological Pirate
					Ms = "Mythological Pirate [Lv. 1850]"
					NameQuest = "DeepForestIsland"
					QuestLv = 2
					NameMon = "Mythological Pirate"
					CFrameQ = CFrame.new(-13232.662109375, 332.40396118164, -7626.4819335938)
					CFrameMon = CFrame.new(-13508.616210938, 582.46228027344, -6985.3037109375)
				elseif Lv >= 1900 and Lv <= 1924 or SelectMonster == "Jungle Pirate [Lv. 1900]" then -- Jungle Pirate
					Ms = "Jungle Pirate [Lv. 1900]"
					NameQuest = "DeepForestIsland2"
					QuestLv = 1
					NameMon = "Jungle Pirate"
					CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
					CFrameMon = CFrame.new(-12267.103515625, 459.75262451172, -10277.200195313)
				elseif Lv >= 1925 and Lv <= 1974 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then -- Musketeer Pirate
					Ms = "Musketeer Pirate [Lv. 1925]"
					NameQuest = "DeepForestIsland2"
					QuestLv = 2
					NameMon = "Musketeer Pirate"
					CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
					CFrameMon = CFrame.new(-13291.5078125, 520.47338867188, -9904.638671875)
				elseif Lv >= 1975 and Lv <= 1999 or SelectMonster == "Reborn Skeleton [Lv. 1975]" then -- Reborn Skeleton
					Ms = "Musketeer Pirate [Lv. 1925]"
					NameQuest = "DeepForestIsland2"
					QuestLv = 2
					NameMon = "Musketeer Pirate"
					CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
					CFrameMon = CFrame.new(-13291.5078125, 520.47338867188, -9904.638671875)
				elseif Lv >= 2000 and Lv <= 2024 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Living Zombie
					Ms = "Living Zombie [Lv. 2000]"
					NameQuest = "HauntedQuest1"
					QuestLv = 2
					NameMon = "Living Zombie"
					CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
					CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
				elseif Lv >= 2025 and Lv <= 2049 or SelectMonster == "Demonic Soul [Lv. 2025]" then -- Demonic Soul
					Ms = "Demonic Soul [Lv. 2025]"
					NameQuest = "HauntedQuest1"
					QuestLv = 1
					NameMon = "Demonic Souls"
					CFrameQ = CFrame.new(-9515.39551, 172.266037, 6078.89746)
					CFrameMon = CFrame.new(-9709.30762, 204.695892, 6044.04688)
				elseif Lv >= 2050 and Lv <= 2074 or SelectMonster == "Posessed Mummy [Lv. 2050]" then -- Posessed Mummy
					Ms = "Posessed Mummy [Lv. 2050]"
					NameQuest = "HauntedQuest2"
					QuestLv = 2
					NameMon = "Posessed Mummys"
					CFrameQ = CFrame.new(-9515.39551, 172.266037, 6078.89746)
					CFrameMon = CFrame.new(-9554.11035, 65.6141663, 6041.73584)
				elseif Lv >= 2075 and Lv <= 2099 or SelectMonster == "Peanut Scout [Lv. 2075]" then -- Peanut Scout
					Ms = "Peanut Scout [Lv. 2075]"
					NameQuest = "PeanutQuest1"
					QuestLv = 1
					NameMon = "Peanut Scout"
					CFrameQ = CFrame.new(-2104.453125, 38.129974365234, -10194.0078125)
					CFrameMon = CFrame.new(-2068.0949707031, 76.512603759766, -10117.150390625)
				elseif Lv >= 2100 and Lv <= 2124 or SelectMonster == "Peanut President [Lv. 2100]" then -- Peanut President
					Ms = "Peanut President [Lv. 2100]"
					NameQuest = "PeanutQuest2"
					QuestLv = 2
					NameMon = "Peanut Presidents"
					CFrameQ = CFrame.new(-2104.453125, 38.129974365234, -10194.0078125)
					CFrameMon = CFrame.new(-2067.33203125, 90.557350158691, -10552.051757812)
				elseif Lv >= 2125 and Lv <= 2149 or SelectMonster == "Ice Cream Chef [Lv. 2125]" then --Ice Cream Chef
					Ms = "Ice Cream Chef [Lv. 2125]"
					NameQuest = "IceCreamQuest1"
					QuestLv = 1
					NameMon = "	Ice Cream Chefs"
					CFrameQ = CFrame.new(-821.35913085938, 65.845329284668, -10965.2578125)
					CFrameMon = CFrame.new(-796.37261962891, 110.95275878906, -10847.473632812)
				elseif Lv >= 2150 and Lv <= 2200 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then -- Ice Cream Commander
					Ms = "Ice Cream Commander [Lv. 2150]"
					NameQuest = "IceCreamIslandQuest"
					QuestLv = 2
					NameMon = "Ice Cream Commanders"
					CFrameQ = CFrame.new(-821.35913085938, 65.845329284668, -10965.2578125)
					CFrameMon = CFrame.new(-697.65338134766, 174.48368835449, -11218.38671875)
				elseif Lv >= 2200 and Lv <= 2250 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then -- Ice Cream Commander
					Ms = "Cookie Crafter [Lv. 2200]"
					NameQuest = "CakeQuest1"
					QuestLv = 1
					NameMon = "Cookie Crafters"
					CFrameQ = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
					CFrameMon = CFrame.new(-2358.5791015625, 36.85615539550781, -12111.052734375)
				elseif Lv >= 2225 or SelectMonster == "Cake Guard [Lv. 2225]" then
					Ms = "Cake Guard [Lv. 2225]"
					NameQuest = "CakeQuest1"
					QuestLv = 2
					NameMon = "Cake Guards"
					CFrameMon = CFrame.new(-1430.4925537109375, 36.85621643066406, -12322.162109375)
					CFrameQ = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
				end
			end
		end

		function CheckLevel2()
			local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
			if _G.Upto then
				Lv = Lv + 100
			end
			if Old_World and not Auto_Raid then
				if Lv == 1 or Lv <= 9 or SelectMonster == "" then -- Bandit
					Ms = "Bandit [Lv. 5]"
					NameQuest = "BanditQuest1"
					QuestLv = 1
					NameMon = "Bandit"
					CFrameQ = CFrame.new(1059.37195, 15.4495068, 1550.4231, 0.939700544, -0, -0.341998369, 0, 1, -0, 0.341998369, 0, 0.939700544)
					CFrameMon = CFrame.new(1353.44885, 3.40935516, 1376.92029, 0.776053488, -6.97791975e-08, 0.630666852, 6.99138596e-08, 1, 2.4612488e-08, -0.630666852, 2.49917598e-08, 0.776053488)
					TelePBoss(CFrameQ)
				elseif Lv == 10 or Lv <= 14 or SelectMonster == "Monkey [Lv. 14]" then -- Monkey
					 
					Ms = "Monkey [Lv. 14]"
					NameQuest = "JungleQuest"
					QuestLv = 1
					NameMon = "Monkey"
					CFrameQ = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(-1402.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
					TelePBoss(CFrameQ)
					
				elseif Lv == 15 or Lv <= 29 or SelectMonster == "Gorilla [Lv. 20]" then -- Gorilla
					Ms = "Gorilla [Lv. 20]"
					NameQuest = "JungleQuest"
					QuestLv = 2
					NameMon = "Gorilla"
					CFrameQ = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(-1267.89001, 66.2034225, -531.818115, -0.813996196, -5.25169774e-08, -0.580869019, -5.58769671e-08, 1, -1.21082593e-08, 0.580869019, 2.26011476e-08, -0.813996196)
					TelePBoss(CFrameQ)
					if Lv >= 25 then
						_G.SelectBoss = "The Gorilla King [Lv. 25] [Boss]" 
					end
					SelectMonster = "Monkey [Lv. 14]"
				elseif Lv >= 30 and Lv <= 40-1 or SelectMonster == "Pirate [Lv. 35]" then
					 
					Ms = "Pirate [Lv. 35]"
					NameQuest = "BuggyQuest1"
					QuestLv = 1
					NameMon = "Pirate"
					CFrameQ = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(-1169.5365, 5.09531212, 3933.84082, -0.971822679, -3.73200315e-09, 0.235713184, -4.16762763e-10, 1, 1.41145424e-08, -0.235713184, 1.3618596e-08, -0.971822679)
					TelePBoss(CFrameQ)
					
				elseif Lv >= 40 and Lv <= 60-1 or SelectMonster == "Brute [Lv. 45]" then
					
					Ms = "Brute [Lv. 45]"
					NameQuest = "BuggyQuest1"
					QuestLv = 2
					NameMon = "Brute"
					CFrameQ = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(-1165.09985, 15.1531372, 4363.51514, -0.962800264, 1.17564889e-06, 0.270213336, 2.60172015e-07, 1, -3.4237969e-06, -0.270213336, -3.22613073e-06, -0.962800264)
					TelePBoss(CFrameQ)
					if Lv >= 55 then
						_G.SelectBoss = "Bobby [Lv. 55] [Boss]"
					end
					SelectMonster = "Pirate [Lv. 35]"
				elseif Lv >= 60 and Lv <= 75-1 or SelectMonster == "Desert Bandit [Lv. 60]" then
					 
					Ms = "Desert Bandit [Lv. 60]"
					NameQuest = "DesertQuest"
					QuestLv = 1
					NameMon = "Desert Bandit"
					CFrameQ = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
					CFrameMon = CFrame.new(932.788818, 6.8503746, 4488.24609, -0.998625934, 3.08948351e-08, 0.0524050146, 2.79967303e-08, 1, -5.60361286e-08, -0.0524050146, -5.44919629e-08, -0.998625934)
					TelePBoss(CFrameQ)
					
				elseif Lv >= 75 and Lv <= 100-1 or SelectMonster == "Desert Officer [Lv. 70]" then
					Ms = "Desert Officer [Lv. 70]"
					NameQuest = "DesertQuest"
					QuestLv = 2
					NameMon = "Desert Officer"
					CFrameQ = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
					CFrameMon = CFrame.new(1617.07886, 1.5542295, 4295.54932, -0.997540116, -2.26287735e-08, -0.070099175, -1.69377223e-08, 1, -8.17798806e-08, 0.070099175, -8.03913949e-08, -0.997540116)
					TelePBoss(CFrameQ)
					SelectMonster = "Desert Bandit [Lv. 60]"
				elseif SelectMonster == "Snow Bandit [Lv. 90]" then -- Snow Bandits
					Ms = "Snow Bandit [Lv. 90]"
					NameQuest = "SnowQuest"
					QuestLv = 1
					NameMon = "Snow Bandits"
					CFrameQ = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
					CFrameMon = CFrame.new(1412.92346, 55.3503647, -1260.62036, -0.246266365, -0.0169920288, -0.969053388, 0.000432241941, 0.999844253, -0.0176417865, 0.969202161, -0.00476344163, -0.246220857)
					TelePBoss(CFrameQ)
					
				elseif Lv == 100 or Lv <= 119 or SelectMonster == "Snowman [Lv. 100]" then -- Snowman
					
					Ms = "Snowman [Lv. 100]"
					NameQuest = "SnowQuest"
					QuestLv = 2
					NameMon = "Snowman"
					CFrameQ = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
					CFrameMon = CFrame.new(1376.86401, 97.2779999, -1396.93115, -0.986755967, 7.71178321e-08, -0.162211925, 7.71531674e-08, 1, 6.08143536e-09, 0.162211925, -6.51427134e-09, -0.986755967)
					TelePBoss(CFrameQ)
					if Lv >= 110 then
						_G.SelectBoss = "Yeti [Lv. 110] [Boss]"
					end
					SelectMonster = "Snow Bandit [Lv. 90]"
					_G.Farm_Mon = true
				elseif Lv == 120 or Lv <= 174 or SelectMonster == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
					Ms = "Chief Petty Officer [Lv. 120]"
					NameQuest = "MarineQuest2"
					QuestLv = 1
					NameMon = "Chief Petty Officer"
					CFrameQ = CFrame.new(-5039.58643, 27.3500385, 4324.68018, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
					TelePBoss(CFrameQ)
					if Lv >= 130 then
						_G.SelectBoss = "Vice Admiral [Lv. 130] [Boss]"
					end
					
				elseif SelectMonster == "Sky Bandit [Lv. 150]" then -- Sky Bandit
					Ms = "Sky Bandit [Lv. 150]"
					NameQuest = "SkyQuest"
					QuestLv = 1
					NameMon = "Sky Bandit"
					CFrameQ = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-4959.51367, 365.39267, -2974.56812, 0.964867651, 7.74418396e-08, 0.262737453, -6.95931988e-08, 1, -3.91783708e-08, -0.262737453, 1.95171506e-08, 0.964867651)
					TelePBoss(CFrameQ)
					
				elseif Lv == 175 or Lv <= 209 or SelectMonster == "Dark Master [Lv. 175]" then -- Dark Master
					 
					Ms = "Dark Master [Lv. 175]"
					NameQuest = "SkyQuest"
					QuestLv = 2
					NameMon = "Dark Master"
					CFrameQ = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-5079.98096, 376.477356, -2194.17139, 0.465965867, -3.69776352e-08, 0.884802461, 3.40249851e-09, 1, 4.00000886e-08, -0.884802461, -1.56281423e-08, 0.465965867)
					TelePBoss(CFrameQ)
					SelectMonster = "Sky Bandit [Lv. 150]"
				elseif SelectMonster == "Prisoner [Lv. 190]" then
					 
					Ms = "Prisoner [Lv. 190]"
					QuestLv = 1
					NameQuest = "PrisonerQuest"
					NameMon = "Prisoner"
					CFrameQ = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
					CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
					TelePBoss(CFrameQ)
					
				elseif Lv == 210 or Lv <= 249 or SelectMonster == "Dangerous Prisoner [Lv. 210]" then
					 
					Ms = "Dangerous Prisoner [Lv. 210]"
					QuestLv = 2
					NameQuest = "PrisonerQuest"
					NameMon = "Dangerous Prisoner"
					CFrameQ = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
					CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
					TelePBoss(CFrameQ)
					if Lv >= 240 then
						_G.SelectBoss = "Swan [Lv. 240] [Boss]"
						
					elseif Lv >= 230 then
						_G.SelectBoss = "Chief Warden [Lv. 230] [Boss]"
						
					elseif Lv >= 220 then
						_G.SelectBoss = "Warden [Lv. 220] [Boss]"
					end
					SelectMonster = "Prisoner [Lv. 190]"
				elseif Lv == 250 or Lv <= 274 or SelectMonster == "Toga Warrior [Lv. 250]" then -- Toga Warrior
					 
					Ms = "Toga Warrior [Lv. 250]"
					NameQuest = "ColosseumQuest"
					QuestLv = 1
					NameMon = "Toga Warrior"
					CFrameQ = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
					CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
					TelePBoss(CFrameQ)
					
				elseif Lv == 275 or Lv <= 324 or SelectMonster == "Gladiator [Lv. 275]" then -- Gladiato
					 
					Ms = "Gladiator [Lv. 275]"
					NameQuest = "ColosseumQuest"
					QuestLv = 2
					NameMon = "Gladiato"
					CFrameQ = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
					CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
					TelePBoss(CFrameQ)
					SelectMonster = "Toga Warrior [Lv. 250]"
				elseif SelectMonster == "Military Soldier [Lv. 300]" then -- Military Soldier
					 
					Ms = "Military Soldier [Lv. 300]"
					NameQuest = "MagmaQuest"
					QuestLv = 1
					NameMon = "Military Soldier"
					CFrameQ = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
					CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
					TelePBoss(CFrameQ)
					
				elseif Lv == 325 or Lv <= 374 or SelectMonster == "Military Spy [Lv. 325]" then -- Military Spy
					 
					Ms = "Military Spy [Lv. 325]"
					NameQuest = "MagmaQuest"
					QuestLv = 2
					NameMon = "Military Spy"
					CFrameQ = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
					CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
					TelePBoss(CFrameQ)
					if Lv >= 350 then
						_G.SelectBoss = "Magma Admiral [Lv. 350] [Boss]"
					end
					SelectMonster = "Military Soldier [Lv. 300]"
				elseif Lv == 375 or Lv <= 399 or SelectMonster == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior
					 
					Ms = "Fishman Warrior [Lv. 375]"
					NameQuest = "FishmanQuest"
					QuestLv = 1
					NameMon = "Fishman Warrior"
					CFrameQ = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
					CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						_G.Stop_Tween = true
						TP(CFrameQ)
						wait(.5)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
						wait(.5)
						_G.Stop_Tween = nil
					end
					
				elseif Lv == 400 or Lv <= 449 or SelectMonster == "Fishman Commando [Lv. 400]" then -- Fishman Commando
					 
					Ms = "Fishman Commando [Lv. 400]"
					NameQuest = "FishmanQuest"
					QuestLv = 2
					NameMon = "Fishman Commando"
					CFrameQ = CFrame.new(61122.5625, 18.4716396, 1568.16504)
					CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.916871)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						_G.Stop_Tween = true
						TP(CFrameQ)
						wait(.5)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
						wait(.5)
						_G.Stop_Tween = nil
					end
					if Lv >= 425 then
						_G.SelectBoss = "Fishman Lord [Lv. 425] [Boss]"
					end
					SelectMonster = "Fishman Warrior [Lv. 375]"
				elseif Lv == 450 or Lv <= 474 or SelectMonster == "God's Guard [Lv. 450]" then 
					Ms = "God's Guard [Lv. 450]"
					NameQuest = "SkyExp1Quest"
					QuestLv = 1
					NameMon = "God's Guards"
					CFrameQ = CFrame.new(-4721.71436, 845.277161, -1954.20105)
					CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.925427)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						_G.Stop_Tween = true
						TP(CFrameQ)
						wait(.5)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
						wait(.5)
						_G.Stop_Tween = nil
					end
					if Lv >= 425 then
						_G.SelectBoss = "Fishman Lord [Lv. 425] [Boss]"
					end
					SelectMonster = "Fishman Commando [Lv. 400]"
				elseif Lv == 475 or Lv <= 524 or SelectMonster == "Shanda [Lv. 475]" then
					Ms = "Shanda [Lv. 475]"
					NameQuest = "SkyExp1Quest"
					QuestLv = 2
					NameMon = "Shandas"
					CFrameQ = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998)
					CFrameMon = CFrame.new(-7904.57373, 5584.37646, -459.62973, 0.65171206, 5.11171692e-08, 0.758466363, -4.76232476e-09, 1, -6.33034247e-08, -0.758466363, 3.76435416e-08, 0.65171206)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
						_G.Stop_Tween = true
						TP(CFrameQ)
						wait(.5)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
						wait(.5)
						_G.Stop_Tween = nil
					end
					if Lv >= 500 then
						_G.SelectBoss = "Wysper [Lv. 500] [Boss]"
					end
					SelectMonster = "God's Guard [Lv. 450]"
				elseif Lv == 525 or Lv <= 549 or SelectMonster == "Royal Squad [Lv. 525]" then -- Royal Squad
					 
					Ms = "Royal Squad [Lv. 525]"
					NameQuest = "SkyExp2Quest"
					QuestLv = 1
					NameMon = "Royal Squad"
					CFrameQ = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-7555.04199, 5606.90479, -1303.24744, -0.896107852, -9.6057462e-10, -0.443836004, -4.24974544e-09, 1, 6.41599973e-09, 0.443836004, 7.63560326e-09, -0.896107852)
					TelePBoss(CFrameQ) 
					SelectMonster = "Shanda [Lv. 475]"
				elseif Lv == 550 or Lv <= 624 or SelectMonster == "Royal Soldier [Lv. 550]" then -- Royal Soldier
					 
					Ms = "Royal Soldier [Lv. 550]"
					NameQuest = "SkyExp2Quest"
					QuestLv = 2
					NameMon = "Royal Soldier"
					CFrameQ = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-7837.31152, 5649.65186, -1791.08582, -0.716008604, 0.0104285581, -0.698013008, 5.02521061e-06, 0.99988848, 0.0149335321, 0.69809103, 0.0106890313, -0.715928733)
					TelePBoss(CFrameQ)
					if Lv >= 575 then
						_G.SelectBoss = "Thunder God [Lv. 575] [Boss]"
					end
					SelectMonster = "Royal Squad [Lv. 525]"
				elseif Lv == 625 or Lv <= 649 or SelectMonster == "Galley Pirate [Lv. 625]" then -- Galley Pirate
					 
					Ms = "Galley Pirate [Lv. 625]"
					NameQuest = "FountainQuest"
					QuestLv = 1
					NameMon = "Galley Pirate"
					CFrameQ = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5569.80518, 38.5269432, 3849.01196, 0.896460414, 3.98027495e-08, 0.443124533, -1.34262139e-08, 1, -6.26611296e-08, -0.443124533, 5.02237434e-08, 0.896460414)
					TelePBoss(CFrameQ)
				elseif Lv >= 650 or SelectMonster == "Galley Captain [Lv. 650]" then -- Galley Captain
					 
					Ms = "Galley Captain [Lv. 650]"
					NameQuest = "FountainQuest"
					QuestLv = 2
					NameMon = "Galley Captain"
					CFrameQ = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5782.90186, 94.5326462, 4716.78174, 0.361808896, -1.24757526e-06, -0.932252586, 2.16989656e-06, 1, -4.96097414e-07, 0.932252586, -1.84339774e-06, 0.361808896)
					TelePBoss(CFrameQ)
					
					if Lv >= 675 then
						_G.SelectBoss = "Cyborg [Lv. 675] [Boss]"
					end
					SelectMonster = "Galley Pirate [Lv. 625]"
				end
			end
			if New_World and not Auto_Raid then
				 
				if Lv == 700 or Lv <= 724 or SelectMonster == "Raider [Lv. 700]" then -- Raider [Lv. 700]
					Ms = "Raider [Lv. 700]"
					NameQuest = "Area1Quest"
					QuestLv = 1
					NameMon = "Raider"
					CFrameQ = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
					CFrameMon = CFrame.new(-737.026123, 10.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
					TelePBoss(CFrameQ)
				elseif Lv == 725 or Lv <= 774 or SelectMonster == "Mercenary [Lv. 725]" then -- Mercenary [Lv. 725]
					Ms = "Mercenary [Lv. 725]"
					NameQuest = "Area1Quest"
					QuestLv = 2
					NameMon = "Mercenary"
					CFrameQ = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
					CFrameMon = CFrame.new(-1022.21271, 72.9855194, 1891.39148, -0.990782857, 0, -0.135460541, 0, 1, 0, 0.135460541, 0, -0.990782857)
					TelePBoss(CFrameQ)
					SelectMonster = "Raider [Lv. 700]"
				elseif Lv == 775 or Lv <= 799 or SelectMonster == "Swan Pirate [Lv. 775]" then -- Swan Pirate [Lv. 775]
					Ms = "Swan Pirate [Lv. 775]"
					NameQuest = "Area2Quest"
					QuestLv = 1
					NameMon = "Swan Pirate"
					CFrameQ = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
					CFrameMon = CFrame.new(976.467651, 111.174057, 1229.1084, 0.00852567982, -4.73897828e-08, -0.999963999, 1.12251888e-08, 1, -4.7295778e-08, 0.999963999, -1.08215579e-08, 0.00852567982)
					TelePBoss(CFrameQ)
				elseif Lv == 800 or Lv <= 874 or SelectMonster == "Factory Staff [Lv. 800]" then -- Factory Staff [Lv. 800]
					Ms = "Factory Staff [Lv. 800]"
					NameQuest = "Area2Quest"
					QuestLv = 2
					NameMon = "Factory Staff"
					CFrameQ = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
					CFrameMon = CFrame.new(336.74585, 73.1620483, -224.129272, 0.993632793, 3.40154607e-08, 0.112668738, -3.87658332e-08, 1, 3.99718729e-08, -0.112668738, -4.40850592e-08, 0.993632793)
					TelePBoss(CFrameQ)
					SelectMonster = "Swan Pirate [Lv. 775]"
				elseif Lv == 875 or Lv <= 899 or SelectMonster == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant [Lv. 875]
					Ms = "Marine Lieutenant [Lv. 875]"
					NameQuest = "MarineQuest3"
					QuestLv = 1
					NameMon = "Marine Lieutenant"
					CFrameQ = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-2842.69922, 72.9919434, -2901.90479, -0.762281299, 0, -0.64724648, 0, 1.00000012, 0, 0.64724648, 0, -0.762281299)
					TelePBoss(CFrameQ)
				elseif Lv == 900 or Lv <= 949 or SelectMonster == "Marine Captain [Lv. 900]" then -- Marine Captain [Lv. 900]
					Ms = "Marine Captain [Lv. 900]"
					NameQuest = "MarineQuest3"
					QuestLv = 2
					NameMon = "Marine Captain"
					CFrameQ = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-1814.70313, 72.9919434, -3208.86621, -0.900422215, 7.93464423e-08, -0.435017526, 3.68856199e-08, 1, 1.06050372e-07, 0.435017526, 7.94441988e-08, -0.900422215)
					TelePBoss(CFrameQ)
					SelectMonster = "Marine Lieutenant [Lv. 875]"
				elseif Lv == 950 or Lv <= 974 or SelectMonster == "Zombie [Lv. 950]" then -- Zombie [Lv. 950]
					Ms = "Zombie [Lv. 950]"
					NameQuest = "ZombieQuest"
					QuestLv = 1
					NameMon = "Zombie"
					CFrameQ = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
					CFrameMon = CFrame.new(-5649.23438, 126.0578, -737.773743, 0.355238914, -8.10359282e-08, 0.934775114, 1.65461245e-08, 1, 8.04023372e-08, -0.934775114, -1.3095117e-08, 0.355238914)
					TelePBoss(CFrameQ)
				elseif Lv == 975 or Lv <= 999 or SelectMonster == "Vampire [Lv. 975]" then -- Vampire [Lv. 975]
					Ms = "Vampire [Lv. 975]"
					NameQuest = "ZombieQuest"
					QuestLv = 2
					NameMon = "Vampire"
					CFrameQ = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
					CFrameMon = CFrame.new(-6030.32031, 0.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
					TelePBoss(CFrameQ)
					SelectMonster = "Zombie [Lv. 950]"
				elseif Lv == 1000 or Lv <= 1049 or SelectMonster == "Snow Trooper [Lv. 1000]" then -- Snow Trooper [Lv. 1000] **
					Ms = "Snow Trooper [Lv. 1000]"
					NameQuest = "SnowMountainQuest"
					QuestLv = 1
					NameMon = "Snow Trooper"
					CFrameQ = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
					CFrameMon = CFrame.new(621.003418, 391.361053, -5335.43604, 0.481644779, 0, 0.876366913, 0, 1, 0, -0.876366913, 0, 0.481644779)
					TelePBoss(CFrameQ)
				elseif Lv == 1050 or Lv <= 1099 or SelectMonster == "Winter Warrior [Lv. 1050]" then -- Winter Warrior [Lv. 1050]
					Ms = "Winter Warrior [Lv. 1050]"
					NameQuest = "SnowMountainQuest"
					QuestLv = 2
					NameMon = "Winter Warrior"
					CFrameQ = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
					CFrameMon = CFrame.new(1295.62683, 429.447784, -5087.04492, -0.698032081, -8.28980049e-08, -0.71606636, -1.98835952e-08, 1, -9.63858184e-08, 0.71606636, -5.30424877e-08, -0.698032081)
					TelePBoss(CFrameQ)
					SelectMonster = "Snow Trooper [Lv. 1000]"
				elseif Lv == 1100 or Lv <= 1124 or SelectMonster == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate [Lv. 1100]
					Ms = "Lab Subordinate [Lv. 1100]"
					NameQuest = "IceSideQuest"
					QuestLv = 1
					NameMon = "Lab Subordinate"
					CFrameQ = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
					CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
					TelePBoss(CFrameQ)
				elseif Lv == 1125 or Lv <= 1174 or SelectMonster == "Horned Warrior [Lv. 1125]" then -- Horned Warrior [Lv. 1125]
					Ms = "Horned Warrior [Lv. 1125]"
					NameQuest = "IceSideQuest"
					QuestLv = 2
					NameMon = "Horned Warrior"
					CFrameQ = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
					CFrameMon = CFrame.new(-6401.27979, 15.9775667, -5948.24316, 0.388303697, 0, -0.921531856, 0, 1, 0, 0.921531856, 0, 0.388303697)
					TelePBoss(CFrameQ)
					SelectMonster = "Lab Subordinate [Lv. 1100]"
				elseif Lv == 1175 or Lv <= 1199 or SelectMonster == "Magma Ninja [Lv. 1175]" then -- Magma Ninja [Lv. 1175]
					Ms = "Magma Ninja [Lv. 1175]"
					NameQuest = "FireSideQuest"
					QuestLv = 1
					NameMon = "Magma Ninja"
					CFrameQ = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-5466.06445, 57.6952019, -5837.42822, -0.988835871, 0, -0.149006829, 0, 1, 0, 0.149006829, 0, -0.988835871)
					TelePBoss(CFrameQ)
				elseif Lv == 1200 or Lv <= 1249 or SelectMonster == "Lava Pirate [Lv. 1200]" then 
					Ms = "Lava Pirate [Lv. 1200]"
					NameQuest = "FireSideQuest"
					QuestLv = 2
					NameMon = "Lava Pirate"
					CFrameQ = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
					CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
					TelePBoss(CFrameQ)
					SelectMonster = "Magma Ninja [Lv. 1175]"
				elseif Lv == 1250 or Lv <= 1274 or SelectMonster == "Ship Deckhand [Lv. 1250]" then 
					Ms = "Ship Deckhand [Lv. 1250]"
					NameQuest = "ShipQuest1"
					QuestLv = 1
					NameMon = "Ship Deckhand"
					CFrameQ = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
					CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				elseif Lv == 1275 or Lv <= 1299 or SelectMonster == "Ship Engineer [Lv. 1275]" then 
					Ms = "Ship Engineer [Lv. 1275]"
					NameQuest = "ShipQuest1"
					QuestLv = 2
					NameMon = "Ship Engineer"
					CFrameQ = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
					CFrameMon = CFrame.new(921.30249023438, 125.400390625, 32937.34375)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
					SelectMonster = "Ship Deckhand [Lv. 1250]"
				elseif Lv == 1300 or Lv <= 1324 or SelectMonster == "Ship Steward [Lv. 1300]" then 
					Ms = "Ship Steward [Lv. 1300]"
					NameQuest = "ShipQuest2"
					QuestLv = 1
					NameMon = "Ship Steward"
					CFrameQ = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
					CFrameMon = CFrame.new(917.96057128906, 136.89932250977, 33343.4140625)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
				elseif Lv == 1325 or Lv <= 1349 or SelectMonster == "Ship Officer [Lv. 1325]" then 
					Ms = "Ship Officer [Lv. 1325]"
					NameQuest = "ShipQuest2"
					QuestLv = 2
					NameMon = "Ship Officer"
					CFrameQ = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
					CFrameMon = CFrame.new(944.44964599609, 181.40081787109, 33278.9453125)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
					end
					SelectMonster = "Ship Steward [Lv. 1300]"
				elseif Lv == 1350 or Lv <= 1374 or SelectMonster == "Arctic Warrior [Lv. 1350]" then 
					Ms = "Arctic Warrior [Lv. 1350]"
					NameQuest = "FrostQuest"
					QuestLv = 1
					NameMon = "Arctic Warrior"
					CFrameQ = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
					CFrameMon = CFrame.new(5878.23486, 81.3886948, -6136.35596, -0.451037169, 2.3908234e-07, 0.892505825, -1.08168464e-07, 1, -3.22542007e-07, -0.892505825, -2.4201924e-07, -0.451037169)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
					end
				elseif Lv == 1375 or Lv <= 1424 or SelectMonster == "Snow Lurker [Lv. 1375]" then -- Snow Lurker [Lv. 1375]
					Ms = "Snow Lurker [Lv. 1375]"
					NameQuest = "FrostQuest"
					QuestLv = 2
					NameMon = "Snow Lurker"
					CFrameQ = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
					CFrameMon = CFrame.new(5513.36865, 60.546711, -6809.94971, -0.958693981, -1.65617333e-08, 0.284439981, -4.07668654e-09, 1, 4.44854642e-08, -0.284439981, 4.14883701e-08, -0.958693981)
					if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
					end
					SelectMonster = "Arctic Warrior [Lv. 1350]"
				elseif Lv == 1425 or Lv <= 1449 or SelectMonster == "Sea Soldier [Lv. 1425]" then -- Sea Soldier [Lv. 1425]
					Ms = "Sea Soldier [Lv. 1425]"
					NameQuest = "ForgottenQuest"
					QuestLv = 1
					NameMon = "Sea Soldier"
					CFrameQ = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
					CFrameMon = CFrame.new(-3115.78223, 63.8785706, -9808.38574, -0.913427353, 3.11199457e-08, 0.407000452, 7.79564235e-09, 1, -5.89660658e-08, -0.407000452, -5.06883708e-08, -0.913427353)
					TelePBoss(CFrameQ)
				elseif Lv >= 1450 or SelectMonster == "Water Fighter [Lv. 1450]" then -- Water Fighter [Lv. 1450]
					Ms = "Water Fighter [Lv. 1450]"
					NameQuest = "ForgottenQuest"
					QuestLv = 2
					NameMon = "Water Fighter"
					CFrameQ = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
					CFrameMon = CFrame.new(-3212.99683, 263.809296, -10551.8799, 0.742111444, -5.59139615e-08, -0.670276582, 1.69155214e-08, 1, -6.46908234e-08, 0.670276582, 3.66697037e-08, 0.742111444)
					TelePBoss(CFrameQ)
					SelectMonster = "Sea Soldier [Lv. 1425]"
					if Lv >= 1475 then
						_G.SelectBoss = "Tide Keeper [Lv. 1475] [Boss]"
					end
				end
			end
			if Three_World and not Auto_Raid then
				if Lv >= 1500 and Lv <= 1524 or SelectMonster == "Pirate Millionaire [Lv. 1500]" then -- Pirate Millionaire [Lv. 1500]
					Ms = "Pirate Millionaire [Lv. 1500]"
					NameQuest = "PiratePortQuest"
					QuestLv = 1
					NameMon = "Pirate Millionaire"
					CFrameQ = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
					TelePBoss(CFrameQ)
				elseif Lv >= 1525 and Lv <= 1574 or SelectMonster == "Pistol Billionaire [Lv. 1525]" then -- Pistol Billionaire [Lv. 1525]
					Ms = "Pistol Billionaire [Lv. 1525]"
					NameQuest = "PiratePortQuest"
					QuestLv = 2
					NameMon = "Pistol Billionaire"
					CFrameQ = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
					TelePBoss(CFrameQ)
					SelectMonster = "Pirate Millionaire [Lv. 1500]"
				elseif Lv >= 1575 and Lv <= 1599 or SelectMonster == "Dragon Crew Warrior [Lv. 1575]" then -- Dragon Crew Warrior [Lv. 1575]
					Ms = "Dragon Crew Warrior [Lv. 1575]"
					NameQuest = "AmazonQuest"
					QuestLv = 1
					NameMon = "Dragon Crew Warrior"
					CFrameQ = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
					CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
					TelePBoss(CFrameQ)
				elseif Lv >= 1600 and Lv <= 1624 or SelectMonster == "Dragon Crew Archer [Lv. 1600]" then -- Dragon Crew Archer [Lv. 1600]
					Ms = "Dragon Crew Archer [Lv. 1600]"
					NameQuest = "AmazonQuest"
					QuestLv = 2
					NameMon = "Dragon Crew Archer"
					CFrameQ = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
					CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
					TelePBoss(CFrameQ)
					SelectMonster = "Dragon Crew Warrior [Lv. 1575]"
				elseif Lv >= 1625 and Lv <= 1649 or SelectMonster == "Female Islander [Lv. 1625]" then -- Female Islander [Lv. 1625]
					Ms = "Female Islander [Lv. 1625]"
					NameQuest = "AmazonQuest2"
					QuestLv = 1
					NameMon = "Female Islander"
					CFrameQ = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
					TelePBoss(CFrameQ)
				elseif Lv >= 1650 and Lv <= 1699 or SelectMonster == "Giant Islander [Lv. 1650]" then -- Giant Islander [Lv. 1650]
					Ms = "Giant Islander [Lv. 1650]"
					NameQuest = "AmazonQuest2"
					QuestLv = 2
					NameMon = "Giant Islander"
					CFrameQ = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
					TelePBoss(CFrameQ)
					SelectMonster = "Female Islander [Lv. 1625]"
				elseif Lv >= 1700 and Lv <= 1724 or SelectMonster == "Marine Commodore [Lv. 1700]" then -- Marine Commodore [Lv. 1700]
					Ms = "Marine Commodore [Lv. 1700]"
					NameQuest = "MarineTreeIsland"
					QuestLv = 1
					NameMon = "Marine Commodore"
					CFrameQ = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
					CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
					TelePBoss(CFrameQ)
				elseif Lv >= 1725 and Lv <= 1774 or SelectMonster == "Marine Rear Admiral [Lv. 1725]" then -- Marine Rear Admiral [Lv. 1725]
					Ms = "Marine Rear Admiral [Lv. 1725]"
					NameQuest = "MarineTreeIsland"
					QuestLv = 2
					NameMon = "Marine Rear Admiral"
					CFrameQ = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
					CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
					TelePBoss(CFrameQ)
					SelectMonster = "Marine Commodore [Lv. 1700]"
				elseif Lv >= 1775 and Lv <= 1799 or SelectMonster == "Fishman Raider [Lv. 1775]" then -- Fishman Raider [Lv. 1775]
					Ms = "Fishman Raider [Lv. 1775]"
					NameQuest = "DeepForestIsland3"
					QuestLv = 1
					NameMon = "Fishman Raider"
					CFrameQ = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
					TelePBoss(CFrameQ)
				elseif Lv >= 1800 and Lv <= 1824 or SelectMonster == "Fishman Captain [Lv. 1800]" then -- Fishman Captain [Lv. 1800]
					Ms = "Fishman Captain [Lv. 1800]"
					NameQuest = "DeepForestIsland3"
					QuestLv = 2
					NameMon = "Fishman Captain"
					CFrameQ = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
					TelePBoss(CFrameQ)
					SelectMonster = "Fishman Raider [Lv. 1775]"
				elseif Lv >= 1825 and Lv <= 1849 or SelectMonster == "Forest Pirate [Lv. 1825]" then -- Forest Pirate [Lv. 1825]
					Ms = "Forest Pirate [Lv. 1825]"
					NameQuest = "DeepForestIsland"
					QuestLv = 1
					NameMon = "Forest Pirate"
					CFrameQ = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
					CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
					TelePBoss(CFrameQ)
				elseif Lv >= 1850 and Lv <= 1899 or SelectMonster == "Mythological Pirate [Lv. 1850]" then -- Mythological Pirate [Lv. 1850]
					Ms = "Mythological Pirate [Lv. 1850]"
					NameQuest = "DeepForestIsland"
					QuestLv = 2
					NameMon = "Mythological Pirate"
					CFrameQ = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
					CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
					TelePBoss(CFrameQ)
					SelectMonster = "Forest Pirate [Lv. 1825]"
				elseif Lv >= 1900 and Lv <= 1924 or SelectMonster == "Jungle Pirate [Lv. 1900]" then -- Jungle Pirate [Lv. 1900]
					Ms = "Jungle Pirate [Lv. 1900]"
					NameQuest = "DeepForestIsland2"
					QuestLv = 1
					NameMon = "Jungle Pirate"
					CFrameQ = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
					CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
					TelePBoss(CFrameQ)
				elseif Lv >= 1925 and Lv <= 1974 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then -- Musketeer Pirate [Lv. 1925]
					Ms = "Musketeer Pirate [Lv. 1925]"
					NameQuest = "DeepForestIsland2"
					QuestLv = 2
					NameMon = "Musketeer Pirate"
					CFrameQ = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
					CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
					TelePBoss(CFrameQ)
					SelectMonster = "Jungle Pirate [Lv. 1900]"
				elseif Lv >= 1975 and Lv <= 1999 or SelectMonster == "Reborn Skeleton [Lv. 1975]" then
					Ms = "Reborn Skeleton [Lv. 1975]"
					NameQuest = "HauntedQuest1"
					QuestLv = 1
					NameMon = "Reborn Skeleton"
					CFrameQ = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
					CFrameMon = CFrame.new(-8817.880859375, 191.16761779785, 6298.6557617188)
					TelePBoss(CFrameQ)
				elseif Lv >= 2000 and Lv <= 2024 or SelectMonster == "Living Zombie [Lv. 2000]" then
					Ms = "Living Zombie [Lv. 2000]"
					NameQuest = "HauntedQuest1"
					QuestLv = 2
					NameMon = "Living Zombie"
					CFrameQ = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
					CFrameMon = CFrame.new(-10125.234375, 183.94705200195, 6242.013671875)
					TelePBoss(CFrameQ)
					SelectMonster = "Reborn Skeleton [Lv. 1975]"
				elseif Lv >= 2025 and Lv <= 2049  or  SelectMonster == "Demonic Soul [Lv. 2025]" then
					Ms = "Demonic Soul [Lv. 2025]"
					NameQuest = "HauntedQuest2"
					QuestLv = 1
					NameMon = "Demonic"
					CFrameQ = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
					CFrameMon = CFrame.new(-9712.03125, 204.69589233398, 6193.322265625)
					TelePBoss(CFrameQ)
					SelectMonster = "Living Zombie [Lv. 2000]"
				elseif Lv >= 2050 and Lv <= 2074 or SelectMonster == "Posessed Mummy [Lv. 2050]" then
					Ms = "Posessed Mummy [Lv. 2050]"
					NameQuest = "HauntedQuest2"
					QuestLv = 2
					NameMon = "Posessed Mummy"
					CFrameQ = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
					CFrameMon = CFrame.new(-9545.7763671875, 69.619895935059, 6339.5615234375)    
					TelePBoss(CFrameQ)
					SelectMonster = "Demonic Soul [Lv. 2025]"
				elseif Lv >= 2075 and Lv <= 2099 or SelectMonster == "Peanut Scout [Lv. 2075]" then
					Ms = "Peanut Scout [Lv. 2075]"
					NameQuest = "NutsIslandQuest"
					QuestLv = 1
					NameMon = "Peanut Scout"
					CFrameQ = CFrame.new(-2104.17163, 38.1299706, -10194.418, 0.758814394, -1.38604395e-09, 0.651306927, 2.85280208e-08, 1, -3.1108879e-08, -0.651306927, 4.21863646e-08, 0.758814394)
					CFrameMon = CFrame.new(-2098.07544, 192.611862, -10248.8867, 0.983392298, -9.57031787e-08, 0.181492642, 8.7276355e-08, 1, 5.44169616e-08, -0.181492642, -3.76732068e-08, 0.983392298)
					TelePBoss(CFrameQ)
				elseif Lv >= 2100 and Lv <= 2124 or SelectMonster == "Peanut President [Lv. 2100]" then
					Ms = "Peanut President [Lv. 2100]"
					NameQuest = "NutsIslandQuest"
					QuestLv = 2
					NameMon = "Peanut President"
					CFrameQ = CFrame.new(-2104.17163, 38.1299706, -10194.418, 0.758814394, -1.38604395e-09, 0.651306927, 2.85280208e-08, 1, -3.1108879e-08, -0.651306927, 4.21863646e-08, 0.758814394)
					CFrameMon = CFrame.new(-1876.95959, 192.610947, -10542.2939, 0.0553516336, -2.83836812e-08, 0.998466909, -6.89634405e-10, 1, 2.84654931e-08, -0.998466909, -2.26418861e-09, 0.0553516336)
					SelectMonster = "Peanut Scout [Lv. 2075]"
					TelePBoss(CFrameQ)
				elseif Lv >= 2125 and Lv <= 2149 or SelectMonster == "Ice Cream Chef [Lv. 2125]" then
					Ms = "Ice Cream Chef [Lv. 2125]"
					NameQuest = "IceCreamIslandQuest"
					QuestLv = 1
					NameMon = "Ice Cream Chef"
					CFrameQ = CFrame.new(-820.404358, 65.8453293, -10965.5654, 0.822534859, 5.24448502e-08, -0.568714678, -2.08336317e-08, 1, 6.20846663e-08, 0.568714678, -3.92184099e-08, 0.822534859)
					CFrameMon = CFrame.new(-821.614075, 208.39537, -10990.7617, -0.870096624, 3.18909272e-08, 0.492881238, -1.8357893e-08, 1, -9.71107568e-08, -0.492881238, -9.35439957e-08, -0.870096624)
					TelePBoss(CFrameQ)
				elseif Lv >= 2150 and Lv <= 2199 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then 
					Ms = "Ice Cream Commander [Lv. 2150]"
					NameQuest = "IceCreamIslandQuest"
					QuestLv = 2
					NameMon = "Ice Cream Commander"
					CFrameQ = CFrame.new(-819.376526, 67.4634171, -10967.2832)
					CFrameMon = CFrame.new(-610.11669921875, 208.26904296875, -11253.686523438)
					TelePBoss(CFrameQ)
					SelectMonster = "Ice Cream Chef [Lv. 2125]"
				elseif Lv >= 2200 and Lv <= 2224 or SelectMonster == "Cookie Crafter [Lv. 2200]" then 
					Ms = "Cookie Crafter [Lv. 2200]"
					NameQuest = "CakeQuest1"
					QuestLv = 1
					NameMon = "Cookie Crafter"
					CFrameQ = CFrame.new(-2020.6068115234375, 37.82400894165039, -12027.80859375)
					CFrameMon = CFrame.new(-2286.684326171875, 146.5656280517578, -12226.8818359375)
					TelePBoss(CFrameQ)
				elseif Lv >= 2225 and Lv <= 2249 or SelectMonster == "Cake Guard [Lv. 2225]" then 
					Ms = "Cake Guard [Lv. 2225]"
					NameQuest = "CakeQuest1"
					QuestLv = 2
					NameMon = "Cake Guard"
					CFrameQ = CFrame.new(-2020.6068115234375, 37.82400894165039, -12027.80859375)
					CFrameMon = CFrame.new(-1817.9747314453125, 209.5632781982422, -12288.9228515625)
					SelectMonster = "Cookie Crafter [Lv. 2200]"
					TelePBoss(CFrameQ)
				elseif Lv >= 2250 or SelectMonster == "Baking Staff [Lv. 2250]" then 
					Ms = "Baking Staff [Lv. 2250]"
					NameQuest = "CakeQuest2"
					QuestLv = 1
					NameMon = "Baking Staff"
					CFrameQ = CFrame.new(-1928.31763, 37.7296638, -12840.626)
					CFrameMon = CFrame.new(-1818.347900390625, 93.41275787353516, -12887.66015625)
					TelePBoss(CFrameQ)
				end
			end
		end

		function TP(P1)
			if not _G.Stop_Tween then
				local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
				Speed = 100
				if Distance < 250 then
					Speed = 5000
				elseif Distance < 500 then
					Speed = 650
				elseif Distance < 1000 then
					Speed = 350
				elseif Distance >= 1000 then
					Speed = 250
				end
				Tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),{CFrame = P1})
				if _G.Stop_Tween or Auto_Raid then
					Tween:Cancel()
				elseif game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
					Tween:Play()
				end
			end
		end
		
function TP3(P1)
	local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
	if Distance < 250 then
		Speed = 10000
	elseif Distance < 500 then
		Speed = 500
	elseif Distance < 1000 then
		Speed = 250
	elseif Distance >= 1000 then
		Speed = 250
	end
	game:GetService("TweenService"):Create(
		game.Players.LocalPlayer.Character.HumanoidRootPart,
		TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
		{CFrame = P1}
	):Play()
	if _G.Stop_Tween then
		game:GetService("TweenService"):Create(
		game.Players.LocalPlayer.Character.HumanoidRootPart,
		TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
			{CFrame = P1}
		):Cancel()
	end
end

function TP2(P1)
	local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
	if Distance < 150 then
		Speed = 5000
	elseif Distance < 200 then
		Speed = 1500
	elseif Distance < 300 then
		Speed = 800
	elseif Distance < 500 then
		Speed = 500
	elseif Distance < 1000 then
		Speed = 250
	elseif Distance >= 1000 then
		Speed = 250
	end
	game:GetService("TweenService"):Create(
		game.Players.LocalPlayer.Character.HumanoidRootPart,
		TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
		{CFrame = P1}
	):Play()
	if _G.Stop_Tween then
		game:GetService("TweenService"):Create(
		game.Players.LocalPlayer.Character.HumanoidRootPart,
		TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
			{CFrame = P1}
		):Cancel()
	end
	_G.Clip = true
	wait(Distance/Speed)
	_G.Clip = false
end

function EquipWeapon(ToolSe)
	if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
		local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
		wait(.4)
		game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
	end
end

spawn(function()
    while wait(.1) do
        pcall(function()
            if _G.Clip or Auto_Farm_Bounty or Auto_Twin_Hooks or Auto_Canvander or Auto_Buddy_Sword or Auto_Hallow_Scryte or Auto_Spikey_Trident or Auto_Dark_Dagger or Auto_Serpent_Bow or Auto_Acidum_Rifle or Auto_Swan_Glass or Auto_Pale_Scarf or Auto_Valkyrie_Helmet or Saber_Farm or Pole_Farm or Rengoku_A or Auto_Dragon_Trident or Triple_A or Auto_Yama or Auto_Tushita or Auto_Dark_Coat or _G.Setting_table.Human_Evo or _G.Setting_table.Mink_Evo or _G.Setting_table.Death_Step or _G.Setting_table.Sharkman_Karate or _G.Setting_table.Electric_Claw or _G.Setting_table.Dragon_Talon or _G.Setting_table.Superhuman or Auto_Three_World or Bartlio_Farm or Auto_New_A or Auto_Elite_Hunter or Auto_Phoenix_Awaken or Auto_Raid or _G.Setting_table.Farm_Ken_Hop or _G.Setting_table.Auto_Farm_Boss_Hop or _G.Setting_table.Auto_Farm_Boss_All_Hop or Open_Color_Haki or Auto_Holy_Torch or Grab_Chest or Auto_Farm_Monster or Farm_Ken or Auto_Farm_Bone or Farm_Ken_V2 or Auto_Farm_Melee or Auto_Farm_Sword or Auto_Farm or Auto_Farm_Gun or Auto_Farm_Boss_All or Auto_Farm_Boss or Auto_Farm_Fruit then
				if game.Players.LocalPlayer.Character.Humanoid.Sit == true then
					game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
					wait(5)
				end
				PIO = false
                if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") then 
					local L_1 = Instance.new("BodyVelocity")
                    L_1.Name = "BodyGyrozz"
                    L_1.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart 
                    L_1.MaxForce=Vector3.new(1000000000,1000000000,1000000000)
                    L_1.Velocity=Vector3.new(0,0,0) 
                end
            elseif PIO == false then
				for i,v in pairs(game.Players.LocalPlayer.Character.HumanoidRootPart:GetChildren()) do
					if v.Name == "BodyGyrozz" then
						v:Destroy()
						PIO = true
					end
				end
            end
        end)
    end
end)

IKAI = true
if IKAI then
	do
		local ui = game.CoreGui:FindFirstChild("RippleHUBLIB")
		if ui then
			ui:Destroy()
		end
	end
	
	local UserInputService = game:GetService("UserInputService")
	local TweenService = game:GetService("TweenService")
	local RunService = game:GetService("RunService")
	local LocalPlayer = game:GetService("Players").LocalPlayer
	local Mouse = LocalPlayer:GetMouse()
	local tween = game:GetService("TweenService")
	local Red = {RainbowColorValue = 0, HueSelectionPosition = 0}
	local LogoButton = [[7040391851]]
	
	
	local function Tween(instance, properties,style,wa)
		if style == nil or "" then
			return Back
		end
		tween:Create(instance,TweenInfo.new(wa,Enum.EasingStyle[style]),{properties}):Play()
	end
	
	local ActualTypes = {
		RoundFrame = "ImageLabel",
		Shadow = "ImageLabel",
		Circle = "ImageLabel",
		CircleButton = "ImageButton",
		Frame = "Frame",
		Label = "TextLabel",
		Button = "TextButton",
		SmoothButton = "ImageButton",
		Box = "TextBox",
		ScrollingFrame = "ScrollingFrame",
		Menu = "ImageButton",
		NavBar = "ImageButton"
	}
	
	local Properties = {
		RoundFrame = {
			BackgroundTransparency = 1,
			Image = "http://www.roblox.com/asset/?id=5554237731",
			ScaleType = Enum.ScaleType.Slice,
			SliceCenter = Rect.new(3,3,297,297)
		},
		SmoothButton = {
			AutoButtonColor = false,
			BackgroundTransparency = 1,
			Image = "http://www.roblox.com/asset/?id=5554237731",
			ScaleType = Enum.ScaleType.Slice,
			SliceCenter = Rect.new(3,3,297,297)
		},
		Shadow = {
			Name = "Shadow",
			BackgroundTransparency = 1,
			Image = "http://www.roblox.com/asset/?id=5554236805",
			ScaleType = Enum.ScaleType.Slice,
			SliceCenter = Rect.new(23,23,277,277),
			Size = UDim2.fromScale(1,1) + UDim2.fromOffset(30,30),
			Position = UDim2.fromOffset(-15,-15)
		},
		Circle = {
			BackgroundTransparency = 1,
			Image = "http://www.roblox.com/asset/?id=5554831670"
		},
		CircleButton = {
			BackgroundTransparency = 1,
			AutoButtonColor = false,
			Image = "http://www.roblox.com/asset/?id=5554831670"
		},
		Frame = {
			BackgroundTransparency = 1,
			BorderSizePixel = 0,
			Size = UDim2.fromScale(1,1)
		},
		Label = {
			BackgroundTransparency = 1,
			Position = UDim2.fromOffset(5,0),
			Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
			TextSize = 14,
			TextXAlignment = Enum.TextXAlignment.Left
		},
		Button = {
			BackgroundTransparency = 1,
			Position = UDim2.fromOffset(5,0),
			Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
			TextSize = 14,
			TextXAlignment = Enum.TextXAlignment.Left
		},
		Box = {
			BackgroundTransparency = 1,
			Position = UDim2.fromOffset(5,0),
			Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
			TextSize = 14,
			TextXAlignment = Enum.TextXAlignment.Left
		},
		ScrollingFrame = {
			BackgroundTransparency = 1,
			ScrollBarThickness = 0,
			CanvasSize = UDim2.fromScale(0,0),
			Size = UDim2.fromScale(1,1)
		},
		Menu = {
			Name = "More",
			AutoButtonColor = false,
			BackgroundTransparency = 1,
			Image = "http://www.roblox.com/asset/?id=5555108481",
			Size = UDim2.fromOffset(20,20),
			Position = UDim2.fromScale(1,0.5) - UDim2.fromOffset(25,10)
		},
		NavBar = {
			Name = "SheetToggle",
			Image = "http://www.roblox.com/asset/?id=5576439039",
			BackgroundTransparency = 1,
			Size = UDim2.fromOffset(20,20),
			Position = UDim2.fromOffset(5,5),
			AutoButtonColor = false
		}
	}
	
	local Types = {
		"RoundFrame",
		"Shadow",
		"Circle",
		"CircleButton",
		"Frame",
		"Label",
		"Button",
		"SmoothButton",
		"Box",
		"ScrollingFrame",
		"Menu",
		"NavBar"
	}
	
	function FindType(String)
		for _, Type in next, Types do
			if Type:sub(1, #String):lower() == String:lower() then
				return Type
			end
		end
		return false
	end
	
	local Objects = {}
	
	function Objects.new(Type)
		local TargetType = FindType(Type)
		if TargetType then
			local NewImage = Instance.new(ActualTypes[TargetType])
			if Properties[TargetType] then
				for Property, Value in next, Properties[TargetType] do
					NewImage[Property] = Value
				end
			end
			return NewImage
		else
			return Instance.new(Type)
		end
	end
	
	local function GetXY(GuiObject)
		local Max, May = GuiObject.AbsoluteSize.X, GuiObject.AbsoluteSize.Y
		local Px, Py = math.clamp(Mouse.X - GuiObject.AbsolutePosition.X, 0, Max), math.clamp(Mouse.Y - GuiObject.AbsolutePosition.Y, 0, May)
		return Px/Max, Py/May
	end
	
	local function CircleAnim(GuiObject, EndColour, StartColour)
		local PX, PY = GetXY(GuiObject)
		local Circle = Objects.new("Circle")
		Circle.Size = UDim2.fromScale(0,0)
		Circle.Position = UDim2.fromScale(PX,PY)
		Circle.ImageColor3 = StartColour or GuiObject.ImageColor3
		Circle.ZIndex = 200
		Circle.Parent = GuiObject
		local Size = GuiObject.AbsoluteSize.X
		TweenService:Create(Circle, TweenInfo.new(0.5), {Position = UDim2.fromScale(PX,PY) - UDim2.fromOffset(Size/2,Size/2), ImageTransparency = 1, ImageColor3 = EndColour, Size = UDim2.fromOffset(Size,Size)}):Play()
		spawn(function()
			wait(0.5)
			Circle:Destroy()
		end)
	end
	
	
	local function MakeDraggable(topbarobject, object)
		local Dragging = nil
		local DragInput = nil
		local DragStart = nil
		local StartPosition = nil
	
		local function Update(input)
			local Delta = input.Position - DragStart
			local pos =
				UDim2.new(
					StartPosition.X.Scale,
					StartPosition.X.Offset + Delta.X,
					StartPosition.Y.Scale,
					StartPosition.Y.Offset + Delta.Y
				)
			local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
			Tween:Play()
		end
	
		topbarobject.InputBegan:Connect(
			function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
					Dragging = true
					DragStart = input.Position
					StartPosition = object.Position
	
					input.Changed:Connect(
						function()
							if input.UserInputState == Enum.UserInputState.End then
								Dragging = false
							end
						end
					)
				end
			end
		)
	
		topbarobject.InputChanged:Connect(
			function(input)
				if
					input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch
				then
					DragInput = input
				end
			end
		)
	
		UserInputService.InputChanged:Connect(
			function(input)
				if input == DragInput and Dragging then
					Update(input)
				end
			end
		)
	end
	
	library = {}
	
	function library:Window(text,text2,text3,logo,keybind)
		local uihide = false
		local abc = false
		local logo = logo or 0
		local currentpage = ""
		local keybind = keybind or Enum.KeyCode.RightControl
		local yoo = string.gsub(tostring(keybind),"Enum.KeyCode.","")
		
		local RippleHUBLIB = Instance.new("ScreenGui")
		RippleHUBLIB.Name = "RippleHUBLIB"
		RippleHUBLIB.Parent = game.CoreGui
		RippleHUBLIB.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	
		local Main = Instance.new("Frame")
		Main.Name = "Main"
		Main.Parent = RippleHUBLIB
		Main.ClipsDescendants = true
		Main.AnchorPoint = Vector2.new(0.5,0.5)
		Main.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
		Main.Position = UDim2.new(0.5, 0, 0.5, 0)
		Main.Size = UDim2.new(0, 0, 0, 0)
		
		Main:TweenSize(UDim2.new(0, 656, 0, 300),"Out","Quad",0.4,true)
	
		local MCNR = Instance.new("UICorner")
		MCNR.Name = "MCNR"
		MCNR.Parent = Main
	
	
		local Top = Instance.new("Frame")
		Top.Name = "Top"
		Top.Parent = Main
		Top.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
		Top.Size = UDim2.new(0, 656, 0, 27)
	
		local TCNR = Instance.new("UICorner")
		TCNR.Name = "TCNR"
		TCNR.Parent = Top
	
		local Logo = Instance.new("ImageLabel")
		Logo.Name = "Logo"
		Logo.Parent = Top
		Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Logo.BackgroundTransparency = 1.000
		Logo.Position = UDim2.new(0, 14, 0, 2)
		Logo.Size = UDim2.new(0, 23, 0, 23)
		Logo.Image = "rbxassetid://"..tostring(logo)
	
		local Name = Instance.new("TextLabel")
		Name.Name = "Name"
		Name.Parent = Top
		Name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Name.BackgroundTransparency = 1.000
		Name.Position = UDim2.new(0.0609756112, 5, 0, 0.5)
		Name.Size = UDim2.new(0, 61, 0, 27)
		Name.Font = Enum.Font.GothamSemibold
		Name.Text = text
		Name.TextColor3 = Color3.fromRGB(225, 225, 225)
		Name.TextSize = 16.000
	
		local Hub = Instance.new("TextLabel")
		Hub.Name = "Hub"
		Hub.Parent = Top
		Hub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Hub.BackgroundTransparency = 1.000
		Hub.Position = UDim2.new(0, 105, 0, 0.5)
		Hub.Size = UDim2.new(0, 81, 0, 27)
		Hub.Font = Enum.Font.GothamSemibold
		Hub.Text = text2
		Hub.TextColor3 = _G.Color
		Hub.TextSize = 16.000
		Hub.TextXAlignment = Enum.TextXAlignment.Left
	
		local Ver = Instance.new("TextLabel")
		Ver.Name = "Ver"
		Ver.Parent = Top
		Ver.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Ver.BackgroundTransparency = 1.000
		Ver.Position = UDim2.new(0.847561002, 0, 0, 1)
		Ver.Size = UDim2.new(0, 47, 0, 27)
		Ver.Font = Enum.Font.GothamSemibold
		Ver.Text = text3
		Ver.TextColor3 = _G.Color
		Ver.TextSize = 15.000
	
	
		local BindButton = Instance.new("TextButton")
		BindButton.Name = "BindButton"
		BindButton.Parent = Top
		BindButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		BindButton.BackgroundTransparency = 1.000
		BindButton.Position = UDim2.new(0.227561002, 0, 0, 1)
		BindButton.Size = UDim2.new(0, 100, 0, 27)
		BindButton.Font = Enum.Font.GothamSemibold
		BindButton.Text = "[ "..string.gsub(tostring(keybind),"Enum.KeyCode.","").." ]"
		BindButton.TextColor3 = Color3.fromRGB(100, 100, 100)
		BindButton.TextSize = 11.000
		
		BindButton.MouseButton1Click:Connect(function ()
			BindButton.Text = "[ ... ]"
			local inputwait = game:GetService("UserInputService").InputBegan:wait()
			local shiba = inputwait.KeyCode == Enum.KeyCode.Unknown and inputwait.UserInputType or inputwait.KeyCode
	
			if shiba.Name ~= "Focus" and shiba.Name ~= "MouseMovement" then
				BindButton.Text = "[ "..shiba.Name.." ]"
				yoo = shiba.Name
			end
		end)
	
		do  local ui =  game:GetService("CoreGui"):FindFirstChild("Ripple")  if ui then ui:Destroy() end end
	
	
		local Luna = Instance.new("ScreenGui")
		local ToggleFrameUi = Instance.new("Frame")
		local UICorner = Instance.new("UICorner")
		local ToggleImgUi = Instance.new("ImageLabel")
		local Uitoggle = Instance.new("TextLabel")
		local Yedhee = Instance.new("TextLabel")
		local SearchStroke = Instance.new("UIStroke")
		
		
		Luna.Name = "Ripple"
		Luna.Parent = game.CoreGui
		Luna.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
		
		ToggleFrameUi.Name = "ToggleFrameUi"
		ToggleFrameUi.Parent = Luna
		ToggleFrameUi.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
		ToggleFrameUi.Position = UDim2.new(0.883, -60,0.282, 0)
		ToggleFrameUi.Size = UDim2.new(0, 198, 0, 48)
		
		SearchStroke.Thickness = 1
		SearchStroke.Name = ""
		SearchStroke.Parent = ToggleFrameUi
		SearchStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
		SearchStroke.LineJoinMode = Enum.LineJoinMode.Round
		SearchStroke.Color = _G.Color
		SearchStroke.Transparency = 0
		
		UICorner.CornerRadius = UDim.new(0, 4)
		UICorner.Parent = ToggleFrameUi
		
		ToggleImgUi.Name = "ToggleImgUi"
		ToggleImgUi.Parent = ToggleFrameUi
		ToggleImgUi.BackgroundColor3 = Color3.fromRGB(5, 5, 5)
		ToggleImgUi.BackgroundTransparency = 1
		ToggleImgUi.Position = UDim2.new(0.0454545468, 0, 0.125000313, 0)
		ToggleImgUi.Size = UDim2.new(0, 35, 0, 35)
		ToggleImgUi.Image = "rbxassetid://9606070311"
		-- http://www.roblox.com/asset/?id=9605991378
		Uitoggle.Name = "Uitoggle"
		Uitoggle.Parent = ToggleFrameUi
		Uitoggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Uitoggle.BackgroundTransparency = 1.000
		Uitoggle.Position = UDim2.new(0.25757575, 0, 0, 0)
		Uitoggle.Size = UDim2.new(0, 137, 0, 25)
		Uitoggle.Font = Enum.Font.GothamSemibold
		Uitoggle.Text = "Ui Toggle :"
		Uitoggle.TextColor3 = Color3.fromRGB(255, 255, 255)
		Uitoggle.TextSize = 12.000
		
		Yedhee.Name = "Yedhee"
		Yedhee.Parent = ToggleFrameUi
		Yedhee.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Yedhee.BackgroundTransparency = 1.000
		Yedhee.Position = UDim2.new(0.25757575, 0, 0.479166657, 0)
		Yedhee.Size = UDim2.new(0, 137, 0, 25)
		Yedhee.Font = Enum.Font.GothamSemibold
		Yedhee.Text = "Lable"
		Yedhee.TextColor3 = Color3.fromRGB(255, 255, 255)
		Yedhee.TextSize = 12.000
		spawn(function()
			while wait() do
				Yedhee.Text = '['..yoo..']'
			end
		end)
	
	do  local ui =  game:GetService("CoreGui"):FindFirstChild("RippleFPS")  if ui then ui:Destroy() end 
	local uix =  game:GetService("CoreGui"):FindFirstChild("Rippletime")  if uix then uix:Destroy() end end
	
	
	local RippleFPS = Instance.new("ScreenGui")
	local Rippletime = Instance.new("ScreenGui")
	local Framefps = Instance.new("Frame")
	local Frametime = Instance.new("Frame")
	local UICorner213 = Instance.new("UICorner")
	local UICorner214 = Instance.new("UICorner")
	local TextLabelfps = Instance.new("TextLabel")
	local TextLabeltime = Instance.new("TextLabel")
	local ImageLabelfps = Instance.new("ImageLabel")
	local ImageLabeltime = Instance.new("ImageLabel")
	local Strokefps = Instance.new("UIStroke")
	local Stroketime = Instance.new("UIStroke")
	
	RippleFPS.Name = "RippleFPS"
	RippleFPS.Parent = game.CoreGui
	RippleFPS.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	
	Rippletime.Name = "Rippletime"
	Rippletime.Parent = game.CoreGui
	Rippletime.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	
	Framefps.Name = "Framefps"
	Framefps.Parent = RippleFPS
	Framefps.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Framefps.BorderSizePixel = 0
	Framefps.Position = UDim2.new(0.010, 0, 0.21084006, 0)
	Framefps.Size = UDim2.new(0, 193, 0, 44)
	
	UICorner213.CornerRadius = UDim.new(0, 4)
	UICorner213.Parent = Framefps
	
	Strokefps.Thickness = 1
	Strokefps.Name = ""
	Strokefps.Parent = Framefps
	Strokefps.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	Strokefps.LineJoinMode = Enum.LineJoinMode.Round
	Strokefps.Color = _G.Color
	Strokefps.Transparency = 0
	
	Frametime.Name = "Frametime"
	Frametime.Parent = Rippletime
	Frametime.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Frametime.BorderSizePixel = 0
	Frametime.Position = UDim2.new(0.010, 0, 0.11084006, 0)
	Frametime.Size = UDim2.new(0, 293, 0, 44)
	
	UICorner214.CornerRadius = UDim.new(0, 4)
	UICorner214.Parent = Frametime
	
	Stroketime.Thickness = 1
	Stroketime.Name = ""
	Stroketime.Parent = Frametime
	Stroketime.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	Stroketime.LineJoinMode = Enum.LineJoinMode.Round
	Stroketime.Color = _G.Color
	Stroketime.Transparency = 0
	
	TextLabelfps.Name = "TextLabelfps"
	TextLabelfps.Parent = Framefps
	TextLabelfps.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextLabelfps.BackgroundTransparency = 1.000
	TextLabelfps.Position = UDim2.new(0.356857866, 0, 0.234848887, 0)
	TextLabelfps.Size = UDim2.new(0, 124, 0, 23)
	TextLabelfps.Font = Enum.Font.GothamSemibold
	TextLabelfps.Text = "FPS:N/A"
	TextLabelfps.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabelfps.TextSize = 14.000
	TextLabelfps.TextXAlignment = Enum.TextXAlignment.Left
	
	TextLabeltime.Name = "TextLabeltime"
	TextLabeltime.Parent = Frametime
	TextLabeltime.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextLabeltime.BackgroundTransparency = 1.000
	TextLabeltime.Position = UDim2.new(0.356857866, 0, 0.234848887, 0)
	TextLabeltime.Size = UDim2.new(0, -35, 0, 23)
	TextLabeltime.Font = Enum.Font.GothamSemibold
	TextLabeltime.Text = "FPS:N/A"
	TextLabeltime.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabeltime.TextSize = 14.000
	TextLabeltime.TextXAlignment = Enum.TextXAlignment.Left
	
	spawn(function()
		while wait() do
			pcall(function()
				local scripttime=game.Workspace.DistributedGameTime
				local seconds = scripttime%60
				local minutes = math.floor(scripttime/60%60)
				local hours = math.floor(scripttime/3600)
				local tempo = string.format("%.0f Hour , %.0f Minute , %.0f Second", hours ,minutes, seconds)
				TextLabeltime.Text = tempo
			end)
		end
	end)
	
	spawn(function()
		while wait() do
			pcall(function()
				TextLabelfps.Text = "FPS:"..string.format("%d",workspace:GetRealPhysicsFPS())
			end)
		end
	end)
	
	ImageLabelfps.Name = "ImageLabelfps"
	ImageLabelfps.Parent = Framefps
	ImageLabelfps.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ImageLabelfps.BackgroundTransparency = 1.000
	ImageLabelfps.Position = UDim2.new(0.083989636, 0, 0.15545856, 0)
	ImageLabelfps.Size = UDim2.new(0, 29, 0, 29)
	ImageLabelfps.Image = "rbxassetid://9606070311"
	
	ImageLabeltime.Name = "ImageLabeltime"
	ImageLabeltime.Parent = Frametime
	ImageLabeltime.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ImageLabeltime.BackgroundTransparency = 1.000
	ImageLabeltime.Position = UDim2.new(0.083989636, -9, 0.15545856, 0)
	ImageLabeltime.Size = UDim2.new(0, 29, 0, 29)
	ImageLabeltime.Image = "rbxassetid://9606070311"
	
	
	Framefps.MouseEnter:Connect(function()
		TweenService:Create(
			Framefps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{BackgroundTransparency = 1}
		):Play()
		TweenService:Create(
			Strokefps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{Transparency = 1}
		):Play()
		TweenService:Create(
			TextLabelfps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{TextTransparency = 1}
		):Play()
		TweenService:Create(
			ImageLabelfps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{ImageTransparency = 1}
		):Play()
	end)
	Framefps.MouseLeave:Connect(function()
		TweenService:Create(
			Framefps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{BackgroundTransparency = 0}
		):Play()
		TweenService:Create(
			Strokefps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{Transparency = 0}
		):Play()
		TweenService:Create(
			TextLabelfps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{TextTransparency = 0}
		):Play()
		TweenService:Create(
			ImageLabelfps,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{ImageTransparency = 0}
		):Play()
	end)
	
	Frametime.MouseEnter:Connect(function()
		TweenService:Create(
			Frametime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{BackgroundTransparency = 1}
		):Play()
		TweenService:Create(
			Stroketime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{Transparency = 1}
		):Play()
		TweenService:Create(
			TextLabeltime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{TextTransparency = 1}
		):Play()
		TweenService:Create(
			ImageLabeltime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{ImageTransparency = 1}
		):Play()
	end)
	Frametime.MouseLeave:Connect(function()
		TweenService:Create(
			Frametime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{BackgroundTransparency = 0}
		):Play()
		TweenService:Create(
			Stroketime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{Transparency = 0}
		):Play()
		TweenService:Create(
			TextLabeltime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{TextTransparency = 0}
		):Play()
		TweenService:Create(
			ImageLabeltime,
			TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{ImageTransparency = 0}
		):Play()
	end)
	
	Yedhee.TextTransparency = 1
		Uitoggle.TextTransparency = 1
		ToggleImgUi.ImageTransparency = 1
		ToggleFrameUi.BackgroundTransparency = 1.000
		SearchStroke.Transparency = 1
		TweenService:Create(
			Framefps,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{BackgroundTransparency = 1}
		):Play()
		TweenService:Create(
			Strokefps,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{Transparency = 1}
		):Play()
		TweenService:Create(
			TextLabelfps,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{TextTransparency = 1}
		):Play()
		TweenService:Create(
			ImageLabelfps,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{ImageTransparency = 1}
		):Play()
	
		UserInputService.InputBegan:Connect(function(input)
			if input.KeyCode == Enum.KeyCode[yoo] then
				if uihide == false then
					ToggleFrameUi:TweenSize(UDim2.new(0, 198, 0, 48),"In","Quad",0.2,true)
					game:GetService("TweenService"):Create(
						ToggleFrameUi,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 0}
					):Play()
					Framefps:TweenSize(UDim2.new(0, 193, 0, 44),"In","Quad",0.2,true)
					TweenService:Create(
						Framefps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 0}
					):Play()
					TweenService:Create(
						Strokefps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Transparency = 0}
					):Play()
					TweenService:Create(
						TextLabelfps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
					TweenService:Create(
						ImageLabelfps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{ImageTransparency = 0}
					):Play()
					Yedhee.TextTransparency = 0
					Uitoggle.TextTransparency = 0
					ToggleImgUi.ImageTransparency = 0
					SearchStroke.Transparency = 0
					wait(.2)
					uihide = true
					Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
				else
					ToggleFrameUi:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.2,true)
					game:GetService("TweenService"):Create(
						ToggleFrameUi,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
					Framefps:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.2,true)
					game:GetService("TweenService"):Create(
						Framefps,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
					TweenService:Create(
						Strokefps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Transparency = 1}
					):Play()
					TweenService:Create(
						TextLabelfps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 1}
					):Play()
					TweenService:Create(
						ImageLabelfps,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{ImageTransparency = 1}
					):Play()
					Yedhee.TextTransparency = 1
					Uitoggle.TextTransparency = 1
					ToggleImgUi.ImageTransparency = 1
					SearchStroke.Transparency = 1
					wait(.2)
					uihide = false
					Main:TweenSize(UDim2.new(0, 656, 0, 300),"Out","Quad",0.4,true)
				end
			end
		end)
	
		TweenService:Create(
			Frametime,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{BackgroundTransparency = 1}
		):Play()
		TweenService:Create(
			Stroketime,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{Transparency = 1}
		):Play()
		TweenService:Create(
			TextLabeltime,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{TextTransparency = 1}
		):Play()
		TweenService:Create(
			ImageLabeltime,
			TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
			{ImageTransparency = 1}
		):Play()
	
		UserInputService.InputBegan:Connect(function(input)
			if input.KeyCode == Enum.KeyCode[yoo] then
				if uihide == false then
					ToggleFrameUi:TweenSize(UDim2.new(0, 198, 0, 48),"In","Quad",0.2,true)
					game:GetService("TweenService"):Create(
						ToggleFrameUi,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 0}
					):Play()
					Frametime:TweenSize(UDim2.new(0, 293, 0, 44),"In","Quad",0.2,true)
					TweenService:Create(
						Frametime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 0}
					):Play()
					TweenService:Create(
						Stroketime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Transparency = 0}
					):Play()
					TweenService:Create(
						TextLabeltime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
					TweenService:Create(
						ImageLabeltime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{ImageTransparency = 0}
					):Play()
					Yedhee.TextTransparency = 0
					Uitoggle.TextTransparency = 0
					ToggleImgUi.ImageTransparency = 0
					SearchStroke.Transparency = 0
					wait(.2)
					uihide = true
					Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
				else
					ToggleFrameUi:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.2,true)
					game:GetService("TweenService"):Create(
						ToggleFrameUi,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
					Framefps:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.2,true)
					game:GetService("TweenService"):Create(
						Frametime,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
					TweenService:Create(
						Stroketime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Transparency = 1}
					):Play()
					TweenService:Create(
						TextLabeltime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 1}
					):Play()
					TweenService:Create(
						ImageLabeltime,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{ImageTransparency = 1}
					):Play()
					Yedhee.TextTransparency = 1
					Uitoggle.TextTransparency = 1
					ToggleImgUi.ImageTransparency = 1
					SearchStroke.Transparency = 1
					wait(.2)
					uihide = false
					Main:TweenSize(UDim2.new(0, 656, 0, 300),"Out","Quad",0.4,true)
				end
			end
		end)
	
		MakeDraggable(ToggleFrameUi,ToggleFrameUi)
	
	
	
	
	
		local Tab = Instance.new("Frame")
		Tab.Name = "Tab"
		Tab.Parent = Main
		Tab.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
		Tab.Position = UDim2.new(0, 5, 0, 30)
		Tab.Size = UDim2.new(0, 150, 0, 265)
	
		local TCNR = Instance.new("UICorner")
		TCNR.Name = "TCNR"
		TCNR.Parent = Tab
	
		local ScrollTab = Instance.new("ScrollingFrame")
		ScrollTab.Name = "ScrollTab"
		ScrollTab.Parent = Tab
		ScrollTab.Active = true
		ScrollTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ScrollTab.BackgroundTransparency = 1.000
		ScrollTab.Size = UDim2.new(0, 150, 0, 265)
		ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
		ScrollTab.ScrollBarThickness = 0
	
		local PLL = Instance.new("UIListLayout")
		PLL.Name = "PLL"
		PLL.Parent = ScrollTab
		PLL.SortOrder = Enum.SortOrder.LayoutOrder
		PLL.Padding = UDim.new(0, 15)
	
		local PPD = Instance.new("UIPadding")
		PPD.Name = "PPD"
		PPD.Parent = ScrollTab
		PPD.PaddingLeft = UDim.new(0, 10)
		PPD.PaddingTop = UDim.new(0, 10)
	
		local Page = Instance.new("Frame")
		Page.Name = "Page"
		Page.Parent = Main
		Page.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
		Page.Position = UDim2.new(0.245426834, 0, 0, 30)
		Page.Size = UDim2.new(0, 490, 0, 265)
	
		local PCNR = Instance.new("UICorner")
		PCNR.Name = "PCNR"
		PCNR.Parent = Page
	
		local MainPage = Instance.new("Frame")
		MainPage.Name = "MainPage"
		MainPage.Parent = Page
		MainPage.ClipsDescendants = true
		MainPage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		MainPage.BackgroundTransparency = 1.000
		MainPage.Size = UDim2.new(0, 490, 0, 365)
	
		local PageList = Instance.new("Folder")
		PageList.Name = "PageList"
		PageList.Parent = MainPage
	
		local UIPageLayout = Instance.new("UIPageLayout")
	
		UIPageLayout.Parent = PageList
		UIPageLayout.SortOrder = Enum.SortOrder.LayoutOrder
		UIPageLayout.EasingDirection = Enum.EasingDirection.InOut
		UIPageLayout.EasingStyle = Enum.EasingStyle.Quad
		UIPageLayout.FillDirection = Enum.FillDirection.Vertical
		UIPageLayout.Padding = UDim.new(0, 15)
		UIPageLayout.TweenTime = 0.400
		UIPageLayout.GamepadInputEnabled = false
		UIPageLayout.ScrollWheelInputEnabled = false
		UIPageLayout.TouchInputEnabled = false
		
		MakeDraggable(Top,Main)
	
		
		local uitab = {}
		
		function uitab:Tab(text,logo1)
			local TabButton = Instance.new("TextButton")
			TabButton.Parent = ScrollTab
			TabButton.Name = text.."Server"
			TabButton.Text = text
			TabButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			TabButton.BackgroundTransparency = 1.000
			TabButton.Size = UDim2.new(0, 130, 0, 23)
			TabButton.Font = Enum.Font.GothamSemibold
			TabButton.TextColor3 = Color3.fromRGB(225, 225, 225)
			TabButton.TextSize = 15.000
			TabButton.TextTransparency = 0.500
	
			local IDK = Instance.new("ImageLabel")
			IDK.Name = "LogoIDK"
			IDK.Parent = TabButton
			IDK.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			IDK.BackgroundTransparency = 1.000
			IDK.Position = UDim2.new(0, 0, 0, 1)
			IDK.Size = UDim2.new(0, 20, 0, 20)
			IDK.Image = "rbxassetid://"..tostring(logo1)
	
	
			local MainFramePage = Instance.new("ScrollingFrame")
			MainFramePage.Name = text.."_Page"
			MainFramePage.Parent = PageList
			MainFramePage.Active = true
			MainFramePage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			MainFramePage.BackgroundTransparency = 1.000
			MainFramePage.BorderSizePixel = 0
			MainFramePage.Size = UDim2.new(0, 490, 0, 265)
			MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
			MainFramePage.ScrollBarThickness = 0
			
			local UIPadding = Instance.new("UIPadding")
			local UIListLayout = Instance.new("UIListLayout")
			
			UIPadding.Parent = MainFramePage
			UIPadding.PaddingLeft = UDim.new(0, 10)
			UIPadding.PaddingTop = UDim.new(0, 10)
	
			UIListLayout.Padding = UDim.new(0,15)
			UIListLayout.Parent = MainFramePage
			UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
			
			TabButton.MouseButton1Click:Connect(function()
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0.5}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				for i,v in next, PageList:GetChildren() do
					currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
					if v.Name == currentpage then
						UIPageLayout:JumpTo(v)
					end
				end
			end)
	
			if abc == false then
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0.5}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				UIPageLayout:JumpToIndex(1)
				abc = true
			end
			
			game:GetService("RunService").Stepped:Connect(function()
				pcall(function()
					MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
					ScrollTab.CanvasSize = UDim2.new(0,0,0,PLL.AbsoluteContentSize.Y + 20)
				end)
			end)
	
			
			local main = {}
			function main:Button(text,callback)
				local Button = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local TextBtn = Instance.new("TextButton")
				local UICorner_2 = Instance.new("UICorner")
				local Black = Instance.new("Frame")
				local UICorner_3 = Instance.new("UICorner")
				local IMGBUTTON = Instance.new("ImageLabel")
				
				Button.Name = "Button"
				Button.Parent = MainFramePage
				Button.BackgroundColor3 = _G.Color
				Button.Size = UDim2.new(0, 470, 0, 31)
				
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = Button
				
	
				
				TextBtn.Name = "TextBtn"
				TextBtn.Parent = Button
				TextBtn.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				TextBtn.Position = UDim2.new(0, 1, 0, 1)
				TextBtn.Size = UDim2.new(0, 468, 0, 29)
				TextBtn.AutoButtonColor = false
				TextBtn.Font = Enum.Font.GothamSemibold
				TextBtn.Text = text
				TextBtn.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextBtn.TextSize = 15.000
				TextBtn.ClipsDescendants = true
	
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = TextBtn
	
				IMGBUTTON.Name = "IconB"
				IMGBUTTON.Parent = TextBtn
				IMGBUTTON.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				IMGBUTTON.BackgroundTransparency = 1.000
				IMGBUTTON.Position = UDim2.new(0, 10, 0, 5)
				IMGBUTTON.Size = UDim2.new(0, 20, 0, 20)
				IMGBUTTON.Image = "http://www.roblox.com/asset/?id=9606312215"
	
	
				Black.Name = "Black"
				Black.Parent = Button
				Black.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Black.BackgroundTransparency = 1.000
				Black.BorderSizePixel = 0
				Black.Position = UDim2.new(0, 1, 0, 1)
				Black.Size = UDim2.new(0, 468, 0, 29)
				
				UICorner_3.CornerRadius = UDim.new(0, 5)
				UICorner_3.Parent = Black
	
				TextBtn.MouseEnter:Connect(function()
					TweenService:Create(
						Black,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 0.7}
					):Play()
				end)
				TextBtn.MouseLeave:Connect(function()
					TweenService:Create(
						Black,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
				end)
				TextBtn.MouseButton1Click:Connect(function()
					CircleAnim(TextBtn, Color3.fromRGB(255,255,255), Color3.fromRGB(255,255,255))
					TextBtn.TextSize = 1
					TweenService:Create(
						TextBtn,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextSize = 15}
					):Play()
					callback()
				end)
			end
			function main:Toggle(text,Imgidicon,config,callback)
				config = config or false
				local toggled = config
				local Toggle = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local Button = Instance.new("TextButton")
				local UICorner_2 = Instance.new("UICorner")
				local Label = Instance.new("TextLabel")
				local ToggleImage = Instance.new("Frame")
				local UICorner_3 = Instance.new("UICorner")
				local Circle = Instance.new("Frame")
				local UICorner_4 = Instance.new("UICorner")
				local imgLabelIcon = Instance.new("ImageLabel")
	
	
				Toggle.Name = "Toggle"
				Toggle.Parent = MainFramePage
				Toggle.BackgroundColor3 = Color3.fromRGB(255, 46, 46)
				Toggle.Size = UDim2.new(0, 470, 0, 31)
	
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = Toggle
	
				Button.Name = "Button"
				Button.Parent = Toggle
				Button.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				Button.Position = UDim2.new(0, 1, 0, 1)
				Button.Size = UDim2.new(0, 468, 0, 29)
				Button.AutoButtonColor = false
				Button.Font = Enum.Font.SourceSans
				Button.Text = ""
				Button.TextColor3 = Color3.fromRGB(0, 0, 0)
				Button.TextSize = 11.000
	
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = Button
	
				Label.Name = "Label"
				Label.Parent = Toggle
				Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Label.BackgroundTransparency = 1.000
				Label.Position = UDim2.new(0, 1, 0, 1)
				Label.Size = UDim2.new(0, 468, 0, 29)
				Label.Font = Enum.Font.GothamSemibold
				Label.Text = text
				Label.TextColor3 = Color3.fromRGB(225, 225, 225)
				Label.TextSize = 15.000
	
				ToggleImage.Name = "ToggleImage"
				ToggleImage.Parent = Toggle
				ToggleImage.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
				ToggleImage.Position = UDim2.new(0, 415, 0, 5)
				ToggleImage.Size = UDim2.new(0, 45, 0, 20)
	
				UICorner_3.CornerRadius = UDim.new(0, 10)
				UICorner_3.Parent = ToggleImage
	
				Circle.Name = "Circle"
				Circle.Parent = ToggleImage
				Circle.BackgroundColor3 = Color3.fromRGB(255, 46, 46)
				Circle.Position = UDim2.new(0, 2, 0, 2)
				Circle.Size = UDim2.new(0, 16, 0, 16)
	
				UICorner_4.CornerRadius = UDim.new(0, 10)
				UICorner_4.Parent = Circle
	
				imgLabelIcon.Name = "Icon"
				imgLabelIcon.Parent = Toggle
				imgLabelIcon.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				imgLabelIcon.BackgroundTransparency = 1.000
				imgLabelIcon.Position = UDim2.new(0, 10, 0, 5)
				imgLabelIcon.Size = UDim2.new(0, 20, 0, 20)
				imgLabelIcon.Image = "http://www.roblox.com/asset/?id="..Imgidicon
	
				Button.MouseButton1Click:Connect(function()
					if toggled == false then
						toggled = true
						Circle:TweenPosition(UDim2.new(0,27,0,2),"Out","Sine",0.2,true)
						TweenService:Create(
							Toggle,
							TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = _G.Color}
						):Play()
						TweenService:Create(
							Circle,
							TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = _G.Color}
						):Play()
					else
						toggled = false
						Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0.2,true)
						TweenService:Create(
							Toggle,
							TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = Color3.fromRGB(255, 46, 46)}
						):Play()
						TweenService:Create(
							Circle,
							TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = Color3.fromRGB(255, 46, 46)}
						):Play()
					end
					pcall(callback,toggled)
				end)
	
				if config == true then
					toggled = true
					Circle:TweenPosition(UDim2.new(0,27,0,2),"Out","Sine",0.4,true)
					TweenService:Create(
						Toggle,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = _G.Color}
					):Play()
					TweenService:Create(
						Circle,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = _G.Color}
					):Play()
					pcall(callback,toggled)
				end
			end
			function main:Dropdown(text,old,option,callback)
				local isdropping = false
				local Dropdown = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local DropTitle = Instance.new("TextLabel")
				local DropScroll = Instance.new("ScrollingFrame")
				local UIListLayout = Instance.new("UIListLayout")
				local UIPadding = Instance.new("UIPadding")
				local DropButton = Instance.new("TextButton")
				local DropImage = Instance.new("ImageLabel")
				
				Dropdown.Name = "Dropdown"
				Dropdown.Parent = MainFramePage
				Dropdown.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				Dropdown.ClipsDescendants = true
				Dropdown.Size = UDim2.new(0, 470, 0, 31)
				
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = Dropdown
				
				if type(old) == "string" then
					DropTitle.Name = "DropTitle"
					DropTitle.Parent = Dropdown
					DropTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					DropTitle.BackgroundTransparency = 1.000
					DropTitle.Size = UDim2.new(0, 470, 0, 31)
					DropTitle.Font = Enum.Font.GothamSemibold
					DropTitle.Text = text.. " : "..old
					DropTitle.TextColor3 = Color3.fromRGB(225, 225, 225)
					DropTitle.TextSize = 15.000
				else
					DropTitle.Name = "DropTitle"
					DropTitle.Parent = Dropdown
					DropTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					DropTitle.BackgroundTransparency = 1.000
					DropTitle.Size = UDim2.new(0, 470, 0, 31)
					DropTitle.Font = Enum.Font.GothamSemibold
					DropTitle.Text = text.. " : "
					DropTitle.TextColor3 = Color3.fromRGB(225, 225, 225)
					DropTitle.TextSize = 15.000
				end
				
				DropScroll.Name = "DropScroll"
				DropScroll.Parent = DropTitle
				DropScroll.Active = true
				DropScroll.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				DropScroll.BackgroundTransparency = 1.000
				DropScroll.BorderSizePixel = 0
				DropScroll.Position = UDim2.new(0, 0, 0, 31)
				DropScroll.Size = UDim2.new(0, 470, 0, 100)
				DropScroll.CanvasSize = UDim2.new(0, 0, 0, 2)
				DropScroll.ScrollBarThickness = 3
				
				UIListLayout.Parent = DropScroll
				UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
				UIListLayout.Padding = UDim.new(0, 5)
				
				UIPadding.Parent = DropScroll
				UIPadding.PaddingLeft = UDim.new(0, 5)
				UIPadding.PaddingTop = UDim.new(0, 5)
				
				DropImage.Name = "DropImage"
				DropImage.Parent = Dropdown
				DropImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				DropImage.BackgroundTransparency = 1.000
				DropImage.Position = UDim2.new(0, 445, 0, 6)
				DropImage.Rotation = -90
				DropImage.Size = UDim2.new(0, 20, 0, 20)
				DropImage.Image = "rbxassetid://6031090990"
				
				DropButton.Name = "DropButton"
				DropButton.Parent = Dropdown
				DropButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				DropButton.BackgroundTransparency = 1.000
				DropButton.Size = UDim2.new(0, 470, 0, 31)
				DropButton.Font = Enum.Font.SourceSans
				DropButton.Text = ""
				DropButton.TextColor3 = Color3.fromRGB(0, 0, 0)
				DropButton.TextSize = 14.000
	
				for i,v in next,option do
					local Item = Instance.new("TextButton")
	
					Item.Name = "Item"
					Item.Parent = DropScroll
					Item.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					Item.BackgroundTransparency = 1.000
					Item.Size = UDim2.new(0, 460, 0, 26)
					Item.Font = Enum.Font.GothamSemibold
					Item.Text = tostring(v)
					Item.TextColor3 = Color3.fromRGB(225, 225, 225)
					Item.TextSize = 13.000
					Item.TextTransparency = 0.500
					Item.ClipsDescendants = true
	
	
					Item.MouseEnter:Connect(function()
						TweenService:Create(
							Item,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end)
	
					Item.MouseLeave:Connect(function()
						TweenService:Create(
							Item,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0.5}
						):Play()
					end)
	
					Item.MouseButton1Click:Connect(function()
						CircleAnim(Item, Color3.fromRGB(255,255,255), Color3.fromRGB(255,255,255))
						isdropping = false
						Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
						TweenService:Create(
							DropImage,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{Rotation = -90}
						):Play()
						DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)
						callback(Item.Text)
						DropTitle.Text = text.." : "..Item.Text
					end)
				end
	
				DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)
	
				DropButton.MouseButton1Click:Connect(function()
					if isdropping == false then
						isdropping = true
						Dropdown:TweenSize(UDim2.new(0,470,0,131),"Out","Quad",0.3,true)
						TweenService:Create(
							DropImage,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{Rotation = 180}
						):Play()
						DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)
					else
						isdropping = false
						Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
						TweenService:Create(
							DropImage,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{Rotation = -90}
						):Play()
						DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)
					end
				end)
	
				local dropfunc = {}
				function dropfunc:Add(t)
					local Item = Instance.new("TextButton")
					Item.Name = "Item"
					Item.Parent = DropScroll
					Item.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					Item.BackgroundTransparency = 1.000
					Item.Size = UDim2.new(0, 470, 0, 26)
					Item.Font = Enum.Font.GothamSemibold
					Item.Text = tostring(t)
					Item.TextColor3 = Color3.fromRGB(225, 225, 225)
					Item.TextSize = 13.000
					Item.TextTransparency = 0.500
					Item.ClipsDescendants = true
	
					Item.MouseEnter:Connect(function()
						TweenService:Create(
							Item,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end)
	
					Item.MouseLeave:Connect(function()
						TweenService:Create(
							Item,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0.5}
						):Play()
					end)
	
					Item.MouseButton1Click:Connect(function()
						isdropping = false
						CircleAnim(Item, Color3.fromRGB(255,255,255), Color3.fromRGB(255,255,255))
						Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
						TweenService:Create(
							DropImage,
							TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{Rotation = -90}
						):Play()
						DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)
						callback(Item.Text)
						DropTitle.Text = text.." : "..Item.Text
					end)
				end
				
				function dropfunc:Clear()
					DropTitle.Text = tostring(text).." : "
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = -90}
					):Play()
					for i,v in next, DropScroll:GetChildren() do
						if v:IsA("TextButton") then
							v:Destroy()
						end
					end
				end
				return dropfunc
			end
	
			function main:Slider(text,min,max,set,callback)
				local Slider = Instance.new("Frame")
				local slidercorner = Instance.new("UICorner")
				local sliderr = Instance.new("Frame")
				local sliderrcorner = Instance.new("UICorner")
				local SliderLabel = Instance.new("TextLabel")
				local HAHA = Instance.new("Frame")
				local AHEHE = Instance.new("TextButton")
				local bar = Instance.new("Frame")
				local bar1 = Instance.new("Frame")
				local bar1corner = Instance.new("UICorner")
				local barcorner = Instance.new("UICorner")
				local circlebar = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local slidervalue = Instance.new("Frame")
				local valuecorner = Instance.new("UICorner")
				local TextBox = Instance.new("TextBox")
				local UICorner_2 = Instance.new("UICorner")
	
				Slider.Name = "Slider"
				Slider.Parent = MainFramePage
				Slider.BackgroundColor3 = _G.Color
				Slider.BackgroundTransparency = 0
				Slider.Size = UDim2.new(0, 470, 0, 51)
	
				slidercorner.CornerRadius = UDim.new(0, 5)
				slidercorner.Name = "slidercorner"
				slidercorner.Parent = Slider
	
				sliderr.Name = "sliderr"
				sliderr.Parent = Slider
				sliderr.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				sliderr.Position = UDim2.new(0, 1, 0, 1)
				sliderr.Size = UDim2.new(0, 468, 0, 49)
	
				sliderrcorner.CornerRadius = UDim.new(0, 5)
				sliderrcorner.Name = "sliderrcorner"
				sliderrcorner.Parent = sliderr
	
				SliderLabel.Name = "SliderLabel"
				SliderLabel.Parent = sliderr
				SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				SliderLabel.BackgroundTransparency = 1.000
				SliderLabel.Position = UDim2.new(0, 15, 0, 0)
				SliderLabel.Size = UDim2.new(0, 180, 0, 26)
				SliderLabel.Font = Enum.Font.GothamSemibold
				SliderLabel.Text = text
				SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
				SliderLabel.TextSize = 16.000
				SliderLabel.TextTransparency = 0
				SliderLabel.TextXAlignment = Enum.TextXAlignment.Left
	
				HAHA.Name = "HAHA"
				HAHA.Parent = sliderr
				HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				HAHA.BackgroundTransparency = 1.000
				HAHA.Size = UDim2.new(0, 468, 0, 29)
	
				AHEHE.Name = "AHEHE"
				AHEHE.Parent = sliderr
				AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				AHEHE.BackgroundTransparency = 1.000
				AHEHE.Position = UDim2.new(0, 10, 0, 35)
				AHEHE.Size = UDim2.new(0, 448, 0, 5)
				AHEHE.Font = Enum.Font.SourceSans
				AHEHE.Text = ""
				AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
				AHEHE.TextSize = 14.000
	
				bar.Name = "bar"
				bar.Parent = AHEHE
				bar.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				bar.Size = UDim2.new(0, 448, 0, 5)
	
				bar1.Name = "bar1"
				bar1.Parent = bar
				bar1.BackgroundColor3 = _G.Color
				bar1.BackgroundTransparency = 0
				bar1.Size = UDim2.new(set/max, 0, 0, 5)
	
				bar1corner.CornerRadius = UDim.new(0, 5)
				bar1corner.Name = "bar1corner"
				bar1corner.Parent = bar1
	
				barcorner.CornerRadius = UDim.new(0, 5)
				barcorner.Name = "barcorner"
				barcorner.Parent = bar
	
				circlebar.Name = "circlebar"
				circlebar.Parent = bar1
				circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
				circlebar.Position = UDim2.new(1, -2, 0, -3)
				circlebar.Size = UDim2.new(0, 10, 0, 10)
	
				UICorner.CornerRadius = UDim.new(0, 100)
				UICorner.Parent = circlebar
	
				slidervalue.Name = "slidervalue"
				slidervalue.Parent = sliderr
				slidervalue.BackgroundColor3 = _G.Color
				slidervalue.BackgroundTransparency = 0
				slidervalue.Position = UDim2.new(0, 395, 0, 5)
				slidervalue.Size = UDim2.new(0, 65, 0, 18)
	
				valuecorner.CornerRadius = UDim.new(0, 5)
				valuecorner.Name = "valuecorner"
				valuecorner.Parent = slidervalue
	
				TextBox.Parent = slidervalue
				TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TextBox.Position = UDim2.new(0, 1, 0, 1)
				TextBox.Size = UDim2.new(0, 63, 0, 16)
				TextBox.Font = Enum.Font.GothamSemibold
				TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextBox.TextSize = 9.000
				TextBox.Text = set
				TextBox.TextTransparency = 0
	
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = TextBox
	
				local mouse = game.Players.LocalPlayer:GetMouse()
				local uis = game:GetService("UserInputService")
	
				if Value == nil then
					Value = set
					pcall(function()
						callback(Value)
					end)
				end
				
				AHEHE.MouseButton1Down:Connect(function()
					Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
					pcall(function()
						callback(Value)
					end)
					TweenService:Create(
						bar1,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
					TweenService:Create(
						circlebar,
						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)} -- UDim2.new(0, 128, 0, 25)
					):Play()
					--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
					moveconnection = mouse.Move:Connect(function()
						TextBox.Text = Value
						Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
						pcall(function()
							callback(Value)
						end)
						TweenService:Create(
							bar1,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						TweenService:Create(
							circlebar,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
					end)
					releaseconnection = uis.InputEnded:Connect(function(Mouse)
						if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
							Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
							pcall(function()
								callback(Value)
							end)
							TweenService:Create(
								bar1,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
							TweenService:Create(
								circlebar,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
							moveconnection:Disconnect()
							releaseconnection:Disconnect()
						end
					end)
				end)
				releaseconnection = uis.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
						TextBox.Text = Value
					end
				end)
	
				TextBox.FocusLost:Connect(function()
					if tonumber(TextBox.Text) > max then
						TextBox.Text  = max
					end
					bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
					circlebar.Position = UDim2.new(1, -2, 0, -3)
					TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
					pcall(callback, TextBox.Text)
				end)
			end
	
			function main:Textbox(text,disappear,callback)
				local Textbox = Instance.new("Frame")
				local TextboxCorner = Instance.new("UICorner")
				local Textboxx = Instance.new("Frame")
				local TextboxxCorner = Instance.new("UICorner")
				local TextboxLabel = Instance.new("TextLabel")
				local txtbtn = Instance.new("TextButton")
				local RealTextbox = Instance.new("TextBox")
				local UICorner = Instance.new("UICorner")
	
				Textbox.Name = "Textbox"
				Textbox.Parent = MainFramePage
				Textbox.BackgroundColor3 = _G.Color
				Textbox.BackgroundTransparency = 0
				Textbox.Size = UDim2.new(0, 470, 0, 31)
	
				TextboxCorner.CornerRadius = UDim.new(0, 5)
				TextboxCorner.Name = "TextboxCorner"
				TextboxCorner.Parent = Textbox
	
				Textboxx.Name = "Textboxx"
				Textboxx.Parent = Textbox
				Textboxx.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				Textboxx.Position = UDim2.new(0, 1, 0, 1)
				Textboxx.Size = UDim2.new(0, 468, 0, 29)
	
				TextboxxCorner.CornerRadius = UDim.new(0, 5)
				TextboxxCorner.Name = "TextboxxCorner"
				TextboxxCorner.Parent = Textboxx
	
				TextboxLabel.Name = "TextboxLabel"
				TextboxLabel.Parent = Textbox
				TextboxLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TextboxLabel.BackgroundTransparency = 1.000
				TextboxLabel.Position = UDim2.new(0, 15, 0, 0)
				TextboxLabel.Text = text
				TextboxLabel.Size = UDim2.new(0, 145, 0, 31)
				TextboxLabel.Font = Enum.Font.GothamSemibold
				TextboxLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextboxLabel.TextSize = 16.000
				TextboxLabel.TextTransparency = 0
				TextboxLabel.TextXAlignment = Enum.TextXAlignment.Left
	
				txtbtn.Name = "txtbtn"
				txtbtn.Parent = Textbox
				txtbtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				txtbtn.BackgroundTransparency = 1.000
				txtbtn.Position = UDim2.new(0, 1, 0, 1)
				txtbtn.Size = UDim2.new(0, 468, 0, 29)
				txtbtn.Font = Enum.Font.SourceSans
				txtbtn.Text = ""
				txtbtn.TextColor3 = Color3.fromRGB(0, 0, 0)
				txtbtn.TextSize = 14.000
	
				RealTextbox.Name = "RealTextbox"
				RealTextbox.Parent = Textbox
				RealTextbox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				RealTextbox.BackgroundTransparency = 0
				RealTextbox.Position = UDim2.new(0, 360, 0, 4)
				RealTextbox.Size = UDim2.new(0, 100, 0, 24)
				RealTextbox.Font = Enum.Font.GothamSemibold
				RealTextbox.Text = ""
				RealTextbox.TextColor3 = Color3.fromRGB(225, 225, 225)
				RealTextbox.TextSize = 11.000
				RealTextbox.TextTransparency = 0
	
				RealTextbox.FocusLost:Connect(function()
					callback(RealTextbox.Text)
					if disappear then
						RealTextbox.Text = ""
					end
				end)
	
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = RealTextbox
			end
			function main:Label(text)
				local Label = Instance.new("TextLabel")
				local PaddingLabel = Instance.new("UIPadding")
				local labell = {}
		
				Label.Name = "Label"
				Label.Parent = MainFramePage
				Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Label.BackgroundTransparency = 1.000
				Label.Size = UDim2.new(0, 470, 0, 20)
				Label.Font = Enum.Font.GothamSemibold
				Label.TextColor3 = Color3.fromRGB(225, 225, 225)
				Label.TextSize = 16.000
				Label.Text = text
				Label.TextXAlignment = Enum.TextXAlignment.Left
	
				PaddingLabel.PaddingLeft = UDim.new(0,0)
				PaddingLabel.Parent = Label
				PaddingLabel.Name = "PaddingLabel"
		
				function labell:Set(newtext)
					Label.Text = newtext
				end
	
				return labell
			end
			function main:LabelP(text)
				local Label = Instance.new("TextLabel")
				local PaddingLabel = Instance.new("UIPadding")
				local labell = {}
		
				Label.Name = "Label"
				Label.Parent = MainFramePage
				Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Label.BackgroundTransparency = 1.000
				Label.Size = UDim2.new(0, 470, 0, 20)
				Label.Font = Enum.Font.GothamSemibold
				Label.TextColor3 = Color3.fromRGB(195, 195, 195)
				Label.TextSize = 15.000
				Label.Text = text
				Label.TextXAlignment = Enum.TextXAlignment.Left
	
				PaddingLabel.PaddingLeft = UDim.new(0,25)
				PaddingLabel.Parent = Label
				PaddingLabel.Name = "PaddingLabel"
		
				function labell:Set(newtext)
					Label.Text = newtext
				end
	
				return labell
			end
			function main:Seperator(text)
				local Seperator = Instance.new("Frame")
				local Sep1 = Instance.new("Frame")
				local Sep2 = Instance.new("TextLabel")
				local Sep3 = Instance.new("Frame")
				
				Seperator.Name = "Seperator"
				Seperator.Parent = MainFramePage
				Seperator.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Seperator.BackgroundTransparency = 1.000
				Seperator.Size = UDim2.new(0, 470, 0, 20)
				
				Sep1.Name = "Sep1"
				Sep1.Parent = Seperator
				Sep1.BackgroundColor3 = _G.Color
				Sep1.BorderSizePixel = 0
				Sep1.Position = UDim2.new(0, 0, 0, 10)
				Sep1.Size = UDim2.new(0, 80, 0, 1)
				
				Sep2.Name = "Sep2"
				Sep2.Parent = Seperator
				Sep2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Sep2.BackgroundTransparency = 1.000
				Sep2.Position = UDim2.new(0, 185, 0, 0)
				Sep2.Size = UDim2.new(0, 100, 0, 20)
				Sep2.Font = Enum.Font.GothamSemibold
				Sep2.Text = text
				Sep2.TextColor3 = Color3.fromRGB(255, 255, 255)
				Sep2.TextSize = 14.000
				
				Sep3.Name = "Sep3"
				Sep3.Parent = Seperator
				Sep3.BackgroundColor3 = _G.Color
				Sep3.BorderSizePixel = 0
				Sep3.Position = UDim2.new(0, 390, 0, 10)
				Sep3.Size = UDim2.new(0, 80, 0, 1)
			end
	
			function main:Line()
				local Linee = Instance.new("Frame")
				local Line = Instance.new("Frame")
				
				Linee.Name = "Linee"
				Linee.Parent = MainFramePage
				Linee.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Linee.BackgroundTransparency = 1.000
				Linee.Position = UDim2.new(0, 0, 0.119999997, 0)
				Linee.Size = UDim2.new(0, 470, 0, 20)
				
				Line.Name = "Line"
				Line.Parent = Linee
				Line.BackgroundColor3 = _G.Color
				Line.BorderSizePixel = 0
				Line.Position = UDim2.new(0, 0, 0, 10)
				Line.Size = UDim2.new(0, 470, 0, 1)
			end
			return main
		end
		return uitab
	end
end

game.StarterGui:SetCore("SendNotification", {
	Title = "MODZ Notification", 
	Text = "ฟังชั่นที่มีไอคอนนี้สามารถเปิด\nพร้อมฟามเวลได้",
	Icon = "http://www.roblox.com/asset/?id=9610159123",
	Duration = 8
})

local win = library:Window("MODZ",[[ BLACK]],[[Version : Premium ]],"9606070311",Enum.KeyCode.RightControl)
local General_Tab = win:Tab("General",[[7040391851]])
local Quest_Tab = win:Tab("    Quest & Item",[[9606626859]])
local PvP_Tab = win:Tab("PvP",[[9606626034]])
local Raid_Tab = win:Tab("Raid",[[9606629300]])
local Shop_Tab = win:Tab("Shop",[[9606625251]])
local Island_Tab = win:Tab("Island",[[9606628205]])
local Setting_Tab = win:Tab("Setting",[[9606644121]])
local Status_Tab = win:Tab("Status",[[9613645002]])
local Esp_Tab = win:Tab("ESP",[[9606628205]])
local Hop_Tab = win:Tab("Hop",[[9608089732]])
General_Tab:Label("Farm Level")

General_Tab:Toggle("Auto Farm","9606294253",_G.Setting_table.AutoFarm,function(vu)
	Auto_Farm = vu
	_G.Setting_table.AutoFarm = vu
	Update_Setting(getgenv()['MyName'])
end)
	local plr = game.Players.LocalPlayer
	local CbFw = getupvalues(require(plr.PlayerScripts.CombatFramework))
	local CbFw2 = CbFw[2]

    function GetCurrentBlade() 
        local p13 = CbFw2.activeController
        local ret = p13.blades[1]
        if not ret then return end
        while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
        return ret
    end
    
    function AttackNoCD()
        if not Auto_Farm_Bounty and not Auto_Farm_Fruit or Mix_Farm then
            if not Auto_Raid then
                local AC = CbFw2.activeController
                for i = 1, 1 do 
                    local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
                        plr.Character,
                        {plr.Character.HumanoidRootPart},
                        60
                    )
                    local cac = {}
                    local hash = {}
                    for k, v in pairs(bladehit) do
                        if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                            table.insert(cac, v.Parent.HumanoidRootPart)
                            hash[v.Parent] = true
                        end
                    end
                    bladehit = cac
                    if #bladehit > 0 then
                        local u8 = debug.getupvalue(AC.attack, 5)
                        local u9 = debug.getupvalue(AC.attack, 6)
                        local u7 = debug.getupvalue(AC.attack, 4)
                        local u10 = debug.getupvalue(AC.attack, 7)
                        local u12 = (u8 * 798405 + u7 * 727595) % u9
                        local u13 = u7 * 798405
                        (function()
                            u12 = (u12 * u9 + u13) % 1099511627776
                            u8 = math.floor(u12 / u9)
                            u7 = u12 - u8 * u9
                        end)()
                        u10 = u10 + 1
                        debug.setupvalue(AC.attack, 5, u8)
                        debug.setupvalue(AC.attack, 6, u9)
                        debug.setupvalue(AC.attack, 4, u7)
                        debug.setupvalue(AC.attack, 7, u10)
                        pcall(function()
                            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then
                                AC.animator.anims.basic[1]:Play(0.01,0.01,0.01)
                                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "")
                            end
                        end)
                    end
                end
            end
        end
        if Auto_Farm_Bounty or Auto_Farm_Fruit and not Mix_Farm then
            local Fast = getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
            local Lop = Fast[2]
            Lop.activeController.timeToNextAttack = (-math.huge^math.huge*math.huge)
            Lop.activeController.attacking = false
            Lop.activeController.timeToNextBlock = 0
            Lop.activeController.humanoid.AutoRotate = 80
            Lop.activeController.increment = 3
            Lop.activeController.blocking = false
            Lop.activeController.hitboxMagnitude = 80
        end
    end
spawn(function()
	while wait(.1) do
		pcall(function()
			if Auto_Farm then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						if _G.Farm_Boss then
							_G.SelectBoss = nil
							_G.Farm_Boss = nil
							SelectMonster = nil
							_G.Farm_Mon = nil
							wait(1)
						end
						if _G.SelectBoss ~= nil and game.Workspace.Enemies:FindFirstChild(_G.SelectBoss) or _G.SelectBoss ~= nil and game.ReplicatedStorage:FindFirstChild(_G.SelectBoss) then
							CheckQuestBoss()
							repeat wait(.2)
								TelePBoss(CFrameQBoss)
								TP(CFrameQBoss)
							until (CFrameQBoss.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 10
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuestBoss, QuestLvBoss)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							_G.Farm_Boss = true
						elseif SelectMonster ~= nil then
							CheckLevel2()
							repeat wait(.2)
								TelePBoss(CFrameQ)
								TP(CFrameQ)
							until (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 10
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							SelectMonster = nil
							_G.Farm_Mon = nil
						else
							StatrMagnet = nil
							CheckLevel2()
							repeat wait(.2)
								TelePBoss(CFrameQ)
								TP(CFrameQ)
							until (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 10
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
						end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						if _G.Farm_Boss then
							if game.Workspace.Enemies:FindFirstChild(_G.SelectBoss) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == _G.SelectBoss and v.Humanoid.Health > 0 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										v.Humanoid:ChangeState(11)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(5,5,5)
										StatrMagnet = nil
										repeat wait(_G.Fast_Delay)
											TelePBoss(CFrameQBoss)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,50))
											AttackNoCD()
										until game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false or not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) or not v.Parent or v.Humanoid.Health <= 0 or not Auto_Farm or Mix_Farm
										if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameBoss) then
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									end
								end
							else
								TP(CFrameBoss*CFrame.new(0,30,0))
								TelePBoss(CFrameBoss)
							end
						else
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == Ms and v.Humanoid.Health > 0 then
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										v.Humanoid:ChangeState(11)
										v.Humanoid.JumpPower = 0
										v.Humanoid.WalkSpeed = 0
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(5,5,5)
										repeat wait(_G.Fast_Delay)
											TelePBoss(CFrameQ)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,10))
											AttackNoCD()
										until game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false or not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) or not v.Parent or v.Humanoid.Health <= 0 or not Auto_Farm or Mix_Farm
										if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
										Attack = nil
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(game.ReplicatedStorage:FindFirstChild(Ms).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
								TelePBoss(CFrameQ)
							end
						end
					end
				end
			else
				wait(2)
			end
		end)
	end
end)

spawn(function()
	while task.wait() do
		pcall(function()
			if StatrMagnet then
				if Auto_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == Ms and (v.HumanoidRootPart.Position-_G.PosMon.Position).Magnitude <= 350 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								v.Humanoid:ChangeState(11)
								v.Humanoid.JumpPower = 0
								v.Humanoid.WalkSpeed = 0
								v.HumanoidRootPart.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(5,5,5)
								v.HumanoidRootPart.CFrame = _G.PosMon
								sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
								Attack = true
							end
						end
					end
				else
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if (v.HumanoidRootPart.Position-_G.PosMon.Position).Magnitude <= 350 then
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							v.Humanoid:ChangeState(11)
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(5,5,5)
							v.HumanoidRootPart.CFrame = _G.PosMon
							sethiddenproperty(game.Players.LocalPlayer, "MaximumSimulationRadius",  math.huge)
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  9e20)
						end
					end
				end
			end
		end)
	end
end)
	
if _G.Setting_table.FastAttack_Mode == nil then
	_G.Setting_table.FastAttack_Mode = "Fast"
end
MIo = {
	"Super Fast",
	"Fast",
	"Smooth"
}
General_Tab:Toggle("Fast Attack ","9606294253",_G.Setting_table.FastAttack,function(vu)
	_G.Setting_table.FastAttack = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if _G.Setting_table.FastAttack then
				repeat wait(_G.Fast_Delay)
					AttackNoCD()
				until not _G.Setting_table.FastAttack
			end
		end)
	end
end)
General_Tab:Dropdown("FastAttack","Fast",MIo,function(vu)
	_G.Setting_table.FastAttack_Mode = vu
	Update_Setting(getgenv()['MyName'])
	if _G.Setting_table.FastAttack_Mode == "Fast" then
		_G.Fast_Delay = 0.1
	elseif _G.Setting_table.FastAttack_Mode == "Smooth" then
		_G.Fast_Delay = 0.3
	elseif _G.Setting_table.FastAttack_Mode == "Super Fast" then
		_G.Fast_Delay = 0
	end
end)
local Camera = require(game.ReplicatedStorage.Util.CameraShaker)
Camera:Stop()

Waspon = {}
for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
    if v:IsA("Tool") then
        table.insert(Waspon ,v.Name)
    end
end
for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
    if v:IsA("Tool") then
        table.insert(Waspon ,v.Name)
    end
end
if type(_G.Setting_table.Weapon) == 'string' then
else
	_G.Setting_table.Weapon = ""
end
local Select_W = General_Tab:Dropdown("Select Weapon",_G.Setting_table.Weapon,Waspon,function(vu)
	_G.Setting_table.Weapon = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Button("Refresh Weapon",function(vu)
	Select_W:Clear()
	for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
		if v:IsA("Tool") then
			Select_W:Add(v.Name)
		end
	end
	for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
		if v:IsA("Tool") then
			Select_W:Add(v.Name)
		end
	end
end)

General_Tab:Label("Farm Boss")
General_Tab:Toggle("Auto Farm","9610159123",_G.Setting_table.Farm_Boss,function(vu)
	Auto_Farm_Boss = vu
	_G.Setting_table.Farm_Boss = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Boss then
				if not Mix_Farm or Auto_Farm_Boss_Ex then
					if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) or game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
						Mix_Farm = true
						Auto_Farm_Boss_Ex = true
						if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == _G.Setting_table.Boss_Name and v.Humanoid.Health > 0 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm_Boss == false
									Mix_Farm = nil
									Auto_Farm_Boss_Ex = nil
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
							TP(game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Lock) or game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Lock) then
						Mix_Farm = true
						Auto_Farm_Boss_Ex = true
						if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Lock) then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == _G.Setting_table.Boss_Lock and v.Humanoid.Health > 0 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm_Boss == false
									Mix_Farm = nil
									Auto_Farm_Boss_Ex = nil
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Lock) then
							TP(game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Lock).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif Auto_Farm_Boss_Ex then
						Mix_Farm = nil
						Auto_Farm_Boss_Ex = nil
					else
						wait(3)
					end
				end
			elseif _G.Setting_table.Auto_Farm_Boss_Hop then
				if Ping == nil then
					Hop_Boss()
					wait(1)
					print("....".._G.Setting_table.Boss_Name)
					Ping = true
				end
				if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) or game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
					Mix_Farm = true
					Auto_Farm_Boss_Ex = true
					if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == _G.Setting_table.Boss_Name and v.Humanoid.Health > 0 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or _G.Setting_table.Auto_Farm_Boss_Hop == false
								Mix_Farm = nil
								Auto_Farm_Boss_Ex = nil
								Ping = nil
							end
						end
					elseif game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
						TP(game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
					end
				elseif Auto_Farm_Boss_Ex then
					Mix_Farm = nil
					Auto_Farm_Boss_Ex = nil
					Ping = nil
				else
					wait(5)
					if not game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) and not game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
						Hop_Boss()
						wait(1)
						print("....".._G.Setting_table.Boss_Name)
						wait(3)
						if not game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) and not game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
							HopServer()
							wait(50)
						end
					end
				end
			elseif Auto_Farm_Boss_Ex then
				Mix_Farm = nil
				Auto_Farm_Boss_Ex = nil
			else
				wait(3)
			end
		end)
	end
end)
General_Tab:Toggle("Auto Farm All Boss","9610159123",_G.Setting_table.Farm_All_Boss,function(vu)
	Auto_Farm_Boss_All = vu
	_G.Setting_table.Farm_All_Boss = vu
	Update_Setting(getgenv()['MyName'])
end)
function Hop_Boss()
	CheckBoss()
	for i,v in pairs(Boss_A) do
		for i2,v2 in pairs(_G.Setting_table.Boss_All_Select) do
			if v == v2 then
				print(v)
				_G.Setting_table.Boss_Name = v
				return 
			end
		end
	end
end
function H_B()
	CheckBoss()
	for i,v in pairs(Boss_A) do
		if type(v) == 'string' then
			print(v)
			_G.Setting_table.Boss_Name = v
			return
		end
	end
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Boss_All then
				if not Mix_Farm or Auto_Farm_Boss_All_Ex then
					if Ping == nil then
						H_B()
						wait(1)
						print("....".._G.Setting_table.Boss_Name)
						Ping = true
					end
					if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) or game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
						Mix_Farm = true
						Auto_Farm_Boss_All_Ex = true
						if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == _G.Setting_table.Boss_Name and v.Humanoid.Health > 0 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm_Boss_All == false
									Mix_Farm = nil
									Auto_Farm_Boss_All_Ex = nil
									Ping = nil
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
							TP(game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif Auto_Farm_Boss_All_Ex then
						Mix_Farm = nil
						Auto_Farm_Boss_All_Ex = nil
						Ping = nil
					else
						Ping = nil
						wait(5)
					end
				end
			elseif _G.Setting_table.Auto_Farm_Boss_All_Hop then
				if not Mix_Farm or Auto_Farm_Boss_All_Ex then
					if Ping == nil then
						H_B()
						wait(1)
						print("....".._G.Setting_table.Boss_Name)
						Ping = true
					end
					if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) or game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
						Mix_Farm = true
						Auto_Farm_Boss_All_Ex = true
						if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == _G.Setting_table.Boss_Name and v.Humanoid.Health > 0 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or _G.Setting_table.Auto_Farm_Boss_All_Hop == false
									Mix_Farm = nil
									Auto_Farm_Boss_All_Ex = nil
									Ping = nil
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
							TP(game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif Auto_Farm_Boss_All_Ex then
						Mix_Farm = nil
						Auto_Farm_Boss_All_Ex = nil
						Ping = nil
					else
						Ping = nil
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) and not game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
							if Ping == nil then
								H_B()
								wait(1)
								print("....".._G.Setting_table.Boss_Name)
								Ping = true
							end
							wait(3)
							if not game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Boss_Name) and not game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Boss_Name) then
								HopServer()
								wait(50)
							end
						end
					end
				end
			elseif Auto_Farm_Boss_All_Ex then
				Mix_Farm = nil
				Auto_Farm_Boss_All_Ex = nil
				Ping = nil
			else
				wait(2)
			end
		end)
	end
end)
Boss_A = {}
function CheckBoss()
	for i,v in pairs(Boss_A) do
		table.remove(Boss_A,i)
	end
	for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
		if string.find(v.Name,"Boss") then
			table.insert(Boss_A,v.Name)
		end
	end
	for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
		if string.find(v.Name,"Boss") then
			table.insert(Boss_A,v.Name)
		end
	end
end
Boss = {}
for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
	if string.find(v.Name,"Boss") then
		table.insert(Boss,v.Name)
	end
end
for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
	if string.find(v.Name,"Boss") then
		table.insert(Boss,v.Name)
	end
end
if type(_G.Setting_table.Boss_Name) == 'string' then
else
	_G.Setting_table.Boss_Name = ""
end
Boss_List = {
	"Saber Expert [Lv. 200] [Boss]" ,
	"Thunder God [Lv. 575] [Boss]",
	"Diamond [Lv. 750] [Boss]",
	"Jeremy [Lv. 850] [Boss]",
	"Fajita [Lv. 925] [Boss]",
	"Don Swan [Lv. 1000] [Boss]",
	"Darkbeard [Lv. 1000] [Raid Boss]",
	"Tide Keeper [Lv. 1475] [Boss]",
	"Island Empress [Lv. 1675] [Boss]",
	"Captain Elephant [Lv. 1875] [Boss]",
	"rip_indra True Form [Lv. 5000] [Raid Boss]",
	"Longma [Lv. 2000] [Boss]",
	"Soul Reaper [Lv. 2100] [Raid Boss]",
	"Cake Queen [Lv. 2175] [Boss]"
}
local Select_B = General_Tab:Dropdown("Select Boss",_G.Setting_table.Boss_Name,Boss,function(vu)
	_G.Setting_table.Boss_Name = vu
	Update_Setting(getgenv()['MyName'])
end)
local Select_BK = General_Tab:Dropdown("Select Lock Boss",_G.Setting_table.Boss_Lock,Boss_List,function(vu)
	_G.Setting_table.Boss_Lock = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Button("Refresh Boss",function(vu)
	Select_B:Clear()
	for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
		if string.find(v.Name,"Boss") then
			Select_B:Add(v.Name)
		end
	end
	for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
		if string.find(v.Name,"Boss") then
			Select_B:Add(v.Name)
		end
	end
end)

General_Tab:Label("Farm Monster")
General_Tab:Toggle("Auto Farm","9606294253",_G.Setting_table.Auto_Farm_Monster,function(vu)
	Auto_Farm_Monster = vu
	_G.Setting_table.Auto_Farm_Monster = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Monster then
				if not Mix_Farm then
					if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Mon_Name) or game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Mon_Name) then
						if game.Workspace.Enemies:FindFirstChild(_G.Setting_table.Mon_Name) then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == _G.Setting_table.Mon_Name and v.Humanoid.Health > 0 then
									_G.PosMon = v.HumanoidRootPart.CFrame
									StatrMagnet = true
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Monster
									StatrMagnet = false
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Mon_Name) then
							TP(game.ReplicatedStorage:FindFirstChild(_G.Setting_table.Mon_Name).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
local Mons = {}
local xx = {}

for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
    if string.find(v.Name , "Lv.") then
        table.insert(xx, v.Name)
    end
end

for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
    if string.find(v.Name , "Lv.") then
        table.insert(xx, v.Name)
    end
end

table.sort(xx)
local result = {}

for key,value in ipairs(xx) do
    if value ~=xx[key+1] then
        table.insert(result,value)
    end
end
for key,value in ipairs(result) do
    table.insert(Mons, value)
end
local Select_M = General_Tab:Dropdown("Select Monster",_G.Setting_table.Mon_Name,Mons,function(vu)
	_G.Setting_table.Mon_Name = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Button("Refresh Monster",function(vu)
	Select_M:Clear()
	local xx = {}

	for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
		if string.find(v.Name , "Lv.") then
			table.insert(xx, v.Name)
		end
	end

	for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
		if string.find(v.Name , "Lv.") then
			table.insert(xx, v.Name)
		end
	end

	table.sort(xx)
	local result = {}

	for key,value in ipairs(xx) do
		if value ~=xx[key+1] then
			table.insert(result,value)
		end
	end
	for key,value in ipairs(result) do
		Select_M:Add(value)
	end
end)

General_Tab:Label("Farm Mastery")
General_Tab:Toggle("Auto Farm Fruit","9606294253",_G.Setting_table.Farm_Fruit,function(vu)
	Auto_Farm_Fruit = vu
	_G.Setting_table.Farm_Fruit = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.MinHealth == nil then
	_G.Setting_table.MinHealth = 20
end
General_Tab:Slider("Health %",1,30,_G.Setting_table.MinHealth,function(vu)
	MinHealth = vu
	_G.Setting_table.MinHealth = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Fruit then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						CheckLevel()
						if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10 then
                            TP(CFrameQ)
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                        end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						CheckLevel()
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait(.2)
											local health = v.Humanoid.Health
											local maxhealth = v.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent <= MinHealth then
												EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												PositionSkillMasteryDevilFruit = v.HumanoidRootPart.Position
												UseSkillMasteryDevilFruit = true
												if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then
													if SkillZ  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
													if SkillX  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
													end   
												elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
													if SkillZ  and v.Humanoid.Health > 0 and game.Players.LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(7.6, 7.676, 3.686) then
													else
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
													if SkillX  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
													end
													if SkillC  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
													end  
												elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value) then
													game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value).MousePos.Value = v.HumanoidRootPart.Position
													if SkillZ  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
													if SkillX  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
													end
													if SkillC  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
													end
													if SkillV  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "V", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "V", false, game)
													end
												end
											elseif percent > MinHealth and v.Humanoid.Health > 0 then
												if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
													if game.Players.LocalPlayer.Character.HumanoidRootPart.Size.Y >= 6 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
												end
												UseSkillMasteryDevilFruit = false
												EquipWeapon(_G.Setting_table.Weapon)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												local health = v.Humanoid.Health
												local maxhealth = v.Humanoid.MaxHealth
												local percent = (health / maxhealth) * 100
												if percent > MinHealth and v.Humanoid.Health > 0 then
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
												else
													EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
													wait(1)
												end
											end
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Fruit
										StatrMagnet = false
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(CFrameMon)
							else
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait(.2)
											local MinHealth = 17
											local health = v.Humanoid.Health
											local maxhealth = v.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent <= MinHealth then
												EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												PositionSkillMasteryDevilFruit = v.HumanoidRootPart.Position
												UseSkillMasteryDevilFruit = true
												if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then
													if SkillZ  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
													if SkillX  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
													end   
												elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
													if SkillZ  and v.Humanoid.Health > 0 and game.Players.LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(7.6, 7.676, 3.686) then
													else
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
													if SkillX  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
													end
													if SkillC  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
													end  
												elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value) then
													game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value).MousePos.Value = v.HumanoidRootPart.Position
													if SkillZ  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
													if SkillX  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
													end
													if SkillC  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
													end
													if SkillV  and v.Humanoid.Health > 0 then
														game:service('VirtualInputManager'):SendKeyEvent(true, "V", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "V", false, game)
													end
												end
											elseif percent > MinHealth and v.Humanoid.Health > 0 then
												if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
													if SkillZ  and v.Humanoid.Health > 0 and game.Players.LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(7.6, 7.676, 3.686) then
														game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
														wait(.1)
														game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
													end
												end
												UseSkillMasteryDevilFruit = false
												EquipWeapon(_G.Setting_table.Weapon)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												local health = v.Humanoid.Health
												local maxhealth = v.Humanoid.MaxHealth
												local percent = (health / maxhealth) * 100
												if percent > MinHealth and v.Humanoid.Health > 0 then
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
												else
													EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
													wait(1)
												end
											end
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Fruit
										StatrMagnet = false
									end
								end
							end
						end
					end
				end
			end
		end)
	end
end)
General_Tab:Toggle("Auto Farm Gun","9606294253",_G.Setting_table.Farm_Gun,function(vu)
	Auto_Farm_Gun = vu
	_G.Setting_table.Farm_Gun = vu
	Update_Setting(getgenv()['MyName'])
end)

spawn(function()
	while wait(.5) do
		pcall(function()
			if game.Players.LocalPlayer.Character.Humanoid.Health <= 0 or not game.Players.LocalPlayer then
				_G.Stop_Tween = true
				wait(3)
				_G.Stop_Tween = nil
			end
		end)
	end
end)

spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Gun then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						CheckLevel()
						if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10 then
                            TP(CFrameQ)
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                        end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						CheckLevel()
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
											if v2:IsA("Tool") then
												if tostring(v2.ToolTip) == "Gun" then
													SelectToolWeaponGun = v2.Name
												end
											end
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										_G.Mon = v
										StatrMagnet = true
										repeat wait(.2)
											local MinHealth = 17
											local health = v.Humanoid.Health
											local maxhealth = v.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent <= MinHealth then
												EquipWeapon(SelectToolWeaponGun)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												_G.Mon = v
												game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun).MousePos.Value = v.HumanoidRootPart.Position
												PositionSkillMasteryDevilFruit = v.HumanoidRootPart.Position
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
												Aimbot_G = true
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
												UseSkillMasteryDevilFruit = true
												if SkillZ  and v.Humanoid.Health > 0 then
													game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
													wait(.1)
													game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
												end
												if SkillX  and v.Humanoid.Health > 0 then
													game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
													wait(.1)
													game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
												end
											elseif percent > MinHealth and v.Humanoid.Health > 0 then
												UseSkillMasteryDevilFruit = false
												EquipWeapon(_G.Setting_table.Weapon)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												local health = v.Humanoid.Health
												local maxhealth = v.Humanoid.MaxHealth
												local percent = (health / maxhealth) * 100
												if percent > MinHealth and v.Humanoid.Health > 0 then
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
												else
													EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
													wait(1)
												end
											end
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Gun
										StatrMagnet = false
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(CFrameMon)
							else
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
											if v2:IsA("Tool") then
												if tostring(v2.ToolTip) == "Gun" then
													SelectToolWeaponGun = v2.Name
												end
											end
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										_G.Mon = v
										StatrMagnet = true
										repeat wait(.2)
											local MinHealth = 17
											local health = v.Humanoid.Health
											local maxhealth = v.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent <= MinHealth then
												EquipWeapon(SelectToolWeaponGun)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												_G.Mon = v.Name
												game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun).MousePos.Value = v.HumanoidRootPart.Position
												game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
												game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun).MousePos.Value = v.HumanoidRootPart.Position
												PositionSkillMasteryDevilFruit = v.HumanoidRootPart.Position
												UseSkillMasteryDevilFruit = true
												if SkillZ  and v.Humanoid.Health > 0 then
													game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
													wait(.1)
													game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
												end
												if SkillX  and v.Humanoid.Health > 0 then
													game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
													wait(.1)
													game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
												end
											elseif percent > MinHealth and v.Humanoid.Health > 0 then
												UseSkillMasteryDevilFruit = false
												EquipWeapon(_G.Setting_table.Weapon)
												TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
												local health = v.Humanoid.Health
												local maxhealth = v.Humanoid.MaxHealth
												local percent = (health / maxhealth) * 100
												if percent > MinHealth and v.Humanoid.Health > 0 then
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
												else
													EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
													wait(1)
												end
											end
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Gun
										StatrMagnet = false
									end
								end
							end
						end
					end
				end
			end
		end)
	end
end)
local lp = game:GetService('Players').LocalPlayer
local mouse = lp:GetMouse()
mouse.Button1Down:Connect(function()
    if SelectToolWeaponGun ~= nil then
        if game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) and game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun):FindFirstChild("RemoteFunctionShoot") then
            tool = game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun]
            v17 = workspace:FindPartOnRayWithIgnoreList(Ray.new(tool.Handle.CFrame.p, (_G.Mon.HumanoidRootPart.Position - tool.Handle.CFrame.p).unit * 100), { game.Players.LocalPlayer.Character, workspace._WorldOrigin });
            game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun).RemoteFunctionShoot:InvokeServer(_G.Mon.HumanoidRootPart.Position, (ReplicatedStorage_Util.Other.hrpFromPart(v17)));
        end
    end
end)

General_Tab:Toggle("Skill Z","9606294253",_G.Setting_table.Skill_Z,function(vu)
	SkillZ = vu
	_G.Setting_table.Skill_Z = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Skill X","9606294253",_G.Setting_table.Skill_X,function(vu)
	SkillX = vu
	_G.Setting_table.Skill_Z = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Skill C","9606294253",_G.Setting_table.Skill_C,function(vu)
	SkillC = vu
	_G.Setting_table.Skill_Z = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Skill V","9606294253",_G.Setting_table.Skill_V,function(vu)
	SkillV = vu
	_G.Setting_table.Skill_Z = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Auto Farm Melee","9606294253",_G.Setting_table.Farm_Melee,function(vu)
	Auto_Farm_Melee = vu
	_G.Setting_table.Farm_Melee = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.2) do
		pcall(function()
			if Auto_Farm_Melee then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						CheckLevel()
						if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10 then
                            TP(CFrameQ)
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                        end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						CheckLevel()
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
											if v2:IsA("Tool") then
												if tostring(v2.ToolTip) == "Melee" then
													_G.Setting_table.Weapon = v2.Name
												end
											end
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Melee
										StatrMagnet = false
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(CFrameMon)
							else
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
											if v2:IsA("Tool") then
												if tostring(v2.ToolTip) == "Melee" then
													_G.Setting_table.Weapon = v2.Name
												end
											end
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Melee
										StatrMagnet = false
									end
								end
							end
						end
					end
				end
			end
		end)
	end
end)
General_Tab:Toggle("Auto Farm Sword","9606294253",_G.Setting_table.Farm_Sword,function(vu)
	Auto_Farm_Sword = vu
	_G.Setting_table.Farm_Sword = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.2) do
		pcall(function()
			if Auto_Farm_Sword then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						CheckLevel()
						if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10 then
                            TP(CFrameQ)
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                        end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						CheckLevel()
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
											if v2:IsA("Tool") then
												if tostring(v2.ToolTip) == "Sword" then
													_G.Setting_table.Weapon = v2.Name
												end
											end
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Sword
										StatrMagnet = false
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(CFrameMon)
							else
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
											if v2:IsA("Tool") then
												if tostring(v2.ToolTip) == "Sword" then
													_G.Setting_table.Weapon = v2.Name
												end
											end
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Sword
										StatrMagnet = false
									end
								end
							end
						end
					end
				end
			end
		end)
	end
end)

General_Tab:Label('Farm Bone')
General_Tab:Toggle("Auto Farm Bone","9606294253",_G.Setting_table.Farm_Bone,function(vu)
	Auto_Farm_Bone = vu
	_G.Setting_table.Farm_Bone = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Bone then
				if not Mix_Farm then
					if game.Workspace.Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == "Reborn Skeleton [Lv. 1975]" and v.Humanoid.Health > 0 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								_G.PosMon = v.HumanoidRootPart.CFrame
								StatrMagnet = true
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Bone 
								StatrMagnet = false
							end
						end
					elseif game.ReplicatedStorage:FindFirstChild("Reborn Skeleton [Lv. 1975]") then
						TP(game.ReplicatedStorage:FindFirstChild("Reborn Skeleton [Lv. 1975]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
					else
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								_G.PosMon = v.HumanoidRootPart.CFrame
								StatrMagnet = true
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Auto_Farm_Bone
								StatrMagnet = false
							end
						end
					end
				end
			end
		end)
	end
end)
General_Tab:Toggle("Auto Buy Random Surprise","9606294253",_G.Setting_table.Farm_Random_S,function(vu)
	Farm_Random_S = vu
	_G.Setting_table.Farm_Random_S = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Farm_Random_S then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
			end
		end)
	end
end)

General_Tab:Label('Farm Observation Haki')
General_Tab:Toggle("Auto Farm Observation Haki","9606294253",_G.Setting_table.Farm_Ken,function(vu)
	Farm_Ken = vu
	_G.Setting_table.Farm_Ken = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Farm_Ken then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						CheckLevel()
						if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10 then
                            TP(CFrameQ)
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                        end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						CheckLevel()
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										spawn(function()
											repeat wait(1)
												if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 7 then
													wait(7)
													if game.Players.LocalPlayer.Character.Humanoid.Health == game.Players.LocalPlayer.Character.Humanoid.MaxHealth then
														_G.IKAI = true
														--break
													end
												end
											until _G.IKAI == true or StatrMagnet
										end)
										repeat wait(.2)
											local health = game.Players.LocalPlayer.Character.Humanoid.Health
											local maxhealth = game.Players.LocalPlayer.Character.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent >= 90 then
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,0,2))
											else
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											end
										until _G.IKAI or percent < 90 or v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Farm_Ken
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										_G.IKAI = false
										StatrMagnet = true
										repeat wait(_G.Fast_Delay)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											EquipWeapon(_G.Setting_table.Weapon)
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Farm_Ken 
										StatrMagnet = false
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(game.ReplicatedStorage:FindFirstChild(Ms).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
							else
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = false
										spawn(function()
											repeat wait(1)
												if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 7 then
													wait(7)
													if game.Players.LocalPlayer.Character.Humanoid.Health == game.Players.LocalPlayer.Character.Humanoid.MaxHealth then
														_G.IKAI = true
														--break
													end
												end
											until _G.IKAI == true or StatrMagnet
										end)
										repeat wait(.2)
											local health = game.Players.LocalPlayer.Character.Humanoid.Health
											local maxhealth = game.Players.LocalPlayer.Character.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent >= 90 then
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,0,2))
											else
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											end
										until _G.IKAI or percent < 90 or v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not _G.Setting_table.Farm_Ken_Hop
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										_G.IKAI = false
										StatrMagnet = true
										repeat wait(_G.Fast_Delay)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											EquipWeapon(_G.Setting_table.Weapon)
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not Farm_Ken 
										StatrMagnet = false
									end
								end
							end
						end
					end
				end
			elseif _G.Setting_table.Farm_Ken_Hop then
				if not Mix_Farm then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
						CheckLevel()
						if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10 then
                            TP(CFrameQ)
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                        end
					elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						CheckLevel()
						if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
							if game.Workspace.Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										spawn(function()
											repeat wait(1)
												if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 7 then
													wait(15)
													if game.Players.LocalPlayer.Character.Humanoid.Health == game.Players.LocalPlayer.Character.Humanoid.MaxHealth then
														_G.IKAI = true
														--break
													end
												end
											until _G.IKAI == true
										end)
										repeat wait(.2)
											local health = game.Players.LocalPlayer.Character.Humanoid.Health
											local maxhealth = game.Players.LocalPlayer.Character.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent >= 90 then
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,0,2))
											else
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											end
										until _G.IKAI or percent < 90 or v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not _G.Setting_table.Farm_Ken_Hop
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										if _G.IKAI then
											_G.Upto = true
											_G.IKAI = false
										else
											_G.TP_Ser = true
											game:GetService("TeleportService"):Teleport(game.PlaceId)
											wait(50)
										end
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild(Ms) then
								TP(game.ReplicatedStorage:FindFirstChild(Ms).HumanoidRootPart.CFrame*CFrame.new(0,30,0))
							else
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										spawn(function()
											repeat wait(1)
												if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 7 then
													wait(15)
													if game.Players.LocalPlayer.Character.Humanoid.Health == game.Players.LocalPlayer.Character.Humanoid.MaxHealth then
														_G.IKAI = true
														--break
													end
												end
											until _G.IKAI == true 
										end)
										repeat wait(.2)
											local health = game.Players.LocalPlayer.Character.Humanoid.Health
											local maxhealth = game.Players.LocalPlayer.Character.Humanoid.MaxHealth
											local percent = (health / maxhealth) * 100
											if percent >= 90 then
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,0,2))
											else
												TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											end
										until _G.IKAI or percent < 90 or v.Humanoid.Health <= 0 or not v.Parent or Mix_Farm or not _G.Setting_table.Farm_Ken_Hop
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										if _G.IKAI then
											_G.Upto = true
											_G.IKAI = false
										else
											_G.TP_Ser = true
											game:GetService("TeleportService"):Teleport(game.PlaceId)
											wait(50)
										end
									end
								end
							end
						end
					end
				end
			else
				wait(2)
			end
		end)
	end
end)

if New_World or Three_World then
	local OPP = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Status")
	local Lpp = string.match(tostring(OPP), "%d+")
	_G.Lv_Ken = tonumber(Lpp)
end

spawn(function()
    while wait(2) do
        pcall(function()
            if CH_K then
                local OPP = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Status")
                local Lpp = string.match(tostring(OPP), "%d+")
                _G.Lv_Ken = tonumber(Lpp)
                wait(5)
            end
        end)
    end
end)

spawn(function()
    while wait(.3) do
        pcall(function()
            if Farm_Ken_V2 then
                if not Mix_Farm or Farm_Ken_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    if Lv >= 1800 and Beli >= 5000000 then
                        CH_K = true
                        if _G.Lv_Ken >= 5000 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 3 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Start")
                                if not game.Players.LocalPlayer.Backpack:FindFirstChild("Pineapple") and not game.Players.LocalPlayer.Character:FindFirstChild("Pineapple") then
                                    for i,v in pairs(game.Workspace.PineappleSpawner:GetChildren()) do
                                        if v.Name == "Pineapple" then
                                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Handle.CFrame
                                            wait(1)
                                        end
                                    end
                                    if not GPIJdz then
                                        Text("wait Fruit Spawn\nรอผลไม้เกิด")
                                        GPIJdz = true
                                    end
                                elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Banana") and not game.Players.LocalPlayer.Character:FindFirstChild("Banana") then
                                    for i,v in pairs(game.Workspace.BananaSpawner:GetChildren()) do
                                        if v.Name == "Banana" then
                                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Handle.CFrame
                                            wait(1)
                                        end
                                    end
                                    if not GPIJdx then
                                        Text("wait Fruit Spawn\nรอผลไม้เกิด")
                                        GPIJdx = true
                                    end
                                elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Apple") and not game.Players.LocalPlayer.Character:FindFirstChild("Apple") then
                                    for i,v in pairs(game.Workspace.AppleSpawner:GetChildren()) do
                                        if v.Name == "Apple" then
                                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Handle.CFrame
                                            wait(1)
                                        end
                                    end
                                    if not GPIJdcw then
                                        Text("wait Fruit Spawn\nรอผลไม้เกิด")
                                        GPIJdcw = true
                                    end
                                elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Fruit Bowl") and not  game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fruit Bowl") then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen")
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk2","Buy")
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 2 then
                                Mix_Farm = true
                                Farm_Ken_Ex = true
								TP(CFrame.new(-12512.6533203125, 336.21612548828125, -9872.841796875))
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 1 then
                                if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
                                    Mix_Farm = true
                                    Farm_Ken_Ex = true
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Name == "Captain Elephant [Lv. 1875] [Boss]" and v.Humanoid.Health > 0 then
											repeat wait(_G.Fast_Delay)
												EquipWeapon(_G.Setting_table.Weapon)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                                AttackNoCD()
                                            until v.Humanoid.Health <= 0 or not v.Parent or Farm_Ken_V2 == false
                                        end
                                    end
                                elseif game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
                                    Mix_Farm = true
                                    Farm_Ken_Ex = true
									TP(CFrame.new(-13400.6103515625, 317.9277648925781, -8409.9853515625)*CFrame.new(0,200,0))
                                elseif Farm_Ken_Ex then
                                    Mix_Farm = nil
                                    Farm_Ken_Ex = nil
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 0 then
                                if LIPO == nil then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","CitizenQuest",1)
                                    LIPO = true
                                end
                                if game.Workspace.Enemies:FindFirstChild("Forest Pirate [Lv. 1825]") then
                                    Mix_Farm = true
                                    Farm_Ken_Ex = true
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Name == "Forest Pirate [Lv. 1825]" and v.Humanoid.Health > 0 then
                                            _G.PosMon = v.HumanoidRootPart.CFrame
                                            StatrMagnet = true
                                            repeat wait(_G.Fast_Delay)
												EquipWeapon(_G.Setting_table.Weapon)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                                AttackNoCD()
                                            until v.Humanoid.Health <= 0 or not v.Parent or Farm_Ken_V2 == false
                                            StatrMagnet = false
                                        end
                                    end
                                elseif game.ReplicatedStorage:FindFirstChild("Forest Pirate [Lv. 1825]") then
                                    Mix_Farm = true
                                    Farm_Ken_Ex = true
									TP(game.ReplicatedStorage:FindFirstChild("Forest Pirate [Lv. 1825]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
								elseif Farm_Ken_Ex then
									Farm_Ken_Ex = nil
									Mix_Farm = nil
								end
							elseif Farm_Ken_Ex then
								Farm_Ken_Ex = nil
								Mix_Farm = nil
                            end
                        elseif _G.Lv_Ken < 5000 then
                            if XER == nil then
								if Lv < 1800 then
									Text("❌ Level < 1800")
									_G.Have_Lv = "0"
								else
									Text("✅ Level >= 1800")
									_G.Have_Lv = "1"
								end
								if Beli < 5000000 then
									Text("❌ Money < 5M")
									_G.Have_B = "0"
								else
									Text("✅ Money >= 5M")
									_G.Have_B = "1"
								end
								if _G.Lv_Ken < 5000 then
									Text("❌ Ken Level < 5000")
								else
									Text("✅ Ken Level == 5000")
								end
								XER = true
							end
							--Farm_Ken = true
                        end
                    else
                        if XER == nil then
                            if Lv < 1800 then
                                Text("❌ Level < 1800")
                                _G.Have_Lv = "0"
                            else
                                Text("✅ Level >= 1800")
                                _G.Have_Lv = "1"
                            end
                            if Beli < 5000000 then
                                Text("❌ Money < 5M")
                                _G.Have_B = "0"
                            else
                                Text("✅ Money >= 5M")
                                _G.Have_B = "1"
                            end
                            if _G.Lv_Ken < 5000 then
                                Text("❌ Ken Level < 5000")
                            else
                                Text("✅ Ken Level == 5000")
                            end
                            XER = true
                        end
                        --Farm_Ken = true
                    end
                end
			elseif Farm_Ken_Ex then
				Farm_Ken_Ex = nil
				Mix_Farm = nil
			else
				wait(2)
            end
        end)
    end
end)

General_Tab:Label("Farm Object")
General_Tab:Toggle("Auto Open Color Haki","9606294253",_G.Setting_table.Farm_Ob_Color,function(vu)
	Open_Color_Haki = vu
	_G.Setting_table.Farm_Ob_Color = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.3) do
        pcall(function()
            if Open_Color_Haki then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Winter Sky")
            	wait(0.5)
            	repeat TP2(CFrame.new(-5420.16602, 1084.9657, -2666.8208)) wait() 
                until _G.StopTween == true or Open_Color_Haki == false or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5420.16602, 1084.9657, -2666.8208)).Magnitude <= 10
                wait(0.5)
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Pure Red")
                wait(0.5)
                repeat TP2(CFrame.new(-5414.41357, 309.865753, -2212.45776)) wait() 
                until _G.StopTween == true or Open_Color_Haki == false or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5414.41357, 309.865753, -2212.45776)).Magnitude <= 10
                wait(0.5)
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Snow White")
                wait(0.5)
                repeat TP2(CFrame.new(-4971.47559, 331.565765, -3720.02954)) wait() 
                until _G.StopTween == true or Open_Color_Haki == false or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-4971.47559, 331.565765, -3720.02954)).Magnitude <= 10
                wait(0.5)
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                wait(3)
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
            end
        end) 
    end
end)
General_Tab:Toggle("Auto Holy Torch","9606294253",_G.Setting_table.Auto_Holy_Torch,function(vu)
	Auto_Holy_Torch = vu
	_G.Setting_table.Auto_Holy_Torch = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Auto Grab Chest","9606294253",_G.Setting_table.Grab_Chest,function(vu)
	Grab_Chest = vu
	_G.Setting_table.Grab_Chest = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Auto Grab Chest Stop Torch","9606294253",_G.Setting_table.STP,function(vu)
	Grab_Chest = vu
	T_P_H = vu
	_G.Setting_table.STP = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Hop Chest Lock","9606294253",_G.Setting_table.Hop_Chest,function(vu)
	_G.Setting_table.Hop_Chest = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Slider("Chest Lock",1,100,_G.Setting_table.K_MAX,function(vu)
	_G.Setting_table.K_MAX = vu
	Update_Setting(getgenv()['MyName'])
end)
local K_C = General_Tab:Label('Chest Lock : 0')
if _G.Setting_table.Grab_Chest then
	Grab_Chest = true
end
spawn(function()
	while wait(2) do
		pcall(function()
			if _G.Setting_table.Hop_Chest then
				if K_CH >= _G.Setting_table.K_MAX and not H_F then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Fist of Darkness") or game.Players.LocalPlayer.Character:FindFirstChild("Fist of Darkness") then
						H_F = true
					else
						HopServer()
						wait(50)
					end
				end
			end
		end)
	end
end)
K_CH = 0
K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
spawn(function()
    while wait(.2) do
        pcall(function()
            if Grab_Chest then
                if T_P_H then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fist of Darkness") or game.Players.LocalPlayer.Character:FindFirstChild("Fist of Darkness") then
                        TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
                        H_F = true
						game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                        wait(3)
                    else
						_G.Chest_100 = nil
						_G.Chest_500 = nil
						_G.Chest_1000 = nil
						_G.Chest_1500 = nil
						_G.Chest_2000 = nil
						_G.Chest_2500 = nil
						_G.Chest_3500 = nil
						_G.Chest_4500 = nil
						_G.Chest_5500 = nil
						_G.Chest_6500 = nil
						_G.Chest_7500 = nil
						_G.Chest_9500 = nil
						_G.Chest_10500 = nil
						_G.Chest_12500 = nil
						_G.Chest_15500 = nil
						_G.Chest_17500 = nil
						Chest_100()
						Chest_500()
						Chest_1000()
						Chest_1500()
						Chest_2000()
						Chest_2500()
						Chest_3500()
						Chest_4500()
						Chest_5500()
						Chest_6500()
						Chest_7500()
						Chest_9500()
						Chest_10500()
						Chest_12500()
						Chest_15500()
						Chest_17500()
						if _G.Chest_100 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_100.CFrame)
							until not _G.Chest_100.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_500.CFrame)
							until not _G.Chest_500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_1000 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_1000.CFrame)
							until not _G.Chest_1000.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_1500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_1500.CFrame)
							until not _G.Chest_1500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_2000 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_2000.CFrame)
							until not _G.Chest_2000.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_2500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_2500.CFrame)
							until not _G.Chest_2500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_3500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_3500.CFrame)
							until not _G.Chest_3500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_4500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_4500.CFrame)
							until not _G.Chest_4500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_5500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_5500.CFrame)
							until not _G.Chest_5500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_6500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_6500.CFrame)
							until not _G.Chest_6500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_7500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_7500.CFrame)
							until not _G.Chest_7500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_9500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_9500.CFrame)
							until not _G.Chest_9500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_10500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_10500.CFrame)
							until not _G.Chest_10500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_12500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_12500.CFrame)
							until not _G.Chest_12500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_15500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_15500.CFrame)
							until not _G.Chest_15500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_17500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_17500.CFrame)
							until not _G.Chest_17500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						end
                    end
                else
					
                    _G.Chest_100 = nil
						_G.Chest_500 = nil
						_G.Chest_1000 = nil
						_G.Chest_1500 = nil
						_G.Chest_2000 = nil
						_G.Chest_2500 = nil
						_G.Chest_3500 = nil
						_G.Chest_4500 = nil
						_G.Chest_5500 = nil
						_G.Chest_6500 = nil
						_G.Chest_7500 = nil
						_G.Chest_9500 = nil
						_G.Chest_10500 = nil
						_G.Chest_12500 = nil
						_G.Chest_15500 = nil
						_G.Chest_17500 = nil
						Chest_100()
						Chest_500()
						Chest_1000()
						Chest_1500()
						Chest_2000()
						Chest_2500()
						Chest_3500()
						Chest_4500()
						Chest_5500()
						Chest_6500()
						Chest_7500()
						Chest_9500()
						Chest_10500()
						Chest_12500()
						Chest_15500()
						Chest_17500()
						if _G.Chest_100 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_100.CFrame)
							until not _G.Chest_100.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_500.CFrame)
							until not _G.Chest_500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_1000 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_1000.CFrame)
							until not _G.Chest_1000.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_1500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_1500.CFrame)
							until not _G.Chest_1500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_2000 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_2000.CFrame)
							until not _G.Chest_2000.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_2500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_2500.CFrame)
							until not _G.Chest_2500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_3500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_3500.CFrame)
							until not _G.Chest_3500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_4500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_4500.CFrame)
							until not _G.Chest_4500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_5500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_5500.CFrame)
							until not _G.Chest_5500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_6500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_6500.CFrame)
							until not _G.Chest_6500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_7500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_7500.CFrame)
							until not _G.Chest_7500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_9500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_9500.CFrame)
							until not _G.Chest_9500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_10500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_10500.CFrame)
							until not _G.Chest_10500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_12500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_12500.CFrame)
							until not _G.Chest_12500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_15500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_15500.CFrame)
							until not _G.Chest_15500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						elseif _G.Chest_17500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_17500.CFrame)
							until not _G.Chest_17500.Parent or not Grab_Chest
							if Grab_Chest then
								K_CH = K_CH + 1
								K_C:Set('Chest : '..tostring(K_CH).."/".._G.Setting_table.K_MAX)
							end
						end
                end
            end
        end)
    end
end)

spawn(function()
    while wait(.5) do
        pcall(function()
            if Auto_Holy_Torch then
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
                    repeat wait(.2)
                        EquipWeapon("Holy Torch")
                        TP2(CFrame.new(-10752.4434, 415.261749, -9367.43848, 1, 0, 0, 0, 1, 0, 0, 0, 1))
                    until (Vector3.new(-10752.4434, 415.261749, -9367.43848)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 5
                    wait(2)
                    repeat wait(.2)
                        EquipWeapon("Holy Torch")
                        TP2(CFrame.new(-11671.6289, 333.78125, -9474.31934, 0.300932229, 0, -0.953645527, 0, 1, 0, 0.953645527, 0, 0.300932229))
                    until (Vector3.new(-11671.6289, 333.78125, -9474.31934)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 5
                    wait(2)
                    repeat wait(.2)
                        EquipWeapon("Holy Torch")
                        TP2(CFrame.new(-12133.1406, 521.507446, -10654.292, 0.80428642, 0, -0.594241858, 0, 1, 0, 0.594241858, 0, 0.80428642))
                    until (Vector3.new(-12133.1406, 521.507446, -10654.292)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 5
                    wait(2)
                    repeat wait(.2)
                        EquipWeapon("Holy Torch")
                        TP2(CFrame.new(-13336.127, 484.521179, -6985.31689, 0.853732228, 0, -0.520712316, 0, 1, 0, 0.520712316, 0, 0.853732228))
                    until (Vector3.new(-13336.127, 484.521179, -6985.31689)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 5
                    wait(2)
                    EquipWeapon("Holy Torch")
                    repeat wait(.2)
                        TP2(CFrame.new(-13487.623, 336.436188, -7924.53857, -0.982848108, 0, 0.184417039, 0, 1, 0, -0.184417039, 0, -0.982848108))
                    until (Vector3.new(-13487.623, 336.436188, -7924.53857)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 5
                    wait(2)
                    Com()
                    wait(20)
                elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") and not game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
                    if Uiio == nil then
						Text("No Have Holy Torch")
						Uiio = true
					end
                    wait(3)
                end
            end
        end)
    end
end)
General_Tab:Label("Farm Stats")
General_Tab:Toggle("Melee","9606294253",_G.Setting_table.Melee_A,function(vu)
	Melee_A = vu
	_G.Setting_table.Melee_A = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Defense","9606294253",_G.Setting_table.Defense_A,function(vu)
	Defense_A = vu
	_G.Setting_table.Defense_A = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Sword","9606294253",_G.Setting_table.Sword_A,function(vu)
	Sword_A = vu
	_G.Setting_table.Sword_A = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Fruit","9606294253",_G.Setting_table.Fruit_A,function(vu)
	Fruit_A = vu
	_G.Setting_table.Fruit_A = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Toggle("Gun","9606294253",_G.Setting_table.Gun_A,function(vu)
	Gun_A = vu
	_G.Setting_table.Gun_A = vu
	Update_Setting(getgenv()['MyName'])
end)
General_Tab:Slider("Point",1,100,3,function(vu)
	Points = vu
end)
General_Tab:Button("Copy Hwid",function()
	setclipboard((syn and syn.request or request)({Url = 'https://api.luauth.xyz/hwid', Method = syn and "Get" or "GET"}).Body)
end)
spawn(function()
    while wait(.5) do
        if Melee_A then
            if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Melee", Points)
            end
        end
    end
end)

spawn(function()
    while wait(.5) do
        if Defense_A then
            if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Defense", Points)
            end
        end
    end
end)

spawn(function()
    while wait(.5) do
        if Sword_A then
            if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Sword", Points)
            end
        end
    end
end)

spawn(function()
    while wait(.5) do
        if Gun_A then
            if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Gun", Points)
            end
        end
    end
end)

spawn(function()
    while wait(.5) do
        if Fruit_A then
            if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Demon Fruit", Points)
            end
        end
    end
end)

Quest_Tab:Label("Old World")
Quest_Tab:Toggle("Auto Second World","9606294253",_G.Setting_table.Second_Farm,function(vu)
	Auto_New_A = vu
	_G.Setting_table.Second_Farm = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.2) do
        if Auto_New_A then
            if Mix_Farm == nil or Auto_New_Farm then
                local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                if Lv >= 700 then
                    Mix_Farm = true
                    Auto_New_Farm = true
                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective") == 1 then
                    else
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
                        wait(2)
                        EquipWeapon("Key")
                    end
                    repeat wait()
                        TP2(CFrame.new(1347.32947, 37.349369, -1325.44922, 0.538348913, 8.57539106e-08, 0.842722058, 8.61935634e-10, 1, -1.0230886e-07, -0.842722058, 5.58042359e-08, 0.538348913))
                    until (Vector3.new(1347.32947, 37.349369, -1325.44922)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1 or Auto_New_A == false
                    wait(2)
                    for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                        if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                             
                            repeat wait(_G.Fast_Delay)
                                EquipWeapon(_G.Setting_table.Weapon)
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,15))
                                AttackNoCD()
                            until v.Humanoid.Health <= 0 or not v.Parent or Auto_New_A == false
                            wait(2)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                            wait(25)
                        end
                    end
                end
            end
        end
    end
end)
Quest_Tab:Label("Second World")
Quest_Tab:Toggle("Auto Bartlio","9606294253",_G.Setting_table.Bartlio_Farm,function(vu)
	Bartlio_Farm = vu
	_G.Setting_table.Bartlio_Farm = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(1) do
		pcall(function()
			if Bartlio_Farm and New_World then
				local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
				if Lv >= 900 then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
						if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game.workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
								for i,v in pairs(game.workspace.Enemies:GetChildren()) do
									if v.Name == "Swan Pirate [Lv. 775]" then
										CFrameMon = v.HumanoidRootPart.CFrame
										_G.PosMon = v.HumanoidRootPart.CFrame
										StatrMagnet = true
										repeat wait()
											EquipWeapon(_G.Setting_table.Weapon)
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
											game:GetService'VirtualUser':CaptureController()
											game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
										until v.Humanoid.Health <= 0 or not v.Parent or Bartlio_Farm ==false
										StatrMagnet = false
									end
								end
							elseif game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]") then
								TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]").HumanoidRootPart.CFrame*CFrame.new(0,20,0))
							end
						else
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","BartiloQuest",1)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
						_G.SelectBoss = "Jeremy [Lv. 850] [Boss]"
						CheckQuestBoss()
						if game.workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
							for i,v in pairs(game.workspace.Enemies:GetChildren()) do
								if v.Name == "Jeremy [Lv. 850] [Boss]" then
									repeat wait()
										EquipWeapon(_G.Setting_table.Weapon)
										v.HumanoidRootPart.Size = Vector3.new(50,50,50)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
									until v.Humanoid.Health <= 0 or not v.Parent or Bartlio_Farm == false
								end
							end
						else
							TP(CFrameBoss)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
						repeat wait()
							TP2(CFrame.new(-1836, 11, 1714))
						until (Vector3.new(-1836, 11, 1714)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
					end
				end
			end
		end)
    end
end)
Quest_Tab:Toggle("Auto Open Swan Glass","9610159123",_G.Setting_table.Open_Don_Swan,function(vu)
	Inventory_Fruit = vu
	BringFruit = vu
	Don_Swan_Quest = vu
	_G.Setting_table.Open_Don_Swan = vu
	Update_Setting(getgenv()['MyName'])
end)

local function split(str, sep)
	local result = {}
	local regex = ("([^%s]+)"):format(sep)
	for each in str:gmatch(regex) do
	   table.insert(result, each)
	end
	return result
 end

spawn(function()
    while wait(.5) do
        pcall(function()
            if Don_Swan_Quest then
                if New_World then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if Lv >= 1200 then
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
                            wait(2)
							local fruit = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryFruits")
                            for i,v in pairs(fruit) do
                                if v["Price"] >= 1000000 then
                                    Inventory_Fruit = false
                                    Mix_Farm = true
                                    wait(1)
                                    local NameFruit = split(v["Name"], "-")[2] .. " Fruit"
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v["Name"])
                                    wait(2)
                                    EquipWeapon(NameFruit)
                                    wait(2)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                    Mix_Farm = nil
                                    Inventory_Fruit = true
									return
                                end
                            end
                        end
                    end
                end
			else
				wait(2)
            end
        end)
    end
end)
Quest_Tab:Toggle("Auto Third World","9606294253",false,function(vu)
	Auto_Three_World = vu
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Three_World then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
					if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == "rip_indra [Lv. 1500] [Boss]" and v.Humanoid.Health > 0 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								repeat wait(.1)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
								until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Three_World or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Zou")
								if not YUHJO then
									Text("ทำเควสโลก 3 เสร็จสิ้น")
									YUHJO = true
								end
							end
						end
					elseif not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
						repeat wait(1)
						until game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") or game.ReplicatedStorage:FindFirstChild("rip_indra [Lv. 1500] [Boss]")
					end
				elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
					if not IJOIJD then
						Text("คุณทำเควสโลก 3 เสร็จแล้ว")
						IJOIJD = true
					end
				else
					if not JUO then
						Text("คุณยังไม่เปิดประตูโดฟา\nไม่สามารถทำได้!!")
						JUO = true
					end
				end
			else
				wait(2)
			end
		end)
	end
end)

Quest_Tab:Label("Third World")
Quest_Tab:Toggle("Auto Elite Hunter","9610159123",_G.Setting_table.Auto_Elite_Hunter,function(vu)
	Auto_Elite_Hunter = vu
	_G.Setting_table.Auto_Elite_Hunter = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Elite_Hunter then
				if not Mix_Farm or Auto_Elite_Hunter_Farm then
					if game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
						Mix_Farm = true
						Auto_Elite_Hunter_Farm = true
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
						if game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Urban [Lv. 1750]" then
									repeat wait(.2)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Elite_Hunter
									Mix_Farm = nil
									Auto_Elite_Hunter_Farm = nil
								end
							end
						elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
							TP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
						Mix_Farm = true
						Auto_Elite_Hunter_Farm = true
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
						if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Diablo [Lv. 1750]" then
									repeat wait(.2)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Elite_Hunter
									Mix_Farm = nil
									Auto_Elite_Hunter_Farm = nil
								end
							end
						elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
							TP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
						Mix_Farm = true
						Auto_Elite_Hunter_Farm = true
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
						if game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Deandre [Lv. 1750]" then
									repeat wait(.2)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Elite_Hunter
									Mix_Farm = nil
									Auto_Elite_Hunter_Farm = nil
								end
							end
						elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
							TP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Elite_Hunter_Hop then
						wait(5)
						if not game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
							HopServer()
							wait(50)
						end
					elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Urban (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Deandre (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Diablo (0/1)" then
						Mix_Farm = nil
						Auto_Elite_Hunter_Farm = nil
					elseif Auto_Elite_Hunter_Farm then
						Mix_Farm = nil
						Auto_Elite_Hunter_Farm = nil
					else
						wait(3)
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Phoenix Awaken","9606294253",_G.Setting_table.Auto_Phoenix_Awaken,function(vu)
	Auto_Phoenix_Awaken = vu
	Auto_Farm_Fruit = vu
	SkillZ = vu
	_G.Setting_table.Auto_Phoenix_Awaken = vu
end)
if _G.Setting_table.Farm_Fruit then
	Auto_Farm_Fruit = true
end
if _G.Setting_table.Skill_Z then
	SkillZ = true
end
function Get_Fruit_Backpack()
	for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
		if v:IsA("Tool") then
			if string.find(v.Name,"Fruit") then
				_G.Have_Fruit = true
				return
			end
		end
	end
end
function Get_Fruit_Character()
	for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
		if v:IsA("Tool") then
			if string.find(v.Name,"Fruit") then
				_G.Have_Fruit = true
				return
			end
		end
	end
end
function Get_Fruit_Inventory()
	local fruit = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryFruits")
	for i,v in pairs(fruit) do
		if _G.Phoenix_R then
			if v["Price"] < 1000000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v["Name"])
				_G.Have_Fruit = true
				return
			end
		elseif _G.Phoenix_XR then
			if v["Price"] >= 1000000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v["Name"])
				_G.Have_Fruit = true
				return
			end
		elseif v["Price"] >= 10 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v["Name"])
			_G.Have_Fruit = true
			return
		end
	end
end
function Raid_FG()
	for i,v6 in pairs(game:GetService("Workspace"):GetChildren()) do
		if v6:IsA ("Tool") and (v6.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 13000 then
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v6.Handle.CFrame
			v6.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
		end
	end
	wait(1)
	Inventory_Fruit = nil
	Get_Fruit_Inventory()
	Get_Fruit_Backpack()
	Get_Fruit_Character()
	if _G.Have_Fruit then
		Mix_Farm = true
		Raid_FG_Ex = true
		Auto_Raid = true
	elseif _G.Setting_table.Melee_Hop then
		HopServer()
		wait(50)
	elseif _G.Setting_table.Phoenix_Hop then
		HopServer()
		wait(50)
	elseif _G.Setting_table.Race_Hop then
		HopServer()
		wait(50)
	elseif _G.Setting_table.Auto_Pole_V2_Hop then
		HopServer()
		wait(50)
	elseif Raid_FG_Ex then
		Mix_Farm = nil
		Raid_FG_Ex = nil
		Auto_Raid = nil
	elseif not _G.Have_Fruit then
		Text("ไม่มีผลปีศาจเหลือ\nไม่สามารถลงดันได้")
	end
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Phoenix_Awaken then
				if not Mix_Farm or Auto_Phoenix_Awaken_Ex then
					if game.Players.LocalPlayer.Character:FindFirstChild("Bird-Bird: Phoenix") or game.Players.LocalPlayer.Backpack:FindFirstChild("Bird-Bird: Phoenix") then
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SickScientist","Check") ~= false then
							if not UHuHI then
								Text("กำลังฟามมาสเตอรี่ผลปีศาจ")
								UHuHI = true
							end
							Auto_Farm_Fruit = true
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SickScientist","Check") == false then
							Auto_Farm_Fruit = false
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SickScientist","Heal") == 1 then
								local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
								local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
								if FG >= 6000 then
									_G.Have_Fruit = nil
									_G.Phoenix_R = nil
									_G.Phoenix_XR = true
									Get_Fruit_Inventory()
									_G.Phoenix_XR = nil
									wait(1)
									if _G.Have_Fruit then
										if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", "Bird: Phoenix") == 1 then
											_G.Setting_table.Select_Map = "Bird: Phoenix"
											_G.Setting_table.Auto_Awaken = true
											Mix_Farm = true
											Auto_Phoenix_Awaken_Ex = true
											Auto_Raid = true
											TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											Text("กำลังลงดันฟีนิกตื่น")
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false
										elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", "Bird: Phoenix") == '[You already have a Special Microchip.]' then
											_G.Setting_table.Select_Map = "Flame"
											Mix_Farm = true
											Auto_Phoenix_Awaken_Ex = true
											Auto_Raid = true
											TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											Text("กำลังลงดันหาเงินม่วง")
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false
										elseif Auto_Phoenix_Awaken_Ex then
											Auto_Phoenix_Awaken_Ex = nil
											Mix_Farm = nil
											Auto_Raid = nil
										elseif _G.Setting_table.Phoenix_Hop then
											if not UHIkx then
												Text("รอ2ช.มถึงจะซื้อชิปลงดันได้\nฟามเงินม่วงรอดีกว่า")
												UHIkx = true
											end
											_G.Phoenix_R = true
											Raid_FG()
										else
											if not UHIkz then
												Text("รอ2ช.มถึงจะซื้อชิปลงดันได้")
												UHIkz = true
											end
										end
									elseif Beli >= 1000000 then
										if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", "Bird: Phoenix") == 1 then
											_G.Setting_table.Select_Map = "Bird: Phoenix"
											_G.Setting_table.Auto_Awaken = true
											Mix_Farm = true
											Auto_Phoenix_Awaken_Ex = true
											Auto_Raid = true
											TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											Text("กำลังลงดันฟีนิกตื่น")
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false
										elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", "Bird: Phoenix") == '[You already have a Special Microchip.]' then
											_G.Setting_table.Select_Map = "Flame"
											Mix_Farm = true
											Auto_Phoenix_Awaken_Ex = true
											Auto_Raid = true
											TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											Text("กำลังลงดันหาเงินม่วง")
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
											repeat wait(1)
											until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false
										elseif Auto_Phoenix_Awaken_Ex then
											Auto_Phoenix_Awaken_Ex = nil
											Mix_Farm = nil
											Auto_Raid = nil
										elseif _G.Setting_table.Phoenix_Hop then
											if not UHIkxz then
												Text("รอ2ช.มถึงจะซื้อชิปลงดันได้\nฟามเงินม่วงรอดีกว่า")
												UHIkxz = true
											end
											_G.Phoenix_R = true
											Raid_FG()
										else
											if not UHIk then
												Text("รอ2ช.มถึงจะซื้อชิปลงดันได้")
												UHIk = true
											end
										end
									elseif Auto_Phoenix_Awaken_Ex then
										Auto_Phoenix_Awaken_Ex = nil
										Mix_Farm = nil
									else
										Text("กำลังฟามเงินไห้ถึง 1ล้าน\nเพื่อซื้อชิปลงดันฟีนิก")
										wait(10)
									end
								elseif Auto_Phoenix_Awaken_Ex then
									Auto_Phoenix_Awaken_Ex = nil
									Mix_Farm = nil
									Auto_Raid = nil
								else
									_G.Phoenix_R = true
									Raid_FG()
									Text("เงินม่วงไม่ถึง 6000\nไม่สามารถลงดันได้")
									Text("กำลังหาผลมาลงดัน!")
									wait(10)
								end
							elseif FG < 1500 then
								if not LPOJO then
									Text("เงินม่วงไม่ถึง 1500\nไม่สามารถทำเควสได้")
									Text("กำลังหาผลมาลงดัน!")
									LPOJO = true
								end
								_G.Phoenix_R = true
								Raid_FG()
							end
						end
					else
						wait(2)
					end
				else
					wait(2)
				end
			else
				wait(2)
			end
		end)
	end
end)

Quest_Tab:Toggle("Auto Observation Haki V2","9606294253",_G.Setting_table.Farm_Ken_V2,function(vu)
	Farm_Ken = vu
	Farm_Ken_V2 = vu
	_G.Setting_table.Farm_Ken_V2 = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Farm_Ken or _G.Setting_table.Farm_Ken_V2 then
	Farm_Ken = true
end

Quest_Tab:Label("Melee")
Quest_Tab:Toggle("Auto Superhuman","9606294253",_G.Setting_table.Superhuman,function(vu)
	_G.Setting_table.Superhuman = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Death Step","9606294253",_G.Setting_table.Death_Step,function(vu)
	_G.Setting_table.Death_Step = vu
	
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Sharkman Karate","9606294253",_G.Setting_table.Sharkman_Karate,function(vu)
	_G.Setting_table.Sharkman_Karate = vu
	
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Electric Claw","9606294253",_G.Setting_table.Electric_Claw,function(vu)
	_G.Setting_table.Electric_Claw = vu
	
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Dragon Talon","9606294253",_G.Setting_table.Dragon_Talon,function(vu)
	_G.Setting_table.Dragon_Talon = vu
	
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Next Melee","9606294253",_G.Setting_table.Next_Melee,function(vu)
	_G.Setting_table.Next_Melee = vu
	Update_Setting(getgenv()['MyName'])
	-- Auto Exc
end)
Quest_Tab:Toggle("Hop","9606294253",_G.Setting_table.Melee_Hop,function(vu)
	_G.Setting_table.Melee_Hop = vu
	Update_Setting(getgenv()['MyName'])
	-- Auto Exc
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if not Mix_Farm or Farm_Melee_Ex then
				if _G.Setting_table.Superhuman and not Superhuman_H then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman") == 2 then
						_G.Setting_table.Weapon = "Superhuman"
						
						if _G.Setting_table.Next_Melee then
							Superhuman_H = true
						end
					else
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
							_G.Setting_table.Weapon = "Combat"
							if game:GetService("Players").LocalPlayer.Data.Beli.Value > 500000 then
								local args = {
									[1] = "BuyElectro"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							
						end
						
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon = "Black Leg"
							
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon = "Electro"
							
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon = "Fishman Karate"
							
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon = "Dragon Claw"
							
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							
							local args = {
								[1] = "BuyFishmanKarate"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							local args = {
								[1] = "BuyFishmanKarate"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
						
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							
							local args = {
								[1] = "BuyBlackLeg"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							
							local args = {
								[1] = "BuyBlackLeg"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 1500 then
								local args = {
									[1] = "BlackbeardReward",
									[2] = "DragonClaw",
									[3] = "2"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							elseif _G.Setting_table.Melee_Hop and not Mix_Farm then
								Raid_FG()
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 1500 then
								local args = {
									[1] = "BlackbeardReward",
									[2] = "DragonClaw",
									[3] = "2"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							elseif _G.Setting_table.Melee_Hop and not Mix_Farm then
								Raid_FG()
							end
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							if Beli >= 300000 then
								local args = {
									[1] = "BuySuperhuman"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							else
								
								_G.Setting_table.Weapon = "Dragon Claw"
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							if Beli >= 300000 then
								local args = {
									[1] = "BuySuperhuman"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							else
								
								_G.Setting_table.Weapon = "Dragon Claw"
							end
						end
					end
				elseif _G.Setting_table.Death_Step and not Death_Step_H then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 2 then
						_G.Setting_table.Weapon = "Death Step"
						
						if _G.Setting_table.Next_Melee then
							Death_Step_H = true
						end
					else
						if not New_World and _G.Setting_table.Next_Melee then
							TP_World2()
							wait(50)
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon = "Black Leg"
							
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and not game.Players.LocalPlayer.Character:FindFirstChild("Death Step") and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							wait(4)
							if not game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and not game.Players.LocalPlayer.Character:FindFirstChild("Death Step") then
								local args = {
									[1] = "BuyBlackLeg"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 5000 and Beli >= 3000000 then
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") ~= 1 then
									if game.Players.LocalPlayer.Backpack:FindFirstChild("Library Key") or game.Players.LocalPlayer.Character:FindFirstChild("Library Key") then
										Mix_Farm = true
										repeat wait(1)
											EquipWeapon("Library Key")
											TP(CFrame.new(6377.12549, 296.634735, -6843.76025, -0.860993743, 1.17677516e-07, -0.508615494, 1.31121894e-07, 1, 9.40274347e-09, 0.508615494, -5.8594928e-08, -0.860993743))
										until not game.Players.LocalPlayer.Backpack:FindFirstChild("Library Key") and not game.Players.LocalPlayer.Character:FindFirstChild("Library Key")
										Mix_Farm = nil
									else
										if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
											Mix_Farm = true
											Farm_Melee_Ex = true
											if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") and not AutoRaid then
												repeat wait()
													TP(game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
													EquipWeapon(_G.Setting_table.Weapon)
													game:GetService'VirtualUser':CaptureController()
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
												until not game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").Humanoid.Health <= 0 
												Mix_Farm = nil
												Farm_Melee_Ex = nil
											elseif game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
												TP(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
											end
										elseif _G.Setting_table.Melee_Hop then
											wait(5)
											if not game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
												HopServer()
												wait(50)
											end
										end
									end
								elseif Farm_Melee_Ex then
									Farm_Melee_Ex = nil
									Mix_Farm = nil
								elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
								end
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 5000 and Beli >= 3000000 then
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") ~= 1 then
									if game.Players.LocalPlayer.Backpack:FindFirstChild("Library Key") or game.Players.LocalPlayer.Character:FindFirstChild("Library Key") then
										Mix_Farm = true
										repeat wait(1)
											EquipWeapon("Library Key")
											TP(CFrame.new(6377.12549, 296.634735, -6843.76025, -0.860993743, 1.17677516e-07, -0.508615494, 1.31121894e-07, 1, 9.40274347e-09, 0.508615494, -5.8594928e-08, -0.860993743))
										until not game.Players.LocalPlayer.Backpack:FindFirstChild("Library Key") and not game.Players.LocalPlayer.Character:FindFirstChild("Library Key")
										Mix_Farm = nil
									else
										if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
											Mix_Farm = true
											Farm_Melee_Ex = true
											if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") and not AutoRaid then
												repeat wait()
													TP(game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
													EquipWeapon(_G.Setting_table.Weapon)
													game:GetService'VirtualUser':CaptureController()
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
												until not game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").Humanoid.Health <= 0 
												Mix_Farm = nil
												Farm_Melee_Ex = nil
											elseif game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
												TP(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
											end
										elseif _G.Setting_table.Melee_Hop then
											wait(5)
											if not game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
												HopServer()
												wait(50)
											end
										end
									end
								elseif Farm_Melee_Ex then
									Farm_Melee_Ex = nil
									Mix_Farm = nil
								elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
								end
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
					end	
				elseif _G.Setting_table.Sharkman_Karate and not Sharkman_Karate_H then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate") == 2 then
						_G.Setting_table.Weapon = "Sharkman Karate"
						if _G.Setting_table.Next_Melee then
							Sharkman_Karate_H = true
						end
					else
						if not New_World and _G.Setting_table.Next_Melee then
							TP_World2()
							wait(50)
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon  = "Fishman Karate"
							
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							wait(5)
							if not game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") then
								local args = {
										[1] = "BuyFishmanKarate"
									}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
							if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then
								if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
									EquipWeapon("Water Key")
									wait(0.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
								else
									if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
										Mix_Farm = true
										Farm_Melee_Ex = true
										if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") and not AutoRaid then
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then
													repeat wait(_G.Fast_Delay)
														EquipWeapon(_G.Setting_table.Weapon)
														TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
														AttackNoCD()
													until v.Humanoid.Health <= 0 or not v.Parent or not _G.Setting_table.Sharkman_Karate
													Mix_Farm = nil
													Farm_Melee_Ex = nil
												end
											end
										elseif game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
											TP(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
										end
									elseif _G.Setting_table.Melee_Hop then
										wait(5)
										if not game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
											HopServer()
											wait(50)
										end
									end
								end
							elseif FG >= 5000 and Beli >= 3000000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
								local args = {
									[1] = "BuySharkmanKarate",
									[2] = true
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								local args = {
									[1] = "BuySharkmanKarate"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							elseif Farm_Melee_Ex then
								Farm_Melee_Ex = nil
								Mix_Farm = nil
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
							if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then
								if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
									EquipWeapon("Water Key")
									wait(0.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
								else
									if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
										Mix_Farm = true
										Farm_Melee_Ex = true
										if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") and not AutoRaid then
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then
													repeat wait(_G.Fast_Delay)
														EquipWeapon(_G.Setting_table.Weapon)
														TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
														AttackNoCD()
													until v.Humanoid.Health <= 0 or not v.Parent or not _G.Setting_table.Sharkman_Karate
													Mix_Farm = nil
													Farm_Melee_Ex = nil
												end
											end
										elseif game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
											TP(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
										end
									elseif _G.Setting_table.Melee_Hop then
										wait(5)
										if not game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
											HopServer()
											wait(50)
										end
									end
								end
							elseif FG >= 5000 and Beli >= 3000000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
								local args = {
									[1] = "BuySharkmanKarate",
									[2] = true
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								local args = {
									[1] = "BuySharkmanKarate"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							elseif Farm_Melee_Ex then
								Farm_Melee_Ex = nil
								Mix_Farm = nil
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
					end
				elseif _G.Setting_table.Electric_Claw and not Electric_Claw_H then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw") == 2 then
						_G.Setting_table.Weapon = "Electric Claw"
						if _G.Setting_table.Next_Melee then
							Electric_Claw_H = true
						end
					else
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon  = "Electro"
							
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and not game.Players.LocalPlayer.Character:FindFirstChild("Electro") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") then
							wait(5)
							if not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and not game.Players.LocalPlayer.Character:FindFirstChild("Electro") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") then
								local args = {
										[1] = "BuyElectro"
									}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 and Three_World then
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 5000 and Beli >= 3000000 then
								if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true) == 4 then
									if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start") == nil and not AutoRaid then
										Mix_Farm = true
										repeat wait(1)
											TP2(CFrame.new(-12548, 337, -7481))
										until (Vector3.new(-12548, 337, -7481)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10
										Mix_Farm = nil
									end
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
								end
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 and Three_World then
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 5000 and Beli >= 3000000 then
								if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true) == 4 then
									if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start") == nil and not AutoRaid then
										Mix_Farm = true
										repeat wait(1)
											TP2(CFrame.new(-12548, 337, -7481))
										until (Vector3.new(-12548, 337, -7481)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10
										Mix_Farm = nil
									end
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
								end
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
					end
				elseif _G.Setting_table.Dragon_Talon and not Dragon_Talon_H then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon") == 2 then
						_G.Setting_table.Weapon = "Dragon Talon"
						if _G.Setting_table.Next_Melee then
							Dragon_Talon_H = true
						end
					else
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							_G.Setting_table.Weapon = "Dragon Claw"
							
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
							wait(5)
							if not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Talon") then
								local args = {
									[1] = "BlackbeardReward",
									[2] = "DragonClaw",
									[3] = "2"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
						end
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 then
							local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 5000 and Beli >= 3000000 and Lv >= 1950 then
								local B_H = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")
								Auto_Farm_Melee = false
								Auto_Farm_Bone = true
								if tonumber(B_H) >= 500 then
									spawn(function()
										repeat wait(1)
											wait(15)
											IKAIP = true
										until IKAIP == true
									end)
									repeat wait(.1)
										local args = {
											[1] = "Bones",
											[2] = "Check"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										local args = {
											[1] = "Bones",
											[2] = "Buy",
											[3] = 1,
											[4] = 1
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									until IKAIP == true or game.Players.LocalPlayer.Backpack:FindFirstChild("Fire Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Fire Essence")
								end
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Fire Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Fire Essence") then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
								end
								if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Buy",1,1)
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
								elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
								else
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
								end
								wait(2)
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
						if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 then
							local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
							local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
							local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
							if FG >= 5000 and Beli >= 3000000 and Lv >= 1950 then
								local B_H = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")
								Auto_Farm_Melee = false
								Auto_Farm_Bone = true
								if tonumber(B_H) >= 500 then
									spawn(function()
										repeat wait(1)
											wait(15)
											IKAIP = true
										until IKAIP == true
									end)
									repeat wait(.1)
										local args = {
											[1] = "Bones",
											[2] = "Check"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										local args = {
											[1] = "Bones",
											[2] = "Buy",
											[3] = 1,
											[4] = 1
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									until IKAIP == true or game.Players.LocalPlayer.Backpack:FindFirstChild("Fire Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Fire Essence")
								end
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Fire Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Fire Essence") then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
								end
								if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Buy",1,1)
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
								elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
								else
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
								end
								wait(2)
							elseif FG < 5000 and not Mix_Farm and _G.Setting_table.Melee_Hop then
								Raid_FG()
							end
						end
					end
				else
					wait(2)
				end
			else
				wait(3)
			end
		end)
	end
end)
Quest_Tab:Label("Race")
Quest_Tab:Toggle("Auto Mink Evo V0 - V3","9606294253",_G.Setting_table.Mink_Evo,function(vu)
	_G.Setting_table.Mink_Evo = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Human Evo V0 - V3","9606294253",_G.Setting_table.Human_Evo,function(vu)
	_G.Setting_table.Human_Evo = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Skypiea Evo V0 - V3","9606294253",_G.Setting_table.Skypiea_Evo,function(vu)
	_G.Setting_table.Skypiea_Evo = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Fish Evo V0 - V3","9606294253",_G.Setting_table.Fishman_Evo,function(vu)
	_G.Setting_table.Fishman_Evo = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Next Race","9606294253",_G.Setting_table.Next_Race,function(vu)
	_G.Setting_table.Next_Race = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Hop","9606294253",_G.Setting_table.Race_Hop,function(vu)
	_G.Setting_table.Race_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
	if game.Players.LocalPlayer.Data.Race.Value == 'Mink' then
		_G.Setting_table.Mink_Evo_H = true
	elseif game.Players.LocalPlayer.Data.Race.Value == 'Human' then
		_G.Setting_table.Human_Evo_H = true
	elseif game.Players.LocalPlayer.Data.Race.Value == 'Skypiea' then
		_G.Setting_table.Skypiea_Evo_H = true
	elseif game.Players.LocalPlayer.Data.Race.Value == 'Fishman' then
		_G.Setting_table.Fishman_Evo_H = true
	end
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if _G.Setting_table.Mink_Evo and not _G.Setting_table.Mink_Evo_H and game.Players.LocalPlayer.Data.Race.Value == 'Mink' then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
					if game.Players.LocalPlayer.Data.Race.Value == 'Mink' then
						_G.Setting_table.Mink_Evo_H = true
						return
					elseif game.Players.LocalPlayer.Data.Race.Value == 'Human' then
						_G.Setting_table.Human_Evo_H = true
						return
					elseif game.Players.LocalPlayer.Data.Race.Value == 'Skypiea' then
						_G.Setting_table.Skypiea_Evo_H = true
						return
					elseif game.Players.LocalPlayer.Data.Race.Value == 'Fishman' then
						_G.Setting_table.Fishman_Evo_H = true
						return
					end
				end
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") ~= -2 then
						if not UIhjdk then
							Text("กำลังทำเผ่ามิงค์วี 1")
							UIhjdk = true
						end
						pcall(function()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
						end)
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") and game:GetService("Workspace"):FindFirstChild("Flower1") then
							if not YUIk then
								Text("กำลังหา ดอกไม้น้ำเงิน")
								YUIk = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower1").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") or not _G.Setting_table.Mink_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") and game:GetService("Workspace"):FindFirstChild("Flower2") then
							if not YUIkx then
								Text("กำลังหา ดอกไม้แดง")
								YUIkx = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower2").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") or not _G.Setting_table.Mink_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 3") then
							if PO == nil then
								Text("กำลังหา ดอกไม้เหลือง")
								PO = true
							end
							if game:GetService("Workspace").Enemies:FindFirstChild("Marine Captain [Lv. 900]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Marine Captain [Lv. 900]" then
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") or not _G.Setting_table.Mink_Evo
									end
								end
							else
								TP2(CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406))
							end
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
							wait(2)
						else
							if not UHuit then
								Text("รอดอกไม้เกิด")
								TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
								UHuit = true
							end
							wait(2)
						end
					elseif _G.Setting_table.Mink_Evo_V2 ~= true then
						if not UIjfiz then
							Text("กำลังทำเผ่ามิงค์วี 2")
							UIjfiz = true
						end
						if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							repeat wait(_G.Fast_Delay)
								EquipWeapon(_G.Setting_table.Weapon)
								TP(game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
								AttackNoCD()
							until not game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not _G.Setting_table.Mink_Evo 
							_G.Setting_table.Mink_Evo_V2 = true
							Update_Setting(getgenv()['MyName'])
						elseif game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						else
							Text("รอบอสโดฟาเกิด")
							TP(CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072))
							wait(10)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") ~= -2 then
						if not UIjfi then
							Text("กำลังทำเผ่ามิงค์วี 3")
							UIjfi = true
						end
						if not ijoijofdga then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
							ijoijofdga = true
						end
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","3")
						for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
                            if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                repeat wait()
                                    TP2(v.CFrame)
                                until not v.Parent or not _G.Setting_table.Mink_Evo 
                            elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                repeat wait()
                                    TP2(v.CFrame)
                                until not v.Parent or not _G.Setting_table.Mink_Evo 
                            elseif New_World then
                                TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
                            end
                        end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
						if not IUHidm then
							Text("ทำเผ่ามิงค์วี 3 เสร็จสิ้น!")
							IUHidm = true
						end
						if _G.Setting_table.Next_Race then
							_G.Setting_table.Mink_Evo_H = true
							Update_Setting(getgenv()['MyName'])
						end
					end
				else
					Text("ประตูโดฟายังไม่เปิด\nไม่สามารถทำเผ่าได้")
					wait(5)
				end
			elseif _G.Setting_table.Human_Evo and not _G.Setting_table.Human_Evo_H and game.Players.LocalPlayer.Data.Race.Value == 'Human' then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") ~= -2 then
						if not UIhjdkh then
							Text("กำลังทำเผ่าคนวี 1")
							UIhjdkh = true
						end
						pcall(function()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
						end)
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") and game:GetService("Workspace"):FindFirstChild("Flower1") then
							if not YUIks then
								Text("กำลังหา ดอกไม้น้ำเงิน")
								YUIks = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower1").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") or not _G.Setting_table.Human_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") and game:GetService("Workspace"):FindFirstChild("Flower2") then
							if not YUIkxz then
								Text("กำลังหา ดอกไม้แดง")
								YUIkxz = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower2").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") or not _G.Setting_table.Human_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 3") then
							if POs == nil then
								Text("กำลังหา ดอกไม้เหลือง")
								POs = true
							end
							if game:GetService("Workspace").Enemies:FindFirstChild("Marine Captain [Lv. 900]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Marine Captain [Lv. 900]" then
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") or not _G.Setting_table.Human_Evo
									end
								end
							else
								TP2(CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406))
							end
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
							wait(2)
						else
							if not UHuits then
								Text("รอดอกไม้เกิด")
								TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
								UHuits = true
							end
							wait(2)
						end
					elseif _G.Setting_table.Human_Evo_V2 ~= true then
						if not UIjfize then
							Text("กำลังทำเผ่าคนวี 2")
							UIjfize = true
						end
						if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							repeat wait(_G.Fast_Delay)
								EquipWeapon(_G.Setting_table.Weapon)
								TP(game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
								AttackNoCD()
							until not game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not _G.Setting_table.Human_Evo 
							_G.Setting_table.Human_Evo_V2 = true
							Update_Setting(getgenv()['MyName'])
						elseif game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						else
							Text("รอบอสโดฟาเกิด")
							TP(CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072))
							wait(10)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") ~= -2 then
						if not UIjfie then
							Text("กำลังทำเผ่าคนวี 3")
							UIjfie = true
						end
						if not ijoijofdga then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
							ijoijofdga = true
						end
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","3")
						if game.Workspace.Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Fajita [Lv. 925] [Boss]" then
									repeat twait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not _G.Setting_table.Human_Evo
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Fajita [Lv. 925] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Fajita [Lv. 925] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						elseif game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Jeremy [Lv. 850] [Boss]" then
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not _G.Setting_table.Human_Evo
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Jeremy [Lv. 850] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						elseif game.Workspace.Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Diamond [Lv. 750] [Boss]" then
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not _G.Setting_table.Human_Evo
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Diamond [Lv. 750] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Diamond [Lv. 750] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						else
							if not IJOijogr then
								TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
								IJOijogr = true
							end
							Text("รอบอสเกิด 5 - 15นาที")
							wait(10)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
						if not IUHidmr then
							Text("ทำเผ่าคนวี 3 เสร็จสิ้น!")
							IUHidmr = true
						end
						if _G.Setting_table.Next_Race then
							_G.Setting_table.Human_Evo_H = true
							Update_Setting(getgenv()['MyName'])
						end
					end
				else
					Text("ประตูโดฟายังไม่เปิด\nไม่สามารถทำเผ่าได้")
					wait(5)
				end
			elseif _G.Setting_table.Skypiea_Evo and not _G.Setting_table.Skypiea_Evo_H and game.Players.LocalPlayer.Data.Race.Value == 'Skypiea' then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") ~= -2 then
						if not UIhjdkhz then
							Text("กำลังทำเผ่าปีกวี 1")
							UIhjdkhz = true
						end
						pcall(function()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
						end)
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") and game:GetService("Workspace"):FindFirstChild("Flower1") then
							if not YUIksz then
								Text("กำลังหา ดอกไม้น้ำเงิน")
								YUIksz = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower1").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") or not _G.Setting_table.Skypiea_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") and game:GetService("Workspace"):FindFirstChild("Flower2") then
							if not YUIkxzx then
								Text("กำลังหา ดอกไม้แดง")
								YUIkxzx = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower2").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") or not _G.Setting_table.Skypiea_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 3") then
							if POsz == nil then
								Text("กำลังหา ดอกไม้เหลือง")
								POsz = true
							end
							if game:GetService("Workspace").Enemies:FindFirstChild("Marine Captain [Lv. 900]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Marine Captain [Lv. 900]" then
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") or not _G.Setting_table.Skypiea_Evo
									end
								end
							else
								TP2(CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406))
							end
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
							wait(2)
						else
							if not UHuitsz then
								Text("รอดอกไม้เกิด")
								TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
								UHuitsz = true
							end
							wait(2)
						end
					elseif _G.Setting_table.Skypiea_Evo_V2 ~= true then
						if not UIjfizez then
							Text("กำลังทำเผ่าปีกวี 2")
							UIjfizez = true
						end
						if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							repeat wait(_G.Fast_Delay)
								EquipWeapon(_G.Setting_table.Weapon)
								TP(game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
								AttackNoCD()
							until not game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not _G.Setting_table.Skypiea_Evo 
							_G.Setting_table.Skypiea_Evo_V2 = true
							Update_Setting(getgenv()['MyName'])
						elseif game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						else
							Text("รอบอสโดฟาเกิด")
							TP(CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072))
							wait(10)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") ~= -2 then
						if not UIjfiez then
							Text("กำลังทำเผ่าปีกวี 3")
							UIjfiez = true
						end
						if not ijoijofdga then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
							ijoijofdga = true
						end
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","3")
						_G.Select_Player = nil
						Check_Race_Skypiea()
						if _G.Select_Player ~= nil then
							print(_G.Select_Player)
							repeat wait(_G.Fast_Delay)
								EquipWeapon(_G.Setting_table.Weapon)
								TP(game.Players:FindFirstChild(_G.Select_Player).Character.HumanoidRootPart.CFrame*CFrame.new(0,0,2))
								AttackNoCD()
							until game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 or game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid.Health <= 0 or not game.Players:FindFirstChild(_G.Select_Player) or not _G.Setting_table.Skypiea_Evo
						elseif _G.Setting_table.Race_Hop then
							Text("ไม่มีคนที่มีเผ่าสกายเปีย\nในโลกนี้เลย")
							HopServer()
							wait(50)
						else
							Text("ไม่มีคนที่มีเผ่าสกายเปีย\nในโลกนี้เลย")
							wait(7)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
						if not IUHidmrz then
							Text("ทำเผ่าปีกวี 3 เสร็จสิ้น!")
							IUHidmrz = true
						end
						if _G.Setting_table.Next_Race then
							_G.Setting_table.Skypiea_Evo_H = true
							Update_Setting(getgenv()['MyName'])
						end
					end
				else
					Text("ประตูโดฟายังไม่เปิด\nไม่สามารถทำเผ่าได้")
					wait(5)
				end
			elseif _G.Setting_table.Fishman_Evo and not _G.Setting_table.Fishman_Evo_H and game.Players.LocalPlayer.Data.Race.Value == 'Fishman' then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") ~= -2 then
						if not UIhjdkhzt then
							Text("กำลังทำเผ่าเงือกวี 1")
							UIhjdkhzt = true
						end
						pcall(function()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
						end)
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") and game:GetService("Workspace"):FindFirstChild("Flower1") then
							if not YUIkszt then
								Text("กำลังหา ดอกไม้น้ำเงิน")
								YUIkszt = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower1").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") or not _G.Setting_table.Fishman_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") and game:GetService("Workspace"):FindFirstChild("Flower2") then
							if not YUIkxzxt then
								Text("กำลังหา ดอกไม้แดง")
								YUIkxzxt = true
							end
							repeat wait(1)
								TP2(game:GetService("Workspace"):FindFirstChild("Flower2").CFrame)
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") or not _G.Setting_table.Fishman_Evo
						elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 3") then
							if POszt == nil then
								Text("กำลังหา ดอกไม้เหลือง")
								POszt = true
							end
							if game:GetService("Workspace").Enemies:FindFirstChild("Marine Captain [Lv. 900]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Marine Captain [Lv. 900]" then
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") or not _G.Setting_table.Fishman_Evo
									end
								end
							else
								TP2(CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406))
							end
						elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
							wait(2)
						else
							if not UHuitszt then
								Text("รอดอกไม้เกิด")
								TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
								UHuitszt = true
							end
							wait(2)
						end
					elseif _G.Setting_table.Fishman_Evo_V2 ~= true then
						if not UIjfizezt then
							Text("กำลังทำเผ่าเงือกวี 2")
							UIjfizezt = true
						end
						if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							repeat wait(_G.Fast_Delay)
								EquipWeapon(_G.Setting_table.Weapon)
								TP(game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
								AttackNoCD()
							until not game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not _G.Setting_table.Fishman_Evo 
							_G.Setting_table.Fishman_Evo_V2 = true
							Update_Setting(getgenv()['MyName'])
						elseif game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						else
							Text("รอบอสโดฟาเกิด")
							TP(CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072))
							wait(10)
						end
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") ~= -2 then
						if not UIjfiezt then
							Text("กำลังทำเผ่าเงือกวี 3")
							UIjfiezt = true
						end
						if not ijoijofdg then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
							ijoijofdg = true
						end
						for i,v in pairs(game:GetService("Workspace").SeaBeasts:GetChildren()) do
							if v:FindFirstChild("HumanoidRootPart") then
								_G.Ping = true
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
									AttackNoCD()
								until not v.Parent or not _G.Setting_table.Fishman_Evo or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2
							end
						end
						Text("เจ้าทะเลยังไม่เกิด")
						if _G.Setting_table.Race_Hop and not _G.Ping then
							HopServer()
							wait(50)
						end
						wait(9)
					elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
						if not IUHidmrzt then
							Text("ทำเผ่าเงือกวี 3 เสร็จสิ้น!")
							IUHidmrzt = true
						end
						if _G.Setting_table.Next_Race then
							_G.Setting_table.Fishman_Evo_H = true
							Update_Setting(getgenv()['MyName'])
						end
					end
				else
					Text("ประตูโดฟายังไม่เปิด\nไม่สามารถทำเผ่าได้")
					wait(5)
				end
			elseif _G.Setting_table.Next_Race and _G.Setting_table.Mink_Evo and not _G.Setting_table.Mink_Evo_H and game.Players.LocalPlayer.Data.Race.Value ~= 'Mink' then
				local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
				if FG >= 3000 then
					local args = {
						[1] = "BlackbeardReward",
						[2] = "Reroll",
						[3] = "2"
					}
					
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					wait(5)
				elseif not Mix_Farm then
					_G.Have_Fruit = nil
					Raid_FG()
				end
			elseif _G.Setting_table.Next_Race and _G.Setting_table.Human_Evo and not _G.Setting_table.Human_Evo_H and game.Players.LocalPlayer.Data.Race.Value ~= 'Human' then
				local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
				if FG >= 3000 then
					local args = {
						[1] = "BlackbeardReward",
						[2] = "Reroll",
						[3] = "2"
					}
					
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					wait(5)
				elseif not Mix_Farm then
					_G.Have_Fruit = nil
					Raid_FG()
				end
			elseif _G.Setting_table.Next_Race and _G.Setting_table.Skypiea_Evo and not _G.Setting_table.Skypiea_Evo_H and game.Players.LocalPlayer.Data.Race.Value ~= 'Skypiea' then
				local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
				if FG >= 3000 then
					local args = {
						[1] = "BlackbeardReward",
						[2] = "Reroll",
						[3] = "2"
					}
					
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					wait(5)
				elseif not Mix_Farm then
					_G.Have_Fruit = nil
					Raid_FG()
				end
			elseif _G.Setting_table.Next_Race and _G.Setting_table.Fishman_Evo and not _G.Setting_table.Fishman_Evo_H and game.Players.LocalPlayer.Data.Race.Value ~= 'Fishman' then
				local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
				if FG >= 3000 then
					local args = {
						[1] = "BlackbeardReward",
						[2] = "Reroll",
						[3] = "2"
					}
					
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					wait(5)
				elseif not Mix_Farm then
					_G.Have_Fruit = nil
					Raid_FG()
				end
			elseif _G.Setting_table.Mink_Evo_H and _G.Setting_table.Fishman_Evo_H and _G.Setting_table.Skypiea_Evo_H and _G.Setting_table.Human_Evo_H then
				Text("อีโวเผ่าขั้น 3 ครบทั้ง4เผ่าแล้ว")
				wait(10)
			else
				wait(2)
			end
		end)
	end
end)

function Check_Race_Skypiea()
	for i,v in pairs(game.Players:GetChildren()) do
		if v.Name ~= game.Players.LocalPlayer.Name and tostring(v.Data.Race.Value) == "Skypiea" then
			print(v.Name)
			_G.Select_Player = v.Name
			return
		end
	end
end

Quest_Tab:Label("Gun")
Quest_Tab:Toggle("Auto Acidum Rifle","9610159123",_G.Setting_table.Auto_Acidum_Rifle,function(vu)
	Auto_Acidum_Rifle = vu
	_G.Setting_table.Auto_Acidum_Rifle = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Acidum_Rifle then
				if not Mix_Farm or Auto_Acidum_Rifle_Farm then
					if game.Workspace.Enemies:FindFirstChild("Core") or game.ReplicatedStorage:FindFirstChild("Core") then
						Mix_Farm = true
						Auto_Acidum_Rifle_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Core") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Core" then
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(CFrame.new(402.404296875, 182.53373718262, -414.73394775391))
										AttackNoCD()
									until not game.Workspace.Enemies:FindFirstChild("Core") or not Auto_Acidum_Rifle
									Mix_Farm = nil
									Auto_Acidum_Rifle_Farm = nil
								end
							end
						else
							TP(CFrame.new(402.404296875, 182.53373718262, -414.73394775391))
						end
					elseif _G.Setting_table.Auto_Acidum_Rifle_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Core") and not game.ReplicatedStorage:FindFirstChild("Core") then
							HopServer()
							wait(50)
						end
					elseif Auto_Acidum_Rifle_Farm then
						Auto_Acidum_Rifle_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Serpent Bow","9610159123",_G.Setting_table.Auto_Serpent_Bow,function(vu)
	Auto_Serpent_Bow = vu
	_G.Setting_table.Auto_Serpent_Bow = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Serpent_Bow then
				if not Mix_Farm or Auto_Serpent_Bow_Farm then
					if game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") or game.ReplicatedStorage:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
						Auto_Serpent_Bow_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Island Empress [Lv. 1675] [Boss]" and v.Humanoid.Health > 0 then
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Serpent_Bow
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Island Empress [Lv. 1675] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Serpent_Bow_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Serpent_Bow_Farm then
						Auto_Serpent_Bow_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(2)
			end
		end)
	end
end)

Quest_Tab:Label("Accessory")
Quest_Tab:Toggle("Auto Dark Coat","9606294253",_G.Setting_table.Auto_Dark_Coat,function(vu)
	Auto_Dark_Coat = vu
	_G.Setting_table.Auto_Dark_Coat = vu
	Update_Setting(getgenv()['MyName'])
end)
function Chest_100()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
			_G.Chest_100 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
			_G.Chest_100 = v
			return
		end
	end
end
function Chest_500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 500 then
			_G.Chest_500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 500 then
			_G.Chest_500 = v
			return
		end
	end
end
function Chest_1000()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
			_G.Chest_1000 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
			_G.Chest_1000 = v
			return
		end
	end
end
function Chest_1500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1500 then
			_G.Chest_1500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1500 then
			_G.Chest_1500 = v
			return
		end
	end
end
function Chest_2000()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2000 then
			_G.Chest_2000 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2000 then
			_G.Chest_2000 = v
			return
		end
	end
end
function Chest_2500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2500 then
			_G.Chest_2500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2500 then
			_G.Chest_2500 = v
			return
		end
	end
end
function Chest_3500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3500 then
			_G.Chest_3500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3500 then
			_G.Chest_3500 = v
			return
		end
	end
end
function Chest_4500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4500 then
			_G.Chest_4500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4500 then
			_G.Chest_4500 = v
			return
		end
	end
end
function Chest_5500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5500 then
			_G.Chest_5500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5500 then
			_G.Chest_5500 = v
			return
		end
	end
end
function Chest_6500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 6500 then
			_G.Chest_6500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 6500 then
			_G.Chest_6500 = v
			return
		end
	end
end
function Chest_7500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 7500 then
			_G.Chest_7500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 7500 then
			_G.Chest_7500 = v
			return
		end
	end
end
function Chest_9500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 9500 then
			_G.Chest_9500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 9500 then
			_G.Chest_9500 = v
			return
		end
	end
end
function Chest_10500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10500 then
			_G.Chest_10500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10500 then
			_G.Chest_10500 = v
			return
		end
	end
end
function Chest_12500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 12500 then
			_G.Chest_12500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 12500 then
			_G.Chest_12500 = v
			return
		end
	end
end
function Chest_15500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 15500 then
			_G.Chest_15500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 15500 then
			_G.Chest_15500 = v
			return
		end
	end
end
function Chest_17500()
	for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
		if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 17500 then
			_G.Chest_17500 = v
			return
		elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 17500 then
			_G.Chest_17500 = v
			return
		end
	end
end

Quest_Tab:Toggle("Auto Swan Glass","9610159123",_G.Setting_table.Auto_Swan_Glass,function(vu)
	Auto_Swan_Glass = vu
	_G.Setting_table.Auto_Swan_Glass = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Swan_Glass then
				if not Mix_Farm or Auto_Swan_Glass_Farm then
					if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
						Auto_Swan_Glass_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Don Swan [Lv. 1000] [Boss]" and v.Humanoid.Health > 0 then
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Swan_Glass
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Swan_Glass_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Swan_Glass_Farm then
						Auto_Swan_Glass_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(3)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Pale Scarf","9606294253",_G.Setting_table.Auto_Pale_Scarf,function(vu)
	Auto_Pale_Scarf = vu
	_G.Setting_table.Auto_Pale_Scarf = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Pale_Scarf then
				if game.Workspace.Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" and v.Humanoid.Health > 0 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Pale_Scarf
							end
						end
					elseif game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
						TP(game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
					end
				elseif _G.Setting_table.Auto_Pale_Scarf_Hop then
					wait(5)
					if not game.Workspace.Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") and not game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
						HopServer()
						wait(50)
					end
				else
					if (Vector3.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1200 then
						CFrameMon = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								_G.PosMon = v.HumanoidRootPart.CFrame
								StatrMagnet = true
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Pale_Scarf
								StatrMagnet = false
							end
						end
					else
						TP(CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625))
					end
				end
			else
				wait(3)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Valkyrie Helmet","9610159123",_G.Setting_table.Auto_Valkyrie_Helmet,function(vu)
	Auto_Valkyrie_Helmet = vu
	_G.Setting_table.Auto_Valkyrie_Helmet = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Valkyrie_Helmet then
				if not Mix_Farm or Auto_Valkyrie_Helmet_Farm then
					if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
						Auto_Valkyrie_Helmet_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Valkyrie_Helmet
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Valkyrie_Helmet_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") and not game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Valkyrie_Helmet_Farm then
						Auto_Valkyrie_Helmet_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(2)
			end
		end)
	end
end)

Quest_Tab:Label("Sword")
Quest_Tab:Toggle("Auto Saber","9606294253",_G.Setting_table.Saber_Farm,function(vu)
	Saber_Farm = vu
	_G.Setting_table.Saber_Farm = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.2) do
        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
        if Old_World and Saber_Farm then
            if Auto_Farm then
                Auto_Farm = false
            end
            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                Auto_Farm = false
                repeat wait()
                    TP(CFrame.new(-1609.29956, 40.0520697, 162.820404))
                until (Vector3.new(-1609.29956, 40.0520697, 162.820404)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10
                wait(3)
                for i,v in pairs(game:GetService("Workspace").Map.Jungle.QuestPlates:GetChildren()) do
                    if v.Name == "Plate1" then
                        repeat wait()
                        TP2(v.Button.CFrame)
                        until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                        wait(1)
                    end
                    if v.Name == "Plate2" then
                        repeat wait()
                        TP2(v.Button.CFrame)
                        until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                        wait(1)
                    end
                    if v.Name == "Plate3" then
                        repeat wait()
                        TP2(v.Button.CFrame)
                        until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                        wait(1)
                    end
                    if v.Name == "Plate4" then
                        repeat wait()
                        TP2(v.Button.CFrame)
                        until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                        wait(1)
                    end
                    if v.Name == "Plate5" then
                        repeat wait()
                        TP2(v.Button.CFrame)
                        until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                        wait(1)
                    end
                end
                wait(2)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1609.29956, 12.0520697, 162.820404, -0.993804812, 2.60902091e-08, 0.11113929, 3.47902116e-08, 1, 7.63408607e-08, -0.11113929, 7.97344768e-08, -0.993804812)
                wait(2)
                repeat wait()
                    EquipWeapon("Torch")
                    TP(CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199))
                until (Vector3.new(1113.9502, 4.92147732, 4350.91992)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1
                wait(1)
                --fireclickdetector(game:GetService("Workspace").Map.Desert.Burn.Fire.ClickDetector)
                wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199)
                wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199)
                wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.87708, 4.9214654, 4349.8501, -0.612586915, -9.68697833e-08, 0.790403247, -1.2634203e-07, 1, 2.4638446e-08, -0.790403247, -8.47679615e-08, -0.612586915)
                wait(10)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.33618, 7.5484705, 4365.56396, -0.618000686, 2.54492516e-08, -0.786177576, -8.16741874e-09, 1, 3.87911392e-08, 0.786177576, 3.03939913e-08, -0.618000686)
                wait(2)
                repeat wait()
                    EquipWeapon("Cup")
                    TP(CFrame.new(1397.73975, 37.3480263, -1321.54456, -0.170597032, -4.99889588e-08, 0.985340893, 2.99880867e-08, 1, 5.59246409e-08, -0.985340893, 3.90890662e-08, -0.170597032))
                until (Vector3.new(1397.73975, 37.3480263, -1321.54456)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1397.73975, 37.3480263, -1321.54456, -0.170597032, -4.99889588e-08, 0.985340893, 2.99880867e-08, 1, 5.59246409e-08, -0.985340893, 3.90890662e-08, -0.170597032)
                wait(3)
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan")
                wait(1)
                Mob_Boss = true
                Saber_Farm = false
                
            else
                Auto_Farm = false
                Mob_Boss = true
                Saber_Farm = false
            end
        elseif not Old_World and Saber_Farm then
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
        end
    end
end)

spawn(function()
    while wait(.2) do
        if Mob_Boss then
            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Relic") or game.Players.LocalPlayer.Character:FindFirstChild("Relic") then
                    EquipWeapon("Relic")
                    repeat wait()
                        EquipWeapon("Relic")
                        TP2(CFrame.new(-1406.60925, 29.8520069, 4.5805192, 0.882920146, 3.62382622e-08, 0.469523162, -3.61928865e-09, 1, -7.03750587e-08, -0.469523162, 6.04362143e-08, 0.882920146))
                    until (Vector3.new(-1406.60925, 29.8520069, 4.5805192)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                    wait(1)
                    Saber_Kill = true
                    Mob_Boss = false
                else
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                end
            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
                if game.Workspace.Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                        if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                            
                            repeat wait()
                                EquipWeapon(_G.Setting_table.Weapon)
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                            until not v.Parent or v.Humanoid.Health <= 0 or Mob_Boss == false
                        end
                    end
                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]").HumanoidRootPart.CFrame)
                end
            else
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
            end
        end
    end
end)

spawn(function()
    while wait(.2) do
        pcall(function()
            if Saber_Kill then
                if game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                        if v.Name == "Saber Expert [Lv. 200] [Boss]" then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                             
                            repeat wait()
                                EquipWeapon(_G.Setting_table.Weapon)
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,15))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                            until not v.Parent or v.Humanoid.Health <= 0 or Saber_Kill == false
                        end
                    end
                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                    TP(game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]").HumanoidRootPart.CFrame)
                elseif _G.Hop_Saber then
                    wait(5)
                    if not game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                        _G.Hop_Saber_Ex = true
                    end
                else
                    TP2(CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094))
                end
            end
        end)
    end
end)

Quest_Tab:Toggle("Auto Pole V1","9610159123",_G.Setting_table.Pole_Farm,function(vu)
	Pole_Farm = vu
	_G.Setting_table.Pole_Farm = vu
	Update_Setting(getgenv()['MyName'])
end)

spawn(function()
	while wait(.5) do
		pcall(function()
			if Pole_Farm then
				if not Mix_Farm or Pole_Farm_Ex then
					if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") or game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
						Pole_Farm_Ex = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Thunder God [Lv. 575] [Boss]" then
									repeat wait(.2)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,15))
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
										game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
										wait(.1)
										game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
										game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
										wait(.1)
										game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
										game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
										wait(.1)
										game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
									until v.Humanoid.Health <= 0 or not v.Parent or not Pole_Farm 
									Pole_Farm_Ex = nil
									Mix_Farm = nil
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Pole_V1_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
							HopServer()
							wait(50)
						end
					elseif Pole_Farm_Ex then
						Mix_Farm = nil
						Pole_Farm_Ex = nil
					else
						wait(5)
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Seperator("Second World")
Quest_Tab:Toggle("Auto Rengoku","9606294253",_G.Setting_table.Rengoku_A,function(vu)
	Rengoku_A = vu
	_G.Setting_table.Rengoku_A = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.3) do
        pcall(function()
            if Rengoku_A then
                if not Mix_Farm or Rengoku_Farm then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key") then
                        repeat wait(.3)
							EquipWeapon("Hidden Key")
                            TP(CFrame.new(6572.29248, 295.712677, -6966.09961, 0.803500533, -3.27515153e-08, 0.595304072, 3.97485422e-08, 1, 1.36659384e-09, -0.595304072, 2.25644108e-08, 0.803500533))
                        until not game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") and not game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key")
                    else
                        if game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Snow Lurker [Lv. 1375]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									_G.PosMon = v.HumanoidRootPart.CFrame
									StatrMagnet = true
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Rengoku_A
									StatrMagnet = false
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Snow Lurker [Lv. 1375]") then
							TP(game.ReplicatedStorage:FindFirstChild("Snow Lurker [Lv. 1375]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
                    end
                end
			else
				wait(2)
            end
        end)
    end
end)
Quest_Tab:Toggle("Auto Ko Ko","9606294253",false,function(vu)
	if vu then
		Text("ยังไม่ทำ")
	end
end)
Quest_Tab:Toggle("Auto Dragon Trident","9610159123",_G.Setting_table.Auto_Dragon_Trident,function(vu)
	Auto_Dragon_Trident = vu
	_G.Setting_table.Auto_Dragon_Trident = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Dragon_Trident then
				if not Mix_Farm or Auto_Dragon_Trident_Farm then
					if game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game.ReplicatedStorage:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
						Auto_Dragon_Trident_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Tide Keeper [Lv. 1475] [Boss]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Dragon_Trident
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif Auto_Dragon_Trident_Farm then
						Auto_Dragon_Trident_Farm = nil
						Mix_Farm = nil
					elseif _G.Setting_table.Auto_Dragon_Trident_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
							HopServer()
							wait(50)
						end
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto True Triple Katana","9606294253",_G.Setting_table.Triple_A,function(vu)
	Auto_Farm_Sword = vu
	Triple_A = vu
	_G.Setting_table.Triple_A = vu
	Update_Setting(getgenv()['MyName'])
end)
function Dis()
    if New_World then
        repeat wait(.2)
			Mix_Farm = true
            TP(CFrame.new(121.6969223022461, 18.738399505615234, 2850.1474609375))
        until (Vector3.new(121.6969223022461, 18.738399505615234, 2850.1474609375)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2
		wait(1)
		for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
			if tostring(v2.ToolTip) == "Melee" then
				EquipWeapon(v2.Name)
			end
		end
		wait(1)
        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
            if tostring(v2.ToolTip) == "Sword" then
                local args = {
                    [1] = "StoreItem",
                    [2] = v2.Name
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end
		wait(1)
		Mix_Farm = nil
    elseif Three_World then
        repeat wait(.2)
			Mix_Farm = true
            TP(CFrame.new(-220.47975158691406, 5.787993431091309, 5324.3720703125))
        until (Vector3.new(-220.47975158691406, 5.787993431091309, 5324.3720703125)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2
        wait(1)
		for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
			if tostring(v2.ToolTip) == "Melee" then
				EquipWeapon(v2.Name)
			end
		end
		wait(1)
        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
            if tostring(v2.ToolTip) == "Sword" then
                local args = {
                    [1] = "StoreItem",
                    [2] = v2.Name
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end
		wait(1)
		Mix_Farm = nil
    end
end
function Load(vu)
    if New_World then
        repeat wait(.2)
			Mix_Farm = true
            TP(CFrame.new(121.6969223022461, 18.738399505615234, 2850.1474609375))
        until (Vector3.new(121.6969223022461, 18.738399505615234, 2850.1474609375)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2
		wait(1)
        local args = {
            [1] = "LoadItem",
            [2] = tostring(vu)
        }
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		wait(2)
		Mix_Farm = nil
    elseif Three_World then
        repeat wait(.2)
			Mix_Farm = true
            TP(CFrame.new(-220.47975158691406, 5.787993431091309, 5324.3720703125))
        until (Vector3.new(-220.47975158691406, 5.787993431091309, 5324.3720703125)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2
		wait(1)
        local args = {
            [1] = "LoadItem",
            [2] = tostring(vu)
        }
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		wait(2)
		Mix_Farm = nil
    end
end
local I_W = game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryWeapons")

for i,x in pairs(I_W) do
    v = {
        Name = x["Name"]
    }
	if v.Name == "Shisui" then
		_G.Setting_table.Shisui = true
	end
	if v.Name == "Wando" then
		_G.Setting_table.Wando = true
	end
		if v.Name == "Saddi" then
		_G.Setting_table.Saddi = true
	end
end
for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
	if v:IsA("Tool") then
		if v.Name == "Shisui" then
			_G.Setting_table.Shisui = true
		end
		if v.Name == "Wando" then
			_G.Setting_table.Wando = true
		end
			if v.Name == "Saddi" then
			_G.Setting_table.Saddi = true
		end
	end
end
for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
	if v:IsA("Tool") then
		if v.Name == "Shisui" then
			_G.Setting_table.Shisui = true
		end
		if v.Name == "Wando" then
			_G.Setting_table.Wando = true
		end
			if v.Name == "Saddi" then
			_G.Setting_table.Saddi = true
		end
	end
end
spawn(function()
    while wait(.1) do
        pcall(function()
            if Triple_A then
                local args = {
                    [1] = "LegendarySwordDealer",
                    [2] = "2"
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end)
    end
end)
spawn(function()
    while wait(.3) do
        pcall(function()
            if Triple_A then
                if game.Players.LocalPlayer.Backpack:FindFirstChild("True Triple Katana") or game.Players.LocalPlayer.Character:FindFirstChild("True Triple Katana") then
                    _G.Setting_table.Weapon = "True Triple Katana"
					Auto_Farm_Sword = true
                elseif _G.Setting_table.Shisui_H and _G.Setting_table.Wando_H and _G.Setting_table.Saddi_H then
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    if Beli >= 3000000 then
                        pcall(function()
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("MysteriousMan","1")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("MysteriousMan","2")
                        end)
                    else
                        Auto_Farm_Sword = true
                    end
                elseif _G.Setting_table.Shisui and not _G.Setting_table.Shisui_H then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui") or game.Players.LocalPlayer.Character:FindFirstChild("Shisui") then
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui") and game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui").Level.Value >= 300 then
                            _G.Setting_table.Weapon = "Shisui"
                            _G.Setting_table.Shisui_H = true
                            Update_Setting(getgenv()['MyName'])
                        elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui") and game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui").Level.Value < 300 then
                            _G.Setting_table.Weapon = "Shisui"
							Auto_Farm_Sword = true
                        end
						if game.Players.LocalPlayer.Character:FindFirstChild("Shisui") and game.Players.LocalPlayer.Character:FindFirstChild("Shisui").Level.Value >= 300 then
                            _G.Setting_table.Weapon = "Shisui"
                            _G.Setting_table.Shisui_H = true
                            Update_Setting(getgenv()['MyName'])
                        elseif game.Players.LocalPlayer.Character:FindFirstChild("Shisui") and game.Players.LocalPlayer.Character:FindFirstChild("Shisui").Level.Value < 300 then
                            _G.Setting_table.Weapon = "Shisui"
							Auto_Farm_Sword = true
                        end
                    else
						wait(5)
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui") or game.Players.LocalPlayer.Character:FindFirstChild("Shisui") then
						else
							Dis()
							Load("Shisui")
						end
                    end
                elseif _G.Setting_table.Wando and not _G.Setting_table.Wando_H then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Wando") or game.Players.LocalPlayer.Character:FindFirstChild("Wando") then
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Wando") and game.Players.LocalPlayer.Backpack:FindFirstChild("Wando").Level.Value >= 300 then
                            _G.Setting_table.Weapon = "Wando"
                            _G.Setting_table.Wando_H = true
                            Update_Setting(getgenv()['MyName'])
                        elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Wando") and game.Players.LocalPlayer.Backpack:FindFirstChild("Wando").Level.Value < 300 then
                            _G.Setting_table.Weapon = "Wando"
							Auto_Farm_Sword = true
                        end
						if game.Players.LocalPlayer.Character:FindFirstChild("Wando") and game.Players.LocalPlayer.Character:FindFirstChild("Wando").Level.Value >= 300 then
                            _G.Setting_table.Weapon = "Wando"
                            _G.Setting_table.Wando_H = true
                            Update_Setting(getgenv()['MyName'])
                        elseif game.Players.LocalPlayer.Character:FindFirstChild("Wando") and game.Players.LocalPlayer.Character:FindFirstChild("Wando").Level.Value < 300 then
                            _G.Setting_table.Weapon = "Wando"
							Auto_Farm_Sword = true
                        end
                    else
						wait(5)
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Wando") or game.Players.LocalPlayer.Character:FindFirstChild("Wando") then
						else
							Dis()
							Load("Wando")
						end
                    end
                elseif _G.Setting_table.Saddi and not _G.Setting_table.Saddi_H then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi") or game.Players.LocalPlayer.Character:FindFirstChild("Saddi") then
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi") and game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi").Level.Value >= 300 then
                            _G.Setting_table.Weapon = "Saddi"
                            _G.Setting_table.Saddi_H = true
                            Update_Setting(getgenv()['MyName'])
                        elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi") and game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi").Level.Value < 300 then
                            _G.Setting_table.Weapon = "Saddi"
							Auto_Farm_Sword = true
                        end
						if game.Players.LocalPlayer.Character:FindFirstChild("Saddi") and game.Players.LocalPlayer.Character:FindFirstChild("Saddi").Level.Value >= 300 then
                            _G.Setting_table.Weapon = "Saddi"
                            _G.Setting_table.Saddi_H = true
                            Update_Setting(getgenv()['MyName'])
                        elseif game.Players.LocalPlayer.Character:FindFirstChild("Saddi") and game.Players.LocalPlayer.Character:FindFirstChild("Saddi").Level.Value < 300 then
                            _G.Setting_table.Weapon = "Saddi"
							Auto_Farm_Sword = true
                        end
                    else
						wait(5)
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi") or game.Players.LocalPlayer.Character:FindFirstChild("Saddi") then
						else
							Dis()
							Load("Saddi")
						end
                    end
                elseif _G.Setting_table.Triple_Hop then
					local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
					if Beli < 2000000 then
						Text("ฟามเงินรอดาบเกิด")
						Auto_Farm_Sword = true
						wait(10)
					else
						Text("กำลังหาดาบ")
						wait(10)
						HopServer()
						wait(50)
					end
				else
					Text("ฟามเงินรอดาบเกิด")
					Auto_Farm_Sword = true
					wait(10)
                end
            end
        end)
    end
end)
Quest_Tab:Seperator("Thrid World")
Quest_Tab:Toggle("Auto Yama","9610159123",_G.Setting_table.Auto_Yama,function(vu)
	Auto_Yama = vu
	_G.Setting_table.Auto_Yama = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Yama then
				if not Mix_Farm or Auto_Yama_Farm then
					if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") < 30 then
                        if game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                            Mix_Farm = true
                            Auto_Yama_Farm = true
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                            if game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Urban [Lv. 1750]" and v.Humanoid.Health > 0 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Yama
									end
								end
                            elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                            end
                        elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                            Mix_Farm = true
                            Auto_Yama_Farm = true
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                            if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Diablo [Lv. 1750]" and v.Humanoid.Health > 0 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Yama
									end
								end
                            elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                            end
                        elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
							Mix_Farm = true
                            Auto_Yama_Farm = true
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                            if game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Deandre [Lv. 1750]" and v.Humanoid.Health > 0 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Yama
									end
								end
                            elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                            end
						elseif Auto_Yama_Farm then
							Auto_Yama_Farm = nil
							Mix_Farm = nil
                        elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Urban (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Deandre (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Diablo (0/1)" then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                        elseif _G.Setting_table.Auto_Yama_Hop then
                            wait(5)
                            if not game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                HopServer()
                                wait(50)
                            end
                        end
                    elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") >= 30 and not Yama_H then
                        Auto_Yama_Farm = true
						Mix_Farm = true
                        if (game.Workspace.Map.Waterfall.SealedKatana.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 300 then
                            TP(game.Workspace.Map.Waterfall.SealedKatana.Handle.CFrame)
                        end
                        if game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
                            for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Ghost [Lv. 1500]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Yama
								end
							end
                        elseif not game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
							Yama_H = true
							fireclickdetector(game.Workspace.Map.Waterfall.SealedKatana.Handle.ClickDetector)
                        end
					elseif Auto_Yama_Farm then
						Auto_Yama_Farm = nil
						Mix_Farm = nil
                    end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Tushita","9610159123",_G.Setting_table.Auto_Tushita,function(vu)
	Auto_Tushita = vu
	_G.Setting_table.Auto_Tushita = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Tushita then
				if not Mix_Farm or Auto_Tushita_Farm then
					if not _G.Setting_table.Quest_Torch then
						if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
							Auto_Tushita_Farm = true
							Mix_Farm = true
							repeat wait(1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") or not Auto_Tushita
							wait(1)
							local Q_Tushita = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
							local Q_Torch = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")['Torches']
							if Q_Torch[1] == false then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
									EquipWeapon("Holy Torch")
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",1)
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
								end
							elseif Q_Torch[2] == false then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
									EquipWeapon("Holy Torch")
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",2)
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
								end
							elseif Q_Torch[3] == false then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
									EquipWeapon("Holy Torch")
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",3)
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
								end
							elseif Q_Torch[4] == false then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
									EquipWeapon("Holy Torch")
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",4)
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
								end
							elseif Q_Torch[5] == false then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
									EquipWeapon("Holy Torch")
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",5)
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress")
								end
							elseif Q_Tushita['KilledLongma'] == false then
								_G.Tushita_Q = true
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",2)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",3)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",4)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TushitaProgress","Torch",5)
								wait(1)
								_G.Setting_table.Quest_Torch = true
								Update_Setting(getgenv()['MyName'])
							elseif game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
								_G.Setting_table.Quest_Torch = true
								Update_Setting(getgenv()['MyName'])
							end
						elseif _G.Setting_table.No_Color_Haki_Tushita and _G.Setting_table.Auto_Tushita_Hop then
							wait(5)
							if not game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") and not game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
								HopServer()
								wait(50)
							end
						elseif not _G.Setting_table.No_Color_Haki_Tushita then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("God's Chalice") or game.Players.LocalPlayer.Character:FindFirstChild("God's Chalice") then
								Mix_Farm = true
								Auto_Tushita_Farm = true
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Winter Sky")
								wait(1)
								repeat TP2(CFrame.new(-5420.16602, 1084.9657, -2666.8208)) wait() until not Auto_Tushita or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5420.16602, 1084.9657, -2666.8208)).Magnitude <= 10
								wait(1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Pure Red")
								wait(1)
								repeat TP2(CFrame.new(-5414.41357, 309.865753, -2212.45776)) wait() until not Auto_Tushita or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5414.41357, 309.865753, -2212.45776)).Magnitude <= 10
								wait(1)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Snow White")
								wait(1)
								repeat TP2(CFrame.new(-4971.47559, 331.565765, -3720.02954)) wait() until not Auto_Tushita or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-4971.47559, 331.565765, -3720.02954)).Magnitude <= 10
								wait(1)
								repeat wait()
									EquipWeapon("God's Chalice")
									TP(CFrame.new(-5561.32471, 314.284546, -2663.39697, -0.391084909, 1.08295005e-07, 0.920354605, 4.10446699e-09, 1, -1.15922504e-07, -0.920354605, -4.15579748e-08, -0.391084909))
								until not Auto_Tushita or not game.Players.LocalPlayer.Backpack:FindFirstChild("God's Chalicee") and not game.Players.LocalPlayer.Character:FindFirstChild("God's Chalice") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]")
								wait(1)
							else
								if game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
									Mix_Farm = true
									Auto_Tushita_Farm = true
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
									if game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Urban [Lv. 1750]" and v.Humanoid.Health > 0 then
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												repeat wait(_G.Fast_Delay)
													EquipWeapon(_G.Setting_table.Weapon)
													TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
													AttackNoCD()
												until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Tushita
											end
										end
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
										TP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									end
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
									Mix_Farm = true
									Auto_Tushita_Farm = true
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
									if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Diablo [Lv. 1750]" and v.Humanoid.Health > 0 then
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												repeat wait(_G.Fast_Delay)
													EquipWeapon(_G.Setting_table.Weapon)
													TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
													AttackNoCD()
												until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Tushita
											end
										end
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
										TP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									end
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
									Mix_Farm = true
									Auto_Tushita_Farm = true
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
									if game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Deandre [Lv. 1750]" and v.Humanoid.Health > 0 then
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												repeat wait(_G.Fast_Delay)
													EquipWeapon(_G.Setting_table.Weapon)
													TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
													AttackNoCD()
												until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Tushita
											end
										end
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
										TP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									end
								elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Urban (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Deandre (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Diablo (0/1)" then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
								elseif _G.Setting_table.Auto_Tushita_Hop then
									wait(5)
									if not game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
										HopServer()
										wait(50)
									end
								elseif Auto_Tushita_Farm then
									Auto_Tushita_Farm = nil
									Mix_Farm = nil
								end
							end
						elseif Auto_Tushita_Farm then
							Auto_Tushita_Farm = nil
							Mix_Farm = nil
						end
					else
						if game.Workspace.Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") or game.ReplicatedStorage:FindFirstChild("Longma [Lv. 2000] [Boss]") then
							Auto_Tushita_Farm = true
							Mix_Farm = true
							if game.Workspace.Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Longma [Lv. 2000] [Boss]" and v.Humanoid.Health > 0 then
										if v.Humanoid:FindFirstChild("Animator") then
											v.Humanoid.Animator:Destroy()
										end
										repeat wait(_G.Fast_Delay)
											EquipWeapon(_G.Setting_table.Weapon)
											TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
											AttackNoCD()
										until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Tushita
									end
								end
							elseif game.ReplicatedStorage:FindFirstChild("Longma [Lv. 2000] [Boss]") then
								TP(game.ReplicatedStorage:FindFirstChild("Longma [Lv. 2000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
							end
						elseif Auto_Tushita_Farm then
							Auto_Tushita_Farm = nil
							Mix_Farm = nil
						end
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("No Color Haki","9610159123",_G.Setting_table.No_Color_Haki_Tushita,function(vu)
	_G.Setting_table.No_Color_Haki_Tushita = vu
	Update_Setting(getgenv()['MyName'])
end)
Quest_Tab:Toggle("Auto Twin Hooks","9610159123",_G.Setting_table.Auto_Twin_Hooks,function(vu)
	Auto_Twin_Hooks = vu
	_G.Setting_table.Auto_Twin_Hooks = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Twin_Hooks then
				if not Mix_Farm or Auto_Twin_Hooks_Farm then
					if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") or game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
						Auto_Twin_Hooks_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Captain Elephant [Lv. 1875] [Boss]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Twin_Hooks
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Twin_Hooks_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Twin_Hooks_Farm then
						Auto_Twin_Hooks_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Canvander","9610159123",_G.Setting_table.Auto_Canvander,function(vu)
	Auto_Canvander = vu
	_G.Setting_table.Auto_Canvander = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Canvander then
				if not Mix_Farm or Auto_Canvander_Farm then
					if game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") or game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
						Auto_Canvander_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Canvander
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Canvander_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Canvander_Farm then
						Auto_Canvander_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Buddy Sword","9610159123",_G.Setting_table.Auto_Buddy_Sword,function(vu)
	Auto_Buddy_Sword = vu
	_G.Setting_table.Auto_Buddy_Sword = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Buddy_Sword then
				if not Mix_Farm or Auto_Buddy_Sword_Farm then
					if game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						Auto_Buddy_Sword_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Cake Queen [Lv. 2175] [Boss]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Buddy_Sword
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Auto_Buddy_Sword_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") and not game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Buddy_Sword_Farm then
						Auto_Buddy_Sword_Farm = nil
						Mix_Farm = nil
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Spikey Trident","9606294253",_G.Setting_table.Auto_Spikey_Trident,function(vu)
	Auto_Spikey_Trident = vu
	_G.Setting_table.Auto_Spikey_Trident = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Spikey_Trident then
				if not Mix_Farm or Auto_Spikey_Trident_Farm then
					if game.Workspace.Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
						Auto_Spikey_Trident_Farm = true
						Mix_Farm = true
						if game.Workspace.Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" and v.Humanoid.Health > 0 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Spikey_Trident
								end
							end
						elseif game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
							TP(game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
						end
					elseif _G.Setting_table.Spikey_Trident_Hop then
						wait(5)
						if not game.Workspace.Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") and not game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
							HopServer()
							wait(50)
						end
					elseif Auto_Spikey_Trident_Farm then
						Auto_Spikey_Trident_Farm = nil
						Mix_Farm = nil
					else
						if (Vector3.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1200 then
							CFrameMon = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if not string.find(v.Name,"Boss") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 1000 then
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									_G.PosMon = v.HumanoidRootPart.CFrame
									StatrMagnet = true
									repeat wait(_G.Fast_Delay)
										EquipWeapon(_G.Setting_table.Weapon)
										TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
										AttackNoCD()
									until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Spikey_Trident
									StatrMagnet = false
								end
							end
						else
							TP(CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625))
						end
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Hallow Scryte","9606294253",_G.Setting_table.Auto_Hallow_Scryte,function(vu)
	Auto_Hallow_Scryte = vu
	_G.Setting_table.Auto_Hallow_Scryte = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Hallow_Scryte then
				if game.Workspace.Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" and v.Humanoid.Health > 0 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Hallow_Scryte
							end
						end
					elseif game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						TP(game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
					end
				elseif game.Players.LocalPlayer.Character:FindFirstChild("Hallow Essence") or game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") then
					repeat wait(.3)
						EquipWeapon("Hallow Essence")
						TP2(CFrame.new(-8932.86, 143.258, 6063.31))
					until not game.Players.LocalPlayer.Character:FindFirstChild("Hallow Essence") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") or game.Workspace.Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") 
				elseif _G.Setting_table.Hallow_Scryte_Hop then
					wait(5)
					if not game.Workspace.Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") and not game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						HopServer()
						wait(50)
					end
				else
					local args = {
						[1] = "Bones",
						[2] = "Check"
					}
					
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			
					local args = {
						[1] = "Bones",
						[2] = "Buy",
						[3] = 1,
						[4] = 1
					}
					
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					if game.Workspace.Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == "Reborn Skeleton [Lv. 1975]" and v.Humanoid.Health > 0 then
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								_G.PosMon = v.HumanoidRootPart.CFrame
								StatrMagnet = true
								repeat wait(_G.Fast_Delay)
									EquipWeapon(_G.Setting_table.Weapon)
									TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
									AttackNoCD()
								until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Hallow_Scryte
								StatrMagnet = false
							end
						end
					elseif game.ReplicatedStorage:FindFirstChild("Reborn Skeleton [Lv. 1975]") then
						TP(game.ReplicatedStorage:FindFirstChild("Reborn Skeleton [Lv. 1975]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
					end
				end
			else
				wait(2)
			end
		end)
	end
end)
Quest_Tab:Toggle("Auto Dark Dagger","9610159123",_G.Setting_table.Auto_Dark_Dagger,function(vu)
	Auto_Dark_Dagger = vu
	_G.Setting_table.Auto_Dark_Dagger = vu
	Update_Setting(getgenv()['MyName'])
end)
function TelePQ(p)
	if (p.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude >= 3000 and not Auto_Raid then
		if game.Players.LocalPlayer.Data.SpawnPoint.Value == 'Fountain' then
			_G.Stop_Tween = true
			Tween:Cancel()
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			wait(1)
			_G.Stop_Tween = nil
		else
			_G.Stop_Tween = true
			local Speed = 100
			local Distance = 100
			game:GetService("TweenService"):Create(
				game.Players.LocalPlayer.Character.HumanoidRootPart,
				TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
				{CFrame = P1}
			):Cancel()
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
			wait(1)
			if not Auto_Raid then
				game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
				wait(.5)
				repeat wait(.2)
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p
					wait()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
				until game.Players.LocalPlayer.Character.Humanoid.Health > 0
				wait(2)
				_G.Stop_Tween = nil
			end
		end
	end
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Dark_Dagger then
                if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                    if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                            if v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" and v.Humanoid.Health > 0 then
                                if v.Humanoid:FindFirstChild("Animator") then
                                    v.Humanoid.Animator:Destroy()
                                end
                                repeat wait(_G.Fast_Delay)
                                    EquipWeapon(_G.Setting_table.Weapon)
                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                    AttackNoCD()
                                until not v.Parent or v.Humanoid.Health <= 0 or not Auto_Dark_Dagger
                            end
                        end
                    elseif game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                        TP(game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                    end
                else
                    wait(5)
                    if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                    else
                        HopServer()
                        wait(20)
                    end
                end
			end
		end)
	end
end)
Quest_Tab:Toggle("No Color Haki","9610159123",_G.Setting_table.No_Color_Haki_Dark_Dagger,function(vu)
	_G.Setting_table.No_Color_Haki_Dark_Dagger = vu
	Update_Setting(getgenv()['MyName'])
end)
function activatefly()
	local mouse=game.Players.LocalPlayer:GetMouse''
	localplayer=game.Players.LocalPlayer
	game.Players.LocalPlayer.Character:WaitForChild("HumanoidRootPart")
	local torso = game.Players.LocalPlayer.Character.HumanoidRootPart
	local keys={a=false,d=false,w=false,s=false}
	local e1
	local e2
	local function start()
		local pos = Instance.new("BodyPosition",torso)
		local gyro = Instance.new("BodyGyro",torso)
		pos.Name="EPIXPOS"
		pos.maxForce = Vector3.new(math.huge, math.huge, math.huge)
		pos.position = torso.Position
		gyro.maxTorque = Vector3.new(9e9, 9e9, 9e9)
		gyro.cframe = torso.CFrame
		repeat
			wait()
			localplayer.Character.Humanoid.PlatformStand=true
			local new=gyro.cframe - gyro.cframe.p + pos.position
			if not keys.w and not keys.s and not keys.a and not keys.d then
				speed=1
			end
			if keys.w then
				new = new + workspace.CurrentCamera.CoordinateFrame.lookVector * speed
				speed=speed+speedSET
			end
			if keys.s then
				new = new - workspace.CurrentCamera.CoordinateFrame.lookVector * speed
				speed=speed+speedSET
			end
			if keys.d then
				new = new * CFrame.new(speed,0,0)
				speed=speed+speedSET
			end
			if keys.a then
				new = new * CFrame.new(-speed,0,0)
				speed=speed+speedSET
			end
			if speed>speedSET then
				speed=speedSET
			end
				pos.position=new.p
			if keys.w then
				gyro.cframe = workspace.CurrentCamera.CoordinateFrame*CFrame.Angles(-math.rad(speed*15),0,0)
			elseif keys.s then
				gyro.cframe = workspace.CurrentCamera.CoordinateFrame*CFrame.Angles(math.rad(speed*15),0,0)
			else
				gyro.cframe = workspace.CurrentCamera.CoordinateFrame
			end
		until not Fly
		if gyro then 
			gyro:Destroy() 
		end
		if pos then 
			pos:Destroy() 
		end
		flying=false
		localplayer.Character.Humanoid.PlatformStand=false
		speed=0
	end
	e1=mouse.KeyDown:connect(function(key)
		if not torso or not torso.Parent then 
			flying=false e1:disconnect() e2:disconnect() return 
		end
		if key=="w" then
			keys.w=true
		elseif key=="s" then
			keys.s=true
		elseif key=="a" then
			keys.a=true
		elseif key=="d" then
			keys.d=true
		end
	end)
	e2=mouse.KeyUp:connect(function(key)
		if key=="w" then
			keys.w=false
		elseif key=="s" then
			keys.s=false
		elseif key=="a" then
			keys.a=false
		elseif key=="d" then
			keys.d=false
		end
	end)
	start()
end
PvP_Tab:Label("Main")
PvP_Tab:Toggle("Fly","9606294253",_G.Setting_table.Fly,function(vu)
	Fly = vu
	_G.Setting_table.Fly = vu
	Update_Setting(getgenv()['MyName'])
	if vu then
		activatefly()
	end
end)
_G.Setting_table.Speed = 15
speedSET = 15
PvP_Tab:Slider("Speed",1,50,_G.Setting_table.Speed,function(vu)
	speedSET = vu
	_G.Setting_table.Speed = vu
	Update_Setting(getgenv()['MyName'])
end)

PvP_Tab:Label("Misc")
PvP_Tab:Toggle("Auto PvP Turn On","9606294253",_G.Setting_table.Auto_PvP_Turn_On,function(vu)
	_G.Setting_table.Auto_PvP_Turn_On = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(1) do
		pcall(function()
			if _G.Setting_table.Auto_PvP_Turn_On then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
			end
		end)
	end
end)
PvP_Tab:Toggle("Auto Teleport To Position Spawn","9606294253",_G.Setting_table.TP_Position_Spawn,function(vu)
	_G.Setting_table.TP_Position_Spawn = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(1) do
		pcall(function()
			if _G.Setting_table.TP_Position_Spawn then
				if _G.Setting_table.Pos_Spawn ~= nil and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
					TP(_G.Setting_table.Pos_Spawn)
				end
			end
		end)
	end
end)
PvP_Tab:Button("Set Position Spawn",function()
	_G.Setting_table.Pos_Spawn = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
	Update_Setting(getgenv()['MyName'])
	Com()
end)

PvP_Tab:Label("No Cooldown & Infinity")
PvP_Tab:Toggle("Soru No Cooldown","9606294253",_G.Setting_table.Sorunocool,function(vu)
	Sorunocool = vu
	_G.Setting_table.Sorunocool = vu
	if vu then
		NoSoruCool()
	end
	Update_Setting(getgenv()['MyName'])
end)
function NoSoruCool()
    for i, v in pairs(getgc()) do
        if type(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character:WaitForChild("Soru") then
            for i2,v2 in pairs(debug.getupvalues(v)) do
                if type(v2) == 'table' then
                    if v2.LastUse then
                        repeat wait()
                            setupvalue(v, i2, {LastAfter = 0,LastUse = 0})
                        until not Sorunocool
                    end
                end
            end
        end
    end
end
PvP_Tab:Toggle("Dodge No Cooldown","9606294253",_G.Setting_table.Dodge_No_Cooldown,function(vu)
	nododgecool = vu
	_G.Setting_table.Dodge_No_Cooldown  = vu
	Update_Setting(getgenv()['MyName'])
    if vu then
        NoDodgeCool()
    end
end)
	function NoDodgeCool()
		if nododgecool then
			for i,v in next, getgc() do
				if game.Players.LocalPlayer.Character.Dodge then
					if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Dodge then
						for i2,v2 in next, getupvalues(v) do
							if tostring(v2) == "0.4" then
								repeat wait(.1)
									setupvalue(v,i2,0)
								until not nododgecool
							end
						end
					end
				end
			end
		end
	end
PvP_Tab:Toggle("Infinity Geppo","9606294253",_G.Setting_table.Infinity_Geppo,function(vu)
	noGeppocool = vu
	_G.Setting_table.Infinity_Geppo = vu
	Update_Setting(getgenv()['MyName'])
    if vu then
        NoGeppoCool()
    end
end)
function NoGeppoCool()
    if noGeppocool then
        for i,v in next, getgc() do
            if game.Players.LocalPlayer.Character.Geppo then
                if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Geppo then
                    for i2,v2 in next, getupvalues(v) do
                        if tostring(v2) == "0" then
                            repeat wait(.1)
                                setupvalue(v,i2,0)
                            until not noGeppocool
                        end
                    end
                end
            end
        end
    end
end
PvP_Tab:Toggle("Infinity Energy","9606294253",_G.Setting_table.InfinitsEnergy,function(vu)
	InfinitsEnergy = vu
	if vu then
		infinitestam()
	end
	_G.Setting_table.InfinitsEnergy = vu
	Update_Setting(getgenv()['MyName'])
end)
	local LocalPlayer = game:GetService'Players'.LocalPlayer
	local originalstam = LocalPlayer.Character.Energy.Value
	function infinitestam()
		game:GetService'Players'.LocalPlayer.Character.Energy.Changed:connect(function()
			if InfinitsEnergy then
				LocalPlayer.Character.Energy.Value = originalstam
			end 
		end)
	end
PvP_Tab:Label("Bounty")
	PvP_Tab:Toggle("Aattack","9606294253",false,function(vu)
		Attack = vu
	end)
	PlayerName = {}
	for i,v in pairs(game.Players:GetChildren()) do  
		table.insert(PlayerName ,v.Name)
	end
	SelectedKillPlayer = "..."
	local Sl_P = PvP_Tab:Dropdown("Select Player","...",PlayerName,function(vu)
		SelectedKillPlayer = vu
	end)
	PvP_Tab:Button("Refresh Select Player",function()
		Sl_P:Clear()
		for i,v in pairs(game.Players:GetChildren()) do  
			Sl_P:Add(v.Name)
		end
	end)
	spawn(function()
		local gg = getrawmetatable(game)
		local old = gg.__namecall
		setreadonly(gg,false)
		gg.__namecall = newcclosure(function(...)
			local method = getnamecallmethod()
			local args = {...}
			if tostring(method) == "FireServer" then
				if tostring(args[1]) == "RemoteEvent" then
					if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
						if UseSkillMasteryDevilFruit then
							args[2] = PositionSkillMasteryDevilFruit
							return old(unpack(args))
						elseif Skillaimbot then
							args[2] = AimBotSkillPosition
							return old(unpack(args))
						end
					end
				end
			end
			return old(...)
		end)
	end)
	PvP_Tab:Toggle("Aimbot Gun","9606294253",false,function(vu)
		Aimbot = vu
		if vu then
			for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectToolWeaponGun = v.Name
					end
				end
			end
			for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectToolWeaponGun = v.Name
					end
				end
			end
		end
	end)
	PvP_Tab:Toggle("Aimbot Skill","9606294253",false,function(vu)
		Skillaimbot = vu
		if Skillaimbot then
			if game.Players:FindFirstChild(SelectedKillPlayer) and game.Players:FindFirstChild(SelectedKillPlayer).Character:FindFirstChild("HumanoidRootPart") and game.Players:FindFirstChild(SelectedKillPlayer).Character:FindFirstChild("Humanoid") and game.Players:FindFirstChild(SelectedKillPlayer).Character.Humanoid.Health > 0 then
				AimBotSkillPosition = game.Players:FindFirstChild(SelectedKillPlayer).Character:FindFirstChild("HumanoidRootPart").Position
			end
		end
	end)
	local lp = game:GetService('Players').LocalPlayer
	local mouse = lp:GetMouse()
	mouse.Button1Down:Connect(function()
		if Aimbot and game.Players.LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) and game:GetService("Players"):FindFirstChild(SelectedKillPlayer) then
			tool = game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun]
			v17 = workspace:FindPartOnRayWithIgnoreList(Ray.new(tool.Handle.CFrame.p, (game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position - tool.Handle.CFrame.p).unit * 100), { game.Players.LocalPlayer.Character, workspace._WorldOrigin });
			game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position, (require(game.ReplicatedStorage.Util).Other.hrpFromPart(v17)));
		end
	end)
PvP_Tab:Toggle("Auto Farm Bounty","9606294253",_G.Setting_table.Auto_Farm_Bounty,function(vu)
	Auto_Farm_Bounty = vu
	_G.Setting_table.Auto_Farm_Bounty = vu
	Update_Setting(getgenv()['MyName'])
end)
PvP_Tab:Slider("Skip Player",1,30,10,function(vu)
	Skip_S = vu
end)
Skip_S = 10
function Get_Mon(vu)    
	for i,v in pairs(game.Workspace.Characters:GetChildren()) do
		if v.Name ~= game.Players.LocalPlayer.Name and v.Name ~= "Sapab" then
			if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= tonumber(vu) then
				_G.Players_Mon = v
				return
			end
		end
	end
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Farm_Bounty then
				_G.Players_Mon = nil
				for i = 10000,500,-500 do
					Get_Mon(i)
				end
				if _G.Players_Mon ~= nil then
					print("Player : "..tostring(_G.Players_Mon.Name))
					SelectedKillPlayer = _G.Players_Mon.Name
					Start_Kill = true
					repeat wait(.1)
					until Kop
					repeat task.wait()
						EquipWeapon(_G.Setting_table.Weapon)
						if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.InCombat.Visible == true then
							TP(_G.Players_Mon.HumanoidRootPart.CFrame*CFrame.new(0,10,0))
						else
							TP(_G.Players_Mon.HumanoidRootPart.CFrame)
						end
						game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
						if Skillaimbot and (_G.Players_Mon.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
							game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
							wait(.1)
							game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
						end
					until _G.Players_Mon == nil or not _G.Players_Mon.Parent or _G.Players_Mon.Humanoid.Health <= 0 or not Auto_Farm_Bounty or game.Players.LocalPlayer.Character.Humanoid.Health <= 0
					if _G.Players_Mon ~= nil then
						print("Kill : "..tostring(_G.Players_Mon.Name))
					end
					_G.Players_Mon.Name = "Sapab"
				end
			end
		end)
	end
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Start_Kill then
				Kop = true
				Kip = 0
				repeat wait()
					if (_G.Players_Mon.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 500 then
						if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.InCombat.Visible == true then
						else
							wait(1)
							Kip = Kip + 1
							print("Skip : "..tostring(Kip))
						end
					end
				until Kip >= Skip_S or not _G.Players_Mon.Parent or _G.Players_Mon.Humanoid.Health <= 0 or not Auto_Farm_Bounty
				Start_Kill = false
				Kop = false
				if Kip >= Skip_S then
					_G.Players_Mon.Name = "Sapab"
					_G.Players_Mon = nil
				end
			end
		end)
	end
end)

Raid_Tab:Label("Main")
Raid_Tab:Toggle("Auto Raid Hop","9606294253",_G.Setting_table.Auto_Raid_Hop,function(vu)
	Auto_Raid = vu
	_G.Setting_table.Auto_Raid_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
Raid_Tab:Toggle("Auto Raid","9606294253",_G.Setting_table.Auto_Raid,function(vu)
	Auto_Raid = vu
	_G.Setting_table.Auto_Raid = vu
	Update_Setting(getgenv()['MyName'])
end)
Raid_Tab:Toggle("Next Islands","9606294253",_G.Setting_table.Next_Islands,function(vu)
	Next_Islands = vu
	_G.Setting_table.Next_Islands = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Raid_Hop then
	Auto_Raid = true
end

if type(_G.Setting_table.Select_Map) ~= 'string' then
    _G.Setting_table.Select_Map = "Flame"
end
function Buy_Chip()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", _G.Setting_table.Select_Map)
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Raid then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
						if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
							repeat wait(.1)
								sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
								v.Humanoid.Health = 0
								v.HumanoidRootPart.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								v.HumanoidRootPart.Transparency = 0.5
							until not Auto_Raid or not v.Parent or v.Humanoid.Health <= 0
						end
					end
				end
			else
				wait(3)
			end
		end)
	end
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Next_Islands then
				if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
					for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
						if v.Name == "Island 5" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2300 then
							TP2(v.CFrame*CFrame.new(0,70,0))
						end
					end
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
					for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
						if v.Name == "Island 4" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2000 then
							TP2(v.CFrame*CFrame.new(0,70,0))
						--wait(2)
						end
					end
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
					for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
						if v.Name == "Island 3" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2100 then
							TP2(v.CFrame*CFrame.new(0,70,0))
							--wait(2)
						end
					end
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
					for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
						if v.Name == "Island 2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2000 then
							TP2(v.CFrame*CFrame.new(0,10,0))
							--wait(2)
						end
					end
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
					for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
						if v.Name == "Island 1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2000 then
							TP2(v.CFrame*CFrame.new(0,70,0))
							--wait(2)
						end
					end
				else
					wait(1)
				end
			else
				wait(2)
			end
		end)
	end
end)

spawn(function()
	while wait(2) do
		pcall(function()
			if Auto_Raid_Farm then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
					_G.Stop_Tween = true
				elseif game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					_G.Stop_Tween = false
				end
			end
		end)
	end
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Raid then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
					if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
						Auto_Raid_Farm = true
						Mix_Farm = true
						if New_World then
							fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
							repeat wait(1)
							until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
						elseif Three_World then
							fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
							repeat wait(1)
							until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
						end
					else
						if _G.Setting_table.Auto_Raid_Hop or _G.Setting_table.Melee_Hop or Auto_Phoenix_Awaken then
							_G.Have_Fruit = nil
							Raid_FG()
						end
						Buy_Chip()
						wait(1)
						if _G.Setting_table.Auto_Raid_Hop and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
							HopServer()
							wait(50)
						elseif Auto_Raid_Farm and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
							Mix_Farm = nil
							_G.Stop_Tween = nil
							Auto_Raid_Farm = nil
							Text("ไม่มีผลปีศาจเหลือแล้ว")
						end
					end
				elseif game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
					repeat wait(1)
					until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false
					if _G.Setting_table.Auto_Awaken then
						wait(2)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Check")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Awaken")
					end
				end
			end
		end)
	end
end)
Raid_Tab:Toggle("Auto Awaken","9606294253",_G.Setting_table.Auto_Awaken,function(vu)
	_G.Setting_table.Auto_Awaken = vu
	Update_Setting(getgenv()['MyName'])
end)
Map = {
    "Dark",
    "Sand",
    "Magma",
    "Rumble",
    "Flame",
    "Ice",
    "Light",
    "Quake",
    "Human: Buddha",
    "Flame",
    "Bird: Phoenix"
}
Raid_Tab:Dropdown("Select Dungeon",_G.Setting_table.Select_Map,Map,function(vu)
	_G.Setting_table.Select_Map = vu
	Update_Setting(getgenv()['MyName'])
end)

Raid_Tab:Label("Misc")
Raid_Tab:Toggle("Bring Fruit","9606294253",_G.Setting_table.BringFruit,function(vu)
	BringFruit = vu
	_G.Setting_table.BringFruit = vu
	Update_Setting(getgenv()['MyName'])
end)
Raid_Tab:Toggle("Get Fruit Inventory","9606294253",_G.Setting_table.Get_Fruit,function(vu)
	_G.Setting_table.Get_Fruit = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.5) do
        pcall(function()
            if _G.Setting_table.Get_Fruit then
                if Inventory_Fruit then
                    Inventory_Fruit = nil
                end
                fruit = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryFruits")
                for i,v in pairs(fruit) do
                    if v["Price"] < 10000000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v["Name"])
                    end
                end
			else
				wait(2)
            end
        end)
    end
end)

Shop_Tab:Label("Main")
Shop_Tab:Toggle("Auto Buy Legendary Sword","9606294253",_G.Setting_table.Auto_Buy_Legendary_Sword,function(vu)
	_G.Setting_table.Auto_Buy_Legendary_Sword = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.1) do
        pcall(function()
            if _G.Setting_table.Auto_Buy_Legendary_Sword or Triple_A then
                local args = {
                    [1] = "LegendarySwordDealer",
                    [2] = "2"
                }
                -- Triple_A
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            else
				wait(2)
			end
        end)
    end
end)

Shop_Tab:Label("Ability")
Shop_Tab:Button("Buy SkyJump",function()
    local args = {
        [1] = "BuyHaki",
        [2] = "Geppo"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Button("Buy Soru",function()
    local args = {
        [1] = "BuyHaki",
        [2] = "Soru"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Button("Buy Haki",function()
    local args = {
        [1] = "BuyHaki",
        [2] = "Buso"
    }

    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))    
end)
Shop_Tab:Button("Buy KenHaki",function()
    local args = {
        [1] = "KenTalk",
        [2] = "Buy"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Label("Fruit")
Shop_Tab:Toggle("Auto Buy Random Fruit","9606294253",_G.Setting_table.Auto_Buy_Random_Fruit,function(vu)
	_G.Setting_table.Auto_Buy_Random_Fruit = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(.2) do
        if _G.Setting_table.Auto_Buy_Random_Fruit then
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
            wait(20)
        end
    end
end)
Shop_Tab:Toggle("Fruit Inventory","9606294253",_G.Setting_table.Inventory_Fruit,function(vu)
	Inventory_Fruit = vu
	_G.Setting_table.Inventory_Fruit = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Open_Don_Swan then
	Inventory_Fruit = true
end

spawn(function()
    while wait(2) do
		pcall(function()
			if Inventory_Fruit then
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bomb-Bomb")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spike-Spike")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Chop-Chop")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spring-Spring")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Kilo-Kilo")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Smoke-Smoke")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spin-Spin")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Flame-Flame")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Falcon")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Ice-Ice")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Sand-Sand")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dark-Dark")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Revive-Revive")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Diamond-Diamond")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Light-Light")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Love-Love")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rubber-Rubber")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Barrier-Barrier")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Magma-Magma")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Door-Door")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Quake-Quake")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Human-Human: Buddha")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","String-String")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Phoenix")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rumble-Rumble")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Paw-Paw")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Gravity-Gravity")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dough-Dough")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Shadow-Shadow")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Venom-Venom")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Control-Control")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dragon-Dragon")
					wait(1)
				end
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Soul Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Soul Fruit") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Soul-Soul")
					wait(1)
				end	
			end
		end)
    end
end)
Shop_Tab:Toggle("Bring Fruit","9606294253",_G.Setting_table.BringFruit,function(vu)
	BringFruit = vu
	_G.Setting_table.BringFruit = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.BringFruit then
	BringFruit = true
end
spawn(function()
    while wait(.2) do
        pcall(function()
            if BringFruit or BringFruit_P then
                for i,v6 in pairs(game:GetService("Workspace"):GetChildren()) do
                    if v6:IsA ("Tool") and (v6.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 13000 then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v6.Handle.CFrame
                        v6.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                    end
                end
            end
        end)
    end
end)
spawn(function()
    while wait(3) do
        if _G.Hop_Bring_Fruit then
            wait(15)
            _G.Hop_Bring_Fruit_Ex = true
        end
    end
end)
Shop_Tab:Toggle("Devil Fruit Sniper","9606294253",_G.Setting_table.Sniper_Fruit,function(vu)
	_G.Setting_table.Sniper_Fruit = vu
	Update_Setting(getgenv()['MyName'])
end)
local l__Remotes__11 = game.ReplicatedStorage:WaitForChild("Remotes");
u45 = l__Remotes__11.CommF_:InvokeServer("GetFruits");
Table_DevilFruitSniper = {}
for i,v in next,u45 do
    table.insert(Table_DevilFruitSniper,v.Name)
end
if _G.Setting_table.Select_Fruit == nil then
    _G.Setting_table.Select_Fruit = ""
end
Shop_Tab:Dropdown("Select Devil Fruit Sniper",_G.Setting_table.Select_Fruit,Table_DevilFruitSniper,function(vu)
	_G.Setting_table.Select_Fruit = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(3) do
        if _G.Setting_table.Sniper_Fruit then
            for s,f in pairs(_G.Setting_table.Select_Fruit) do
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit",f)
			end
			wait(30)
        end
    end
end)

Shop_Tab:Label("Melee")
Shop_Tab:Button("Buy Electro",function()
    local args = {
        [1] = "BuyElectro"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Button("Buy Black Leg",function()
    local args = {
        [1] = "BuyBlackLeg"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Button("Buy Fishman Karate",function()
    local args = {
        [1] = "BuyFishmanKarate"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Shop_Tab:Button("Buy Dragon Claw",function()
    local args = {
        [1] = "BlackbeardReward",
        [2] = "DragonClaw",
        [3] = "1"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
        [1] = "BlackbeardReward",
        [2] = "DragonClaw",
        [3] = "2"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Seperator("V2")
Shop_Tab:Button("Buy Superhuman",function()
    local args = {
        [1] = "BuySuperhuman"
    }

    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Shop_Tab:Button("Buy Death Step",function()
    local args = {
        [1] = "BuyDeathStep"
    }

    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

Shop_Tab:Button("Buy Shakman Karate",function()
    local args = {
        [1] = "BuySharkmanKarate",
        [2] = true
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
        [1] = "BuySharkmanKarate"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Button("Buy ElectricClaw",function()
    local args = {
        [1] = "BuyElectricClaw"
        }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)

    Shop_Tab:Button("Buy Dragon Talon",function()
        local args = {
            [1] = "BuyDragonTalon",
            [2] = true
            }
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        local args = {
            [1] = "BuyDragonTalon"
            }
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
	Shop_Tab:Label("Bones")
    Shop_Tab:Button("Buy Random Surprise",function()
        local args = {
            [1] = "Bones",
            [2] = "Check"
        }
        
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

        local args = {
            [1] = "Bones",
            [2] = "Buy",
            [3] = 1,
            [4] = 1
        }
        
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
	Shop_Tab:Toggle("Auto Buy Random Surprise","9606294253",_G.Setting_table.Auto_Random,function(vu)
		_G.Auto_Random = vu
		_G.Setting_table.Auto_Random = vu
		Update_Setting(getgenv()['MyName'])
	end)
    
    spawn(function()
        while wait(3) do
            pcall(function()
                if _G.Auto_Random then
					spawn(function()
						wait(15)
						IKAI = true
					end)
					repeat wait(.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
					until IKAI == true
                end
            end)
        end
    end)
	Shop_Tab:Label("Sword")
Shop_Tab:Button("Buy Katana",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
end)
Shop_Tab:Button("Buy Cutlass",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
end)
Shop_Tab:Button("Buy Duel Katana",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
end)
Shop_Tab:Button("Buy Iron Mace",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
end)
Shop_Tab:Button("Buy Pipe",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
end)
Shop_Tab:Button("Buy Triple Katana",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
end)
Shop_Tab:Button("Buy Dual-Headed Blade",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
end)
Shop_Tab:Button("Buy Bisento",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
end)
Shop_Tab:Button("Buy Soul Cane",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
end)

Shop_Tab:Label("Gun")
Shop_Tab:Button("Buy Slingshot",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
end)
Shop_Tab:Button("Buy Musket",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
end)
Shop_Tab:Button("Buy Fintlock",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
end)
Shop_Tab:Button("Buy Refined Flintlock",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
end)
Shop_Tab:Button("Buy Cannon",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
end)
Shop_Tab:Button("Buy Kabucha",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
end)

Shop_Tab:Label("Fragments")
Shop_Tab:Button("Buy Refund Stat",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
end)
Shop_Tab:Button("Buy Random Race",function()
    local args = {
        [1] = "BlackbeardReward",
        [2] = "Reroll",
        [3] = "2"
    }
    
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end)
Shop_Tab:Button("Buy Color Buso Haki",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ColorsDealer", "2")
end)
Shop_Tab:Toggle("Auto Buy Color Buso Haki","9606294253",_G.Setting_table.Buso_Haki,function(vu)
	_G.Setting_table.Buso_Haki = vu
	Buso_Haki_Buy = vu
	Update_Setting(getgenv()['MyName'])
end)

spawn(function()
	while wait(.5) do
		pcall(function()
			if Buso_Haki_Buy then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ColorsDealer", "2")
			else
				wait(3)
			end
		end)
	end
end)

spawn(function()
	while wait(2) do
		pcall(function()
			if _G.Setting_table.Buso_Haki_Hop then
				wait(10)
				HopServer()
				wait(50)
			else
				wait(3)
			end
		end)
	end
end)

Island_Tab:Label("Server")
Island_Tab:Button("Hop Server",function()
	HopServer()
end)
function HopServer()
    if not _G.TP_Ser then
		_G.TP_Ser = true
		game.StarterGui:SetCore("SendNotification", {
			Title = "Hop Low Server ", 
			Text = "กำลังหาเซิฟ",
			Icon = "http://www.roblox.com/asset/?id=9606070311",
			Duration = 25
		})
		local PlaceID = game.PlaceId
		local AllIDs = {}
		local foundAnything = ""
		local actualHour = os.date("!*t").hour
		local Deleted = false
		function TPReturner()
			local Site;
			if foundAnything == "" then
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
			else
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
			end
			local ID = ""
			if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
				foundAnything = Site.nextPageCursor
			end
			local num = 0;
			for i,v in pairs(Site.data) do
				local Possible = true
				ID = tostring(v.id)
				game.StarterGui:SetCore("SendNotification", {
					Title = "Hop Low Server ", 
					Text = "Players : " ..tonumber(v.playing),
					Icon = "http://www.roblox.com/asset/?id=9606070311",
					Duration = 1.5
				})
				if tonumber(v.maxPlayers) > tonumber(v.playing) then
					for _,Existing in pairs(AllIDs) do
						if num ~= 0 then
							if ID == tostring(Existing) then
								Possible = false
							end
						else
							if tonumber(actualHour) ~= tonumber(Existing) then
								local delFile = pcall(function()
									-- delfile("NotSameServers.json")
									AllIDs = {}
									table.insert(AllIDs, actualHour)
								end)
							end
						end
						num = num + 1
					end
					if Possible == true then
						table.insert(AllIDs, ID)
						wait()
						pcall(function()
							_G.Setting_table.Hop_Server = true 
							Update_Setting(getgenv()['MyName'])
							_G.TP_Ser = true
							-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
							wait()
							game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
						end)
						wait(.1)
					end
				end
			end
		end
		function Bring()
			while wait(.2) do
				pcall(function()
					TPReturner()
					if foundAnything ~= "" then
						TPReturner()
					end
				end)
			end
		end
		Bring()
	end
end
function HopLowServer()
	if not _G.TP_Ser then
		_G.TP_Ser = true
		game.StarterGui:SetCore("SendNotification", {
			Title = "Hop Server S", 
			Text = "กำลังหาเซิฟ",
			Icon = "http://www.roblox.com/asset/?id=9606070311",
			Duration = 25
		})
		local PlaceID = game.PlaceId
		local AllIDs = {}
		local foundAnything = ""
		local actualHour = os.date("!*t").hour
		local Deleted = false
		function TPReturner()
			local Site;
			if foundAnything == "" then
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
			else
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
			end
			local ID = ""
			if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
				foundAnything = Site.nextPageCursor
			end
			local num = 0;
			for i,v in pairs(Site.data) do
				local Possible = true
				ID = tostring(v.id)
				game.StarterGui:SetCore("SendNotification", {
					Title = "HopServer", 
					Text = "Players : " ..tonumber(v.playing),
					Icon = "http://www.roblox.com/asset/?id=9606070311",
					Duration = 1.5
				})
				if tonumber(v.maxPlayers) > tonumber(v.playing) then
					for _,Existing in pairs(AllIDs) do
						if num ~= 0 then
							if ID == tostring(Existing) then
								Possible = false
							end
						else
							if tonumber(actualHour) ~= tonumber(Existing) then
								local delFile = pcall(function()
									-- delfile("NotSameServers.json")
									AllIDs = {}
									table.insert(AllIDs, actualHour)
								end)
							end
						end
						num = num + 1
					end
					if Possible == true then
						table.insert(AllIDs, ID)
						wait()
						pcall(function()
							_G.Setting_table.Hop_Server = true 
							Update_Setting(getgenv()['MyName'])
							_G.TP_Ser = true
							-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
							wait()
							game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
						end)
						wait(.1)
					end
				end
			end
		end
		function Bring()
			while wait(.2) do
				pcall(function()
					TPReturner()
					if foundAnything ~= "" then
						TPReturner()
					end
				end)
			end
		end
		Bring()
	end
end
Island_Tab:Button("Hop Low Server",function()
	HopLowServer()
end)
Island_Tab:Button("Re join Server",function()
	game.StarterGui:SetCore("SendNotification", {
        Title = "Re Join Server", 
        Text = "Ready Go!",
        Icon = "http://www.roblox.com/asset/?id=9606070311",
        Duration = 10
    })
	_G.TP_Ser = true
	wait(1)
	game:GetService("TeleportService"):Teleport(game.PlaceId)
	wait(50)
end)

function TP_World1()
	_G.TP_Ser = true
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
end
function TP_World2()
	_G.TP_Ser = true
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")	
end
function TP_World3()
	_G.TP_Ser = true
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
end

Island_Tab:Label("World")
Island_Tab:Button("Teleport to World 1", function()
	Com()
	TP_World1()
end)
Island_Tab:Button("Teleport to World 2", function()
	Com()
	TP_World2()
end)

Island_Tab:Button("Teleport to World 3", function()
	Com()
	TP_World3()
end)

Island_Tab:Label("Map")
if Old_World then

    Island_Tab:Button("Jones Salad", function()
        TP2(CFrame.new(1042.1501464844, 16.299360275269, 1444.3442382813))
    end)

    Island_Tab:Button("Marine1", function()
        TP2(CFrame.new(-2599.6655273438, 6.9146227836609, 2062.2216796875))
    end)

    Island_Tab:Button("Marine2", function()
        TP2(CFrame.new(-5081.3452148438, 85.221641540527, 4257.3588867188))
    end)

    Island_Tab:Button("Midle Town", function()
        TP2(CFrame.new(-655.97088623047, 7.878026008606, 1573.7612304688))
    end)

    Island_Tab:Button("Jungle", function()
        TP2(CFrame.new(-1499.9877929688, 22.877912521362, 353.87060546875))
    end)

    Island_Tab:Button("Pirate Village", function()
        TP2(CFrame.new(-1163.3889160156, 44.777843475342, 3842.8276367188))
    end)

    Island_Tab:Button("Desert", function()
        TP2(CFrame.new(954.02056884766, 6.6275520324707, 4262.611328125))
    end)

    Island_Tab:Button("Frozen Village", function()
        TP2(CFrame.new(1144.5270996094, 7.3292083740234, -1164.7322998047))
    end)

    Island_Tab:Button("Colosseum", function()
        TP2(CFrame.new(-1667.5869140625, 39.385631561279, -3135.5817871094))
    end)

    Island_Tab:Button("Prison", function()
        TP2(CFrame.new(4857.6982421875, 5.6780304908752, 732.75750732422))
    end)

    Island_Tab:Button("Mob Leader", function()
        TP2(CFrame.new(-2841.9604492188, 7.3560485839844, 5318.1040039063))
    end)

    Island_Tab:Button("Magma Village", function()
        TP2(CFrame.new(-5328.8740234375, 8.6164798736572, 8427.3994140625))
    end)

    Island_Tab:Button("UnderWater Gate", function()
        TP2(CFrame.new(3893.953125, 5.3989524841309, -1893.4851074219))
    end)

    Island_Tab:Button("UnderWater City", function()
        TP2(CFrame.new(61191.12109375, 18.497436523438, 1561.8873291016))
    end)

    Island_Tab:Button("Fountain City", function()
        TP2(CFrame.new(5244.7133789063, 38.526943206787, 4073.4987792969))
    end)

    Island_Tab:Button("Sky1", function()
        TP2(CFrame.new(-4878.0415039063, 717.71246337891, -2637.7294921875))
    end)

    Island_Tab:Button("Sky2", function()
        TP2(CFrame.new(-7899.6157226563, 5545.6030273438, -422.21798706055))
    end)

    Island_Tab:Button("Sky3", function()
        TP2(CFrame.new(-7868.5288085938, 5638.205078125, -1482.5548095703))
    end)

elseif New_World then


    Island_Tab:Button("Dock", function()
        TP2(CFrame.new(-12.519311904907, 19.302536010742, 2827.853515625))
    end)

    Island_Tab:Button("Mansion", function()
        TP2(CFrame.new(-390.34829711914, 321.89730834961, 869.00506591797))
    end)

    Island_Tab:Button("Kingdom Of Rose", function()
        TP2(CFrame.new(-388.29895019531, 138.35575866699, 1132.1662597656))
    end)

    Island_Tab:Button("Cafe", function()
        TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
    end)

    Island_Tab:Button("Sunflower Field", function()
        TP2(CFrame.new(-1576.7171630859, 198.61849975586, 13.725157737732))
    end)

    Island_Tab:Button("Jeramy Mountain", function()
        TP2(CFrame.new(1986.3519287109, 448.95678710938, 796.70239257813))
    end)

    Island_Tab:Button("Colossuem", function()
        TP2(CFrame.new(-1871.8974609375, 45.820514678955, 1359.6843261719))
    end)

    Island_Tab:Button("Factory", function()
        TP2(CFrame.new(349.53750610352, 74.446998596191, -355.62420654297))
    end)

    Island_Tab:Button("The Bridge", function()
        TP2(CFrame.new(-1860.6354980469, 88.384948730469, -1859.1593017578))
    end)

    Island_Tab:Button("Green Bit", function()
        TP2(CFrame.new(-2202.3706054688, 73.097663879395, -2819.2687988281))
    end)

    Island_Tab:Button("Graveyard", function()
        TP2(CFrame.new(-5617.5927734375, 492.22183227539, -778.3017578125))
    end)

    Island_Tab:Button("Dark Area", function()
        TP2(CFrame.new(3464.7700195313, 13.375151634216, -3368.90234375))
    end)

    Island_Tab:Button("Snow Mountain", function()
        TP2(CFrame.new(561.23834228516, 401.44781494141, -5297.14453125))
    end)

    Island_Tab:Button("Hot Island", function()
        TP2(CFrame.new(-5505.9633789063, 15.977565765381, -5366.6123046875))
    end)

    Island_Tab:Button("Cold Island", function()
        TP2(CFrame.new(-5924.716796875, 15.977565765381, -4996.427734375))
    end)

    Island_Tab:Button("Ice Castle", function()
        TP2(CFrame.new(6111.7109375, 294.41259765625, -6716.4829101563))
    end)

    Island_Tab:Button("Usopp's Island", function()
        TP2(CFrame.new(4760.4985351563, 8.3444719314575, 2849.2426757813))
    end)

    Island_Tab:Button("inscription Island", function()
        TP2(CFrame.new(-5099.01171875, 98.241539001465, 2424.4035644531))
    end)

    Island_Tab:Button("Forgotten Island", function()
        TP2(CFrame.new(-3051.9514160156, 238.87203979492, -10250.807617188))
    end)

    Island_Tab:Button("Ghost Ship", function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
    end)

    Island_Tab:Button("Mini Sky", function()
        TP2(CFrame.new(-262.11901855469, 49325.69140625, -35272.49609375))
    end)

elseif Three_World  then
    Island_Tab:Button("Port Town", function()
        TP2(CFrame.new(-275.21615600586, 43.755737304688, 5451.0659179688))
    end)

    Island_Tab:Button("Hydra Island", function()
        TP2(CFrame.new(5541.2685546875, 668.30456542969, 195.48069763184))
    end)
    
    Island_Tab:Button("Gaint Tree", function()
        TP2(CFrame.new(2276.0859375, 25.87850189209, -6493.03125))
    end)
    
    Island_Tab:Button("Zou Island", function()
        TP2(CFrame.new(-10034.40234375, 331.78845214844, -8319.6923828125))
    end)
    
    Island_Tab:Button("PineApple Village", function()
        TP2(CFrame.new(-11172.950195313, 331.8049621582, -10151.033203125))
    end)
    
    Island_Tab:Button("Mansion", function()
        TP2(CFrame.new(-12548.998046875, 332.40396118164, -7603.1865234375))
    end)

    Island_Tab:Button("Castle on the Sea", function()
        TP2(CFrame.new(-5498.0458984375, 313.79473876953, -2860.6022949219))
    end)

    Island_Tab:Button("Graveyard Island", function()
        TP2(CFrame.new(-9515.07324, 142.130615, 5537.58398))
    end)
    Island_Tab:Button("Haunted Castle",function()
        TP2(CFrame.new(-8932.86, 143.258, 6063.31))
    end)
    Island_Tab:Button("Raid Lab", function()
        TP2(CFrame.new(-5057.146484375, 314.54132080078, -2934.7995605469))
    end)

    Island_Tab:Button("Mini Sky", function()
        TP2(CFrame.new(-263.66668701172, 49325.49609375, -35260))
    end)
    Island_Tab:Button("Ice Cream Island",function()
        TP2(CFrame.new(-691.829, 371.943, -11106.4))
    end)
    Island_Tab:Button("Soa of Cake",function()
        TP2(CFrame.new(-2073.262451171875, 37.16134262084961, -10183.3271484375))
    end)
    Island_Tab:Button("Cake Loaf",function()
        TP2(CFrame.new(-2099.33, 66.9971, -12128.6))
    end)
end

Status_Tab:Label("Setting Status")
Status_Tab:Toggle("Auto Update Status","9606294253",_G.Setting_table.Update_S,function(vu)
	_G.Setting_table.Update_S = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(.5) do
		pcall(function()
			if _G.Setting_table.Update_S then
				CheckStatus()
				wait(_G.Setting_table.Delay_C)
			else
				wait(2)
			end
		end)
	end
end)

Status_Tab:Slider("Delay",1,30,15,function(vu)
	_G.Setting_table.Delay_C = vu
end)
Status_Tab:Button("Update Status",function()
	CheckStatus()
end)

-- ❌
-- ✅
Status_Tab:Label("Status Quest")
local Kill_Elite_Hunter_ST = Status_Tab:LabelP("Kill Elite Hunter : 0")
local Kill_Cake_Monster_ST = Status_Tab:LabelP("Kill Cake Monster : 0/500")
local Bartlio_ST = Status_Tab:LabelP("❌ : Quest Bartlio")
local Open_Don_Swan_ST = Status_Tab:LabelP("❌ : Quest Open Don Swan")
local Phoenix_Awaken_ST = Status_Tab:LabelP("❌ : Quest Phoenix Awaken")
local Observation_Haki_ST = Status_Tab:LabelP("❌ : Quest Observation Haki")
local Observation_Haki_V2_ST = Status_Tab:LabelP("❌ : Quest Observation Haki V2")
Status_Tab:Label("Status Legendary Sword")
local ST_Shisui = Status_Tab:LabelP("❌ : Shisui")
local ST_Saddi = Status_Tab:LabelP("❌ : Saddi")
local ST_Wando = Status_Tab:LabelP("❌ : Wando")
function CheckStatus()
	Kill_Elite_Hunter_ST:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
	local OP = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner")
    local Lp = tonumber(string.match(tostring(OP), "%d+"))
	Kill_Cake_Monster_ST:Set("Kill Cake Monster : "..tostring(Lp).."/500")
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
		Open_Don_Swan_ST:Set("✅ : Open Don Swan Quest")
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
		Bartlio_ST:Set("✅ : Bartilo Quest") 
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SickScientist","Heal") == 1 then
		Phoenix_Awaken_ST:Set('✅ : Quest Phoenix Awaken')
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") == 0 then
		Observation_Haki_ST:Set('✅ : Quest Observation Haki')
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 3 then
		Observation_Haki_V2_ST:Set('✅ : Quest Observation Haki V2')
	end

	for i,x in pairs(I_W) do
		v = {
			Name = x["Name"]
		}
		if v.Name == "Shisui" then
			ST_Shisui:Set("✅ : Shisui")
		end
		if v.Name == "Wando" then
			ST_Wando:Set("✅ : Wando")
		end
		if v.Name == "Saddi" then
			ST_Saddi:Set("✅ : Saddi")
		end
	end
	for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
		if v:IsA("Tool") then
			if v.Name == "Shisui" then
				ST_Shisui:Set("✅ : Shisui")
			end
			if v.Name == "Wando" then
				ST_Wando:Set("✅ : Wando")
			end
			if v.Name == "Saddi" then
				ST_Saddi:Set("✅ : Saddi")
			end
		end
	end
	for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
		if v:IsA("Tool") then
			if v.Name == "Shisui" then
				ST_Shisui:Set("✅ : Shisui")
			end
			if v.Name == "Wando" then
				ST_Wando:Set("✅ : Wando")
			end
			if v.Name == "Saddi" then
				ST_Saddi:Set("✅ : Saddi")
			end
		end
	end
end
CheckStatus()

Status_Tab:Label("Check Status")
Status_Tab:Button("Open Fruit Inventory",function()
	game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
end)
Status_Tab:Button("Open Fruit Awaken",function()
	game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = true
end)
Status_Tab:Button("Open Fruit Store",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
    game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
end)
Status_Tab:Button("Open Inventory",function()
	game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Visible = true 
end)
Status_Tab:Button("Open Color Haki",function()
	game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
end)
Status_Tab:Button("Open Title Name",function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getTitles")
    game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
end)
function isnil(thing)
	return (thing == nil)
end
local function round(n)
	return math.floor(tonumber(n) + 0.5)
end
Number = math.random(1, 1000000)
function UpdatePlayerChams()
	for i,v in pairs(game:GetService'Players':GetChildren()) do
		pcall(function()
			if not isnil(v.Character) then
				if ESPPlayer then
					if not isnil(v.Character.Head) and not v.Character.Head:FindFirstChild('NameEsp'..Number) then
						local bill = Instance.new('BillboardGui',v.Character.Head)
						bill.Name = 'NameEsp'..Number
						bill.ExtentsOffset = Vector3.new(0, 1, 0)
						bill.Size = UDim2.new(1,200,1,30)
						bill.Adornee = v.Character.Head
						bill.AlwaysOnTop = true
						local name = Instance.new('TextLabel',bill)
						name.Font = Enum.Font.GothamSemibold
						name.FontSize = "Size14"
						name.TextWrapped = true
						name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
						name.Size = UDim2.new(1,0,1,0)
						name.TextYAlignment = 'Top'
						name.BackgroundTransparency = 1
						name.TextStrokeTransparency = 0.5
						if v.Team == game.Players.LocalPlayer.Team then
							name.TextColor3 = Color3.new(0,255,0)
						else
							name.TextColor3 = Color3.new(255,0,0)
						end
					else
						v.Character.Head['NameEsp'..Number].TextLabel.Text = (v.Name ..' | '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M\nHealth : ' .. round(v.Character.Humanoid.Health*100/v.Character.Humanoid.MaxHealth) .. '%')
					end
				else
					if v.Character.Head:FindFirstChild('NameEsp'..Number) then
						v.Character.Head:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end
			end
		end)
	end
end
function UpdateChestChams() 
	for i,v in pairs(game.Workspace:GetChildren()) do
		pcall(function()
			if string.find(v.Name,"Chest") then
				if ChestESP then
					if string.find(v.Name,"Chest") then
						if not v:FindFirstChild('NameEsp'..Number) then
							local bill = Instance.new('BillboardGui',v)
							bill.Name = 'NameEsp'..Number
							bill.ExtentsOffset = Vector3.new(0, 1, 0)
							bill.Size = UDim2.new(1,200,1,30)
							bill.Adornee = v
							bill.AlwaysOnTop = true
							local name = Instance.new('TextLabel',bill)
							name.Font = Enum.Font.GothamSemibold
							name.FontSize = "Size14"
							name.TextWrapped = true
							name.Size = UDim2.new(1,0,1,0)
							name.TextYAlignment = 'Top'
							name.BackgroundTransparency = 1
							name.TextStrokeTransparency = 0.5
							if v.Name == "Chest1" then
								name.TextColor3 = Color3.fromRGB(109, 109, 109)
								name.Text = ("Chest 1" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
							end
							if v.Name == "Chest2" then
								name.TextColor3 = Color3.fromRGB(173, 158, 21)
								name.Text = ("Chest 2" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
							end
							if v.Name == "Chest3" then
								name.TextColor3 = Color3.fromRGB(85, 255, 255)
								name.Text = ("Chest 3" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
							end
						else
							v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
						end
					end
				else
					if v:FindFirstChild('NameEsp'..Number) then
						v:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end
			end
		end)
	end
end
function UpdateDevilChams() 
	for i,v in pairs(game.Workspace:GetChildren()) do
		pcall(function()
			if DevilFruitESP then
				if string.find(v.Name, "Fruit") then   
					if not v.Handle:FindFirstChild('NameEsp'..Number) then
						local bill = Instance.new('BillboardGui',v.Handle)
						bill.Name = 'NameEsp'..Number
						bill.ExtentsOffset = Vector3.new(0, 1, 0)
						bill.Size = UDim2.new(1,200,1,30)
						bill.Adornee = v.Handle
						bill.AlwaysOnTop = true
						local name = Instance.new('TextLabel',bill)
						name.Font = Enum.Font.GothamSemibold
						name.FontSize = "Size14"
						name.TextWrapped = true
						name.Size = UDim2.new(1,0,1,0)
						name.TextYAlignment = 'Top'
						name.BackgroundTransparency = 1
						name.TextStrokeTransparency = 0.5
						name.TextColor3 = Color3.fromRGB(255, 0, 0)
						name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					else
						v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					end
				end
			else
				if v.Handle:FindFirstChild('NameEsp'..Number) then
					v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
				end
			end
		end)
	end
end
function UpdateFlowerChams() 
	for i,v in pairs(game.Workspace:GetChildren()) do
		pcall(function()
			if v.Name == "Flower2" or v.Name == "Flower1" then
				if FlowerESP then 
					if not v:FindFirstChild('NameEsp'..Number) then
						local bill = Instance.new('BillboardGui',v)
						bill.Name = 'NameEsp'..Number
						bill.ExtentsOffset = Vector3.new(0, 1, 0)
						bill.Size = UDim2.new(1,200,1,30)
						bill.Adornee = v
						bill.AlwaysOnTop = true
						local name = Instance.new('TextLabel',bill)
						name.Font = Enum.Font.GothamSemibold
						name.FontSize = "Size14"
						name.TextWrapped = true
						name.Size = UDim2.new(1,0,1,0)
						name.TextYAlignment = 'Top'
						name.BackgroundTransparency = 1
						name.TextStrokeTransparency = 0.5
						name.TextColor3 = Color3.fromRGB(255, 0, 0)
						if v.Name == "Flower1" then 
							name.Text = ("Blue Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
							name.TextColor3 = Color3.fromRGB(0, 0, 255)
						end
						if v.Name == "Flower2" then
							name.Text = ("Red Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
							name.TextColor3 = Color3.fromRGB(255, 0, 0)
						end
					else
						v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
					end
				else
					if v:FindFirstChild('NameEsp'..Number) then
					v:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end
			end   
		end)
	end
end
function UpdateRealFruitChams() 
	for i,v in pairs(game.Workspace.AppleSpawner:GetChildren()) do
		if v:IsA("Tool") then
			if RealFruitESP then 
				if not v.Handle:FindFirstChild('NameEsp'..Number) then
					local bill = Instance.new('BillboardGui',v.Handle)
					bill.Name = 'NameEsp'..Number
					bill.ExtentsOffset = Vector3.new(0, 1, 0)
					bill.Size = UDim2.new(1,200,1,30)
					bill.Adornee = v.Handle
					bill.AlwaysOnTop = true
					local name = Instance.new('TextLabel',bill)
					name.Font = Enum.Font.GothamSemibold
					name.FontSize = "Size14"
					name.TextWrapped = true
					name.Size = UDim2.new(1,0,1,0)
					name.TextYAlignment = 'Top'
					name.BackgroundTransparency = 1
					name.TextStrokeTransparency = 0.5
					name.TextColor3 = Color3.fromRGB(255, 0, 0)
					name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
				else
					v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..' '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
				end
			else
				if v.Handle:FindFirstChild('NameEsp'..Number) then
					v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
				end
			end 
		end
	end
	for i,v in pairs(game.Workspace.PineappleSpawner:GetChildren()) do
		if v:IsA("Tool") then
			if RealFruitESP then 
				if not v.Handle:FindFirstChild('NameEsp'..Number) then
					local bill = Instance.new('BillboardGui',v.Handle)
					bill.Name = 'NameEsp'..Number
					bill.ExtentsOffset = Vector3.new(0, 1, 0)
					bill.Size = UDim2.new(1,200,1,30)
					bill.Adornee = v.Handle
					bill.AlwaysOnTop = true
					local name = Instance.new('TextLabel',bill)
					name.Font = Enum.Font.GothamSemibold
					name.FontSize = "Size14"
					name.TextWrapped = true
					name.Size = UDim2.new(1,0,1,0)
					name.TextYAlignment = 'Top'
					name.BackgroundTransparency = 1
					name.TextStrokeTransparency = 0.5
					name.TextColor3 = Color3.fromRGB(255, 174, 0)
					name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
				else
					v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..' '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
				end
			else
				if v.Handle:FindFirstChild('NameEsp'..Number) then
					v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
				end
			end 
		end
	end
	for i,v in pairs(game.Workspace.BananaSpawner:GetChildren()) do
		if v:IsA("Tool") then
			if RealFruitESP then 
				if not v.Handle:FindFirstChild('NameEsp'..Number) then
					local bill = Instance.new('BillboardGui',v.Handle)
					bill.Name = 'NameEsp'..Number
					bill.ExtentsOffset = Vector3.new(0, 1, 0)
					bill.Size = UDim2.new(1,200,1,30)
					bill.Adornee = v.Handle
					bill.AlwaysOnTop = true
					local name = Instance.new('TextLabel',bill)
					name.Font = Enum.Font.GothamSemibold
					name.FontSize = "Size14"
					name.TextWrapped = true
					name.Size = UDim2.new(1,0,1,0)
					name.TextYAlignment = 'Top'
					name.BackgroundTransparency = 1
					name.TextStrokeTransparency = 0.5
					name.TextColor3 = Color3.fromRGB(251, 255, 0)
					name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
				else
					v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..' '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
				end
			else
				if v.Handle:FindFirstChild('NameEsp'..Number) then
					v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
				end
			end 
		end
	end
end
Esp_Tab:Toggle("ESP Players","9606294253",false,function(a)
	ESPPlayer = a
	UpdatePlayerChams()
end)
Esp_Tab:Toggle("ESP Chests","9606294253",false,function(a)
	ChestESP = a
	UpdateChestChams() 
end)
Esp_Tab:Toggle("ESP Devil Fruit","9606294253",false,function(a)
	DevilFruitESP = a
	UpdateDevilChams() 
end)
Esp_Tab:Toggle("ESP Fruit Spawn","9606294253",false,function(a)
	RealFruitESP = a
	UpdateRealFruitChams() 
end)
Esp_Tab:Toggle("ESP Flowers","9606294253",false,function(a)
	FlowerESP = a
	UpdateFlowerChams() 
end)
spawn(function()
	while wait(2) do
		if FlowerESP then
			UpdateFlowerChams() 
		end
		if DevilFruitESP then
			UpdateDevilChams() 
		end
		if ChestESP then
			UpdateChestChams() 
		end
		if ESPPlayer then
			UpdatePlayerChams()
		end
		if RealFruitESP then
			UpdateRealFruitChams()
		end
	end
end)

Setting_Tab:Label("Setting Server")
function FPSBooster()
    local decalsyeeted = true
    local g = game
    local w = g.Workspace
    local l = g.Lighting
    local t = w.Terrain
    sethiddenproperty(l,"Technology",2)
    sethiddenproperty(t,"Decoration",false)
    t.WaterWaveSize = 0
    t.WaterWaveSpeed = 0
    t.WaterReflectance = 0
    t.WaterTransparency = 0
    l.GlobalShadows = false
    l.FogEnd = 9e9
    l.Brightness = 0
    settings().Rendering.QualityLevel = "Level01"
    for i, v in pairs(g:GetDescendants()) do
        if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
            v.Material = "Plastic"
            v.Reflectance = 0
        elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
            v.Transparency = 1
        elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
            v.Lifetime = NumberRange.new(0)
        elseif v:IsA("Explosion") then
            v.BlastPressure = 1
            v.BlastRadius = 1
        elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
            v.Enabled = false
        elseif v:IsA("MeshPart") then
            v.Material = "Plastic"
            v.Reflectance = 0
            v.TextureID = 10385902758728957
        end
    end
    for i, e in pairs(l:GetChildren()) do
        if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
            e.Enabled = false
        end
    end
end
Setting_Tab:Toggle("White Screen","9606294253",_G.Setting_table.White_Screen,function(vu)
	_G.Setting_table.White_Screen = vu
    if _G.Setting_table.White_Screen then
        game:GetService("RunService"):Set3dRenderingEnabled(false)
    else
        game:GetService("RunService"):Set3dRenderingEnabled(true)
    end
end)
Setting_Tab:Button("FPS Booster",function()
	FPSBooster()
end)
Setting_Tab:Button("Redeem All Code",function()
	function UseCode(Text)
        game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
    end
    UseCode("Sub2Fer999")
    UseCode("Enyu_is_Pro")
    UseCode("Magicbus")
    UseCode("JCWK")
    UseCode("Starcodeheo")
    UseCode("Bluxxy")
    UseCode("THEGREATACE")
    UseCode("SUB2GAMERROBOT_EXP1")
    UseCode("StrawHatMaine")
    UseCode("Sub2OfficialNoobie")
    UseCode("SUB2NOOBMASTER123")
    UseCode("Sub2Daigrock")
    UseCode("Axiore")
    UseCode("TantaiGaming")
    UseCode("STRAWHATMAINE")
end)
Setting_Tab:Toggle("Auto Rejoin On Kick","9606294253",_G.Setting_table.Rejoin,function(vu)
	_G.Rejoin = vu
	_G.Setting_table.Rejoin = vu
	Update_Setting(getgenv()['MyName'])
end)
Setting_Tab:Toggle("Anti AFK","9606294253",_G.Setting_table.Anti_AFK,function(vu)
	_G.Setting_table.Anti_AFK = vu
	Update_Setting(getgenv()['MyName'])
end)

Setting_Tab:Label("Setting Attack")
Setting_Tab:Toggle("Auto Buso Haki","9606294253",true,function(vu)
	_G.Setting_table.Auto_Buso = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while wait(1) do
		pcall(function()
			if _G.Setting_table.Auto_Buso then
				if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
				else
					wait(3)
				end
			end
		end)
    end
end)
Setting_Tab:Toggle("Auto Ken Haki","9606294253",_G.Setting_table.Auto_Ken,function(vu)
	_G.Setting_table.Auto_Ken = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
	while wait(2) do
		pcall(function()
			if _G.Setting_table.Auto_Ken then
				game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("Ken",true)
				wait(7)
			end
		end)
	end
end)
Setting_Tab:Toggle("No Clip","9606294253",_G.Setting_table.NoClip,function(vu)
	_G.Setting_table.NoClip = vu
	Update_Setting(getgenv()['MyName'])
end)
spawn(function()
    while game:GetService("RunService").Stepped:wait() do
		pcall(function()
        	if _G.Setting_table.NoClip then
				local character = game.Players.LocalPlayer.Character
				for _, v in pairs(character:GetChildren()) do
					if v:IsA("BasePart") then
						v.CanCollide = false
					end
				end
			end
        end)
    end
end)
Setting_Tab:Toggle("Show Damage","9606294253",_G.Setting_table.Show_Damage,function(vu)
	game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = vu
	_G.Setting_table.Show_Damage = vu
	Update_Setting(getgenv()['MyName'])
end)
Setting_Tab:Button("Delete Effect Slash Hit",function()
    if game:GetService("ReplicatedStorage").Assets:FindFirstChild('SlashHit') then
        game:GetService("ReplicatedStorage").Assets:FindFirstChild('SlashHit'):Destroy()
	end
end)
if game:GetService("ReplicatedStorage").Assets:FindFirstChild('SlashHit') then
	game:GetService("ReplicatedStorage").Assets:FindFirstChild('SlashHit'):Destroy()
end

Setting_Tab:Label("Save Setting")
Setting_Tab:Toggle("Save Member","9606294253",_G.Setting_table.Save_Member,function(vu)
	_G.Setting_table.Save_Member = vu
	if vu then
		_G.Dis = nil
	end
	Update_Setting(_G.Check_Save_Setting)
	if _G.Setting_table.Save_Member then
		getgenv()['MyName'] = game.Players.LocalPlayer.Name
		Update_Setting(getgenv()['MyName'])
		Check_Setting(getgenv()['MyName'])
		Get_Setting(getgenv()['MyName'])
	end
end)
Setting_Tab:Toggle("Save All Member","9606294253",_G.Setting_table.Save_All_Member,function(vu)
	_G.Setting_table.Save_All_Member = vu
	if vu then
		_G.Dis = nil
	end
	Update_Setting(_G.Check_Save_Setting)
	if _G.Setting_table.Save_All_Member then
		getgenv()['MyName'] = "AllMember"
		Update_Setting(getgenv()['MyName'])
		Check_Setting(getgenv()['MyName'])
		Get_Setting(getgenv()['MyName'])
	end
end)

Hop_Tab:Label("Main")
Hop_Tab:Toggle("Bring Fruit Hop","9606294253",_G.Setting_table.BringFruit_Hop,function(vu)
	BringFruit = vu
	_G.Setting_table.BringFruit_Hop = vu
	Update_Setting(getgenv()['MyName'])
	if vu then
		wait(15)
		HopServer()
		wait(50)
	end
end)
if _G.Setting_table.BringFruit then
	BringFruit = true
end
Hop_Tab:Toggle("Auto Farm All Boss Hop","9606294253",_G.Setting_table.Auto_Farm_Boss_All_Hop,function(vu)
	_G.Setting_table.Auto_Farm_Boss_All_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
Hop_Tab:Toggle("Auto Farm Boss Hop","9606294253",_G.Setting_table.Auto_Farm_Boss_Hop,function(vu)
	_G.Setting_table.Auto_Farm_Boss_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)

if _G.Setting_table.Boss_Select_1 == nil then
	_G.Setting_table.Boss_Select_1 = ""
end
_G.Setting_table.Boss_All_Select = {}
local S_B_1 = Hop_Tab:Dropdown("Select Boss 1",_G.Setting_table.Boss_Select_1,Boss_List,function(vu)
	_G.Setting_table.Boss_Select_1 = vu
	if type(_G.Setting_table.Boss_Select_1) == "string" then
		table.insert(_G.Setting_table.Boss_All_Select,_G.Setting_table.Boss_Select_1)
	end
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Boss_Select_2 then
	_G.Setting_table.Boss_Select_2 = ""
end
local S_B_2 = Hop_Tab:Dropdown("Select Boss 2",_G.Setting_table.Boss_Select_2,Boss_List,function(vu)
	_G.Setting_table.Boss_Select_2 = vu
	if type(_G.Setting_table.Boss_Select_2) == "string" then
		table.insert(_G.Setting_table.Boss_All_Select,_G.Setting_table.Boss_Select_2)
	end
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Boss_Select_3 then
	_G.Setting_table.Boss_Select_3 = ""
end
local S_B_3 = Hop_Tab:Dropdown("Select Boss 3",_G.Setting_table.Boss_Select_3,Boss_List,function(vu)
	_G.Setting_table.Boss_Select_3 = vu
	if type(_G.Setting_table.Boss_Select_3) == "string" then
		table.insert(_G.Setting_table.Boss_All_Select,_G.Setting_table.Boss_Select_3)
	end
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Boss_Select_4 == nil then
	_G.Setting_table.Boss_Select_4 = ""
end
local S_B_4 = Hop_Tab:Dropdown("Select Boss 4",_G.Setting_table.Boss_Select_4,Boss_List,function(vu)
	_G.Setting_table.Boss_Select_4 = vu
	if type(_G.Setting_table.Boss_Select_4) == "string" then
		table.insert(_G.Setting_table.Boss_All_Select,_G.Setting_table.Boss_Select_4)
	end
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Boss_Select_5 == nil then
	_G.Setting_table.Boss_Select_5 = ""
end
local S_B_5 = Hop_Tab:Dropdown("Select Boss 5",_G.Setting_table.Boss_Select_5,Boss_List,function(vu)
	_G.Setting_table.Boss_Select_5 = vu
	if type(_G.Setting_table.Boss_Select_5) == "string" then
		table.insert(_G.Setting_table.Boss_All_Select,_G.Setting_table.Boss_Select_5)
	end
	Update_Setting(getgenv()['MyName'])
end)
Hop_Tab:Button("Refresh Select Boss",function()
	S_B_1:Clear()
	S_B_2:Clear()
	S_B_3:Clear()
	S_B_4:Clear()
	S_B_5:Clear()
	for i,v in pairs(Boss_List) do
		S_B_1:Add(v)
		S_B_2:Add(v)
		S_B_3:Add(v)
		S_B_4:Add(v)
		S_B_5:Add(v)
	end
end)
Hop_Tab:Toggle("Auto Farm Observation Haki Hop","9606294253",_G.Setting_table.Farm_Ken_Hop,function(vu)
	_G.Setting_table.Farm_Ken_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
Hop_Tab:Toggle("Auto Buy Legendary Sword Hop","9606294253",_G.Setting_table.Auto_Buy_Legendary_Sword_Hop,function(vu)
	_G.Setting_table.Auto_Buy_Legendary_Sword = vu
	_G.Setting_table.Auto_Buy_Legendary_Sword_Hop = vu
	Update_Setting(getgenv()['MyName'])
	if vu then
		wait(15)
		HopServer()
		wait(50)
	end
end)
Hop_Tab:Toggle("Auto Buy Color Buso Haki Hop","9606294253",_G.Setting_table.Buso_Haki_Hop,function(vu)
	Buso_Haki_Buy = vu
	_G.Setting_table.Buso_Haki_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Buso_Haki then
	Buso_Haki_Buy = vu
end


Hop_Tab:Label("Quest")
Hop_Tab:Toggle("Auto Open Don Swan Hop","9606294253",_G.Setting_table.Open_Don_Swan_Hop,function(vu)
	Inventory_Fruit = vu
	BringFruit = vu
	Don_Swan_Quest = vu
	_G.Setting_table.Open_Don_Swan_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Open_Don_Swan then
	Inventory_Fruit = true
	BringFruit = true
	Don_Swan_Quest = true
end
spawn(function()
	while wait(2) do
		pcall(function()
			if _G.Setting_table.Open_Don_Swan_Hop then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
					wait(15)
					HopServer()
					wait(50)
				else
					_G.TP_Ser = true
					wait(2)
					game.Players.LocalPlayer:Kick("\n✅ : Quest Open Don Swan ")
				end
			else
				wait(2)
			end
		end)
	end
end)

Hop_Tab:Toggle("Auto Farm Elite Hunter Hop","9606294253",_G.Setting_table.Auto_Elite_Hunter_Hop,function(vu)
	Auto_Elite_Hunter = vu
	_G.Setting_table.Auto_Elite_Hunter_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Elite_Hunter then
	Auto_Elite_Hunter = true
end
Hop_Tab:Toggle("Auto Phoenix Awaken Hop","9606294253",false,function(vu)
	_G.Setting_table.Phoenix_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
Hop_Tab:Toggle("Auto Observation Haki V2 Hop","9606294253",_G.Setting_table.Farm_Ken_V2_Hop,function(vu)
	Farm_Ken = vu
	Farm_Ken_V2 = vu
	_G.Setting_table.Farm_Ken_V2_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Farm_Ken_V2 then
	Farm_Ken = true
	Farm_Ken_V2 = true
end

Hop_Tab:Label("Sword")
Hop_Tab:Toggle("Auto Pole V1 Hop","9606294253",_G.Setting_table.Pole_V1_Hop,function(vu)
	Pole_Farm = vu
	_G.Setting_table.Pole_V1_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Pole_Farm then
	Pole_Farm = true
end
Hop_Tab:Toggle("Auto Saber Hop","9606294253",_G.Setting_table.Saber_Farm_Hop,function(vu)
	Saber_Farm = vu
	_G.Setting_table.Saber_Farm_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Saber_Farm then
	Saber_Farm = true
end
Hop_Tab:Seperator("Second World")
Hop_Tab:Toggle("Auto Rengoku Hop","9606294253",_G.Setting_table.Rengoku_Hop,function(vu)
	Rengoku_A = vu
	_G.Setting_table.Rengoku_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Rengoku_A then
	Rengoku_A = true
end
Hop_Tab:Toggle("Auto Ko Ko Hop","9606294253",false,function(vu)
	
end)
Hop_Tab:Toggle("Auto Dragon Trident Hop","9606294253",_G.Setting_table.Auto_Dragon_Trident_Hop,function(vu)
	Auto_Dragon_Trident = vu
	_G.Setting_table.Auto_Dragon_Trident_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Dragon_Trident then
	Auto_Dragon_Trident = true
end
Hop_Tab:Toggle("Auto True Triple Katana Hop","9606294253",_G.Setting_table.Triple_Hop,function(vu)
	Triple_A = vu
	Auto_Farm_Sword = vu
	_G.Setting_table.Triple_Hop = vu
end)
if _G.Setting_table.Triple_A then
	Auto_Farm_Sword = true
	Triple_A = true
end
Hop_Tab:Seperator("Thrid World")
Hop_Tab:Toggle("Auto Yama Hop","9606294253",_G.Setting_table.Auto_Yama_Hop,function(vu)
	Auto_Yama = vu
	_G.Setting_table.Auto_Yama_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Yama then
	Auto_Yama = true
end
Hop_Tab:Toggle("Auto Tushita Hop","9606294253",_G.Setting_table.Auto_Tushita_Hop,function(vu)
	Auto_Tushita = vu
	_G.Setting_table.Auto_Tushita_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Tushita then
	Auto_Tushita = true
end
Hop_Tab:Toggle("No Color Haki","9606294253",_G.Setting_table.No_Color_Haki_Tushita,function(vu)
	_G.Setting_table.No_Color_Haki_Tushita = vu
	Update_Setting(getgenv()['MyName'])
end)
Hop_Tab:Toggle("Auto Twin Hooks Hop","9606294253",_G.Setting_table.Auto_Twin_Hooks_Hop,function(vu)
	Auto_Twin_Hooks = vu
	_G.Setting_table.Auto_Twin_Hooks_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Twin_Hooks then
	Auto_Twin_Hooks = true
end
Hop_Tab:Toggle("Auto Canvander Hop","9606294253",_G.Setting_table.Auto_Canvander_Hop,function(vu)
	Auto_Canvander = vu
	_G.Setting_table.Auto_Canvander_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Canvander then
	Auto_Canvander = true
end
Hop_Tab:Toggle("Auto Buddy Sword Hop","9606294253",_G.Setting_table.Auto_Buddy_Sword_Hop,function(vu)
	Auto_Buddy_Sword = vu
	_G.Setting_table.Auto_Buddy_Sword_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Buddy_Sword then
	Auto_Buddy_Sword = true
end
Hop_Tab:Toggle("Auto Spikey Trident Hop","9606294253",_G.Setting_table.Spikey_Trident_Hop,function(vu)
	Auto_Spikey_Trident = vu
	_G.Setting_table.Spikey_Trident_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Spikey_Trident then
	Auto_Spikey_Trident = true
end
Hop_Tab:Toggle("Auto Hallow Scryte Hop","9606294253",_G.Setting_table.Auto_Hallow_Scryte,function(vu)
	Auto_Hallow_Scryte = vu
	_G.Setting_table.Hallow_Scryte_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Hallow_Scryte then
	Auto_Hallow_Scryte = true
end
Hop_Tab:Toggle("Auto Dark Dagger Hop","9606294253",_G.Setting_table.Auto_Dark_Dagger_Hop,function(vu)
	Auto_Dark_Dagger = vu
	_G.Setting_table.Auto_Dark_Dagger_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Dark_Dagger then
	Auto_Dark_Dagger = true
end
Hop_Tab:Toggle("No Color Haki","9606294253",_G.Setting_table.No_Color_Haki_Dark_Dagger,function(vu)
	_G.Setting_table.No_Color_Haki_Dark_Dagger = vu
	Update_Setting(getgenv()['MyName'])
end)

Hop_Tab:Label("Gun")
Hop_Tab:Toggle("Auto Acidum Rifle Hop","9606294253",_G.Setting_table.Auto_Acidum_Rifle_Hop,function(vu)
	Auto_Acidum_Rifle = vu
	_G.Setting_table.Auto_Acidum_Rifle_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Acidum_Rifle then
	Auto_Acidum_Rifle = true
end
Hop_Tab:Toggle("Auto Serpent Bow Hop","9606294253",_G.Setting_table.Auto_Serpent_Bow_Hop,function(vu)
	Auto_Serpent_Bow = vu
	_G.Setting_table.Auto_Serpent_Bow_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Serpent_Bow then
	Auto_Serpent_Bow = true
end

Hop_Tab:Label("Accessory")
Hop_Tab:Toggle("Auto Dark Coat Hop","9606294253",_G.Setting_table.Auto_Dark_Coat_Hop,function(vu)
	Auto_Dark_Coat = vu
	_G.Setting_table.Auto_Dark_Coat_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Chest_Lock == nil then
	_G.Setting_table.Chest_Lock = 50
end
C_H_H = 0
spawn(function()
	while wait(2) do
		pcall(function()
			if _G.Setting_table.Auto_Dark_Coat_Hop then
				if C_H_H >= _G.Setting_table.Chest_Lock and not H_F_T then
					HopServer()
					wait(50)
				end
			end
		end)
	end
end)
Hop_Tab:Slider("Chest Lock",1,100,_G.Setting_table.Chest_Lock,function(vu)
	_G.Setting_table.Chest_Lock = vu
	Update_Setting(getgenv()['MyName'])
end)

local L_C = Hop_Tab:Label("Chest : "..C_H_H.."/".._G.Setting_table.Chest_Lock)
if _G.Setting_table.Auto_Dark_Coat then
	Auto_Dark_Coat = true
end
spawn(function()
	while wait(.5) do
		pcall(function()
			if Auto_Dark_Coat then
				if game.Workspace.Enemies:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") then
					H_F_T = true
					if game.Workspace.Enemies:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") then
                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                            if v.Name == "Darkbeard [Lv. 1000] [Raid Boss]" and v.Humanoid.Health > 0 then
                                repeat wait(_G.Fast_Delay)
                                    EquipWeapon(_G.Setting_table.Weapon)
                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                    AttackNoCD()
                                until v.Humanoid.Health <= 0 or not v.Parent or not Auto_Dark_Coat
								H_F_T = nil
								if _G.Setting_table.Auto_Dark_Coat_Hop then
									HopServer()
									wait(50)
								end
							end
                        end
                    elseif game.ReplicatedStorage:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") then
                        TP(game.ReplicatedStorage:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                    end
				elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Fist of Darkness") or game.Players.LocalPlayer.Character:FindFirstChild("Fist of Darkness") then
					H_F_T = true
					repeat wait(.5)
                        EquipWeapon("Fist of Darkness")
                        TP(CFrame.new(3778.0603, 15.0511189, -3499.95801, -0.0148028014, 1.28971422e-07, -0.999890447, 3.63752335e-08, 1, 1.28447041e-07, 0.999890447, -3.44698741e-08, -0.0148028014))
                    until game.Workspace.Enemies:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Darkbeard [Lv. 1000] [Raid Boss]") or not Auto_Dark_Coat
				else
					
					H_F_T = nil
					_G.Chest_100 = nil
						_G.Chest_500 = nil
						_G.Chest_1000 = nil
						_G.Chest_1500 = nil
						_G.Chest_2000 = nil
						_G.Chest_2500 = nil
						_G.Chest_3500 = nil
						_G.Chest_4500 = nil
						_G.Chest_5500 = nil
						_G.Chest_6500 = nil
						_G.Chest_7500 = nil
						_G.Chest_9500 = nil
						_G.Chest_10500 = nil
						_G.Chest_12500 = nil
						_G.Chest_15500 = nil
						_G.Chest_17500 = nil
						Chest_100()
						Chest_500()
						Chest_1000()
						Chest_1500()
						Chest_2000()
						Chest_2500()
						Chest_3500()
						Chest_4500()
						Chest_5500()
						Chest_6500()
						Chest_7500()
						Chest_9500()
						Chest_10500()
						Chest_12500()
						Chest_15500()
						Chest_17500()
						if _G.Chest_100 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_100.CFrame)
							until not _G.Chest_100.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_500.CFrame)
							until not _G.Chest_500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_1000 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_1000.CFrame)
							until not _G.Chest_1000.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_1500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_1500.CFrame)
							until not _G.Chest_1500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_2000 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_2000.CFrame)
							until not _G.Chest_2000.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_2500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_2500.CFrame)
							until not _G.Chest_2500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_3500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_3500.CFrame)
							until not _G.Chest_3500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_4500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_4500.CFrame)
							until not _G.Chest_4500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_5500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_5500.CFrame)
							until not _G.Chest_5500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_6500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_6500.CFrame)
							until not _G.Chest_6500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_7500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_7500.CFrame)
							until not _G.Chest_7500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_9500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_9500.CFrame)
							until not _G.Chest_9500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_10500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_10500.CFrame)
							until not _G.Chest_10500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_12500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_12500.CFrame)
							until not _G.Chest_12500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_15500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_15500.CFrame)
							until not _G.Chest_15500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						elseif _G.Chest_17500 ~= nil then
							repeat wait(.3)
								TP(_G.Chest_17500.CFrame)
							until not _G.Chest_17500.Parent or not Auto_Dark_Coat
							if Auto_Dark_Coat then
								C_H_H = C_H_H + 1
								L_C:Set('Chest : '..tostring(C_H_H).."/".._G.Setting_table.Chest_Lock)
							end
						end
				end
			else
				wait(2)
			end
		end)
	end
end)
Hop_Tab:Toggle("Auto Swan Glass Hop","9606294253",_G.Setting_table.Auto_Swan_Glass_Hop,function(vu)
	Auto_Swan_Glass = vu
	_G.Setting_table.Auto_Swan_Glass_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Swan_Glass then
	Auto_Swan_Glass = true
end
Hop_Tab:Toggle("Auto Pale Scarf Hop","9606294253",false,function(vu)
	Auto_Pale_Scarf = vu
	_G.Setting_table.Auto_Pale_Scarf_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Pale_Scarf then
	Auto_Pale_Scarf = true
end
Hop_Tab:Toggle("Auto Valkyrie Helmet Hop","9606294253",_G.Setting_table.Auto_Valkyrie_Helmet_Hop,function(vu)
	Auto_Valkyrie_Helmet = vu
	_G.Setting_table.Auto_Valkyrie_Helmet_Hop = vu
	Update_Setting(getgenv()['MyName'])
end)
if _G.Setting_table.Auto_Valkyrie_Helmet then
	Auto_Valkyrie_Helmet = true
end
