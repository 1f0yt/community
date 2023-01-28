function C()
    if not game:IsLoaded()then 
        local a=Instance.new("Message",workspace);
        a.Text='Waiting game to loaded before scripts is getting executed by Xenon Hub';
        game.Loaded:Wait();
        a:Destroy();
        wait(10);
    end;
    local f=game:GetService("HttpService");
    local e=game:GetService("RunService");
    local J=game:GetService("Players");
    local i=J.LocalPlayer;
    if getrenv()._G.RenderDist1~=100000 then 
        getrenv()._G.RenderDist1=100000;
    end;
    pcall(function()
        repeat wait();
        until not i.PlayerGui:FindFirstChild("LoadingDataUI");
        repeat wait(1);
        until i.Backpack:FindFirstChildOfClass("Tool")or game.PlaceId==5931540094;
        wait(1);
    end);
    
    if not isfolder("Xenon Hub Premium Scripts")then
        makefolder("Xenon Hub Premium Scripts");
    end;
    if not isfile("Xenon Hub Premium Scripts/KL_"..i.Name..".cfg")then 
        writefile("Xenon Hub Premium Scripts/KL_"..i.Name..".cfg","[]");
    end;
    GetSubPrefix=function(a)
        local a=tostring(a):gsub(" ","");
        local bX="";
        if#a==2 then 
            local Yp=string.sub(a,#a,#a+1);
            bX=Yp=="1"and"st"or Yp=="2"and"nd"or Yp=="3"and"rd"or"th";
        end;
        return bX;
    end;
    
    local A,L=loadstring(game:HttpGet("https://paste.website/p/f38d8583-9363-45f2-9865-3351d3731e81.txt"))();

    local h="%A, %B";local t=os.date(" %d",os.time());
    local l=", %Y.";
    h=os.date(h,os.time())..t..GetSubPrefix(t)..os.date(l,os.time());
    local u=A:CreateWindow(("Xenon Hub - "..tostring(h)));
    A:Notify("Loading User Interface.");
    A:Notify("Status:✅");
    local s={Load={AutoLoad={Enabled=true,RageSettings=false,SilentLoad=false,AutoLoadType="Last Config",LastUsedConfig="",LastConfig={},CustomConfig=""},Configs={},Ignored={"SettingsConfigName","SettingsConfigData","SettingsConfigConfigs","SettingsAutoLoadData","SettingsAutoLoadEnabled","SettingsAutoLoadRage","SettingsAutoLoadSilent","SettingsAutoLoadType","SettingsAutoLoadConfig","Level_Limit","Gems_Limit","Beli_Limit"}},Tick=tick()};
    
    function UpdateTheme()
        A.BackgroundColor=L.SettingsMenuBackgroundColor.Value;
        A.MainColor=L.SettingsMenuMainColor.Value;
        A.AccentColor=L.SettingsMenuAccentColor.Value;
        A.AccentColorDark=A:GetDarkerColor(A.AccentColor);
        A.InlineColor=L.SettingsMenuInlineColor.Value;
        A.OutlineColor=L.SettingsMenuOutlineColor.Value;
        A.FontColor=L.SettingsMenuFontColor.Value;
        A:UpdateColorsUsingRegistry();
    end;
    function SetDefault()
        L.SettingsMenuFontColor:SetValueRGB(Color3.fromRGB(255,255,255));
        L.SettingsMenuMainColor:SetValueRGB(Color3.fromRGB(0,15,30));
        L.SettingsMenuBackgroundColor:SetValueRGB(Color3.fromRGB(5,5,20));
        L.SettingsMenuAccentColor:SetValueRGB(Color3.fromRGB(0,180,240));
        L.SettingsMenuInlineColor:SetValueRGB(Color3.fromRGB(10,30,40));
        L.SettingsMenuOutlineColor:SetValueRGB(Color3.fromRGB(0,0,5));
        UpdateTheme();
    end;
    
    function ResetSettings()
        for a,Wb in pairs(L)do if typeof(Wb.Original)~="nil"then Wb:SetValue(Wb.Original);
        end;
    end;
end;

function GetConfigNames()
    local a={};
    for Vq,vq in pairs(s.Load.Configs)do a[#a+1]=vq[1];
    end;
    return a;
end;

function GetConfigByName(a)
    for wG,iG in pairs(s.Load.Configs)do 
        if iG[1]==a then return iG[2];
        end;
    end;
end;

function CreateConfig(a)
    if typeof(a)=="string"then 
        if(#a>3 and#a<=25)then 
            if(not GetConfigByName(a))then 
                s.Load.Configs[#s.Load.Configs+1]={a,(A:GetConfig(s.Load.Ignored))};
                L.SettingsConfigConfigs.Values=GetConfigNames();
                L.SettingsConfigConfigs:SetValues();
                L.SettingsAutoLoadConfig.Values=GetConfigNames();
                L.SettingsAutoLoadConfig:SetValues();
                return A:Notify(("Config \"%s\" Has Been Created."):format(a));
            end;
            return A:Notify(("Config \"%s\" Already Exists."):format(a));
        end;
        return A:Notify("Config Name Is Too Long / Short.");
    end;
    return A:Notify("Config Name Is Not A String.");
end;

function GetConfig()return(f:JSONEncode(A:GetConfig(s.Load.Ignored)));
end;
function LoadConfig(a)if typeof(a)=="table"then A:SetConfig(a,s.Load.Ignored);
elseif typeof(a)=="string"then local U4,T4=pcall(function()a=f:JSONDecode(a);
end);
if U4 then A:SetConfig(a,s.Load.Ignored);
    return A:Notify("Config Data Has Been Imported.");
end;
return A:Notify(("Error When Loading Config Data Statement : %s."):format(T4));
end;
end;

function DeleteConfig(a)
    for Pz,gz in pairs(s.Load.Configs)do 
        if gz[1]==a then table.remove(s.Load.Configs,Pz);
            L.SettingsConfigConfigs.Values=GetConfigNames();
            L.SettingsConfigConfigs:SetValue(L.SettingsConfigConfigs.Value);
            L.SettingsAutoLoadConfig.Values=GetConfigNames();
            L.SettingsAutoLoadConfig:SetValues();
            return A:Notify(("Config \"%s\" Has Been Removed."):format(a));
        end;
    end;
end;

function SaveConfig(a)
    for OO,IO in pairs(s.Load.Configs)do 
        if IO[1]==a then 
            s.Load.Configs[OO]={a,(A:GetConfig(s.Load.Ignored))};
            return A:Notify(("Config \"%s\" Has Been Saved."):format(a));
        end;
    end;
end;

function ExportData()
    setclipboard(GetConfig());
    A:Notify("Config Data Has Been Exported.");
end;

function ImportData()
    LoadConfig(L.SettingsConfigData.Value);
end;

do A.SaveManager={};
    function A.SaveManager:Save()
        s.Load.AutoLoad.LastConfig=A:GetConfig(s.Load.Ignored);
    end;
    function A.SaveManager:Load()local a=f:JSONDecode(readfile("Xenon Hub Premium Scripts/KL_"..i.Name..".cfg"));
        s.Load.AutoLoad=(a.AutoLoad or s.Load.AutoLoad);
        s.Load.Configs=(a.Configs or s.Load.Configs);
        do L.SettingsConfigConfigs.Values=GetConfigNames();
            L.SettingsConfigConfigs:SetValues();
            L.SettingsAutoLoadConfig.Values=GetConfigNames();
            L.SettingsAutoLoadConfig:SetValues();
        end;
        local Jc;
        if s.Load.AutoLoad.AutoLoadType=="Last Used Config"then if GetConfigByName(s.Load.AutoLoad.LastUsedConfig)then 
            Jc=GetConfigByName(s.Load.AutoLoad.LastUsedConfig);
        end;
    elseif s.Load.AutoLoad.AutoLoadType=="Last Config"then
        if s.Load.AutoLoad.LastConfig then
        Jc=s.Load.AutoLoad.LastConfig;
    end;elseif s.Load.AutoLoad.AutoLoadType=="Custom Config"then 
        if GetConfigByName(s.Load.AutoLoad.CustomConfig)then 
            Jc=GetConfigByName(s.Load.AutoLoad.CustomConfig);
        end;
    end;
    if Jc then 
        if(not s.Load.RageSettings)then 
            for JR,DR in pairs(L)do 
                if(DR.Type=="Toggle"and JR:sub(1,4)=="Rage")then 
                    if Jc[JR]then warn(("Set %s to false."):format(JR));Jc[JR]=false;
                    end;
                end;
            end;
        end;
        if s.Load.AutoLoad.SilentLoad then 
            Jc["SettingsMenuKeybinds"]=false;
            Jc["SettingsMenuWatermark"]=false;
            Jc["SettingsMiscNotifications"]=false;
            A:SetWatermarkVisibility(false);
            u.Holder.Visible=false;
        end;
        LoadConfig(Jc);
    end;
end;

function A.SaveManager:SaveFile()
    local a=f:JSONEncode({AutoLoad=s.Load.AutoLoad,Configs=s.Load.Configs});
    writefile("Xenon Hub Premium Scripts/KL_"..i.Name..".cfg",a);
end;
end;
local N=u:AddTab("General");

local p=u:AddTab("Visuals");


local T=u:AddTab("Read");

local x=N:AddLeftTabbox();

local W=N:AddLeftTabbox();

local k=N:AddLeftTabbox();

local V=N:AddRightTabbox();

local b=N:AddRightTabbox();

local O=N:AddRightTabbox();

local y=N:AddRightTabbox();
local oi=T:AddLeftTabbox();

local Q=x:AddTab("Main");

local R=x:AddTab("Special");

local z=x:AddTab("Others");

local He=oi:AddTab("Join On Discord !!!!!!!!!!");

He:AddLabel("Revamped By TERES#1866",true);
He:AddLabel("Cracked By ???",true);
local function disc()
local request = (syn and syn.request) or (http and http.request) or http_request

if request then
    request(
        {
            Url = "http://127.0.0.1:6463/rpc?v=1",
            Method = "POST",
            Headers = {
                ["Content-Type"] = "application/json",
                ["Origin"] = "https://discord.com"
            },
            Body = game:GetService("HttpService"):JSONEncode(
                {
                    cmd = "INVITE_BROWSER",
                    args = {code = "pAet8FmKB3"},
                    nonce = game:GetService("HttpService"):GenerateGUID(false)
                }
            )
        }
    )
end
end
He:AddButton("Join On Discord",disc);

Q:AddLabel("Level",true);

Q:AddToggle("Auto_Farm_Level",{Text="Auto Farm Level"});

Q:AddToggle("Auto_Farm_New_World",{Text="Auto Farm New World"});

Q:AddLabel("Sea Beasts",true);

Q:AddToggle("Auto_Farm_Sea_Beasts",{Text="Auto Farm Sea Beasts"}):OnChanged(function()
    pcall(function()
        getgenv().Old_Pos=i.Character.HumanoidRootPart.CFrame;
    end);
end);

Q:AddToggle("Auto_Farm_Sea_Beasts_Hop",{Text="Auto Farm Sea Beasts Hop"});

local M={"Common","Uncommon","Rare","Epic","Legendary"};

Q:AddDropdown("Auto_Farm_Sea_Beasts_Until",{Text="Hop Until Found",Default=4,Values=M,Multi=true});

Q:AddLabel("Ships",true);

Q:AddToggle("Auto_Farm_Ghost_Ship",{Text="Auto Farm Ghost Ship"});

Q:AddToggle("Auto_Farm_Ghost_Ship_Hop",{Text="Auto Farm Ghost Ship Hop"});

R:AddLabel("?EVENT?",true);

R:AddLabel("Santa [Raid Boss]",false);

R:AddToggle("Auto_Farm_Santa",{Text="Auto Farm Santa"});

R:AddToggle("Auto_Farm_Santa_Hop",{Text="Auto Farm Santa Hop"});

R:AddLabel("Kris Kringle [Raid Boss]",false);

R:AddToggle("Auto_Farm_Kris_Kringle",{Text="Auto Farm Kris Kringle"});

R:AddToggle("Auto_Farm_Kris_Kringle_Hop",{Text="Auto Farm Kris Kringle Hop"});

R:AddLabel("Ms. Mother [Raid Boss]",false);

R:AddToggle("Auto_Farm_Ms_Mother",{Text="Auto Farm Ms. Mother"});

R:AddToggle("Auto_Farm_Ms_Mother_Hop",{Text="Auto Farm Ms. Mother Hop"});

R:AddLabel("Coming Soon",true);

z:AddLabel("??Swords??",true);

local m=z:AddLabel("Enma Owned : ??",false);

local o=z:AddLabel("King Samurai Spawned : ??",false);

z:AddToggle("Auto_Farm_Enma",{Text="Auto Farm Enma"});

z:AddToggle("Auto_Farm_Enma_Hop",{Text="Auto Farm Enma Hop"});

z:AddToggle("Hop_Until_Found_Enma",{Text="Hop Until Found Enma"});

local G=z:AddLabel("Saber Owned : ?",false);

local E=z:AddLabel("Expert Swordsman Spawned : ??",false);

z:AddToggle("Auto_Farm_Saber",{Text="Auto Farm Saber"});

z:AddToggle("Auto_Farm_Saber_Hop",{Text="Auto Farm Saber Hop"});

z:AddToggle("Hop_Until_Found_Saber",{Text="Hop Until Found Saber"});

local D=W:AddTab("Bosses");

local I=W:AddTab("Special Bosses");

local w={};
pcall(function()
    for a in pairs(w)do w[a]=nil;
    end;
    for a,hX in pairs(game:GetService("Workspace").Monster.Boss:GetChildren())do 
        if hX:FindFirstChild("Humanoid")and hX:FindFirstChild("Humanoid").Health~=0 then 
            table.insert(w,hX.Name);
        end;
    end;
end);

D:AddDropdown("Selected_Bosses",{Text="Select Bosses",Values=w,Multi=true});

D:AddToggle("Auto_Farm_Bosses",{Text="Auto Farm Bosses"});

D:AddToggle("Auto_Farm_Bosses_Hop",{Text="Auto Farm Bosses Hop"});
task.spawn(function()
    while true do wait(2);
        pcall(function()
            for a in pairs(w)do 
                w[a]=nil;
            end;
            for a,na in pairs(game:GetService("Workspace").Monster.Boss:GetChildren())do 
                if na:FindFirstChild("Humanoid")and na:FindFirstChild("Humanoid").Health~=0 then 
                    table.insert(w,na.Name);
                end;
            end;
            L.Options.Selected_Bosses.Value.Values=w;
            L.Options.Selected_Bosses.Value:SetValues();
        end);
    end;
end);

local j={"Kaido"};

I:AddDropdown("Selected_Bosses2",{Text="Select Bosses",Values=j,Multi=false});

I:AddToggle("Auto_Farm_Bosses_2",{Text="Auto Farm Bosses"});
local function P(a)local Kv=i.Character:FindFirstChildOfClass("Tool");
    getgenv().Mob=a;if L.Selected_Skill.Value["Skill Z"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,i.Character.HumanoidRootPart);
        wait();
        game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,i.Character.HumanoidRootPart);
    end;
    if L.Selected_Skill.Value["Skill X"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,i.Character.HumanoidRootPart);
        wait();
        game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,i.Character.HumanoidRootPart);
    end;
    if L.Selected_Skill.Value["Skill C"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,i.Character.HumanoidRootPart);
        wait();
        game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,i.Character.HumanoidRootPart);
    end;
    if L.Selected_Skill.Value["Skill V"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,i.Character.HumanoidRootPart);
        wait();
        game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,i.Character.HumanoidRootPart);
    end;
    if L.Selected_Skill.Value["Skill F"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"F",false,i.Character.HumanoidRootPart);
        wait();
        game:GetService("VirtualInputManager"):SendKeyEvent(false,"F",false,i.Character.HumanoidRootPart);
    end;
    if L.Selected_Skill.Value["Skill E"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"E",false,i.Character.HumanoidRootPart);
        wait();game:GetService("VirtualInputManager"):SendKeyEvent(false,"E",false,i.Character.HumanoidRootPart);
    end;
    if L.Selected_Skill.Value["Skill B"]~=nil then 
        game:GetService("VirtualInputManager"):SendKeyEvent(true,"B",false,i.Character.HumanoidRootPart);
        wait();
        game:GetService("VirtualInputManager"):SendKeyEvent(false,"B",false,i.Character.HumanoidRootPart);
    end;
