--[[
	This property is protected.
	You are not allowed to claim this as your own.
	Removal of initial credits to the authors is prohibited.
]]

if 1 == 1 then
	loadstring(game:HttpGet("https://raw.githubusercontent.com/CF-Trail/tzechco-PlsDonateAutofarmBackup/main/old.lua"))()
	return
end

if hookmetamethod and typeof(hookmetamethod) == 'function' then
	local oldHook
	oldHook = hookmetamethod(game, "__namecall", function(self, ...)
		if getnamecallmethod() == "IsVoiceEnabledForUserIdAsync" then
			return true
		end
		return oldHook(self, ...)
	end)
end

repeat
	task.wait()
until game:IsLoaded()

if isfile and writefile and typeof(isfile) == 'function' and typeof(writefile) == 'function' then
	if not isfile('PromptedDiscordLinoriaCFRR.txt') then
		writefile('PromptedDiscordLinoriaCFRR.txt', game:GetService('HttpService'):JSONEncode('hi'))
		local Module = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Discord%20Inviter/Source.lua"))()
		Module.Prompt({
			invite = "https://discord.gg/fNeggqVMZs",
			name = "CF-Community",
		})
	end
end

  --Stops script if on a different game
if game.PlaceId ~= 8737602449 and game.PlaceId ~= 8943844393 then
	return
end

if getgenv().loadedR then
	return
else
	getgenv().loadedR = true
end

local xspin = 0

local httprequest = (syn and syn.request) or http and http.request or http_request or (fluxus and fluxus.request) or request

loadstring(game:HttpGet("https://raw.githubusercontent.com/CF-Trail/random/main/hook/hookwscripts.lua"))()
task.wait()
  --Anti-AFK
