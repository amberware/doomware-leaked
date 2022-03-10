--click raw to view it all
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Doomware - Aimlock", "BloodTheme")



local Tab = Window:NewTab("MAIN")
local Section = Tab:NewSection("MAIN")



Section:NewButton("FLY (X)", "this fly only works for R15 lol", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/iluvje54/fly/main/ok"))()
end)

Section:NewButton("ANIMATIONS", "Once Injected it will give you Kimbladi Animations", function()
    local L_206_ = game.Players.LocalPlayer.Character.Animate
    L_206_.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=782841498"
    L_206_.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=782845736"
    L_206_.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616168032"
    L_206_.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616163682"
    L_206_.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=5319841935"
    L_206_.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=707829716"
    game.Players.LocalPlayer.Character.Humanoid.Jump = true
wait(1)

end)

Section:NewButton("ANTI STOMP (Cannot Be Turned Off)", "gay function", function()
     loadstring(game:HttpGet("https://raw.githubusercontent.com/BlueaqeR/scripts-lol/main/Da%20Hood%20Anti%20Stomp%20(Optimized)"))()
     print("Clicked")
     
end)


local Tab = Window:NewTab("AIMING")
local Section = Tab:NewSection("AIMLOCK")

Section:NewButton("AIMLOCK (Q)", "Q To lock on, T to toggle aimbot on and off.", function()
    getgenv().AimPart = "HumanoidRootPart" -- For R15 Games: {UpperTorso, LowerTorso, HumanoidRootPart, Head} | For R6 Games: {Head, Torso, HumanoidRootPart}
    getgenv().AimlockToggleKey = "t" -- Toggles Aimbot On/Off
    getgenv().AimlockKey = "q"
    getgenv().AimRadius = 35 -- How far away from someones character you want to lock on at
    getgenv().ThirdPerson = true
    getgenv().FirstPerson = true
    getgenv().TeamCheck = false -- Check if Target is on your Team (True means it wont lock onto your teamates, false is vice versa) (Set it to false if there are no teams)
    getgenv().PredictMovement = true -- Predicts if they are moving in fast velocity (like jumping) so the aimbot will go a bit faster to match their speed
    getgenv().PredictionVelocity = 10
    getgenv().CheckIfJumped = true
    getgenv().AutoPrediction = true
    local L_28_, L_29_, L_30_, L_31_ = game:GetService"Players", game:GetService"UserInputService", game:GetService"RunService", game:GetService"StarterGui";
    local L_32_, L_33_, L_34_, L_35_, L_36_, L_37_, L_38_ = L_28_.LocalPlayer, L_28_.LocalPlayer:GetMouse(), workspace.CurrentCamera, CFrame.new, Ray.new, Vector3.new, Vector2.new;
    local L_39_, L_40_, L_41_ = true, false, false;
    local L_42_;
    getgenv().CiazwareUniversalAimbotLoaded = true
    getgenv().WorldToViewportPoint = function(L_43_arg0)
        return L_34_:WorldToViewportPoint(L_43_arg0)
    end
    getgenv().WorldToScreenPoint = function(L_44_arg0)
        return L_34_.WorldToScreenPoint(L_34_, L_44_arg0)
    end
    getgenv().GetObscuringObjects = function(L_45_arg0)
        if L_45_arg0 and L_45_arg0:FindFirstChild(getgenv().AimPart) and L_32_ and L_32_.Character:FindFirstChild("Head") then
            local L_46_ = workspace:FindPartOnRay(L_36_(
        L_45_arg0[getgenv().AimPart].Position, L_32_.Character.Head.Position)
    )
            if L_46_ then
                return L_46_:IsDescendantOf(L_45_arg0)
            end
        end
    end
    getgenv().GetNearestTarget = function()
        local L_47_ = {}
        local L_48_  = {}
        local L_49_ = {}
        for L_51_forvar0, L_52_forvar1 in pairs(L_28_:GetPlayers()) do
            if L_52_forvar1 ~= L_32_ then
                table.insert(L_47_, L_52_forvar1)
            end
        end
        for L_53_forvar0, L_54_forvar1 in pairs(L_47_) do
            if L_54_forvar1.Character ~= nil then
                local L_55_ = L_54_forvar1.Character:FindFirstChild("Head")
                if getgenv().TeamCheck == true and L_54_forvar1.Team ~= L_32_.Team then
                    local L_56_ = (L_54_forvar1.Character:FindFirstChild("Head").Position - game.Workspace.CurrentCamera.CFrame.p).magnitude
                    local L_57_ = Ray.new(game.Workspace.CurrentCamera.CFrame.p, (L_33_.Hit.p - game.Workspace.CurrentCamera.CFrame.p).unit * L_56_)
                    local L_58_, L_59_ = game.Workspace:FindPartOnRay(L_57_, game.Workspace)
                    local L_60_ = math.floor((L_59_ - L_55_.Position).magnitude)
                    L_48_[L_54_forvar1.Name .. L_53_forvar0] = {}
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].dist = L_56_
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].plr = L_54_forvar1
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].diff = L_60_
                    table.insert(L_49_, L_60_)
                elseif getgenv().TeamCheck == false and L_54_forvar1.Team == L_32_.Team then
                    local L_61_ = (L_54_forvar1.Character:FindFirstChild("Head").Position - game.Workspace.CurrentCamera.CFrame.p).magnitude
                    local L_62_ = Ray.new(game.Workspace.CurrentCamera.CFrame.p, (L_33_.Hit.p - game.Workspace.CurrentCamera.CFrame.p).unit * L_61_)
                    local L_63_, L_64_ = game.Workspace:FindPartOnRay(L_62_, game.Workspace)
                    local L_65_ = math.floor((L_64_ - L_55_.Position).magnitude)
                    L_48_[L_54_forvar1.Name .. L_53_forvar0] = {}
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].dist = L_61_
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].plr = L_54_forvar1
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].diff = L_65_
                    table.insert(L_49_, L_65_)
                end
            end
        end
        if unpack(L_49_) == nil then
            return nil
        end
        local L_50_ = math.floor(math.min(unpack(L_49_)))
        if L_50_ > getgenv().AimRadius then
            return nil
        end
        for L_66_forvar0, L_67_forvar1 in pairs(L_48_) do
            if L_67_forvar1.diff == L_50_ then
                return L_67_forvar1.plr
            end
        end
        return nil
    end
    L_33_.KeyDown:Connect(function(L_68_arg0)
        if L_68_arg0 == AimlockKey and L_42_ == nil then
            pcall(function()
                if L_40_ ~= true then
                    L_40_ = true
                end
                local L_69_;
                L_69_ = GetNearestTarget()
                if L_69_ ~= nil then
                    L_42_ = L_69_
                end
            end)
        elseif L_68_arg0 == AimlockKey and L_42_ ~= nil then
            if L_42_ ~= nil then
                L_42_ = nil
            end
            if L_40_ ~= false then
                L_40_ = false
            end
        elseif L_68_arg0 == AimlockToggleKey then
            L_39_ = not L_39_
        end
    end)
    L_30_.RenderStepped:Connect(function()
        if getgenv().ThirdPerson == true and getgenv().FirstPerson == true then
            if (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude > 1 or (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude <= 1 then
                L_41_ = true
            else
                L_41_ = false
            end
        elseif getgenv().ThirdPerson == true and getgenv().FirstPerson == false then
            if (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude > 1 then
                L_41_ = true
            else
                L_41_ = false
            end
        elseif getgenv().ThirdPerson == false and getgenv().FirstPerson == true then
            if (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude <= 1 then
                L_41_ = true
            else
                L_41_ = false
            end
        end
        if L_39_ == true and L_40_ == true then
            if L_42_ and L_42_.Character and L_42_.Character:FindFirstChild(getgenv().AimPart) then
                if getgenv().FirstPerson == true then
                    if L_41_ == true then
                        if getgenv().PredictMovement == true then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position + L_42_.Character[getgenv().AimPart].Velocity / PredictionVelocity)
                        elseif getgenv().PredictMovement == false then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position)
                        end
                    end
                elseif getgenv().ThirdPerson == true then
                    if L_41_ == true then
                        if getgenv().PredictMovement == true then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position + L_42_.Character[getgenv().AimPart].Velocity / PredictionVelocity)
                        elseif getgenv().PredictMovement == false then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position)
                        end
                    end
                end
            end
        end
    end)