end;

local B=0;
local function H(a)
    if a then 
        if tick()>=B then 
            B=tick()+1;if tonumber(i.Character.Haki.Value)==0 then 
                i.Character.Services.Client.Armament:FireServer();
            end;
            i.Character.Services.Client.KenEvent:InvokeServer(true);
        end;
    end;
end;
task.spawn(function()
    repeat wait();
until L.Auto_Farm_Bosses_2.Value;
print("Toggled : Auto Farm Bosses");
while true do wait();
    pcall(function()
        if L.Auto_Farm_Bosses_2.Value then 
            if L.Selected_Bosses2.Value=="Kaido"then 
                if workspace.Monster.Boss:FindFirstChild("Dragon [Lv. 5000]")then 
                    task.spawn(function()
                        pcall(function()
                            i.Character.HumanoidRootPart.CFrame=workspace.Monster.Boss:FindFirstChild("Dragon [Lv. 5000]").HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                            H(true);
                            if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                            elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                P(workspace.Monster.Boss:FindFirstChild("Dragon [Lv. 5000]").HumanoidRootPart);
                            end;
                        end);
                    end);
                else if i.Backpack:FindFirstChild("DragonGem")or i.Character:FindFirstChild("DragonGem")then 
                    local a=i.Backpack:FindFirstChild("DragonGem")or i.Character:FindFirstChild("DragonGem");if a.Parent==i.Backpack then 
                        i.Character.Humanoid:EquipTool(a);
                    elseif a.Parent==i.Character then i.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").Island.SummonAltar.Handle.CFrame*CFrame.new(0,0,2);
                    end;
                else if workspace.Monster.Boss:FindFirstChild("Elite Skeleton [Lv. 3100]")then 
                    task.spawn(function()
                        pcall(function()
                            i.Character.HumanoidRootPart.CFrame=workspace.Monster.Boss:FindFirstChild("Elite Skeleton [Lv. 3100]").HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                            H(true);
                            if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                            elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                P(workspace.Monster.Boss:FindFirstChild("Elite Skeleton [Lv. 3100]").HumanoidRootPart);
                            end;
                        end);
                    end);
                end;
            end;
        end;
    elseif L.Selected_Bosses2.Value=="BigMom"then 
    end;
end;
end);
end;
end);

local c=k:AddTab("Dungeons");

