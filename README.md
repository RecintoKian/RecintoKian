local vu = game:GetService("VirtualUser")
game:GetService("Players").LocalPlayer.Idled:connect(function()
    vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
    wait(5)
    vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
end)
 
game.StarterGui:SetCore("SendNotification", {
    Title = " OP SCRIPTS";
    Text = "Made by KIAN GAMING";
    Duration = 10;
})
wait(1)
game.StarterGui:SetCore("SendNotification", {
    Title = "LOADING";
    Text = "SCRIPT";
    Duration = 10;
})
wait(1)
game.StarterGui:SetCore("SendNotification", {
    Title = "SCRIPT";
    Text = "Black Clover";
    Duration = 10;
})
wait(1)
game.StarterGui:SetCore("SendNotification", {
    Title = "GAME";
    Text = "BEDWARS";
    Duration = 10;
})

local NeonWaterMark = Instance.new("ScreenGui") 
local TextLabel = Instance.new("TextButton") 
local UIGradient = Instance.new("UIGradient") 
local UITextSizeConstraint = Instance.new("UITextSizeConstraint") 
  
NeonWaterMark.Name = "NeonWaterMark" 
NeonWaterMark.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui") 
NeonWaterMark.ZIndexBehavior = Enum.ZIndexBehavior.Sibling 
NeonWaterMark.ResetOnSpawn = false 
  
TextLabel.Parent = NeonWaterMark 
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255) 
TextLabel.BackgroundTransparency = 1.000 
TextLabel.BorderSizePixel = 0 
TextLabel.Position = UDim2.new(-0.000772226602, 0, 0.0343558267, 0) 
TextLabel.Size = UDim2.new(0.170134634, 0, 0.0700389072, 0) 
TextLabel.Font = Enum.Font.GothamBold 
TextLabel.Text = "Black Clover" 
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255) 
TextLabel.TextScaled = true 
TextLabel.TextSize = 28.000 
TextLabel.TextWrapped = true 
TextLabel.TextXAlignment = Enum.TextXAlignment.Left 
TextLabel.MouseButton1Down:Connect(function() 
         kavoUi:ToggleUI()
 end) 
  
UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, Color3.fromRGB(0, 0, 255)), ColorSequenceKeypoint.new(1.00, Color3.fromRGB(0, 0, 255))} 
UIGradient.Parent = TextLabel 

local vu = game:GetService("VirtualUser") 
 game:GetService("Players").LocalPlayer.Idled:connect(function() 
     vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame) 
     wait(1) 
     vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame) 
 end) 

Library = loadstring(game:HttpGet("https://pastebin.com/raw/ZMi6306F",true))();
local Window = Library.CreateLib("Black Clover | Bedwars", "GrapeTheme")