end)



Section:NewButton("SILENT AIM", "silent aim", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/tayodevelup/imsoniac/main/silentaim", true))()
    print("Clicked")
end)


local Tab = Window:NewTab("MOVEMENT")
local Section = Tab:NewSection("MOVEMENT")

Section:NewButton("FAST SPEED (C)", "fast speed", function()
    plr = game:GetService('Players').LocalPlayer
    down = true
    
    function onButton1Down(mouse)
        down = true
        while down do
            if not down then break end
            local char = plr.Character
            char.HumanoidRootPart.Velocity = char.HumanoidRootPart.CFrame.lookVector * 190
            wait()
        end
    end
    
    function onButton1Up(mouse)
        down = false
    end
    
    function onSelected(mouse)
        mouse.KeyDown:connect(function(c) if c:lower()=="c"then onButton1Down(mouse)end end)
        mouse.KeyUp:connect(function(c) if c:lower()=="c"then onButton1Up(mouse)end end)
    end
    onSelected(game.Players.LocalPlayer:GetMouse())
end
)


local Tab = Window:NewTab("TELEPORTS")
local Section = Tab:NewSection("TELEPORTS")

Section:NewButton("BANK", "Teleports Player To Bank.", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-318.891174, 80.2145309, -257.177429, 0.0479469746, -5.14644114e-08, 0.998850107, -3.12971538e-09, 1, 5.16738901e-08, -0.998850107, -5.60372015e-09, 0.0479469746)
end)

