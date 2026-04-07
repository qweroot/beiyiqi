---关注b站KennylolezUID:1531514159
---一群1035184654
---二群2168053189（聊天群）
---十九群1064447273（五百人群）
---二十一群178021813（五百人群）
---二十二群336225224（五百人群）
---二十三群218012845（五百人群）没满
---二十四群1035646571（五百人群）没满
---二十五群1071017763（五百人群）没满
---二十六群820782679（五百人群）没满
---二十七群1067211151（五百人群）
---Kenny脚本群1019547871（五百人群）
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/385j8888/ZOUMAGUIX/refs/heads/main/ProtectUI.lua"))()
repeat
    task.wait()
until game:IsLoaded()
    game:GetService("Players").LocalPlayer.Idled:Connect(function(state)
    game:GetService("VirtualUser"):Button2Down(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
    task.wait(1)
    game:GetService("VirtualUser"):Button2Up(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
    game:GetService("VirtualUser"):CaptureController()
    game:GetService("VirtualUser"):ClickButton2(Vector2.new())
end)
local Floder = {"GeneratorESPFloder", "NPCESPFloder", "KillerESPFloder", "SurvivorsESPFloder", "ToolESPFloder"}
    for i, v in next, Floder do
    local ESPFloder = Instance.new("Folder")
    ESPFloder.Parent = workspace
    ESPFloder.Name = v
end
local jump = false
local jumpp = false
local xj = false
local function removeModelEffects(model)
    local highlight = model:FindFirstChild("ModelHighlight")
    local billboard = model:FindFirstChild("NameBillboard")
    
    if highlight then
        highlight:Destroy()
    end
    
    if billboard then
        billboard:Destroy()
    end
end
local replicatedStorage = game:GetService("ReplicatedStorage")
local lp = game.Players.LocalPlayer
local Mouse = lp:GetMouse()
--local lp = gs("Players").LocalPlayer
local pos = lp.Character.HumanoidRootPart.CFrame + Vector3.new(0, 5, 0)
local ME = game.Players.LocalPlayer.Character.HumanoidRootPart
local Mouse = game:GetService('Players').LocalPlayer:GetMouse()
--local CurrentSlot = game.Players.LocalPlayer:WaitForChild("CurrentSaveSlot").Value
local ScriptLoadOrSave = false
--local CurrentlySavingOrLoading = game.Players.LocalPlayer:WaitForChild("CurrentlySavingOrLoading")
local mouse = game.Players.LocalPlayer:GetMouse()
local tp = function(p)
    lp.Character:PivotTo(p)
end
game:GetService("StarterGui"):SetCore("SendNotification", { 
	Title = "NH 脚本";
	Text = "脚本永远免费";
	Icon = "rbxthumb://type=Asset&id=17366451283&w=150&h=150";
Button1 = "明白";
Duration = 15})
game:GetService("StarterGui"):SetCore("SendNotification", { 
	Title = "NH 脚本";
	Text = "感谢支持小爱同学....";
	Icon = "rbxthumb://type=Asset&id=17366451283&w=150&h=150";
Button1 = "明白";
Duration = 15})
local window = library:new("NH 脚本中心X-被遗弃")

local creds = window:Tab("基本信息")

local bin = creds:section("信息",true)

    bin:Label("你的注入器:"..identifyexecutor())
    bin:Label("作者:小爱........")
    bin:Label("NH 脚本中心:1097885894")

local credits = creds:section("UI设置",true)

    credits:Button("摧毁UI",function()
        game:GetService("CoreGui")["frosty"]:Destroy()
    end)

    credits:Toggle("彩虹UI", "", false, function(state)
        if state then
        game:GetService("CoreGui")["frosty"].Main.Style = "DropShadow"
        else
            game:GetService("CoreGui")["frosty"].Main.Style = "Custom"
        end
    end)
local gm = window:Tab("主要功能")
local gm = gm:section("主要",true)
gm:Textbox("视野(默认80)", "视野", "请输入视野", function(value)
game:GetService("Players").LocalPlayer.PlayerData.Settings.Game.FieldOfView.Value = value
end)
gm:Toggle("禁用耐力", "", false, function(state)
    jump = state  -- 同步阀门状态
    
    if state then
       --  pawn(function()  -- 使用独立协程
           while jump do  -- 检测阀门状态
                 -- 在游戏启动后或玩家加入时运行此脚本
                          local Players = game:GetService("Players")
                          local player = Players.LocalPlayer

-- 确保角色加载完成
                         -- player.CharacterAdded:Connect(function()
    -- 获取耐力模块
                              local sprintModule = require(game.ReplicatedStorage.Systems.Character.Game.Sprinting)
    
    -- 直接覆盖模块中的关键值
                              sprintModule.StaminaLossDisabled = true
    
    -- 如果模块初始化时重置了该值，可监听初始化完成后再次修改
                           --   if sprintModule.Init then
                                --  local originalInit = sprintModule.Init
                                --  sprintModule.Init = function(...)
                              --        originalInit(...)
                                   --   sprintModule.StaminaLossDisabled = true  -- 确保初始化后仍然生效
                                --  end
                            --  end
                        --  end)
                          wait(0.5)
           end
    else
        local sprintModule = require(game.ReplicatedStorage.Systems.Character.Game.Sprinting)
        sprintModule.StaminaLossDisabled = false
    end
end)
local jjump = false
gm:Toggle("无限耐力2(杀手用这个)", "", false, function(state)
    jjump = state  -- 同步阀门状态
    
    if state then
       --  pawn(function()  -- 使用独立协程
           while jjump do  -- 检测阀门状态
                 -- 在游戏启动后或玩家加入时运行此脚本
                          local Players = game:GetService("Players")
                          local player = Players.LocalPlayer
                              local sprintModule = require(game.ReplicatedStorage.Systems.Character.Game.Sprinting)
                              sprintModule.MinStamina = -100000
                          wait(5)
           end
    else
        local sprintModule = require(game.ReplicatedStorage.Systems.Character.Game.Sprinting)
        sprintModule.MinStamina = 0
    end
end)
local jjumpppppp = false
gm:Toggle("自动点击1x4弹窗", "", false, function(state)
    jjumpppppp = state  -- 同步阀门状态
    
    if state then
       --  pawn(function()  -- 使用独立协程
           while jjumpppppp do  -- 检测阀门状态
              for _, i in next,game.Players.LocalPlayer.PlayerGui.TemporaryUI:GetChildren() do
                   if v.Name == "1x1x1x1Popup" then
                      game.VirtualBallsManager:SendMouseButtonEvent(v.AbsolutePosition.X + (v.AbsoluteSize.X / 2), v.AbsolutePosition.Y + (v.AbsoluteSize.Y / 2), Enum.UserInputType.MouseButton1.Value, true, game.Players.PlayerGui, 1)
                      game.VirtualBallsManager:SendMouseButtonEvent(v.AbsolutePosition.X + (v.AbsoluteSize.X / 2), v.AbsolutePosition.Y + (v.AbsoluteSize.Y / 2), Enum.UserInputType.MouseButton1.Value, false, game.Players.PlayerGui, 1)
                   end
              end
              wiat(0.05)
           end
 --   end
           --end
    else
       print("66")
    end
end)

local jjumppp = false
gm:Toggle("免减速，眩晕", "", false, function(state)
    jjumppp = state  -- 同步阀门状态
    
    if state then
       --  pawn(function()  -- 使用独立协程
           while jjumppp do  -- 检测阀门状态
                 -- 配置参数
                 local TARGET_SPEED = 20
                 local player = game.Players.LocalPlayer  -- 客户端使用
-- local player = game:GetService("Players"):GetPlayerByName("你的用户名")  -- 服务器指定玩家

-- 连接存储
                 local wsLoopConnection = nil
                 local charAddedConnection = nil

-- 初始角色处理
                 local char = player.Character
                 if char then
                     local humanoid = char:FindFirstChild("Humanoid")
                     if humanoid then
        -- 设置初始速度
                         humanoid.WalkSpeed = TARGET_SPEED
        
        -- 监听速度变化
                         wsLoopConnection = humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
                             humanoid.WalkSpeed = TARGET_SPEED
                         end)
                     end
                 end

-- 监听新角色生成
                 charAddedConnection = player.CharacterAdded:Connect(function(newChar)
                     local humanoid = newChar:WaitForChild("Humanoid")
    
    -- 清除旧连接
                     if wsLoopConnection then
                         wsLoopConnection:Disconnect()
                         wsLoopConnection = nil
                     end
    
    -- 设置新角色速度
                     humanoid.WalkSpeed = TARGET_SPEED
    
    -- 重新连接监听
                     wsLoopConnection = humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
                         humanoid.WalkSpeed = TARGET_SPEED
                     end)
                 end)
                 wait(0.01)
           end
    else
       humanoid.WalkSpeed = 16
    end
end)
gm:Textbox("修机间隔", "速度", "请输入间隔", function(value)
--print(value)
_fixtime = value
end)
gm:Toggle("自动修机(自定义修机间隔)", "", false, function(state)
    xj = state  -- 同步阀门状态
    
    if state then
       --  pawn(function()  -- 使用独立协程
           while xj do  -- 检测阀门状态
                 -- 在游戏启动后或玩家加入时运行此脚本
                                   --  local a = game:GetService("CoreGui").frosty.Main.TabMain:GetChildren()[2].Section.Objs.TextboxModule.TextboxBack.BoxBG.TextBox.Text
                                    -- wait(a)
                                    wait(_fixtime)
                          	         local FartNapFolder = workspace:FindFirstChild("Map")
				                          and workspace.Map:FindFirstChild("Ingame")
				                          and workspace.Map.Ingame:FindFirstChild("Map")
			                         if FartNapFolder then
				                          local closestGenerator, closestDistance = nil, math.huge
				                          local playerPosition = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
				                          for _, g in ipairs(FartNapFolder:GetChildren()) do
					                          if g.Name == "Generator" and g.Progress.Value < 100 then
						                          local distance = (g.Main.Position - playerPosition).Magnitude
						                          if distance < closestDistance then
							                          closestDistance = distance
							                          closestGenerator = g
						                          end
					                          end
				                          end
				                          if closestGenerator then
					                          