local players = game:GetService("Players") 
 local lplr = players.LocalPlayer 
 local oldchar = lplr.Character 
 local cam = workspace.CurrentCamera 
 local uis = game:GetService("UserInputService") 
 local KnitClient = debug.getupvalue(require(game.Players.LocalPlayer.PlayerScripts.TS.knit).setup, 6) 
 local Client = require(game:GetService("ReplicatedStorage").TS.remotes).default.Client 
 local InventoryUtil = require(game:GetService("ReplicatedStorage").TS.inventory["inventory-util"]).InventoryUtil 
 local itemstuff = debug.getupvalue(require(game:GetService("ReplicatedStorage").TS.item["item-meta"]).getItemMeta, 1) 
 local RenderStepTable = {} 
 local StepTable = {} 
 local connectioninfjump 
 local killauraswing = {["Enabled"] = true} 
 local killaurasound = {["Enabled"] = true} 
 local killaurahitdelay = {["Value"] = 2} 
 local killaurasoundval = {["Value"] = 1} 
 local speedval = {["Value"] = 1} 
 local testtogttt = {["Value"] = 20} 
 local ACC1 
 local ACC2 
 local antivoidtransparent = {["Value"] = 50} 
 local antivoidcolor = {["Hue"] = 0.93, ["Sat"] = 1, ["Value"] = 1} 
 local reachval = {["Value"] = 18} 
 local autoclick = {["Enabled"] = true} 
 local origC0 = game.ReplicatedStorage.Assets.Viewmodel.RightHand.RightWrist.C0 
 local killaurafirstpersonanim = {["Value"] = true} 
 local killauraanimval = {["Value"] = "Cool"} 
  
 local SprintCont = KnitClient.Controllers.SprintController 
 local SwordCont = KnitClient.Controllers.SwordController 
 local KnockbackTable = debug.getupvalue(require(game:GetService("ReplicatedStorage").TS.damage["knockback-util"]).KnockbackUtil.calculateKnockbackVelocity, 1) 
 local ClientHandler = Client 
  
 local function GetURL(scripturl) 
         return game:HttpGet("https://raw.githubusercontent.com/7GrandLittleBrother/SytroNight4ROBLOX/main/"..scripturl, true) 
 end 
  
 local function isAlive(plr) 
         if plr then 
                 return plr and plr.Character and plr.Character.Parent ~= nil and plr.Character:FindFirstChild("HumanoidRootPart") and plr.Character:FindFirstChild("Head") and plr.Character:FindFirstChild("Humanoid") 
         end 
         return lplr and lplr.Character and lplr.Character.Parent ~= nil and lplr.Character:FindFirstChild("HumanoidRootPart") and lplr.Character:FindFirstChild("Head") and lplr.Character:FindFirstChild("Humanoid") 
 end 
  
 local function runcode(func) 
         func() 
 end 
  
 local function playsound(id, volume)  
         local sound = Instance.new("Sound") 
         sound.Parent = workspace 
         sound.SoundId = id 
         sound.PlayOnRemove = true  
         if volume then  
                 sound.Volume = volume 
         end 
         sound:Destroy() 
 end 
  
 local function playanimation(id)  
         if isAlive() then  
                 local animation = Instance.new("Animation") 
                 animation.AnimationId = id 
                 local animatior = lplr.Character.Humanoid.Animator 
                 animatior:LoadAnimation(animation):Play() 
         end 
 end 
  
 function isNumber(str) 
         if tonumber(str) ~= nil or str == 'inf' then 
                 return true 
         end 
 end 
  
 function getinv(plr) 
         local plr = plr or lplr 
         local thingy, thingytwo = pcall(function() return InventoryUtil.getInventory(plr) end) 
         return (thingy and thingytwo or { 
                 items = {}, 
                 armor = {}, 
                 hand = nil 
         }) 
 end 
  
 function getsword() 
         local sd 
         local higherdamage 
         local swordslots 
         local swords = getinv().items 
         for i, v in pairs(swords) do 
                 if v.itemType:lower():find("sword") or v.itemType:lower():find("blade") then 
                         if higherdamage == nil or itemstuff[v.itemType].sword.damage > higherdamage then 
                                 sd = v 
                                 higherdamage = itemstuff[v.itemType].sword.damage 
                                 swordslots = i 
                         end 
                 end 
         end 
         return sd, swordslots 
 end 
  
 local function getremote(tab) 
         for i,v in pairs(tab) do 
                 if v == "Client" then 
                         return tab[i + 1] 
                 end 
         end 
         return "" 
 end 
  
 local function hvFunc(cock) 
         return {hashedval = cock} 
 end 
  
 local function targetCheck(plr, check) 
         return (check and plr.Character.Humanoid.Health > 0 and plr.Character:FindFirstChild("ForceField") == nil or check == false) 
 end 
  
 local function isPlayerTargetable(plr, target) 
         return plr ~= lplr and plr and isAlive(plr) and targetCheck(plr, target) 
 end 
  
 local function GetAllNearestHumanoidToPosition(distance, amount) 
         local returnedplayer = {} 
         local currentamount = 0 
         if entity.isAlive then -- alive check 
                 for i, v in pairs(game.Players:GetChildren()) do -- loop through players 
                         if isPlayerTargetable((v), true, true, v.Character ~= nil) and v.Character:FindFirstChild("HumanoidRootPart") and v.Character:FindFirstChild("Head") and currentamount < amount then -- checks 
                                 local mag = (lplr.Character.HumanoidRootPart.Position - v.Character:FindFirstChild("HumanoidRootPart").Position).magnitude 
                                 if mag <= distance then -- mag check 
                                         table.insert(returnedplayer, v) 
                                         currentamount = currentamount + 1 
                                 end 
                         end 
                 end 
                 for i2,v2 in pairs(game:GetService("CollectionService"):GetTagged("Monster")) do -- monsters 
                         if v2:FindFirstChild("HumanoidRootPart") and currentamount < amount and v2.Name ~= "Duck" then -- no duck 
                                 local mag =  
 (lplr.Character.HumanoidRootPart.Position - v.Character:FindFirstChild("HumanoidRootPart").Position).magnitude 
                                 if mag <= distance then -- mag check 
                                         table.insert(returnedplayer, v) 
                                         currentamount = currentamount + 1 
                                 end 
                         end 
                 end 
                 for i2,v2 in pairs(game:GetService("CollectionService"):GetTagged("Monster")) do -- monsters 
                         if v2:FindFirstChild("HumanoidRootPart") and currentamount < amount and v2.Name ~= "Duck" then -- no duck 
                                 local mag = (lplr.Character.HumanoidRootPart.Position - v2.HumanoidRootPart.Position).magnitude 
                                 if mag <= distance then -- magcheck 
                                         table.insert(returnedplayer, {Name = (v2 and v2.Name or "Monster"), UserId = 1443379645, Character = v2}) -- monsters are npcs so I have to create a fake player for target info 
                                         currentamount = currentamount + 1 
                                 end 
                         end 
                 end 
         end 
         return returnedplayer -- table of attackable entities 
 end 
  
 local function BindToRenderStep(name, num, func) 
         if RenderStepTable[name] == nil then 
                 RenderStepTable[name] = game:GetService("RunService").RenderStepped:connect(func) 
         end 
 end 
 local function UnbindFromRenderStep(name) 
         if RenderStepTable[name] then 
                 RenderStepTable[name]:Disconnect() 
                 RenderStepTable[name] = nil 
         end 
 end 
  
 local function BindToStepped(name, num, func) 
         if StepTable[name] == nil then 
                 StepTable[name] = game:GetService("RunService").Stepped:connect(func) 
         end 
 end 
 local function UnbindFromStepped(name) 
         if StepTable[name] then 
                 StepTable[name]:Disconnect() 
                 StepTable[name] = nil 
         end 
 end 
  
 local attackentitycont = Client:Get(getremote(debug.getconstants(getmetatable(KnitClient.Controllers.SwordController)["attackEntity"]))) 
 local rgfejd = false 
 local DistVal = {["Value"] = 18} 
 function KillauraRemote() 
         for i,v in pairs(game.Players:GetChildren()) do 
                 if v.Character and v.Name ~= game.Players.LocalPlayer.Name and v.Character:FindFirstChild("HumanoidRootPart") then 
                         local mag = (v.Character.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude 
                         if mag <= DistVal["Value"] and v.Team ~= game.Players.LocalPlayer.Team and v.Character:FindFirstChild("Humanoid") then 
                                 if v.Character.Humanoid.Health > 0 then 
                                         rgfejd = true 
                                         local GBW = getsword() 
                                         local selfPosition = lplr.Character.HumanoidRootPart.Position + (DistVal["Value"] > 14 and (lplr.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude > 14 and (CFrame.lookAt(lplr.Character.HumanoidRootPart.Position, v.Character.HumanoidRootPart.Position).lookVector * 4) or Vector3.new(0, 0, 0)) 
                                         local Entity = v.Character 
                                         local target = v.Character:GetPrimaryPartCFrame().Position 
                                         attackentitycont:CallServer({ 
                                                 ["chargedAttack"] = {["chargeRatio"] = 1}, 
                                                 ["weapon"] = GBW ~= nil and GBW.tool, 
                                                 ["entityInstance"] = Entity, 
                                                 ["validate"] = {["targetPosition"] = {["value"] = target, 
                                                         ["hash"] = hvFunc(target)}, 
                                                 ["raycast"] = { 
                                                         ["cameraPosition"] = hvFunc(cam.CFrame.Position),  
                                                         ["cursorDirection"] = hvFunc(Ray.new(cam.CFrame.Position, v.Character:GetPrimaryPartCFrame().Position).Unit.Direction) 
                                                 }, 
                                                 ["selfPosition"] = {["value"] = selfPosition, 
                                                         ["hash"] = hvFunc(selfPosition) 
                                                 } 
                                                 } 
                                         }) 
                                         if killaurasound["Enabled"] then 
                                                 playsound("rbxassetid://6760544639", killaurasoundval["Value"]) 
                                         end 
                                         if killauraswing["Enabled"] then 
                                                 playanimation("rbxassetid://4947108314") 
                                         end 
                                 end 
                         else 
                                 rgfejd = false 
                         end 
                 end 
         end 
 end 
  
 local itemtab = debug.getupvalue(require(game:GetService("ReplicatedStorage").TS.item["item-meta"]).getItemMeta, 1) 
 local CombatConstant = require(game:GetService("ReplicatedStorage").TS.combat["combat-constant"]).CombatConstant 
 local function getEquipped() 
         local typetext = "" 
         local obj = (entity.isAlive and lplr.Character:FindFirstChild("HandInvItem") and lplr.Character.HandInvItem.Value or nil) 
         if obj then 
                 if obj.Name:find("sword") or obj.Name:find("blade") or obj.Name:find("baguette") or obj.Name:find("scythe") or obj.Name:find("dao") then 
                         typetext = "sword" 
                 end 
                 if obj.Name:find("wool") or itemtab[obj.Name]["block"] then 
                         typetext = "block" 
                 end 
                 if obj.Name:find("bow") then 
                         typetext = "bow" 
                 end 
         end 
         return {["Object"] = obj, ["Type"] = typetext} 
 end 

local function createwarning(title, text, delay)
	local suc, res = pcall(function()
		local frame = GuiLibrary["CreateNotification"](title, text, delay, "assets/WarningNotification.png")
		frame.Frame.Frame.ImageColor3 = Color3.fromRGB(236, 129, 44)
		return frame
	end)
	return (suc and res)
end

local Tab1 = Window:NewTab("Credits")
local Tab2 = Window:NewTab("Main")
local Tab3 = Window:NewTab("Others script")
local Tab4 = Window:NewTab("Animation")

local Tab1Section = Tab1:NewSection("Owner: KIAN GAMING")
local Tab1Section = Tab1:NewSection("Helper: MARGIE")
local Tab1Section = Tab1:NewSection("Helper: Black Bull")
local Tab2Section = Tab2:NewSection("Speed 23.4")
local Tab3Section = Tab3:NewSection("Others Script")
local Tab4Section = Tab4:NewSection("Animation | Not Permanent")

Tab2Section:NewToggle("Speed", "increase speed", function()
game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 23.4
    print("...")
end)

local Tab2Section = Tab2:NewSection("Range")
Tab2Section:NewToggle("Reach", "Extend your attack range", function(state) 
         if state then 
                 CombatConstant.RAYCAST_SWORD_CHARACTER_DISTANCE = (reachval["Value"] - 0.0001) 
         else 
                 CombatConstant.RAYCAST_SWORD_CHARACTER_DISTANCE = 14.4 
         end 
 end) 
  
local Tab2Section = Tab2:NewSection("Killaura | Patched")
Tab2Section:NewToggle("KillAura", "Autoswing the sword if someone is near you", function(state)
if state then

		BindToStepped("Killaura", 1, function()

			if entity.isAlive then

				KillauraRemote()

			end

		end)

	else

		UnbindFromStepped("Killaura")

	end

end)

local Tab2Section = Tab2:NewSection("NoClick Delay")
Tab2Section:NewToggle("NoClick Delay", "NoClick Delay", function(state)
    if state then
getgenv().funisus = v
        spawn(function()
            if getgenv().funisus and entity.isAlive then
                for i2,v2 in pairs(itemtable) do
                    if type(v2) == "table" and rawget(v2, "sword") then
                        v2.sword.attackSpeed = 0.000000001
                    end
                    SwordCont.isClickingTooFast = function() return false end
                end
            else
            end
        end)
    end
 
    end)
    
local Tab2Section = Tab2:NewSection("Damage Return")
Tab2Section:NewToggle("Damage Return", "ToggleInfo", function(state)
    if state then
        
local TS = game:GetService("TweenService")
local Tinfo = TweenInfo.new(0.3, Enum.EasingStyle.Quint, Enum.EasingDirection.InOut)

local DamageEvent = game.ReplicatedStorage.DamageEvent --You can remove this line since it is actually unnecessary 
local DamageBoard = game.ReplicatedStorage.DamageBoard

local Red = Color3.fromRGB(255, 0, 0)
local Green = Color3.fromRGB(95,111,64)



game.Players.PlayerAdded:Connect(function(plr)
	plr.CharacterAdded:Connect(function(char)
		
		local hum = char:WaitForChild("Humanoid")
		local humH = hum.Health
		
		hum.HealthChanged:Connect(function(Health)
			if Health < humH and Health > 0 then
				
				local Damage = math.floor(humH - Health)
				print(Damage.." Damage was taken")
				
				local BoardClone = DamageBoard:Clone()
				BoardClone:FindFirstChild("Damage").Text = Damage
				
				local maxH = hum.MaxHealth
				BoardClone.Damage.TextColor3 = Green:lerp(Red, Damage / maxH)
				
				
				BoardClone.Parent = char.HumanoidRootPart
				BoardClone.Damage:TweenSize(UDim2.new(1,0,1,0), "InOut", "Quint", 0.3)
								
				wait(0.3)
				
				local UIupTween = TS:Create(BoardClone, Tinfo, {StudsOffset = BoardClone.StudsOffset + Vector3.new(0,1,0)})
				local textFade = TS:Create(BoardClone.Damage, Tinfo, {TextTransparency = 1})
								
				UIupTween:Play()
				textFade:Play()
				
				game:GetService("Debris"):AddItem(BoardClone, 0.5)
			end
			humH = hum.Health
		end)
		
	end)
end)
    else
        print("Toggle Off")
    end
end)

local Tab2Section = Tab2:NewSection("Infinity jump")
Tab2Section:NewToggle("Infinite Jumps"," Infinite Jumps",function(state)
if state then
		local InfJump = {["Enabled"] = true}
		connectioninfjump = uis.JumpRequest:connect(function(jump)
			if InfJump["Enabled"] then
				lplr.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
			end
		end)
	else
		connectioninfjump:Disconnect()
	end
end)

local Tab2Section = Tab2:NewSection("No KnockBack")
Tab2Section:NewToggle("No KnockBack","No KnockBack",function(state)
local s = require(game:GetService("ReplicatedStorage").TS.damage["knockback-util"]).KnockbackUtil
s.applyKnockbackDirection = function(...)end
s.applyKnockback = function(...)end
    
end)

local Tab2Section = Tab2:NewSection("No Fall Damage")
Tab2Section:NewToggle("No Fall Damage", "Opens No Fall Damage", function(callback)
    local nofall = true
    if callback then
        if nofall then
            spawn(function()
                repeat
                    wait()
                    if nofall == false then
                        return end
                        game:GetService("ReplicatedStorage").rbxts_include.node_modules.net.out._NetManaged.GroundHit:FireServer()
                    until nofall == false
                end)
            end
    else
        local nofall = false
    end
end)

local Tab2Section = Tab2:NewSection("Auto Sprint")
Tab2Section:NewToggle("Sprint", "Automatically on your sprint", function(state) 
         if state then 
                 BindToStepped("Sprint", 1, function() 
                         if SprintCont.sprinting == false then 
                                 SprintCont:startSprinting() 
                         end 
                 end) 
         else 
                 UnbindFromStepped("Sprint") 
                 SprintCont:stopSprinting() 
         end 
 end) 

local Tab2Section = Tab2:NewSection("Gravity")
Tab2Section:NewToggle("Gravity", "Gravity",function()
    game:GetService("Workspace").Gravity = 90
      print("Toggle Off")
end)

local Tab2Section = Tab2:NewSection("FixCam")
Tab2Section:NewButton("FixCam", "fix camera bug on mobile", function()
	cam.CameraType = Enum.CameraType.Fixed
	cam.CameraType = Enum.CameraType.Custom
end)

Tab3Section:NewButton("Infinite Yield Fe", "use tpwalk 0.5", function()
     loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))
end)