Section:NewButton("ADMIN GUNS", "Teleports Player To Admin Guns.", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-872.853516, -34.4276848, -538.013306, -0.999724388, -3.9898886e-08, -0.0234765243, -3.9204977e-08, 1, -3.00177518e-08, 0.0234765243, -2.90890814e-08, -0.999724388)
    end)

    Section:NewButton("rev roof", "Teleports Player To Revolver.", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-634.463135, 80.434761, -204.232559, -0.0190527271, -1.03574322e-07, -0.999818563, 4.36709335e-09, 1, -1.03676342e-07, 0.999818563, -6.3416179e-09, -0.0190527271)
       
    end)

    Section:NewButton("RPG", "Teleports Player To RPG.", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(139.815933, -22.9016266, -136.737762, 0.0339428484, -7.90177737e-08, 0.999423802, -4.7851227e-08, 1, 8.06884728e-08, -0.999423802, -5.0562452e-08, 0.0339428484)
        
    end)

    local Tab = Window:NewTab("AUTO BUYS")
    local Section = Tab:NewSection("AUTO BUYS")

    Section:NewButton("DOUBLE BARREL", "Auto Buys DB.", function()
        L_10_ = game:GetService'Players'.LocalPlayer
        local L_504_ = game.Workspace.Ignored.Shop['[Double-Barrel SG] - $1400']
        local L_505_ = L_10_.Character.HumanoidRootPart.Position
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_504_.Head.CFrame + Vector3.new(0, 3, 0)
        wait(0.5)
        fireclickdetector(game.Workspace.Ignored.Shop['[Double-Barrel SG] - $1400'].ClickDetector)
        fireclickdetector(game.Workspace.Ignored.Shop['[Double-Barrel SG] - $1400'].ClickDetector)
        L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_505_)
        L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_505_)
      
        end)

        Section:NewButton("REVOLVER", "Auto Buys Rev.", function()
            L_10_ = game:GetService'Players'.LocalPlayer
            local L_498_ = '[Revolver] - $1300'
            local L_499_ = game.Workspace.Ignored.Shop[L_498_]
            local L_500_ = L_10_.Character.HumanoidRootPart.Position
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_499_.Head.CFrame + Vector3.new(0, 3, 0)
            wait(0.5)
            fireclickdetector(game.Workspace.Ignored.Shop[L_498_].ClickDetector)
            fireclickdetector(game.Workspace.Ignored.Shop[L_498_].ClickDetector)
            L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_500_)
            L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_500_)
        
        end)

        Section:NewButton("DB AMMO", "Auto Buys DB Ammo.", function()
            local L_506_ = game.Workspace.Ignored.Shop['18 [Double-Barrel SG Ammo] - $60']
                local L_507_ = L_10_.Character.HumanoidRootPart.Position
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_506_.Head.CFrame + Vector3.new(0, 3, 0)
                wait(0.5)
                fireclickdetector(game.Workspace.Ignored.Shop['18 [Double-Barrel SG Ammo] - $60'].ClickDetector)
                fireclickdetector(game.Workspace.Ignored.Shop['18 [Double-Barrel SG Ammo] - $60'].ClickDetector)
                L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_507_)
                L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_507_)
               
            end)

            Section:NewButton("REV AMMO", "Auto Buys Rev Ammo.", function()
                L_10_ = game:GetService'Players'.LocalPlayer
                    local L_501_ = '12 [Revolver Ammo] - $75'
                    local L_502_ = game.Workspace.Ignored.Shop[L_501_]
                    local L_503_ = L_10_.Character.HumanoidRootPart.Position
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_502_.Head.CFrame + Vector3.new(0, 3, 0)
                    wait(0.5)
                    fireclickdetector(game.Workspace.Ignored.Shop[L_501_].ClickDetector)
                    fireclickdetector(game.Workspace.Ignored.Shop[L_501_].ClickDetector)
                    L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_503_)
                    L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_503_)
                    
                end)

                Section:NewButton("ARMOR", "Buys Armor.", function()
                    local plr = game.Players.LocalPlayer
                        local savedarmourpos = plr.Character.HumanoidRootPart.Position
                        plr.Character.HumanoidRootPart.CFrame = CFrame.new(-938.476685, -25.2498264, 570.100159, -0.0353576206, 9.85617206e-08, -0.999374807, -2.69198441e-09, 1, 9.871858e-08, 0.999374807, 6.18077589e-09, -0.0353576206)
--// Decompiled Code. 
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Doomware - Aimlock", "BloodTheme")



local Tab = Window:NewTab("MAIN")
local Section = Tab:NewSection("MAIN")



Section:NewButton("FLY (X)", "this fly only works for R15 lol", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/iluvje54/fly/main/ok"))()
end)

Section:NewButton("ANIMATIONS", "Once Injected it will give you Kimbladi Animations", function()
    local L_206_ = game.Players.LocalPlayer.Character.Animate
    L_206_.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=782841498"
    L_206_.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=782845736"
    L_206_.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616168032"
    L_206_.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616163682"
    L_206_.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=5319841935"
    L_206_.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=707829716"
    game.Players.LocalPlayer.Character.Humanoid.Jump = true
wait(1)

end)

Section:NewButton("ANTI STOMP (Cannot Be Turned Off)", "gay function", function()
     loadstring(game:HttpGet("https://raw.githubusercontent.com/BlueaqeR/scripts-lol/main/Da%20Hood%20Anti%20Stomp%20(Optimized)"))()
     print("Clicked")
     
end)


local Tab = Window:NewTab("AIMING")
local Section = Tab:NewSection("AIMLOCK")

Section:NewButton("AIMLOCK (Q)", "Q To lock on, T to toggle aimbot on and off.", function()
    getgenv().AimPart = "HumanoidRootPart" -- For R15 Games: {UpperTorso, LowerTorso, HumanoidRootPart, Head} | For R6 Games: {Head, Torso, HumanoidRootPart}
    getgenv().AimlockToggleKey = "t" -- Toggles Aimbot On/Off
    getgenv().AimlockKey = "q"
    getgenv().AimRadius = 35 -- How far away from someones character you want to lock on at
    getgenv().ThirdPerson = true
    getgenv().FirstPerson = true
    getgenv().TeamCheck = false -- Check if Target is on your Team (True means it wont lock onto your teamates, false is vice versa) (Set it to false if there are no teams)
    getgenv().PredictMovement = true -- Predicts if they are moving in fast velocity (like jumping) so the aimbot will go a bit faster to match their speed
    getgenv().PredictionVelocity = 10
    getgenv().CheckIfJumped = true
    getgenv().AutoPrediction = true
    local L_28_, L_29_, L_30_, L_31_ = game:GetService"Players", game:GetService"UserInputService", game:GetService"RunService", game:GetService"StarterGui";
    local L_32_, L_33_, L_34_, L_35_, L_36_, L_37_, L_38_ = L_28_.LocalPlayer, L_28_.LocalPlayer:GetMouse(), workspace.CurrentCamera, CFrame.new, Ray.new, Vector3.new, Vector2.new;
    local L_39_, L_40_, L_41_ = true, false, false;
    local L_42_;
    getgenv().CiazwareUniversalAimbotLoaded = true
    getgenv().WorldToViewportPoint = function(L_43_arg0)
        return L_34_:WorldToViewportPoint(L_43_arg0)
    end
    getgenv().WorldToScreenPoint = function(L_44_arg0)
        return L_34_.WorldToScreenPoint(L_34_, L_44_arg0)
    end
    getgenv().GetObscuringObjects = function(L_45_arg0)
        if L_45_arg0 and L_45_arg0:FindFirstChild(getgenv().AimPart) and L_32_ and L_32_.Character:FindFirstChild("Head") then
            local L_46_ = workspace:FindPartOnRay(L_36_(
        L_45_arg0[getgenv().AimPart].Position, L_32_.Character.Head.Position)
    )
            if L_46_ then
                return L_46_:IsDescendantOf(L_45_arg0)
            end
        end
    end
    getgenv().GetNearestTarget = function()
        local L_47_ = {}
        local L_48_  = {}
        local L_49_ = {}
        for L_51_forvar0, L_52_forvar1 in pairs(L_28_:GetPlayers()) do
            if L_52_forvar1 ~= L_32_ then
                table.insert(L_47_, L_52_forvar1)
            end
        end
        for L_53_forvar0, L_54_forvar1 in pairs(L_47_) do
            if L_54_forvar1.Character ~= nil then
                local L_55_ = L_54_forvar1.Character:FindFirstChild("Head")
                if getgenv().TeamCheck == true and L_54_forvar1.Team ~= L_32_.Team then
                    local L_56_ = (L_54_forvar1.Character:FindFirstChild("Head").Position - game.Workspace.CurrentCamera.CFrame.p).magnitude
                    local L_57_ = Ray.new(game.Workspace.CurrentCamera.CFrame.p, (L_33_.Hit.p - game.Workspace.CurrentCamera.CFrame.p).unit * L_56_)
                    local L_58_, L_59_ = game.Workspace:FindPartOnRay(L_57_, game.Workspace)
                    local L_60_ = math.floor((L_59_ - L_55_.Position).magnitude)
                    L_48_[L_54_forvar1.Name .. L_53_forvar0] = {}
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].dist = L_56_
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].plr = L_54_forvar1
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].diff = L_60_
                    table.insert(L_49_, L_60_)
                elseif getgenv().TeamCheck == false and L_54_forvar1.Team == L_32_.Team then
                    local L_61_ = (L_54_forvar1.Character:FindFirstChild("Head").Position - game.Workspace.CurrentCamera.CFrame.p).magnitude
                    local L_62_ = Ray.new(game.Workspace.CurrentCamera.CFrame.p, (L_33_.Hit.p - game.Workspace.CurrentCamera.CFrame.p).unit * L_61_)
                    local L_63_, L_64_ = game.Workspace:FindPartOnRay(L_62_, game.Workspace)
                    local L_65_ = math.floor((L_64_ - L_55_.Position).magnitude)
                    L_48_[L_54_forvar1.Name .. L_53_forvar0] = {}
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].dist = L_61_
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].plr = L_54_forvar1
                    L_48_[L_54_forvar1.Name .. L_53_forvar0].diff = L_65_
                    table.insert(L_49_, L_65_)
                end
            end
        end
        if unpack(L_49_) == nil then
            return nil
        end
        local L_50_ = math.floor(math.min(unpack(L_49_)))
        if L_50_ > getgenv().AimRadius then
            return nil
        end
        for L_66_forvar0, L_67_forvar1 in pairs(L_48_) do
            if L_67_forvar1.diff == L_50_ then
                return L_67_forvar1.plr
            end
        end
        return nil
    end
    L_33_.KeyDown:Connect(function(L_68_arg0)
        if L_68_arg0 == AimlockKey and L_42_ == nil then
            pcall(function()
                if L_40_ ~= true then
                    L_40_ = true
                end
                local L_69_;
                L_69_ = GetNearestTarget()
                if L_69_ ~= nil then
                    L_42_ = L_69_
                end
            end)
        elseif L_68_arg0 == AimlockKey and L_42_ ~= nil then
            if L_42_ ~= nil then
                L_42_ = nil
            end
            if L_40_ ~= false then
                L_40_ = false
            end
        elseif L_68_arg0 == AimlockToggleKey then
            L_39_ = not L_39_
        end
    end)
    L_30_.RenderStepped:Connect(function()
        if getgenv().ThirdPerson == true and getgenv().FirstPerson == true then
            if (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude > 1 or (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude <= 1 then
                L_41_ = true
            else
                L_41_ = false
            end
        elseif getgenv().ThirdPerson == true and getgenv().FirstPerson == false then
            if (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude > 1 then
                L_41_ = true
            else
                L_41_ = false
            end
        elseif getgenv().ThirdPerson == false and getgenv().FirstPerson == true then
            if (L_34_.Focus.p - L_34_.CoordinateFrame.p).Magnitude <= 1 then
                L_41_ = true
            else
                L_41_ = false
            end
        end
        if L_39_ == true and L_40_ == true then
            if L_42_ and L_42_.Character and L_42_.Character:FindFirstChild(getgenv().AimPart) then
                if getgenv().FirstPerson == true then
                    if L_41_ == true then
                        if getgenv().PredictMovement == true then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position + L_42_.Character[getgenv().AimPart].Velocity / PredictionVelocity)
                        elseif getgenv().PredictMovement == false then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position)
                        end
                    end
                elseif getgenv().ThirdPerson == true then
                    if L_41_ == true then
                        if getgenv().PredictMovement == true then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position + L_42_.Character[getgenv().AimPart].Velocity / PredictionVelocity)
                        elseif getgenv().PredictMovement == false then
                            L_34_.CFrame = L_35_(L_34_.CFrame.p, L_42_.Character[getgenv().AimPart].Position)
                        end
                    end
                end
            end
        end
    end)
