repeat task.wait() until game:IsLoaded()
repeat task.wait() until game.Players
repeat task.wait() until game.Players.LocalPlayer
repeat task.wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui")

local player = game:GetService("Players").LocalPlayer
local playerGui = player:FindFirstChild("PlayerGui")
local mainGui = playerGui and playerGui:FindFirstChild("Main (minimal)")
local chooseTeamGui = mainGui and mainGui:FindFirstChild("ChooseTeam")

if chooseTeamGui then
    repeat
        task.wait()
        if chooseTeamGui.Visible then
            for _, v in pairs(getconnections(chooseTeamGui.Container["Pirates"].Frame.TextButton.Activated)) do
                for _, b in pairs(getconnections(game:GetService("UserInputService").TouchTapInWorld)) do
                    b:Fire() 
                end
                v.Function()
            end
        end
    until player.Team ~= nil and game:IsLoaded()
end

local GodHuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman", true))
if GodHuman == 1 then
    loadstring(game:HttpGet("https://raw.githubusercontent.com/SandKingTH/RawScriptAll/refs/heads/main/Maru_mumu.lua"))()
else
    loadstring(game:HttpGet("https://raw.githubusercontent.com/SandKingTH/RawScriptAll/refs/heads/main/Banana_mumu.lua"))()
    task.spawn(function()
        while true do
            task.wait(300)
            local inv = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventory")
            for _, item in pairs(inv) do
                if item.Type == "FightingStyle" and item.Name == "Godhuman" then
                    game:Shutdown()
                    return
                end
            end
        end
    end)
end