Tab3Section:NewButton("Keyboard", "Execute Keyboard Script", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/advxzivhsjjdhxhsidifvsh/mobkeyboard/main/main.txt", true))()
end)

local Tab3Section = Tab3:NewSection("Vape")
Tab3Section:NewButton("Vape", "op", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/main/NewMainScript.lua", true))()
end)

local Tab3Section = Tab3:NewSection("like a vape")
Tab3Section:NewButton("black clover", "op", function()
    loadstring(game:httpget("https://raw.githubusercontent.com/7granddadpgn/vapev4forroblox/main/newmainscript.lua", true))()
end)

Tab4Section:NewButton(" Combo Animation","Plays Special Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=782841498"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=782845736"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=656121766"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=656118852"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=656117878"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=656114359"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=656115606"
end)

Tab4Section:NewButton("Second Combo Animation","Plays Robot Animation",function()
local Animate = 
game.Players.LocalPlayer.Character.Animate
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=4417979645"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=4417979645"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616008936"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616003713"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616005863"
end)

Tab4Section:NewButton("Zombie" , "Plays Zombie Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=616158929"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=616160636"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616168032"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616163682"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616161997"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616156119"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616157476"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Ninja","Plays Ninja Animation",function()
loadstring(game:HttpGet("https://pastebin.com/raw/bwGLPVV7",true))()
end)