local U=k:AddTab("Settings");
local K={"Easy","Normal"};
U:AddLabel("Dungeons Difficulty",true);
U:AddDropdown("Dungeons_Difficulty",{Text="Select Difficulty",Default=1,Values=K,Multi=false});
U:AddLabel("Cyborg Heal",true);
U:AddSlider("Cyborg_Heal_At",{Text="Cyborg Heal At",Default=50,Min=0,Max=100,Rounding=0,Suffix="%"});
U:AddToggle("Cyborg_Heal_Enabled",{Text="Cyborg Heal",Default=true});
c:AddLabel("Auto Farm Dungeons",true);
local r=c:AddLabel("Enemies Left : 24",false);
local q=c:AddLabel("Earned Gems : 3",false);
i:WaitForChild("PlayerStats");
i:WaitForChild("PlayerStats"):WaitForChild("Gem");
local S=i.PlayerStats.Gem.Value;
task.spawn(function()
    while true do wait();
        local as=#game:GetService("Workspace").MOB:GetChildren();
        r:ChangeText(("Enemies Left : %s"):format(tonumber(as)));
        q:ChangeText(("Earned Gems : %s"):format(tonumber(i.PlayerStats.Gem.Value-S)));
    end;
end);

c:AddLabel("?? Required : ShadowShadow ??",false);
c:AddToggle("Auto_Farm_Dungeons",{Text="Auto Farm Dungeons [PATCHED]"});
c:AddToggle("Auto_Farm_Dungeons_ATL",{Text="Quick Leaves [Instant]",Default=true});
_G.Safe=true;
i=i;
task.spawn(function()
    repeat wait();
    until L.Auto_Farm_Dungeons_ATL.Value;
    while true do wait();
        if L.Auto_Farm_Dungeons_ATL.Value then 
            task.spawn(function()
                pcall(function()
                    if i.PlayerGui:FindFirstChild("GoldenArena GUI").Rise.Visible then 
                        game:GetService('TeleportService'):Teleport(4520749081);
                    end;
                end);
            end);
        end;
    end;
end);

local g={"Skill Z","Skill X","Skill C","Skill V","Skill F","Skill E","Skill B"};
local d=0;
local F=function(a)
    if tick()>=d then 
        d=tick()+0.1;
        for km=1,100 do 
            task.spawn(function()
                pcall(function()
                    if i.Backpack:FindFirstChild("ShadowShadow")then 
                        i.Character.Humanoid:EquipTool(i.Backpack.ShadowShadow);
                    else i.Character.ShadowShadow.Z:InvokeServer(a);
                    end;
                end);
            end);
        end;
    end;
end;

task.spawn(function()
    while true do task.wait();
        pcall(function()
            if L.Auto_Farm_Dungeons.Value and game.PlaceId==5931540094 then 
                for a,uf in pairs(workspace.Effects:GetChildren())do 
                    game.Debris:AddItem(uf,0);
                end;
            end;
        end);
    end;
end);

task.spawn(function()
    while true do task.wait();
    pcall(function()
        if L.Auto_Farm_Dungeons.Value and game.PlaceId==5931540094 then 
            local a=game.Players.LocalPlayer.Character.Humanoid.FloorMaterial==Enum.Material.Air;
            if a==false then 
                F(workspace:FindFirstChild("SpawnPoint5").CFrame);
            end;
        end;
    end);
end;
end);

task.spawn(function()
    repeat wait();
    until L.Auto_Farm_Dungeons.Value;while true do task.wait();
        if L.Auto_Farm_Dungeons.Value then 
        end;
    end;
end);

local fy=V:AddTab("Settings");
getgenv().Tools={};
pcall(function()for a,cL in pairs(i.Backpack:GetChildren())do 
    if cL:IsA("Tool")and not table.find(getgenv().Tools,cL.Name)then 
        table.insert(getgenv().Tools,cL.Name);
    end;
end;

for a,uv in pairs(i.Character:GetChildren())do 
    if uv:IsA("Tool")and not table.find(getgenv().Tools,uv.Name)then 
        table.insert(getgenv().Tools,uv.Name);
    end;
end;
end);

fy:AddDropdown("Selected_Weapons",{Text="Select Combat / Weapons",Values=getgenv().Tools,Multi=false});
task.spawn(function()
    while true do wait(1);
        pcall(function()
            for a in pairs(getgenv().Tools)do 
                getgenv().Tools[a]=nil;
            end;
            for a,wY in pairs(i.Backpack:GetChildren())do 
                if wY:IsA("Tool")and not table.find(getgenv().Tools,wY.Name)then 
                    table.insert(getgenv().Tools,wY.Name);
                end;
            end;
            for a,X6 in pairs(i.Character:GetChildren())do 
                if X6:IsA("Tool")and not table.find(getgenv().Tools,X6.Name)then 
                    table.insert(getgenv().Tools,X6.Name);
                end;
            end;
            L.Selected_Weapons.Values=getgenv().Tools;
            L.Selected_Weapons:SetValues();
        end);
    end;
end);

fy:AddSlider("Auto_Farm_Modes",{Text="Auto Farm Modes",Default=1,Min=1,Max=3,Rounding=0});

fy:AddSlider("Auto_Farm_Distance",{Text="Auto Farm Distance",Default=6,Min=-30,Max=30,Rounding=0});

local ey={"Skill Z","Skill X","Skill C","Skill V","Skill F","Skill E","Skill B"};

fy:AddDropdown("Selected_Skill",{Text="Select Skill",Values=ey,Multi=true});

local Jy={"Defense","Melee","Sword","Power Fruit"};local iy=b:AddTab("LocalPlayer");

iy:AddDropdown("Selected_Stats",{Text="Select Stats",Values=Jy,Multi=true});

iy:AddToggle("Auto_Stats",{Text="Auto Stats"});

local Ay=b:AddTab("Abilities");

Ay:AddToggle("Buso_Haki",{Text="Buso Haki"});

Ay:AddToggle("Inf_Geppo",{Text="Inf Geppo"});

Ay:AddToggle("Bring_Fruits",{Text="Bring Fruits"});

local ay=O:AddTab("Unlock Gamepass");

ay:AddToggle("Unlock_Coffin_Boat",{Text="Unlock Coffin Boat"});

ay:AddToggle("Unlock_Fruit_Position",{Text="Unlock Fruit Position"});

task.spawn(function()
    i.PlayerGui.ChildAdded:connect(function(a)
        if a.Name=="BuyShips"then 
            a.Dialogue.CoffinBoat.MouseButton1Click:connect(function()
                local OD=nil;
                local SD=math.huge;
                for uM,bM in pairs(game:GetService("Workspace").ShipSpawnPoints:GetChildren())do 
                    if bM and bM:FindFirstChildOfClass("Part")then 
                        local Dv=(bM:FindFirstChildOfClass("Part").Position-i.Character:WaitForChild("HumanoidRootPart").Position).magnitude;
                        if Dv<SD then 
                            OD=bM;
                            SD=Dv;
                        end;
                    end;
                end;
                if L.Unlock_Coffin_Boat.Value then 
                    game:GetService("ReplicatedStorage").Remotes.Events.Ship:FireServer("CoffinBoat",tostring(OD));
                end;
            end);
        end;
    end);
end);

local Ly=workspace.AllspawnDF;

getgenv().FindDF=function()
    local a,XB,PB=pairs(Ly:GetDescendants());
    while true do 
        local Sp,wp=a(XB,PB);
        if Sp then else break;
        end;
        PB=Sp;
        if wp:IsA("BasePart")then 
            if wp.Name=="Handle"then return wp;
            end;
        end;
    end;
end;

task.spawn(function()
    while true do wait(0.3);
        pcall(function()
            local a=i.PlayerGui.Stats.TextLabel;
            local fH=FindDF();
            if L.Unlock_Fruit_Position.Value and fH then 
                local VW;
                if not a.Visible then 
                    a.Visible=true;
                end;
                VW=math.floor((i.Character.HumanoidRootPart.Position-fH.Position).Magnitude);
                if i.PlayerStats.Language.Value=="TH"then 
                    a.Text="\224\184\156\224\184\165\224\185\132\224\184\161\224\185\137\224\184\163\224\184\176\224\184\162\224\184\176: "..VW.." \224\185\128\224\184\161\224\184\149\224\184\163";
                else a.Text="Fruit: "..VW.."m away.";
                end;
            else if a.Visible then a.Visible=false;
            end;
        end;
    end);
end;
end);

local function hy()
    local a=Instance.new("Tool",i.Backpack);
    a.Name="LegacyPose";
    a.TextureId="rbxassetid://6886064327";
    local PL=Instance.new("MeshPart",a);
    PL.Name="Handle";PL.MeshId="rbxassetid://6867982510";
end;