end)



Section:NewButton("SILENT AIM", "silent aim", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/tayodevelup/imsoniac/main/silentaim", true))()
    print("Clicked")
end)


local Tab = Window:NewTab("MOVEMENT")
local Section = Tab:NewSection("MOVEMENT")

Section:NewButton("FAST SPEED (C)", "fast speed", function()
    plr = game:GetService('Players').LocalPlayer
    down = true
    
    function onButton1Down(mouse)
        down = true
        while down do
            if not down then break end
            local char = plr.Character
            char.HumanoidRootPart.Velocity = char.HumanoidRootPart.CFrame.lookVector * 190
            wait()
        end
    end
    
    function onButton1Up(mouse)
        down = false
    end
    
    function onSelected(mouse)
        mouse.KeyDown:connect(function(c) if c:lower()=="c"then onButton1Down(mouse)end end)
        mouse.KeyUp:connect(function(c) if c:lower()=="c"then onButton1Up(mouse)end end)
    end
    onSelected(game.Players.LocalPlayer:GetMouse())
end
)


local Tab = Window:NewTab("TELEPORTS")
local Section = Tab:NewSection("TELEPORTS")

Section:NewButton("BANK", "Teleports Player To Bank.", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-318.891174, 80.2145309, -257.177429, 0.0479469746, -5.14644114e-08, 0.998850107, -3.12971538e-09, 1, 5.16738901e-08, -0.998850107, -5.60372015e-09, 0.0479469746)
end)