local Players = game:GetService("Players")
Players.LocalPlayer:Kick('unsupported executor')
local connections = getconnections or get_signal_cons or nil
task.spawn(function()
	if connections then
		for a, b in next, connections(game:GetService('Players').LocalPlayer.Idled) do
			b:Disable()
		end
	else
		local vu = game:GetService("VirtualUser")
		game:GetService("Players").LocalPlayer.Idled:Connect(function()
			vu:Button2Down(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
			wait(1)
			vu:Button2Up(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
		end)
	end
end)
  
  --Variables
local unclaimed = {}
local counter = 0
local donation, boothText, spamming, hopTimer
local signPass = false
local httpservice = game:GetService('HttpService')
local event = require(game:GetService('ReplicatedStorage').Remotes)
local errCount = 0
local booths = {
	["1"] = "72, 3, 36",
	["2"] = "83, 3, 161",
	["3"] = "11, 3, 36",
	["4"] = "100, 3, 59",
	["5"] = "72, 3, 166",
	["6"] = "2, 3, 42",
	["7"] = "-9, 3, 52",
	["8"] = "10, 3, 166",
	["9"] = "-17, 3, 60",
	["10"] = "35, 3, 173",
	["11"] = "24, 3, 170",
	["12"] = "48, 3, 29",
	["13"] = "24, 3, 33",
	["14"] = "101, 3, 142",
	["15"] = "-18, 3, 142",
	["16"] = "60, 3, 33",
	["17"] = "35, 3, 29",
	["18"] = "0, 3, 160",
	["19"] = "48, 3, 173",
	["20"] = "61, 3, 170",
	["21"] = "91, 3, 151",
	["22"] = "-24, 3, 72",
	["23"] = "-28, 3, 88",
	["24"] = "92, 3, 51",
	["25"] = "-28, 3, 112",
	["26"] = "-24, 3, 129",
	["27"] = "83, 3, 42",
	["28"] = "-8, 3, 151"
}

getgenv().settingsR = {}
  --Load Settings
if isfile("plsdonatesettingsR.txt") then
	local sl, er = pcall(function()
		getgenv().settingsR = httpservice:JSONDecode(readfile('plsdonatesettingsR.txt'))
	end)
	if er ~= nil then
		task.spawn(function()
			errMsg = Instance.new("Hint")
			errMsg.Parent = workspace
			errMsg.Text = tostring("Settings reset due to error: " .. er)
			task.wait(15)
			errMsg:Destroy()
		end)
		delfile("plsdonatesettingsR.txt")
	end
end
local sNames = {
	'BegMessages',
	'ThankMessages'
}
local sValues = {
	{
		'Jumping for robux!',
		'1R$ Donated = 1 jump!'
	},
	{
		'Thank you',
		'ty :D',
		'tysm!!'
	}
}
if #getgenv().settingsR ~= sNames then
	for i, v in ipairs(sNames) do
		if getgenv().settingsR[v] == nil then
			getgenv().settingsR[v] = sValues[i]
		end
	end
	writefile('plsdonatesettingsR.txt', httpservice:JSONEncode(getgenv().settingsR))
end
  
  --Save Settings
local settingsLock = true
local function saveSettings()
	print('Settings saved.')
	writefile('plsdonatesettingsR.txt', httpservice:JSONEncode(getgenv().settingsR))
end

function serverHop()
	--local isVip = game:GetService('RobloxReplicatedStorage').GetServerType:InvokeServer()
	--if isVip == "VIPServer" then return end
	if Toggles.autoSHEnabled == false and not getgenv().clickSH then
		return
	end
	local gameId
	gameId = "8737602449"
	if Toggles.serverHopAtVoice.Value == true then
		gameId = "8943844393"
	end
	if Toggles.RandomServersHop.Value == true then
		math.randomseed(tick())
		local random = math.random(0, 1)
		if random == 1 then
			gameId = '8943844393'
		else
			gameId = '8737602449'
		end
	end
	local servers = {}
	local req = httprequest({
		Url = "https://games.roblox.com/v1/games/" .. gameId .. "/servers/Public?sortOrder=Desc&limit=100"
	})
	local body = httpservice:JSONDecode(req.Body)
	if body and body.data then
		for i, v in next, body.data do
			if type(v) == "table" and tonumber(v.playing) and tonumber(v.maxPlayers) and v.playing < v.maxPlayers and v.playing > 19 then
				table.insert(servers, 1, v.id)
			end
		end
	end
	if #servers > 0 then
		game:GetService("TeleportService"):TeleportToPlaceInstance(gameId, servers[math.random(1, #servers)], Players.LocalPlayer)
	end
	game:GetService("TeleportService").TeleportInitFailed:Connect(function()
		game:GetService("TeleportService"):TeleportToPlaceInstance(gameId, servers[math.random(1, #servers)], Players.LocalPlayer)
	end)
end
local function waitServerHop()
	task.wait(Options.AutoSHMinutes.Value * 60)
	serverHop()
end
local function hopSet()
	if hopTimer then
		task.cancel(hopTimer)
	end
	if Toggles.autoSHEnabled.Value == true then
		hopTimer = task.spawn(waitServerHop)
	end
end

local function playerChecker(player)
	if Toggles.ServerHopIfMod.Value == false then
		return
	end
	pcall(function()
		if player:GetRankInGroup(12121240) >= 254 then
			serverHop()
		end
	end)
end

local function hex(c3)
	local r, g, b = math.floor(c3.R * 255), math.floor(c3.G * 255), math.floor(c3.B * 255)
	return string.format("#%02X%02X%02X", r, g, b)
end

local function update()
	print('Starting update function')
	local text
	local current = Players.LocalPlayer.leaderstats.Raised.Value
	local goal = current + tonumber(Options.GoalSlider.Value)
	if goal == 420 or goal == 425 then
		goal = goal + 10
	end
	if current == 420 or current == 425 then
		current = current + 10
	end
	if goal > 999 then
		if tonumber(Options.GoalSlider.Value) < 10 then
			goal = string.format("%.2fk", (current + 10) / 10 ^ 3)
		else
			goal = string.format("%.2fk", (goal) / 10 ^ 3)
		end
	end
	if current > 999 then
		current = string.format("%.2fk", current / 10 ^ 3)
	end
	if Options.boothTextTextbox.Value then
		print('started setting up text')
		textxs = string.gsub(Options.boothTextTextbox.Value, "$C", current)
		text = string.gsub(textxs, "$G", goal)
		print('gsubbed the goals')
		boothText = tostring('<font color="' .. hex(Options.textColorPicker.Value) .. '">' .. text .. '</font>')
		print('got the text')
		  --Updates the booth text
		local myBooth = Players.LocalPlayer.PlayerGui.MapUIContainer.MapUI.BoothUI:FindFirstChild(tostring("BoothUI" .. unclaimed[1]))
		print('got booth')
		if myBooth.Sign.TextLabel.Text ~= boothText then
			if string.find(myBooth.Sign.TextLabel.Text, "# #") or string.find(myBooth.Sign.TextLabel.Text, "##") then
				print('tags found')
				if Toggles.ServerHopIfTag.Value == true then
					serverHop()
					return
				end
				require(game:GetService("ReplicatedStorage").Remotes).Event("SetBoothText"):FireServer("your text here", "booth")
				task.wait(3)
			end
			print('tags not found')
			require(game:GetService('ReplicatedStorage').Remotes).Event("SetBoothText"):FireServer(boothText, "booth")
			task.wait(3)
		end
	end
	if Toggles.EquipSignT.Value == true then
		local sign = Players.LocalPlayer.Backpack:FindFirstChild('DonateSign')
		if sign then
			sign.Parent = Players.LocalPlayer.Character
		end
		task.wait(0.3)
		task.spawn(function()
			while task.wait(10) do
				require(game:GetService('ReplicatedStorage').Remotes).Event("SetBoothText"):FireServer(Options.addSignText.Value, "sign")
			end
		end)
	end
end
local function begging()
	while Toggles.AutoBegT.Value == true do
		game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.SayMessageRequest:FireServer(getgenv().settingsR.BegMessages[math.random(1, #getgenv().settingsR.BegMessages)], "All")
		task.wait(Options.BegDelaySlid.Value)
	end
end
local function webhook(msg)
	pcall(function()
		httprequest({
			Url = Options.webhookInputT.Value,
			Body = httpservice:JSONEncode({
				["content"] = msg
			}),
			Method = "POST",
			Headers = {
				["content-type"] = "application/json"
			}
		})
	end)
end

-- [[ ACTUAL CODE ]]

local queueonteleport = (syn and syn.queue_on_teleport) or queue_on_teleport or (fluxus and fluxus.queue_on_teleport)
local httpservice = game:GetService('HttpService')
queueonteleport("loadstring(game:HttpGet('https://raw.githubusercontent.com/CF-Trail/tzechco-PlsDonateAutofarmBackup/main/autofarm'))()")
local repoLib = 'https://raw.githubusercontent.com/wally-rblx/LinoriaLib/main/'

local Library = loadstring(game:HttpGet(repoLib .. 'Library.lua'))()
local ThemeManager = loadstring(game:HttpGet(repoLib .. 'addons/ThemeManager.lua'))()
local SaveManager = loadstring(game:HttpGet(repoLib .. 'addons/SaveManager.lua'))()
local positionX = workspace:WaitForChild('Boomboxes'):WaitForChild('Spawn')

local Window = Library:CreateWindow({
	Title = 'pls donate | szze#6220',
	Center = true,
	AutoShow = true,
})

local Tabs = {
	InfoTab = Window:AddTab('Info'),
	BoothTab = Window:AddTab('Booth'),
	serverHopTab = Window:AddTab('ServerHop'),
	miscTab = Window:AddTab('Miscellaneous'),
	['UI Settings'] = Window:AddTab('UI/Configs'),
}

local boothTextSettings = Tabs.BoothTab:AddLeftGroupbox('Text Settings')
local boothOtherSettings = Tabs.BoothTab:AddRightGroupbox('Other')
local serverHopSettings = Tabs.serverHopTab:AddLeftGroupbox('Settings')
local serverHopMain = Tabs.serverHopTab:AddRightGroupbox('Main')
local miscMain = Tabs.miscTab:AddLeftGroupbox('')
local miscMainT = Tabs.miscTab:AddRightGroupbox('')
--SCRAPPED
local infoMain = Tabs.InfoTab:AddLeftGroupbox('')
local infoExpand = Tabs.InfoTab:AddRightGroupbox('')

infoMain:AddLabel('Pls Donate | overhaul by szze#6220')
infoMain:AddLabel('Config saves every 10 seconds')

boothTextSettings:AddInput('boothTextTextbox', {
	Default = "✅ 1 ROBUX DONATED = 1 JUMP ✅",
	Numeric = false,
	Finished = true,
	Text = 'Booth Text',
	Tooltip = '$C = Current / $G = Goal',
	Placeholder = 'A text that shows on your booth',
})

boothTextSettings:AddDivider()

boothTextSettings:AddSlider('textUpdateSlider', {
	Text = 'Text update delay (S)',
	Default = 30,
	Min = 1,
	Max = 120,
	Rounding = 0,
	Compact = false,
})

boothTextSettings:AddLabel('Text Color'):AddColorPicker('textColorPicker', {
	Default = Color3.new(0, 1, 0),
	Title = 'Text Color',
})

boothTextSettings:AddDivider()

boothTextSettings:AddSlider('GoalSlider', {
	Text = 'Goal Increase',
	Default = 5,
	Min = 0,
	Max = 100,
	Rounding = 0,
	Compact = false,
})

boothOtherSettings:AddToggle('donationJumpToggle', {
	Text = 'Donation Jump',
	Default = true,
	Tooltip = 'Automatically jumps amount of R$ you got donated',
})

boothOtherSettings:AddToggle('spinSet', {
	Text = 'Spin',
	Default = false,
	Tooltip = '1R$ Donated = +1 spin speed',
})

Toggles.spinSet:OnChanged(function()
	local valll = Toggles.spinSet.Value
	if valll == true then
		local root = Players.LocalPlayer.Character.Humanoid.RootPart
		local Spin = Instance.new("BodyAngularVelocity")
		Spin.Name = "Spin"
		Spin.Parent = root
		Spin.MaxTorque = Vector3.new(0, math.huge, 0)
		Spin.AngularVelocity = Vector3.new(0, 0.25 * Options.spinSpeeder.Value, 0)
	elseif valll == false and Players.LocalPlayer.Character.Humanoid.RootPart:FindFirstChild('Spin') then
		Players.LocalPlayer.Character.Humanoid.RootPart.Spin:Destroy()
	end
end)

boothOtherSettings:AddDropdown('standingPositionDrop', {
	Values = {
		'Front',
		'Right',
		'Left',
		'Behind'
	},
	Default = 1,
	Multi = false,
	Text = 'Standing position',
	Tooltip = 'self explanatory',
})

serverHopSettings:AddToggle('serverHopAfterDonationTog', {
	Text = 'ServerHop after donation',
	Default = false,
	Tooltip = 'will switch servers after you get donated',
})

serverHopMain:AddButton('ServerHop', function()
	getgenv().clickSH = true
	serverHop()
end)

serverHopMain:AddDivider()

serverHopMain:AddToggle('autoSHEnabled', {
	Text = 'Auto ServerHop',
	Default = true,
	Tooltip = 'will server hop you after the time you set',
})

serverHopMain:AddSlider('AutoSHMinutes', {
	Text = 'ServerHop Delay (M)',
	Default = 15,
	Min = 5,
	Max = 60,
	Rounding = 0,
	Compact = false,
})

serverHopSettings:AddToggle('serverHopAtVoice', {
	Text = 'VC servers',
	Default = false,
	Tooltip = 'will teleport you to voice chat servers instead of normal',
})

serverHopSettings:AddToggle('RandomServersHop', {
	Text = 'Random Hop',
	Default = false,
	Tooltip = 'will randomly pick between voice and normal servers',
})

serverHopSettings:AddInput('minimumDonated', {
	Default = "0",
	Numeric = false,
	Finished = true,
	Text = 'Minimum Donated',
	Tooltip = 'will switch servers if not even 1 player got minimum donated',
	Placeholder = 'Minimum Donated',
})

miscMain:AddToggle('AutoBegT', {
	Text = 'Auto Beg',
	Default = true,
	Tooltip = 'Automatically types begging things in the chat',
})

miscMain:AddToggle('AutoThanksq', {
	Text = 'Auto Thanks',
	Default = true,
	Tooltip = 'Thanks the one who donated you',
})

miscMain:AddToggle('webhookToggleT', {
	Text = 'Webhook Notifications',
	Default = false,
	Tooltip = 'Sends a webhook message when you get donated'
})

miscMain:AddDivider()

miscMain:AddButton('Clear all beg messages', function()
	getgenv().settingsR.BegMessages = {}
end)

miscMain:AddButton('Clear all thank messages', function()
	getgenv().settingsR.ThankMessages = {}
end)

miscMain:AddDivider()

miscMain:AddInput('addBegMsgInput', {
	Default = '',
	Numeric = false,
	Finished = true,
	Text = 'Add beg message',
	Tooltip = 'adds a beg msg [PRESS ENTER AFTER TYPED]',
	Placeholder = 'Beg message ',
})

miscMain:AddInput('autoThanksInput', {
	Default = '',
	Numeric = false,
	Finished = true,
	Text = 'Add AutoThanks message',
	Tooltip = 'adds thank msg [PRESS ENTER AFTER TYPED]',
	Placeholder = 'AutoThanks message',
})

miscMain:AddInput('webhookInputT', {
	Default = '',
	Numeric = false,
	Finished = false,
	Text = 'Webhook',
	Tooltip = 'Discord/Guilded webhook [PRESS ENTER AFTER TYPED]',
	Placeholder = 'Webhook',
})

Options.addBegMsgInput:OnChanged(function()
	if Options.addBegMsgInput.Value:gsub(' ', '') ~= '' then
		table.insert(getgenv().settingsR.BegMessages, Options.addBegMsgInput.Value)
	end
end)

Options.autoThanksInput:OnChanged(function()
	if Options.autoThanksInput.Value:gsub(' ', '') ~= '' then
		table.insert(getgenv().settingsR.ThankMessages, Options.autoThanksInput.Value)
	end
end)

miscMain:AddDivider()

miscMain:AddSlider('BegDelaySlid', {
	Text = 'Beg Delay (S)',
	Default = 300,
	Min = 10,
	Max = 600,
	Rounding = 0,
	Compact = false,
})

miscMain:AddSlider('jumpsPerRobux', {
	Text = 'Jumps per robux',
	Default = 1,
	Min = 1,
	Max = 50,
	Rounding = 0,
	Compact = false,
})


if setfpscap and typeof(setfpscap) == 'function' then
	miscMain:AddSlider('FpsCapS', {
		Text = 'Fps Cap',
		Default = 60,
		Min = 10,
		Max = 60,
		Rounding = 0,
		Compact = false,
	})
	Options.FpsCapS:OnChanged(function()
		setfpscap(Options.FpsCapS.Value)
	end)
end

miscMain:AddSlider('spinSpeeder', {
	Text = 'Spin speed multiplier',
	Default = 1,
	Min = 1,
	Max = 3,
	Rounding = 0,
	Compact = false,
})

miscMain:AddDivider()

miscMain:AddDropdown('DanceChoiceD', {
	Values = {
		'/e wave',
		'/e cheer',
		'/e dance',
		'/e dance2',
		'/e dance3'
	},
	Default = 3,
	Multi = false,
	Text = 'Dance Choice',
	Tooltip = 'Automatically dances after claiming booth',
})

Options.DanceChoiceD:OnChanged(function()
	Players:Chat(Options.DanceChoiceD.Value)
end)

miscMainT:AddToggle('AutoNearReply', {
	Text = 'Auto Near Reply',
	Default = false,
	Tooltip = 'Replies to user if they are in <11 range from you'
})

miscMainT:AddToggle('DisableRenderingT', {
	Text = 'Disable Rendering',
	Default = false,
	Tooltip = 'Disables rendering to save CPU'
})

miscMainT:AddToggle('webASH', {
	Text = 'ServerHop webhook',
	Default = false,
	Tooltip = 'webhooks after serverhopping'
})

Toggles.DisableRenderingT:OnChanged(function()
	local valx = Toggles.DisableRenderingT.Value
	if valx == true then
		game:GetService("RunService"):Set3dRenderingEnabled(false)
	else
		game:GetService("RunService"):Set3dRenderingEnabled(true)
	end
end)

miscMainT:AddToggle('AutoAnonymous', {
	Text = 'Auto Anonymous Mode',
	Default = false,
	Tooltip = 'Stops showing how much R$ you donated'
})

local valw = Toggles.AutoAnonymous.Value
if valw == true then
	require(game:GetService('ReplicatedStorage').Remotes).Event('SetDonatedVisibility'):FireServer(false)
else
	require(game:GetService('ReplicatedStorage').Remotes).Event('SetDonatedVisibility'):FireServer(true)
end

miscMainT:AddToggle('ServerHopIfTag', {
	Text = 'ServerHop if tagged booth',
	Default = true,
	Tooltip = 'switches server if your booth gets tagged'
})

miscMainT:AddToggle('ServerHopIfMod', {
	Text = 'Staff Hop',
	Default = true,
	Tooltip = 'server hops if staff is in the server'
})

miscMainT:AddDivider()

miscMainT:AddToggle('EquipSignT', {
	Text = 'Auto Sign',
	Default = false,
	Tooltip = 'Automatically equips sign (gamepass required)'
})

Toggles.EquipSignT:OnChanged(function()
	local vall = Toggles.EquipSignT.Value
	if vall == false and Players.LocalPlayer.Character:FindFirstChild('DonateSign') then
		Players.LocalPlayer.Character.DonateSign.Parent = Players.LocalPlayer.Backpack
	elseif vall == true and Players.LocalPlayer.Backpack:FindFirstChild('DonateSign') then
		Players.LocalPlayer.Backpack.DonateSign.Parent = Players.LocalPlayer.Character
	end
end)

miscMainT:AddInput('addSignText', {
	Default = '',
	Numeric = false,
	Finished = true,
	Text = 'Sign Text',
	Tooltip = 'Sign text (gamepass required)',
	Placeholder = 'sign text',
})

local MenuGroup = Tabs['UI Settings']:AddLeftGroupbox('Menu')
MenuGroup:AddButton('Unload', function()
	Library:Unload()
end)
MenuGroup:AddLabel('Menu bind'):AddKeyPicker('MenuKeybind', {
	Default = 'End',
	NoUI = true,
	Text = 'Menu keybind'
}) 
Library.ToggleKeybind = Options.MenuKeybind 
ThemeManager:SetLibrary(Library)
SaveManager:SetLibrary(Library)
SaveManager:IgnoreThemeSettings() 
SaveManager:SetIgnoreIndexes({
	'MenuKeybind'
}) 
ThemeManager:SetFolder('pls-2donate')
SaveManager:SetFolder('pls-2donate/plsdonate')
SaveManager:BuildConfigSection(Tabs['UI Settings']) 
ThemeManager:ApplyToTab(Tabs['UI Settings'])

task.spawn(function()
	while task.wait(10) do
		SaveManager:Save('autosave')
		local name = 'autosave'
		writefile('pls-2donate/plsdonate/settings/autoload.txt', name)
		saveSettings()
	end
end)

task.spawn(function()
	while task.wait(1) do
		for i, v in next, Players:GetPlayers() do
			playerChecker(v)
		end
	end
end)

SaveManager:LoadAutoloadConfig()

  --Finds unclaimed booths
local function findUnclaimed()
	for i, v in pairs(Players.LocalPlayer.PlayerGui.MapUIContainer.MapUI.BoothUI:GetChildren()) do
		if (v.Details.Owner.Text == "unclaimed") then
			table.insert(unclaimed, tonumber(string.match(tostring(v), "%d+")))
		end
	end
end
if not pcall(findUnclaimed) then
	serverHop()
end
local claimCount = #unclaimed
  --Claim booth function
local function boothclaim()
	require(game:GetService('ReplicatedStorage').Remotes).Event("ClaimBooth"):InvokeServer(unclaimed[1])
	if not string.find(Players.LocalPlayer.PlayerGui.MapUIContainer.MapUI.BoothUI:FindFirstChild(tostring("BoothUI" .. unclaimed[1])).Details.Owner.Text, Players.LocalPlayer.DisplayName) then
		task.wait(1)
		if not string.find(Players.LocalPlayer.PlayerGui.MapUIContainer.MapUI.BoothUI:FindFirstChild(tostring("BoothUI" .. unclaimed[1])).Details.Owner.Text, Players.LocalPlayer.DisplayName) then
			error()
		end
	end
end
  --Checks if booth claim fails
while not pcall(boothclaim) do
	if errCount >= claimCount then
		serverHop()
	end
	table.remove(unclaimed, 1)
	errCount = errCount + 1
end
hopSet()
local function walkToBooth()
	local theCframe
	local standVal = Options.standingPositionDrop.Value
	getgenv().standingPositionX = standVal
	if standVal == "Front" then
		getgenv().standingPositionX = 3
	elseif standVal == "Left" then
		getgenv().standingPositionX = -6
	elseif standVal == "Right" then
		getgenv().standingPositionX = 6
	else
		getgenv().standingPositionX = -5.5
	end
	if string.find(tostring(getgenv().standingPositionX), "6") then
		theCframe = CFrame.new(getgenv().standingPositionX, 0, 0)
	else
		theCframe = CFrame.new(0, 0, getgenv().standingPositionX)
	end
	local boothPos
	for i, v in ipairs(game:GetService("Workspace").BoothInteractions:GetChildren()) do
		if v:GetAttribute("BoothSlot") == unclaimed[1] then
			boothPos = v.CFrame * theCframe
			break
		end
	end
	game:GetService('VirtualInputManager'):SendKeyEvent(true, "LeftControl", false, game)
	local Controls = require(Players.LocalPlayer.PlayerScripts:WaitForChild("PlayerModule")):GetControls()
	Controls:Disable()
	local atBooth = false
	game:GetService("Workspace").Map.Main.Bench:Destroy()
	Players.LocalPlayer.Character.Humanoid:MoveTo(boothPos.Position)
	Players.LocalPlayer.Character.Humanoid.MoveToFinished:Connect(function(reached)
		atBooth = true
	end)
	repeat
		task.wait()
	until atBooth
	Players.LocalPlayer.Character.Humanoid.RootPart.CFrame = CFrame.new(boothPos.Position)
	Controls:Enable()
	game:GetService('VirtualInputManager'):SendKeyEvent(false, "LeftControl", false, game)
	Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Players.LocalPlayer.Character.HumanoidRootPart.Position, Vector3.new(40, 14, 101)))
	task.wait(1)
	Players:Chat(Options.DanceChoiceD.Value)
end
walkToBooth()
if Toggles.AutoBegT.Value == true then
	spamming = task.spawn(begging)
end
local RaisedC = Players.LocalPlayer.leaderstats.Raised.value
Players.LocalPlayer.leaderstats.Raised.Changed:Connect(function()
	hopSet()
	xspin = ((xspin + Players.LocalPlayer.leaderstats.Raised.Value - RaisedC) / 3) * Options.spinSpeeder.Value
	if Toggles.webhookToggleT.Value == true then
		local LogService = Game:GetService("LogService")
		local logs = LogService:GetLogHistory()
		if string.find(logs[#logs].message, Players.LocalPlayer.DisplayName) then
			webhook("💰 Tip | Amount: " .. tostring(Players.LocalPlayer.leaderstats.Raised.Value - RaisedC) .. 'R$ (after tax: ' .. tostring(math.floor((Players.LocalPlayer.leaderstats.Raised.Value - RaisedC) * 0.6)) .. 'R$) | Total: ' .. tostring(Players.LocalPlayer.leaderstats.Raised.Value) .. 'R$ | Account: ' .. Players.LocalPlayer.DisplayName .. ' (' .. Players.LocalPlayer.Name .. ') | Server Message: ' .. logs[#logs].message:gsub('', ''))
		else
			webhook("💰 Tip | Amount: " .. tostring(Players.LocalPlayer.leaderstats.Raised.Value - RaisedC) .. 'R$ (after tax: ' .. tostring(math.floor((Players.LocalPlayer.leaderstats.Raised.Value - RaisedC) * 0.6)) .. 'R$) | Total: ' .. tostring(Players.LocalPlayer.leaderstats.Raised.Value) .. 'R$ | Account: ' .. Players.LocalPlayer.DisplayName .. ' (' .. Players.LocalPlayer.Name .. ') | Couldnt fetch server message')
		end	
	end
	if Toggles.serverHopAfterDonationTog.Value == true then
		task.spawn(function()
			serverHop()
		end)
	end
	if Players.LocalPlayer.Character.Humanoid.RootPart:FindFirstChild('Spin') and Toggles.spinSet.Value == true then
		local spin = Players.LocalPlayer.Character.Humanoid.RootPart:FindFirstChild('Spin')
		spin.AngularVelocity = Vector3.new(0, xspin, 0)
	end
	if Toggles.donationJumpToggle.Value == true and Toggles.spinSet.Value == false then
		task.spawn(function()
			if Options.jumpsPerRobux.Value == 1 then
				for i = 1, game:GetService('Players').LocalPlayer.leaderstats.Raised.value - RaisedC do
					game:GetService('Players').LocalPlayer.Character.Humanoid:ChangeState("Jumping")
					repeat
						task.wait()
					until game:GetService('Players').LocalPlayer.Character.Humanoid:GetState() == Enum.HumanoidStateType.Running
				end
			else
				for i = 1, (game:GetService('Players').LocalPlayer.leaderstats.Raised.value - RaisedC) * Options.jumpsPerRobux.Value do
					game:GetService('Players').LocalPlayer.Character.Humanoid:ChangeState("Jumping")
					repeat
						task.wait()
					until game:GetService('Players').LocalPlayer.Character.Humanoid:GetState() == Enum.HumanoidStateType.Running
				end
			end
		end)
	end
	RaisedC = Players.LocalPlayer.leaderstats.Raised.value
	if Toggles.AutoThanksq.Value == true then
		task.spawn(function()
			game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.SayMessageRequest:FireServer(getgenv().settingsR.ThankMessages[math.random(1, #getgenv().settingsR.ThankMessages)], "All")
		end)
	end
	task.wait(Options.textUpdateSlider.Value)
	update()
end)
update()
task.spawn(function()
	task.wait(5)
	Players.LocalPlayer.CharacterRemoving:Connect(function()
		if Toggles.spinSet.Value == true then
			serverHop()
		end
	end)
	for i,v in next, Players:GetPlayers() do
		if v:FindFirstChild('leaderstats') and v ~= Players.LocalPlayer then
			if raisedV ~= nil then
				if v.leaderstats.Raised.Value > raisedV then
					raisedV = v.leaderstats.Raised.Value
				end
			else
				raisedV.Value = v.leaderstats.Raised.Value
			end
		end
	end
	if raisedV < Options.minimumDonated.Value then
		serverHop()
	end
end)

task.spawn(function()
	while task.wait(5) do
		if (Players.LocalPlayer.Character and Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').RootPart) then
			local root = Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').RootPart
			if (root.Position - positionX.Position).Magnitude > 1500 or (root.Position - positionX.Position).Magnitude < -1500 then
				serverHop()
			end
		end
	end
end)

if Toggles.webASH.Value == true then
	webhook('hi hello ' .. Players.LocalPlayer.DisplayName .. ' (' .. Players.LocalPlayer.Name .. ') serverhopped')
end

local msgdone = game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.OnMessageDoneFiltering
local randommsgs = {
	'yes',
	'ok',
	'alr',
	'yeah'
}
local messageRequest = game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.SayMessageRequest
msgdone.OnClientEvent:Connect(function(msgdata)
	local speaker = tostring(msgdata.FromSpeaker)
	local message = string.lower(msgdata.Message)
	task.wait(1.4 + math.random(0.1, 0.4))
	local plrChatted = game:GetService('Players')[speaker] or nil
	if (plrChatted and plrChatted == game:GetService('Players').LocalPlayer) or Toggles.AutoNearReply.Value == false or not plrChatted then
		return
	end
	pcall(function()
		local chatChar = plrChatted.Character
		if (plrChatted.Character and plrChatted.Character.Humanoid.RootPart) then
			local root = chatChar.Humanoid.RootPart
			if (root.Position - game:GetService('Players').LocalPlayer.Character.Humanoid.RootPart.Position).Magnitude < 11 then
				if message == 'hello' or message == 'hi' or message == 'sup' then
					messageRequest:FireServer("hello", 'All')
				elseif string.find(message, 'jump') then
					messageRequest:FireServer('ok', 'All')
				elseif string.find(message, '?') and not string.find(message,'bot') then
					messageRequest:FireServer('yes', 'All')
				elseif string.find(message,'bot') then
					messageRequest:FireServer('no im not', 'All')
				else
					messageRequest:FireServer(randommsgs[math.random(1, #randommsgs)], 'All')
				end
			end
		end
	end)
end)
while task.wait(Options.AutoSHMinutes.Value * 60) do
	if not hopTimer then
		hopSet()
	end
end