ay:AddButton("Unlock Legacy Pose",hy);
task.spawn(function()
    while true do wait(1);
        pcall(function()
            local a;for kv,Jv in pairs(i.Backpack:GetChildren())do 
                if Jv.Name=="LegacyPose"and not Jv:FindFirstChild("DevilFruit")then 
                    a=Jv;
                end;
            end;
            for gf,Of in pairs(i.Character:GetChildren())do 
                if Of.Name=="LegacyPose"and not Of:FindFirstChild("DevilFruit")then 
                    a=Of;
                end;
            end;
            if a~=nil then 
                local pu=i;
                local Tu=pu.Character;
                local Au=nil;
                local Xu=Tu:WaitForChild("HumanoidRootPart");
                local Eu=Tu:WaitForChild("Humanoid");
                local Iu=game:GetService("RunService");
                if not a:FindFirstChild("DevilFruit")then 
                    local qp=Instance.new("IntValue",a);
                    qp.Name="DevilFruit";
                    a.Equipped:Connect(function()Au=true;
                        local gd=nil;
                        local Ud=nil;
                        while true do 
                            local Zq=workspace.Areas:FindFirstChild("LegacyIslandArea");
                            if Zq then 
                                if not gd then gd=game.ReplicatedStorage.Chest.Etc.Arrow:Clone();
                                    gd.Parent=workspace.Effects;
                                end;
                                gd.CFrame=CFrame.new(Xu.Position,Xu.Position+(Zq.Position-Xu.Position).Unit*Vector3.new(1,0,1))*CFrame.new(0,0,-3);
                                gd.Transparency=math.abs(math.sin(tick()*1))*0.5;
                            end;
                            local mq=workspace:FindFirstChild("GhostMonster");
                            if mq then local Cq=mq:FindFirstChild("Ghost Ship");
                                if Cq then 
                                    if not Ud then 
                                    Ud=game.ReplicatedStorage.Chest.Etc.Arrow:Clone();
                                    Ud.Color=Color3.fromRGB(148,190,129);
                                    Ud.Parent=workspace.Effects;
                                end;
                                Ud.CFrame=CFrame.new(Xu.Position,Xu.Position+(Cq.Hitbox.Position-Xu.Position).Unit*Vector3.new(1,0,1))*CFrame.new(0,0,-3);
                                Ud.Transparency=math.abs(math.sin(tick()*1))*0.5;
                            end;
                        end;
                        if Eu.Health<=0 then 
                            break;
                        end;
                        if not Au then 
                            break;
                        end;
                        Iu.Heartbeat:Wait();
                    end;
                    if gd then 
                        gd:Destroy();
                    end;
                    if Ud then 
                        Ud:Destroy();
                    end;
                end);
                a.Unequipped:Connect(function()Au=nil;
                end);
            end;
        end;
    end);
end;
end);
repeat wait();
until i:FindFirstChild("PlayerStats");
repeat wait();
until i:FindFirstChild("PlayerStats"):FindFirstChild("lvl");
repeat wait();
until i:FindFirstChild("PlayerStats"):FindFirstChild("beli");
repeat wait();
until i:FindFirstChild("PlayerStats"):FindFirstChild("Gem");
local ty=y:AddTab("Limit");local ly=y:AddTab("Settings");
ly:AddInput("Level_Limit_At",{Text="Level Limit At",Placeholder="Enter your number here."});
ly:AddInput("Beli_Limit_At",{Text="Beli Limit At",Placeholder="Enter your number here."});
ly:AddInput("Gems_Limit_At",{Text="Gems Limit At",Placeholder="Enter your number here."});
ty:AddLabel("Level Limit",true);ty:AddToggle("Level_Limit",{Text="Level Limit"});
ty:AddLabel("Beli Limit",true);ty:AddToggle("Beli_Limit",{Text="Beli Limit"});
ty:AddLabel("Gems Limit",true);ty:AddToggle("Gems_Limit",{Text="Gems Limit"});
task.spawn(function()
    while true do wait();
    pcall(function()
        if L.Level_Limit.Value then 
            if tonumber(i:FindFirstChild("PlayerStats"):FindFirstChild("lvl").Value)>=tonumber(L.Level_Limit_At.Value)then
                game:Shutdown();
            end;
        end;
        if L.Beli_Limit.Value then 
            if tonumber(i:FindFirstChild("PlayerStats"):FindFirstChild("beli").Value)>=tonumber(L.Beli_Limit_At.Value)then 
                game:Shutdown();
            end;
        end;
        if L.Gems_Limit.Value then 
            if tonumber(i:FindFirstChild("PlayerStats"):FindFirstChild("Gem").Value)>=tonumber(L.Gems_Limit_At.Value)then 
                game:Shutdown();
            end;
        end;
    end);
end;
end);

local uy=p:AddLeftTabbox();
local sy={};
local Ny=uy:AddTab("Players");
for a,w4 in pairs(game:GetService("Players"):GetChildren())do 
    if w4.Name~=i.Name then table.insert(sy,w4.Name);
    end;
end;

Ny:AddLabel("Select Players",true);

Ny:AddDropdown("Selected_Players",{Text="Select Players",Values=sy,Multi=false});
game:GetService("Players").PlayerAdded:Connect(function(a)table.insert(sy,tostring(a.Name));
    L.Selected_Players.Values=sy;L.Selected_Players:SetValues();
end);
game:GetService("Players").PlayerRemoving:Connect(function(a)
    local ce=table.find(sy,tostring(a.Name));
    if ce then table.remove(sy,ce);
    end;
    L.Selected_Players.Values=sy;
    L.Selected_Players:SetValues();
end);

Ny:AddLabel("Main Stuff",true);
Ny:AddToggle("Auto_Farm_Players",{Text="Auto Farm Players"});
task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Players.Value then 
            for a,C1 in next,game:GetService('Players'):GetPlayers()do 
                if C1.Name~=game:GetService('Players').LocalPlayer.Name and C1.Character and C1.Character:FindFirstChild("HumanoidRootPart")and C1.Character:FindFirstChildOfClass("Humanoid")and C1.Character:FindFirstChildOfClass("Humanoid").Health>0 and C1.Name==L.Selected_Players.Value then 
                    local FQ=C1:FindFirstChildOfClass("Humanoid");
                    pcall(function()
                        repeat wait();
                            task.spawn(function()
                                pcall(function()
                                    i.Character.HumanoidRootPart.CFrame=C1.Character.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                    H(true);
                                    if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                        i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                    elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                        i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                        P(C1.Character.HumanoidRootPart);
                                    end;
                                end);
                            end);
                        until not C1 or not C1.Parent or not C1:FindFirstChild("HumanoidRootPart")or not FQ or FQ.Health<=0 or not L.Auto_Farm_Players.Value;
                        wait();
                    end);
                end;
            end;
        end;
    end;
end);

Ny:AddLabel("Miscellaneous",true);
pcall(function()
    getgenv().ESP=loadstring(game:HttpGet("https://androssy.net/TrashXenon/ESP.lua"))();
end);

Ny:AddToggle("ESP_Players",{Text="ESP Players"}):OnChanged(function(a)getgenv().ESP:Toggle(a);
end);
Ny:AddToggle("Spectate_Players",{Text="Spectate"}):OnChanged(function(a)
    if not a then 
        pcall(function()game:GetService("Workspace").Camera.CameraSubject=i.Character;
        end);
    end;
end);

Ny:AddButton("Teleport",function()
    i.Character.HumanoidRootPart.CFrame=game.Players:FindFirstChild(tostring(L.Selected_Players.Value)).Character.HumanoidRootPart.CFrame;
end);

task.spawn(function()
    while true do wait();
        if L.Spectate_Players.Value then 
            pcall(function()
                game:GetService("Workspace").Camera.CameraSubject=game.Players:FindFirstChild(tostring(L.Selected_Players.Value)).Character;
            end);
        end;
    end;
end);

local Yy=p:AddLeftTabbox();
local py=Yy:AddTab("Bounty");
py:AddToggle("Auto_Farm_Bounty",{Text="Auto Farm Bounty"});
py:AddToggle("Auto_Farm_Bounty_Hop",{Text="Auto Farm Bounty Hop"});
getgenv().count=0;
getgenv().count2=0;
getgenv().lastguy="";
task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Bounty.Value then 
            for a,aq in pairs(game.Players:GetPlayers())do 
                if aq.Name~=i.Name and aq.Name~=getgenv().lastguy and aq:FindFirstChild("PvpOffTime")and aq:FindFirstChild("PvpOffTime").Value==0 and aq:FindFirstChild("PlayerStats")and aq:FindFirstChild("PlayerStats").PVP then 
                    pcall(function()
                        repeat game:GetService("RunService").Heartbeat:Wait();
                            getgenv().lastguy=aq.Name;
                            if i.Character:FindFirstChild("LowerTorso")then 
                                if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)or i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                    if game.PlaceId==4520749081 then 
                                        i.Character.HumanoidRootPart.CFrame=CFrame.new(2211,51,-1617);
                                    else i.Character.HumanoidRootPart.CFrame=CFrame.new(30200,354,93566);
                                    end;
                                    wait(0.5);
                                    i.Character:FindFirstChild("LowerTorso"):Remove();
                                    wait(0.5);
                                end;
                            else getgenv().count=getgenv().count+1;
                                task.spawn(function()
                                    pcall(function()
                                        i.Character.HumanoidRootPart.CFrame=aq.Character.HumanoidRootPart.CFrame*CFrame.new(1,0,-4.5);
                                        i.Character.HumanoidRootPart.CFrame=i.Character.HumanoidRootPart.CFrame*CFrame.Angles(0,math.rad(180),0);
                                        if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                            i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                        end;
                                        if i.Character:FindFirstChildOfClass("Tool")then 
                                            i.Character:FindFirstChildOfClass("Tool"):Activate();
                                            P(aq.Character.HumanoidRootPart);
                                        end;
                                    end);
                                end);
                            end;
                        until not aq or not aq.Character or aq.Character.Humanoid.Health==0 or getgenv().count>=2500 or i.PlayerGui:FindFirstChild("Stats"):FindFirstChild("SafeZone").Visible==true and not i.Character:FindFirstChild("LowerTorso")and i.Danger.Value=="Danger"or not L.Auto_Farm_Bounty.Value;
                        i.PlayerGui:FindFirstChild("Stats"):FindFirstChild("SafeZone").Visible=false;
                        print(getgenv().count);
                        getgenv().count=0;
                        getgenv().count2=getgenv().count2+1;
                        if L.Auto_Farm_Bounty.Value_Hop and getgenv().count2>=15 and i.Danger.Value=="Danger"then 
                            getgenv().Teleport();
                        end;
                    end);
                    wait(1);
                end;
            end;
        end;
    end;