Section:NewButton("ADMIN GUNS", "Teleports Player To Admin Guns.", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-872.853516, -34.4276848, -538.013306, -0.999724388, -3.9898886e-08, -0.0234765243, -3.9204977e-08, 1, -3.00177518e-08, 0.0234765243, -2.90890814e-08, -0.999724388)
    end)

    Section:NewButton("rev roof", "Teleports Player To Revolver.", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-634.463135, 80.434761, -204.232559, -0.0190527271, -1.03574322e-07, -0.999818563, 4.36709335e-09, 1, -1.03676342e-07, 0.999818563, -6.3416179e-09, -0.0190527271)
       
    end)

    Section:NewButton("RPG", "Teleports Player To RPG.", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(139.815933, -22.9016266, -136.737762, 0.0339428484, -7.90177737e-08, 0.999423802, -4.7851227e-08, 1, 8.06884728e-08, -0.999423802, -5.0562452e-08, 0.0339428484)
        
    end)

    local Tab = Window:NewTab("AUTO BUYS")
    local Section = Tab:NewSection("AUTO BUYS")

    Section:NewButton("DOUBLE BARREL", "Auto Buys DB.", function()
        L_10_ = game:GetService'Players'.LocalPlayer
        local L_504_ = game.Workspace.Ignored.Shop['[Double-Barrel SG] - $1400']
        local L_505_ = L_10_.Character.HumanoidRootPart.Position
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_504_.Head.CFrame + Vector3.new(0, 3, 0)
        wait(0.5)
        fireclickdetector(game.Workspace.Ignored.Shop['[Double-Barrel SG] - $1400'].ClickDetector)
        fireclickdetector(game.Workspace.Ignored.Shop['[Double-Barrel SG] - $1400'].ClickDetector)
        L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_505_)
        L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_505_)
      
        end)

        Section:NewButton("REVOLVER", "Auto Buys Rev.", function()
            L_10_ = game:GetService'Players'.LocalPlayer
            local L_498_ = '[Revolver] - $1300'
            local L_499_ = game.Workspace.Ignored.Shop[L_498_]
            local L_500_ = L_10_.Character.HumanoidRootPart.Position
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_499_.Head.CFrame + Vector3.new(0, 3, 0)
            wait(0.5)
            fireclickdetector(game.Workspace.Ignored.Shop[L_498_].ClickDetector)
            fireclickdetector(game.Workspace.Ignored.Shop[L_498_].ClickDetector)
            L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_500_)
            L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_500_)
        
        end)

        Section:NewButton("DB AMMO", "Auto Buys DB Ammo.", function()
            local L_506_ = game.Workspace.Ignored.Shop['18 [Double-Barrel SG Ammo] - $60']
                local L_507_ = L_10_.Character.HumanoidRootPart.Position
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_506_.Head.CFrame + Vector3.new(0, 3, 0)
                wait(0.5)
                fireclickdetector(game.Workspace.Ignored.Shop['18 [Double-Barrel SG Ammo] - $60'].ClickDetector)
                fireclickdetector(game.Workspace.Ignored.Shop['18 [Double-Barrel SG Ammo] - $60'].ClickDetector)
                L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_507_)
                L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_507_)
               
            end)

            Section:NewButton("REV AMMO", "Auto Buys Rev Ammo.", function()
                L_10_ = game:GetService'Players'.LocalPlayer
                    local L_501_ = '12 [Revolver Ammo] - $75'
                    local L_502_ = game.Workspace.Ignored.Shop[L_501_]
                    local L_503_ = L_10_.Character.HumanoidRootPart.Position
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = L_502_.Head.CFrame + Vector3.new(0, 3, 0)
                    wait(0.5)
                    fireclickdetector(game.Workspace.Ignored.Shop[L_501_].ClickDetector)
                    fireclickdetector(game.Workspace.Ignored.Shop[L_501_].ClickDetector)
                    L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_503_)
                    L_10_.Character.HumanoidRootPart.CFrame = CFrame.new(L_503_)
                    
                end)

                Section:NewButton("ARMOR", "Buys Armor.", function()
                    local plr = game.Players.LocalPlayer
                        local savedarmourpos = plr.Character.HumanoidRootPart.Position
                        plr.Character.HumanoidRootPart.CFrame = CFrame.new(-938.476685, -25.2498264, 570.100159, -0.0353576206, 9.85617206e-08, -0.999374807, -2.69198441e-09, 1, 9.871858e-08, 0.999374807, 6.18077589e-09, -0.0353576206)
                        wait(.2)
                    
                        fireclickdetector(game.Workspace.Ignored.Shop['[High-Medium Armor] - $2300'].ClickDetector)
                        plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
                       
                    end)

        local Tab = Window:NewTab("KEYBIND")
        local Section = Tab:NewSection("UI Keybind")

        Section:NewKeybind("Keybind", "Toggles The UI Visiblity", Enum.KeyCode.V, function()
            Library:ToggleUI()
        end)
        
        
        
        frames = nil