Tab4Section:NewButton("Robot","Plays Robot Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=616088211"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=616089559"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616095330"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616091570"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616090535"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616086039"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616087089"
end)

Tab4Section:NewButton("Toy","Opens Toy Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=782841498"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=782845736"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=782843345"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=782842708"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=782847020"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=782843869"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=782846423"
end)

Tab4Section:NewButton("Levitation","Opens Levitation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=616006778"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=616008087"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616013216"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616010382"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616008936"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616003713"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616005863"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Astronaut" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=891621366"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=891633237"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=891667138"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=891636393"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=891627522"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=891609353"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=891617961"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Bubbly" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=910004836"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=910009958"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=910034870"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=910025107"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=910016857"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=910001910"
Animate.swimidle.SwimIdle.AnimationId = "http://www.roblox.com/asset/?id=910030921"
Animate.swim.Swim.AnimationId = "http://www.roblox.com/asset/?id=910028158"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Cartoony" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=742637544"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=742638445"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=742640026"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=742638842"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=742637942"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=742636889"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=742637151"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Elder" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=845397899"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=845400520"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=845403856"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=845386501"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=845398858"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=845392038"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=845396048"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Knight" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=657595757"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=657568135"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=657552124"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=657564596"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=658409194"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=658360781"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=657600338"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Mage" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=707742142"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=707855907"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=707897309"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=707861613"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=707853694"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=707826056"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=707829716"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Pirate" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=750781874"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=750782770"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=750785693"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=750783738"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=750782230"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=750779899"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=750780242"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Stylish" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=616136790"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=616138447"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616146177"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616140816"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616139451"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616133594"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616134815"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Super Hero" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=616111295"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=616113536"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616122287"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616117076"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616115533"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616104706"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616108001"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Vampire" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1083445855"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1083450166"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1083473930"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1083462077"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1083455352"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1083439238"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1083443587"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("WereWolf" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1083195517"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1083214717"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1083178339"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1083216690"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1083218792"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1083182000"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1083189019"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("CowBoy" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1014390418"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1014398616"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1014421541"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1014401683"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1014394726"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1014380606"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1014384571"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)


Tab4Section:NewButton("Patrol" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1149612882"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1150842221"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1151231493"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1150967949"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1148811837"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1148811837"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1148863382"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Confident" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1069977950"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1069987858"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1070017263"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1070001516"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1069984524"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1069946257"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1069973677"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("PopStar" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1212900985"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1150842221"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1212980338"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1212980348"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1212954642"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1213044953"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1212900995"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Ghost" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=616006778"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=616008087"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616013216"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616013216"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=616008936"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=616005863"
Animate.swimidle.SwimIdle.AnimationId = "http://www.roblox.com/asset/?id=616012453"
Animate.swim.Swim.AnimationId = "http://www.roblox.com/asset/?id=616011509"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)

Tab4Section:NewButton("Sneaky" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=1132473842"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=1132477671"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=1132510133"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=1132494274"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1132489853"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=1132461372"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1132469004"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)y

Tab4Section:NewButton("Princess" , "Plays Animation",function()
local Animate =
game.Players.LocalPlayer.Character.Animate
Animate.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=941003647"
Animate.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=941013098"
Animate.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=941028902"
Animate.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=941015281"
Animate.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=941008832"
Animate.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=940996062"
Animate.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=941000007"
game.Players.LocalPlayer.Character.Humanoid.Jump = true
end)