end);
local xy=p:AddLeftTabbox();
local Ty={"WolfWolf","BombBomb","BarrierBarrier","DarkDark","DragonDragon","FlameFlame","GiraffeGiraffe","GravityGravity","GumGum","HumanHuman","IceIce","LeopardLeopard","LightLight","LoveLove","MagmaMagma","OpOp","PawPaw","PhoenixPhoenix","QuakeQuake","RumbleRumble","SandSand","ShadowShadow","SnowSnow","StringString","VenomVenom","BuddhaBuddha","SpinoSpino","AlloAllo","DoughDough","BrachioBrachio","GasGas","SpinSpin","SpiritSpirit","SpikeSpike","SmokeSmoke","MammothMammoth"};
local ny=xy:AddTab("Fruit Sniper");
ny:AddLabel("Select Fruits",true);
ny:AddDropdown("Selected_Fruits",{Text="Select Fruits",Values=Ty,Multi=true});
ny:AddLabel("Main Stuff",true);
ny:AddToggle("Auto_Snipe_Fruits",{Text="Auto Snipe Fruits"});
task.spawn(function()
    while true do wait();
    pcall(function()
        if L.Auto_Snipe_Fruits.Value then 
            if L.Selected_Fruits.Value[tostring(i.PlayerStats.DFName.Value)]==nil then 
                for a,o7 in pairs(L.Selected_Fruits.Value)do 
                    if L.Selected_Fruits.Value[tostring(i.PlayerStats.DFName.Value)]==nil then 
                        print(a,o7);
                        game.ReplicatedStorage.Remotes.Functions.dfbeli:InvokeServer(tostring(a),true);
                    end;
                end;
            end;
        end;
    end);
end;
end);

local Wy=xy:AddTab("Random DF");
local ky={"Beli","Gem"};
Wy:AddLabel("Select Method",true);
Wy:AddDropdown("Selected_Method",{Text="Select Method",Values=ky,Multi=false});
Wy:AddLabel("Main Stuff",true);
Wy:AddToggle("Auto_Random_DF",{Text="Auto Random DF"});
task.spawn(function()while true do wait();
    if L.Auto_Random_DF.Value then 
        pcall(function()
            i.PlayerStats.RanFruitTime.Value=5;
            i.Character.HumanoidRootPart.CFrame=workspace.AllNPC.ARandomFruit.HumanoidRootPart.CFrame*CFrame.new(0,0,-7);
            game.ReplicatedStorage.Remotes.Functions.CheckQuest:InvokeServer(workspace.AllNPC.ARandomFruit);
            local a=i.PlayerGui.ARandomFruit.Dialogue[L.Selected_Method.Value];
            a:ClearAllChildren();
            a.BackgroundTransparency=1;
            a.ImageTransparency=1;
            a.Position=UDim2.new(0,-700,0,-700);
            a.Size=UDim2.new(100,100,100,100);
            wait();
            game:GetService('VirtualUser'):CaptureController();
            game:GetService('VirtualUser'):ClickButton1(Vector2.new(100,100),CFrame.new(Vector3.new(0,0,0)));
        end);
    end;
end;
end);

local Vy=p:AddLeftTabbox();
local by=Vy:AddTab("World Teleport");
local Oy=function()repeat wait();
    task.spawn(function()
        pcall(function()
            i.Character.HumanoidRootPart.CFrame=workspace.AllNPC:FindFirstChild("Elite Pirate").HumanoidRootPart.CFrame;
            game:GetService("ReplicatedStorage").Remotes.Functions.CheckQuest:InvokeServer(workspace.AllNPC:FindFirstChild("Elite Pirate"));
        end);
    end);
until game.PlaceId==1;
end;

by:AddLabel("World 1 | 4520749081",true);
by:AddButton("Teleport Old World",Oy);
by:AddButton("Teleport New World",Oy);
local Xy=p:AddRightTabbox();
local yy=Xy:AddTab("Shop Teleport");
local Cy={};
for a,CB in pairs(workspace.AllNPC:GetChildren())do 
    if CB and CB:FindFirstChild("Setting")and CB:FindFirstChild("Setting"):FindFirstChild("NameWeapon")and CB:FindFirstChild("Setting"):FindFirstChild("Price")then 
        if not table.find(Cy,tostring(CB.Setting.NameWeapon.Value.." : $"..CB.Setting.Price.Value))then 
            table.insert(Cy,tostring(CB.Setting.NameWeapon.Value.." : $"..CB.Setting.Price.Value));
        end;
    end;
end;

yy:AddDropdown("Selected_Shop",{Text="Select NPCS",Values=Cy,Multi=false});
yy:AddButton("Teleport",function()
    for a,Hw in pairs(workspace.AllNPC:GetChildren())do 
        if Hw and Hw:FindFirstChild("Setting")and Hw:FindFirstChild("Setting"):FindFirstChild("NameWeapon")and Hw:FindFirstChild("Setting"):FindFirstChild("Price")and tostring(Hw.Setting.NameWeapon.Value.." : $"..Hw.Setting.Price.Value)==tostring(L.Selected_Shop.Value)then 
            i.Character.HumanoidRootPart.CFrame=Hw.PrimaryPart.CFrame*CFrame.new(0,0,-5);
        end;
    end;
end);

local Qy=p:AddRightTabbox();
local Ry=Qy:AddTab("Areas Teleport");
local zy={};
for a,Sj in pairs(workspace.Areas:GetChildren())do 
    if not table.find(zy,Sj.Name)then 
        table.insert(zy,Sj.Name);
        Ry:AddButton(tostring(Sj.Name),function()
            i.Character.HumanoidRootPart.CFrame=Sj.CFrame*CFrame.new(0,500,0);
        end);
    end;
end;
local My=u:AddTab("Settings");
local vy=My:AddLeftGroupbox("Menu");
local my=My:AddRightGroupbox("Config");
local oy=My:AddLeftGroupbox("Auto-Load");
local Gy=My:AddRightGroupbox("Misc");
vy:AddLabel("Background Color"):AddColorPicker("SettingsMenuBackgroundColor",{Default=A.BackgroundColor});
vy:AddLabel("Main Color"):AddColorPicker("SettingsMenuMainColor",{Default=A.MainColor});
vy:AddLabel("Accent Color"):AddColorPicker("SettingsMenuAccentColor",{Default=A.AccentColor});
vy:AddLabel("Inline Color"):AddColorPicker("SettingsMenuInlineColor",{Default=A.InlineColor});
vy:AddLabel("Outline Color"):AddColorPicker("SettingsMenuOutlineColor",{Default=A.OutlineColor});
vy:AddLabel("Font Color"):AddColorPicker("SettingsMenuFontColor",{Default=A.FontColor});
vy:AddButton("Default Theme",SetDefault);
vy:AddToggle("SettingsMenuKeybinds",{Text="Show Keybinds Menu"}):OnChanged(function(a)
    A.KeybindFrame.Visible=a;
end);
vy:AddToggle("SettingsMenuWatermark",{Text="Show Watermark",Default=true}):OnChanged(function(a)
    A:SetWatermarkVisibility(a);
end);

vy:AddButton("Unload",function()
    A:Unload();
end);

my:AddInput("SettingsConfigName",{Text="Config Name",Default="",Placeholder="Name"});
my:AddButton("Create Config",function()
    CreateConfig(L.SettingsConfigName.Value);
end);
my:AddDropdown("SettingsConfigConfigs",{Text="Configs",Default=1,Values=GetConfigNames()});
my:AddButton("Load Config",function()
    s.Load.AutoLoad.LastUsedConfig=L.SettingsConfigConfigs.Value;
    LoadConfig(GetConfigByName(L.SettingsConfigConfigs.Value));
    A:Notify(("Config \"%s\" Has Been Loaded."):format(L.SettingsConfigConfigs.Value));
end);
my:AddButton("Save Config",function()
    SaveConfig(L.SettingsConfigConfigs.Value);
end);
my:AddButton("Delete Config",function()
    DeleteConfig(L.SettingsConfigConfigs.Value,true);
end);
my:AddInput("SettingsConfigData",{Text="Config Data",Default="",Placeholder="Data"});
my:AddButton("Export Data",ExportData);
my:AddButton("Import Data",ImportData);
oy:AddToggle("SettingsAutoLoadEnabled",{Text="Enabled",Default=true}):OnChanged(function(a)
    s.Load.AutoLoad.Enabled=a;
end);

oy:AddToggle("SettingsAutoLoadRage",{Text="Rage Settings"}):OnChanged(function(a)
    s.Load.AutoLoad.RageSettings=a;
end);

oy:AddToggle("SettingsAutoLoadSilent",{Text="Silent Load"}):OnChanged(function(a)
    s.Load.AutoLoad.SilentLoad=a;
end);

oy:AddDropdown("SettingsAutoLoadType",{Text="Type",Default=2,Values={"Last Used Config","Last Config","Custom Config"}}):OnChanged(function(a)
    s.Load.AutoLoad.AutoLoadType=a;
end);

oy:AddDropdown("SettingsAutoLoadConfig",{Text="Custom Config",Default=1,Values=GetConfigNames()}):OnChanged(function(a)
    s.Load.AutoLoad.CustomConfig=a;
end);

Gy:AddToggle("SettingsMiscNotifications",{Text="Show Notifications",Default=true}):OnChanged(function(a)
    A.NotificationArea.Visible=a;
end);
Gy:AddButton("Reset All Settings",ResetSettings);
SetDefault();
L.SettingsMenuBackgroundColor:OnChanged(UpdateTheme);
L.SettingsMenuMainColor:OnChanged(UpdateTheme);
L.SettingsMenuAccentColor:OnChanged(UpdateTheme);
L.SettingsMenuInlineColor:OnChanged(UpdateTheme);
L.SettingsMenuOutlineColor:OnChanged(UpdateTheme);
L.SettingsMenuFontColor:OnChanged(UpdateTheme);
N:ShowTab();
A.SaveManager:Load();
task.spawn(function()
    while(task.wait(1)and A and A.SaveManager)do 
        A.SaveManager:SaveFile();
    end;
end);