local RunService = game:GetService("RunService")
RunService.RenderStepped:Connect(function(step)
frames = math.floor(1/step)..  " FPS┃Doomware"
end)

function CreateInstance(cls, props) local inst = Instance.new(cls) for i,v in pairs(props) do inst[i] = v end return inst end
local UserInputService = game:GetService("UserInputService")
fpscounter = CreateInstance("ScreenGui", {ZIndexBehavior=Enum.ZIndexBehavior.Global, ResetOnSpawn=false, Name="fpscounter", Parent=game.CoreGui})
syn.protect_gui(fpscounter)
textHolder = CreateInstance("Frame", {BackgroundColor3=Color3.fromRGB(0, 0, 0), BorderColor3=Color3.fromRGB(0, 0, 0), Position=UDim2.new(0.00853788853, 0, 0.0364473727, 0), Size=UDim2.new(0, 129, 0, 33), Name = "textHolder", Parent=fpscounter})
border = CreateInstance("Frame", {BackgroundColor3=Color3.fromRGB(0, 0, 0), BorderColor3=Color3.fromRGB(0, 0, 0), BorderSizePixel=0, Position=UDim2.new(0.00999999978, 0, 0.0520000011, 0), Size=UDim2.new(0, 128, 0, 30), Name="border", Parent=textHolder})
gradient = CreateInstance("Frame", {Name="gradient", Parent=textHolder, BackgroundColor3=Color3.fromRGB(255, 255, 255), BorderSizePixel=0, Position = UDim2.new(0.00999999978, 0, 0.0289999992, 0), Size = UDim2.new(0, 127, 0, 3) })
UIGradient = CreateInstance("UIGradient", {Color=ColorSequence.new{ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 0, 0)), ColorSequenceKeypoint.new(0.51, Color3.fromRGB(255, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 0, 0))}, Name="UIGradient", Parent=gradient})
fps = CreateInstance("TextLabel", {BackgroundColor3=Color3.fromRGB(255, 255, 255), BackgroundTransparency=1, Position=UDim2.new(0.0100000072, 0, 0.18051517, 0), Size=UDim2.new(0, 127, 0, 20), Font=Enum.Font.Code, Text="Doomware", TextColor3=Color3.fromRGB(255, 255, 255), TextSize=16, Name="FPS", Parent=textHolder})

local loop = "chimkin"
repeat
    wait(.10)
fps.Text = (frames)
until loop == "rice"