_G.Current_Time="N/A";
A:SetWatermark(("Xenon Hub Premium Scripts | %s"):format(_G.Current_Time));
task.spawn(function()
    while true do wait();
        pcall(function()
            local a=math.floor(workspace.DistributedGameTime);
            local bR=math.floor(workspace.DistributedGameTime/60);
            local rR=math.floor(workspace.DistributedGameTime/60/60);
            local a=a-(bR*60);local bR=bR-(rR*60);
            if rR<1 then 
                if bR<1 then 
                    _G.Current_Time=a.." Second(s)";
                else _G.Current_Time=bR.." Minute(s), "..a.." Second(s)";
                end;
            else _G.Current_Time=rR.." Hour(s), "..bR.." Minute(s), "..a.." Second(s)";
            end;
            A:SetWatermark(("Xenon Hub Premium Scripts | %s"):format(_G.Current_Time));
        end);
    end;
end);

A:Notify("User Interface Finished Loading.");
local Ey=math.floor(((tick()-s.Tick)*1000)*10)/10;
A:Notify(("Loading Time : %sms."):format(Ey));
local Dy=game.PlaceId;
local Iy={};
local wy="";
local jy=os.date("!*t").hour;
local Py=false;
function TPReturner()
    local a;
    if wy==""then 
        a=game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/'..Dy..'/servers/Public?sortOrder=Desc&limit=100'));
    else a=game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/'..Dy..'/servers/Public?sortOrder=Desc&limit=100&cursor='..wy));
    end;
    local Xs="";
    if a.nextPageCursor and a.nextPageCursor~="null"and a.nextPageCursor~=nil then wy=a.nextPageCursor;
    end;
    local Os=0;
    for cW,wW in pairs(a.data)do 
        local TW=true;Xs=tostring(wW.id);
        if tonumber(wW.maxPlayers)>tonumber(wW.playing)then 
            for uO,ZO in pairs(Iy)do if Os~=0 then if Xs==tostring(ZO)then 
                TW=false;
            end;
        else if tonumber(jy)~=tonumber(ZO)then 
            local om=pcall(function()Iy={};
            table.insert(Iy,jy);
        end);
    end;
end;
Os=Os+1;
end;
if TW==true then 
    table.insert(Iy,Xs);
    wait();
    pcall(function()
        wait();
        game:GetService("TeleportService"):TeleportToPlaceInstance(Dy,Xs,i);
    end);
    wait(5);
end;
end;
end;
end;
if getgenv().Teleport==nil then 
    getgenv().Teleport=function()while true do task.wait(1);
        pcall(function()TPReturner();
            if wy~=""then TPReturner();
            end;
        end);
    end;
end;
end;
task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Dungeons.Value or L.Auto_Farm_Level.Value or L.Auto_Farm_Bosses.Value or L.Auto_Farm_Bosses_2.Value or L.Auto_Farm_Santa.Value or L.Auto_Farm_Kris_Kringle.Value or L.Auto_Farm_Ms_Mother.Value or L.Auto_Farm_Enma.Value or L.Auto_Farm_Saber.Value then 
            _G.Aimbot=true;
        else _G.Aimbot=false;
        end;
    end;
end);
task.spawn(function()
    local a;
    a=hookmetamethod(game,"__namecall",newcclosure(function(...)
        local SW={...};
        local cW=getnamecallmethod();
        if cW=="InvokeServer"or cW=="FireServer"then 
            if _G.Aimbot then 
                if tostring(SW[1])=="Z"or tostring(SW[1])=="X"or tostring(SW[1])=="C"or tostring(SW[1])=="V"or tostring(SW[1])=="F"or tostring(SW[1])=="E"or tostring(SW[1])=="B"then 
                    for hi,qi in pairs(SW)do 
                        if getgenv().Mob~=nil then 
                            if typeof(qi)=="CFrame"then 
                                SW[hi]=getgenv().Mob.CFrame;elseif typeof(qi)=="Vector3"then 
                                    SW[hi]=getgenv().Mob.Position;
                                end;
                            end;
                        end;
                    end;
                end;
                return a(unpack(SW));
            end;
            return a(...);
        end));
    end);
    
    local J=game:GetService("Players");
    local i=J.LocalPlayer;
    local By=game.ReplicatedStorage.Remotes.Functions.CheckQuest;
    local Hy=require(game.ReplicatedStorage.Modules.QuestManager);
    local cy={[3350]="Ice Crystal",[3375]="Magma Crystal"};local Uy="Hell Sword";
    local function Ky()
        if getrenv()._G.RenderDist1~=100000 then 
            getrenv()._G.RenderDist1=100000;
        end;
        local a=nil;
        local W5=false;
        local H5=nil;
        local p5={};
        for QH,ZH in pairs(game:GetService("Workspace").AllNPC:GetChildren())do 
            if ZH.Name:match("QuestLvl")then 
                local IJ=string.match(tostring(ZH.Name),"%d+");
                if L.Auto_Farm_New_World.Value and game.Players.LocalPlayer.PlayerStats.lvl.Value>=2250 and game.PlaceId~=6381829480 then 
                    game:GetService("TeleportService"):Teleport(6381829480);end;if tonumber(IJ)<=tonumber(i.PlayerStats.lvl.Value)then 
                        table.insert(p5,IJ);
                    end;
                end;
            end;
            a=math.max(unpack(p5));
            if a==3350 or a==3375 then 
                W5=true;
                H5=cy[a];
            end;
            return'QuestLvl'..a,W5,H5;
        end;
        local function Zy()
            local a=nil;
            local l1=false;
            if i.CurrentQuest.Value~=""then 
                a=Hy[i.CurrentQuest.Value].Mob;
                if Hy[i.CurrentQuest.Value].Ammount==1 then 
                    l1=true;
                end;
            end;
            return a,l1;
        end;
        local function ry(so)
            game:GetService("VirtualInputManager"):SendMouseButtonEvent(so.AbsolutePosition.X+so.AbsoluteSize.X/2,so.AbsolutePosition.Y+50,0,true,so,1);
            game:GetService("VirtualInputManager"):SendMouseButtonEvent(so.AbsolutePosition.X+so.AbsoluteSize.X/2,so.AbsolutePosition.Y+50,0,false,so,1);
        end;
        local function qy()
            for a,H0 in pairs(i.PlayerGui:GetChildren())do 
                if H0:FindFirstChild("Dialogue")then 
                    local tX=H0.Dialogue;
                    if not tX:FindFirstChild("Accept")then 
                        i.Character:BreakJoints();
                    end;
                    task.spawn(function()
                        pcall(function()tX.Accept.BackgroundTransparency=1;
                            tX.Accept.ImageTransparency=1;
                            tX.Accept:ClearAllChildren();
                        end);
                    end);
                    task.spawn(function()
                        pcall(function()
                            tX.Accept.Position=UDim2.new(0,-700,0,-700);
                        end);
                    end);
                    task.spawn(function()
                        pcall(function()
                            tX.Accept.Size=UDim2.new(100,100,100,100);
                        end);
                    end);
                end;
            end;
            wait();
            game:GetService('VirtualUser'):CaptureController();
            game:GetService('VirtualUser'):ClickButton1(Vector2.new(100,100),CFrame.new(Vector3.new(0,0,0)));
        end;
        
        local function Sy()
            local a,B1,b1=Ky();
            if B1 and not i.Backpack:FindFirstChild(b1)and not i.Character:FindFirstChild(b1)then 
                a="QuestLvl3325";
            end;
            if workspace.AllNPC:FindFirstChild(a)then 
                i.Character.HumanoidRootPart.CFrame=workspace.AllNPC:FindFirstChild(a):FindFirstChild("HumanoidRootPart").CFrame*CFrame.new(0,-8,0);By:InvokeServer(workspace.AllNPC:FindFirstChild(a));
                qy();
            end;
        end;
        task.spawn(function()
            while true do task.wait();
                if L.Auto_Farm_Level.Value then 
                    local a,kk=pcall(function()
                        if i.CurrentQuest.Value==""then 
                            Sy();
                        else local yv,Ev=Zy();
                            if Ev then 
                                Folder=workspace.Monster.Boss;
                            else Folder=workspace.Monster.Mon;
                            end;
                            for fd,Ad in pairs(Folder:GetChildren())do 
                                if Ad.Name==yv and Ad:FindFirstChild("HumanoidRootPart")and Ad:FindFirstChild("Humanoid")and Ad:FindFirstChild("Humanoid").Health>0 and Ad:FindFirstChild("Head")and Ad:FindFirstChild("Head").Transparency~=1 then 
                                    repeat task.wait();
                                        task.spawn(function()
                                            pcall(function()
                                                i.Character.HumanoidRootPart.CFrame=Ad.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                                H(true);
                                                if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                                    i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                                elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                                    i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                                    P(Ad.HumanoidRootPart);
                                                end;
                                            end);
                                        end);
                                    until Ad==nil or not Ad:FindFirstChild("HumanoidRootPart")or not Ad:FindFirstChild("Humanoid")or Ad:FindFirstChild("Humanoid").Health==0 or not Ad:FindFirstChild("Head")or Ad:FindFirstChild("Head").Transparency==1 or not L.Auto_Farm_Level.Value;
                                end;
                            end;
                        end;
                    end);
                    if _G.DEBUG then 
                        warn(kk);
                    end;
                end;
            end;
        end);
    getgenv().Tier_Table={
        ["rbxassetid://8704131464"]="Common",
        ["rbxassetid://9170466907"]="Uncommon",
        ["rbxassetid://9170467299"]="Rare",
        ["rbxassetid://9170467728"]="Epic",
        ["rbxassetid://9170468009"]="Legendary"};
        local function gy()
            if game:GetService("Workspace").Island:FindFirstChild("Legacy Island1")then 
                return{true,"1"};
            elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island2")then 
                return{true,"2"};
            elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island3")then 
                return{true,"3"};
            elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island4")then 
                return{true,"4"};
            elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island5")then 
                return{true,"5"};
            else return{false,"nil"};
            end;
        end;
        task.spawn(function()
            repeat wait();
            until L.Auto_Farm_Sea_Beasts.Value;
            while true do 
                if L.Auto_Farm_Sea_Beasts.Value then 
                    if gy()[1]==true then 
                        pcall(function()
                            if game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing")then 
                                if game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing").Humanoid.Health~=0 then 
                                    task.spawn(function()
                                        pcall(function()
                                            i.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing").HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                            H(true);
                                            if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                                i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                            elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                                i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                                P(game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing").HumanoidRootPart);
                                            end;
                                        end);
                                    end);
                                end;
                            else i.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").Island["Legacy Island"..gy()[2]].ChestSpawner.CFrame;
                            end;
                        end);
                    else if L.Auto_Farm_Sea_Beasts_Hop.Value then 
                        allowed_hop=true;
                        for a,LI in pairs(i.Backpack:GetChildren())do 
                            if LI:IsA("Tool")then 
                                if L.Auto_Farm_Sea_Beasts_Until.Value[getgenv().Tier_Table[tostring(LI.TextureId)]]~=nil then 
                                    allowed_hop=false;
                                end;
                            end;
                        end;
                        for a,Zh in pairs(i.Character:GetChildren())do 
                            if Zh:IsA("Tool")then 
                                if L.Auto_Farm_Sea_Beasts_Until.Value[getgenv().Tier_Table[tostring(Zh.TextureId)]]~=nil then 
                                    allowed_hop=false;
                                end;
                            end;
                        end;
                        if allowed_hop then 
                            getgenv().Teleport();
                        else i.Character.HumanoidRootPart.CFrame=getgenv().Old_Pos;
                        end;
                    end;
                end;
            end;
            wait();
        end;
    end);

task.spawn(function()
    repeat wait();
    until L.Auto_Farm_Sea_Beasts.Value;
    while true do if L.Auto_Farm_Sea_Beasts.Value then 
        if gy()[1]==true then pcall(function()if game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing")then 
            if game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing").Humanoid.Health==0 then 
                i.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").Island["Legacy Island"..gy()[2]].ChestSpawner.CFrame*CFrame.new(0,2,-2);
                delay(10,function()
                    pcall(function()
                        if game:GetService("Workspace").Island["Legacy Island"..gy()[2]]~=nil then 
                            game:GetService("Workspace").Island["Legacy Island"..gy()[2]]:Remove();
                        end;
                    end);
                end);
            end;
        else i.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").Island["Legacy Island"..gy()[2]].ChestSpawner.CFrame*CFrame.new(0,2,-2);
        end;
    end);
end;
end;
wait(3);
end;
end);
task.spawn(function()
    repeat wait();
    until L.Auto_Farm_Ghost_Ship.Value;
    while true do wait();
        if L.Auto_Farm_Ghost_Ship.Value then 
            pcall(function()
                local a=workspace:FindFirstChild("GhostMonster");
                if a then local CJ=a:FindFirstChild("Ghost Ship");
                    if CJ then task.spawn(function()
                        pcall(function()
                            i.Character.HumanoidRootPart.CFrame=CJ.Hitbox.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                            H(true);
                            if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                            elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                P(CJ.Hitbox);
                            end;
                        end);
                    end);
                else founded_chest=false;
                    for oM,PM in pairs(game.Workspace:GetChildren())do 
                        if PM.Name:find("Chest")then 
                            founded_chest=true;
                        end;
                    end;
                    if founded_chest then 
                        for Dh,oh in pairs(game.Workspace:GetChildren())do 
                            if oh.Name:find("Chest")then 
                                i.Character.HumanoidRootPart.CFrame=oh.PrimaryPart.CFrame;
                                wait(0.3);
                            end;
                        end;
                    else i.Character.HumanoidRootPart.CFrame=CFrame.new(30200,354,93566);
                    end;
                    if L.Auto_Farm_Ghost_Ship_Hop.Value and founded_chest==false then getgenv().Teleport();
                    end;
                end;
            end;
        end);
    end;
end;
end);
task.spawn(function()
    repeat wait();
    until L.Auto_Farm_Bosses.Value;
    print("Toggled : Auto Farm Bosses");
    while true do wait();
        if L.Auto_Farm_Bosses.Value then 
            pcall(function()n=true;
                for a,GU in pairs(game:GetService("Workspace").Monster.Boss:GetChildren())do 
                    if L.Selected_Bosses.Value[tostring(GU)]~=nil then 
                        n=false;
                    end;
                end;
                for a,Bg in pairs(game:GetService("Workspace").Monster.Boss:GetChildren())do 
                    if L.Selected_Bosses.Value[tostring(Bg)]~=nil then 
                        n=false;
                    end;
                end;
                if n==true then 
                    if L.Auto_Farm_Bosses_Hop.Value then 
                        Teleport();
                    end;
                end;
                for a,SZ in pairs(workspace.Monster.Boss:GetChildren())do 
                    if L.Selected_Bosses.Value[tostring(SZ.Name)]~=nil and SZ:FindFirstChild("HumanoidRootPart")and SZ:FindFirstChildOfClass("Humanoid")and SZ:FindFirstChildOfClass("Humanoid").Health>0 then 
                        local kD=SZ:FindFirstChild("Humanoid");
                        repeat wait();
                            task.spawn(function()
                                pcall(function()
                                    i.Character.HumanoidRootPart.CFrame=SZ.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                    H(true);
                                    if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                        i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                    elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                        P(SZ.HumanoidRootPart);
                                    end;
                                end);
                            end);
                        until SZ==nil or not SZ:FindFirstChild("HumanoidRootPart")or not SZ:FindFirstChild("Humanoid")or SZ:FindFirstChild("Humanoid").Health<=0 or not L.Auto_Farm_Bosses.Value;
                    end;
                end;
            end);
        end;
    end;
end);

task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Santa.Value then
             Bosses="Santa [Lv. 5000]";
             if not workspace.Monster.Boss:FindFirstChild(Bosses)then 
                if L.Auto_Farm_Santa.Value and L.Auto_Farm_Santa_Hop.Value then 
                    getgenv().Teleport();
                end;
            end;
            for a,IM in pairs(workspace.Monster.Boss:GetChildren())do 
                if IM:FindFirstChild("HumanoidRootPart")and IM:FindFirstChildOfClass("Humanoid")and IM:FindFirstChildOfClass("Humanoid").Health>0 and IM.Name==Bosses then 
                    local j7=IM:FindFirstChild("Humanoid");
                    pcall(function()
                        repeat task.wait();
                            task.spawn(function()
                                pcall(function()
                                    i.Character.HumanoidRootPart.CFrame=IM.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                    H(true);
                                    if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                        i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                    elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                        i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                        P(IM.HumanoidRootPart);
                                    end;
                                end);
                            end);
                        until IM==nil or not IM:FindFirstChild("HumanoidRootPart")or not IM:FindFirstChild("Humanoid")or IM:FindFirstChild("Humanoid").Health<=0 or not L.Auto_Farm_Santa.Value;
                    end);
                end;
            end;
        end;
    end;
end);

task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Kris_Kringle.Value then 
            Bosses="Kris Kringle [Lv. 10000]";
            if not workspace.Monster.Boss:FindFirstChild(Bosses)then 
                if L.Auto_Farm_Kris_Kringle.Value and L.Auto_Farm_Kris_Kringle_Hop.Value then 
                    getgenv().Teleport();
                end;
            elseif workspace.Monster.Boss:FindFirstChild(Bosses)and workspace.Monster.Boss:FindFirstChild(Bosses).Humanoid.Health==0 then 
                if L.Auto_Farm_Kris_Kringle.Value and L.Auto_Farm_Kris_Kringle_Hop.Value then 
                    getgenv().Teleport();
                end;
            end;
            for a,Bp in pairs(workspace.Monster.Boss:GetChildren())do 
                if Bp:FindFirstChild("HumanoidRootPart")and Bp:FindFirstChildOfClass("Humanoid")and Bp:FindFirstChildOfClass("Humanoid").Health>0 and Bp.Name==Bosses then 
                    local aI=Bp:FindFirstChild("Humanoid");
                    pcall(function()
                        repeat task.wait();
                            task.spawn(function()
                                pcall(function()
                                    i.Character.HumanoidRootPart.CFrame=Bp.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                    H(true);
                                if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                    i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                    P(Bp.HumanoidRootPart);
                                end;
                            end);
                        end);
                    until Bp==nil or not Bp:FindFirstChild("HumanoidRootPart")or not Bp:FindFirstChild("Humanoid")or Bp:FindFirstChild("Humanoid").Health<=0 or not L.Auto_Farm_Kris_Kringle.Value;
                end);
            end;
        end;
    end;
end;
end);

task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Ms_Mother.Value then 
            Bosses="Ms. Mother [Lv.7500]";
            if not workspace.Monster.Boss:FindFirstChild(Bosses)then 
                if L.Auto_Farm_Ms_Mother.Value and L.Auto_Farm_Ms_Mother_Hop.Value then 
                    getgenv().Teleport();
                end;
            elseif workspace.Monster.Boss:FindFirstChild(Bosses)and workspace.Monster.Boss:FindFirstChild(Bosses).Humanoid.Health==0 then 
                if L.Auto_Farm_Ms_Mother.Value and L.Auto_Farm_Ms_Mother_Hop.Value then 
                    getgenv().Teleport();
                end;
            end;
            for a,s5 in pairs(workspace.Monster.Boss:GetChildren())do 
                if s5:FindFirstChild("HumanoidRootPart")and s5:FindFirstChildOfClass("Humanoid")and s5:FindFirstChildOfClass("Humanoid").Health>0 and s5.Name==Bosses then 
                    local ZO=s5:FindFirstChild("Humanoid");
                    pcall(function()
                        repeat task.wait();
                        task.spawn(function()
                            pcall(function()
                                i.Character.HumanoidRootPart.CFrame=s5.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                H(true);
                                if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                    i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                    i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                    P(s5.HumanoidRootPart);
                                end;
                            end);
                        end);
                    until s5==nil or not s5:FindFirstChild("HumanoidRootPart")or not s5:FindFirstChild("Humanoid")or s5:FindFirstChild("Humanoid").Health<=0 or not L.Auto_Farm_Ms_Mother.Value;
                end);
            end;
        end;
    end;
end;
end);
task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Enma.Value then 
            Bosses="King Samurai [Lv. 3500]";
            if not workspace.Monster.Boss:FindFirstChild(Bosses)then 
                if L.Auto_Farm_Enma.Value and L.Auto_Farm_Enma_Hop.Value then 
                    if L.Hop_Until_Found_Enma.Value then 
                    if not i.Inventory:FindFirstChild("Hell Sword")then 
                        getgenv().Teleport();
                    end;
                else getgenv().Teleport();
                end;
            end;
        end;
        for a,G4 in pairs(workspace.Monster.Boss:GetChildren())do 
            if G4:FindFirstChild("HumanoidRootPart")and G4:FindFirstChildOfClass("Humanoid")and G4:FindFirstChildOfClass("Humanoid").Health>0 and G4.Name==Bosses then 
                local mu=G4:FindFirstChild("Humanoid");
                pcall(function()
                    repeat task.wait();
                        task.spawn(function()
                            pcall(function()
                                i.Character.HumanoidRootPart.CFrame=G4.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                                H(true);
                                if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                    i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                                elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then 
                                    i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                    P(G4.HumanoidRootPart);
                                end;
                            end);
                        end);
                    until G4==nil or not G4:FindFirstChild("HumanoidRootPart")or not G4:FindFirstChild("Humanoid")or G4:FindFirstChild("Humanoid").Health<=0 or not L.Auto_Farm_Enma.Value;
                end);
            end;
        end;
    end;
end;
end);

task.spawn(function()
    while true do wait();
        if L.Auto_Farm_Saber.Value then 
            Bosses="Expert Swordman [Lv. 3000]";
            if not workspace.Monster.Boss:FindFirstChild(Bosses)then 
                if L.Auto_Farm_Saber.Value and L.Auto_Farm_Saber_Hop.Value then 
                    if L.Hop_Until_Found_Saber.Value then if not i.Inventory:FindFirstChild("Saber")then 
                        getgenv().Teleport();
                    end;
                else getgenv().Teleport();
                end;
            end;
        end;
        
        for a,Hp in pairs(workspace.Monster.Boss:GetChildren())do 
            if Hp:FindFirstChild("HumanoidRootPart")and Hp:FindFirstChildOfClass("Humanoid")and Hp:FindFirstChildOfClass("Humanoid").Health>0 and Hp.Name==Bosses then 
                local M0=Hp:FindFirstChild("Humanoid");
                pcall(function()
                    repeat task.wait();
                    task.spawn(function()
                        pcall(function()
                            i.Character.HumanoidRootPart.CFrame=Hp.HumanoidRootPart.CFrame*CFrame.Angles(math.rad(-90),0,0)+Vector3.new(0,L.Auto_Farm_Distance.Value,0);
                            H(true);
                            if i.Backpack:FindFirstChild(L.Selected_Weapons.Value)then 
                                i.Character.Humanoid:EquipTool(i.Backpack:FindFirstChild(L.Selected_Weapons.Value));
                            elseif i.Character:FindFirstChild(L.Selected_Weapons.Value)then i.Character:FindFirstChild(L.Selected_Weapons.Value):Activate();
                                P(Hp.HumanoidRootPart);
                            end;
                        end);
                    end);
                until Hp==nil or not Hp:FindFirstChild("HumanoidRootPart")or not Hp:FindFirstChild("Humanoid")or Hp:FindFirstChild("Humanoid").Health<=0 or not L.Auto_Farm_Saber.Value;
            end);
        end;
    end;
end;
end;
end);

task.spawn(function()
    while true do wait();
        if L.Bring_Fruits.Value then 
            pcall(function()
                for a,hI in pairs(game:GetService("Workspace"):GetChildren())do 
                    if hI:IsA("Tool")then hI.Handle.CFrame=i.Character.HumanoidRootPart.CFrame;
                    end;
                end;
            end);
        end;
    end;
end);

task.spawn(function()
    while true do wait();
        if L.Inf_Geppo.Value then 
            pcall(function()
                for a,VY in next,getgc()do 
                    if typeof(VY)=="function"and getfenv(VY).script==i.Backpack.GeppoNew then 
                        for Zh,ah in next,getupvalues(VY)do 
                            if Zh==7 then 
                                repeat wait();
                                    i.Backpack.GeppoNew.cds.Value=100;
                                    setupvalue(VY,Zh,0);
                                until L.Inf_Geppo.Value==false;
                            end;
                        end;
                    end;
                end;
            end);
        end;
    end;
end);

function getRemote()
    for a,MR in pairs(i.PlayerGui.Stats.Button:GetDescendants())do 
        if MR:IsA("RemoteEvent")then 
            remote=MR;
        end;
    end;
end;

pcall(function()
    getRemote();
end);

task.spawn(function()
    while true do 
        if L.Auto_Stats.Value then 
            pcall(function()
                getRemote();
            end);
            wait(2);
        end;
        wait();
    end;
end);

task.spawn(function()
    while true do wait();
        pcall(function()
            if L.Auto_Stats.Value then 
                if L.Selected_Stats.Value["Defense"]then 
                    remote:FireServer("Defense",1);
                end;
                if L.Selected_Stats.Value["Melee"]then 
                    remote:FireServer("Melee",1);
                end;
                if L.Selected_Stats.Value["Sword"]then 
                    remote:FireServer("Sword",1);
                end;
                if L.Selected_Stats.Value["Power Fruit"]then 
                    remote:FireServer("Devil Fruit",1);
                end;
            end;
        end);
    end;
end);

task.spawn(function()
    while true do wait();
        pcall(function()
            if not workspace.Monster.Boss:FindFirstChild("King Samurai [Lv. 3500]")then 
                o:ChangeText("King Samurai Spawned : ❌");
            else o:ChangeText("King Samurai Spawned : ✅ ");
            end;
            if i.Inventory:FindFirstChild("Hell Sword")then 
                m:ChangeText("Enma Owned : ✅");
            else m:ChangeText("Enma Owned : ❌");
            end;
            if not workspace.Monster.Boss:FindFirstChild("Expert Swordsman [Lv. 3000]")then 
                E:ChangeText("Expert Swordsman Spawned : ❌");
            else E:ChangeText("Expert Swordsman Spawned : ✅ ");
            end;
            if i.Inventory:FindFirstChild("Saber")then 
                G:ChangeText("Saber Owned : ✅");
            else G:ChangeText("Saber Owned : ❌");
            end;
        end);
    end;
end);
setfflag("HumanoidParallelRemoveNoPhysics","False");
setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2","False");
task.spawn(function()
    game:GetService("RunService").Stepped:Connect(function()
        local a=i.Character or i.CharacterAdded:Wait();
        if L.Auto_Farm_Level.Value or L.Auto_Farm_New_World.Value or L.Auto_Farm_Sea_Beasts.Value or L.Auto_Farm_Ghost_Ship.Value or L.Auto_Farm_Enma.Value or L.Auto_Farm_Saber.Value or L.Auto_Farm_Santa.Value or L.Auto_Farm_Kris_Kringle.Value or L.Auto_Farm_Ms_Mother.Value or L.Auto_Farm_Bosses.Value or L.Auto_Farm_Bosses_2.Value or L.Auto_Farm_Players.Value or L.Auto_Random_DF.Value or L.Auto_Farm_Bounty.Value then 
            pcall(function()
                if syn_crypt_encrypt then 
                    a.Humanoid:ChangeState(11);
                else i.Character.Humanoid.Sit=false;
                    if not i.Character.HumanoidRootPart:FindFirstChild("BV")then 
                        local QW=Instance.new("BodyVelocity");
                        QW.Parent=i.Character.HumanoidRootPart;
                        QW.Name="BV";
                        QW.MaxForce=Vector3.new(100000,100000,100000);
                        QW.Velocity=Vector3.new(0,0,0);
                    end;
                end;
            end);
        else if i.Character.HumanoidRootPart:FindFirstChild("BV")then 
            i.Character.HumanoidRootPart:FindFirstChild("BV"):Remove();
        end;
    end;
end);
end);
end;
C();
