local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "Shadow Hub", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})
local Tab = Window:MakeTab({
	Name = "Nft and buy",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
local Tab1 = Window:MakeTab({
	Name = "Player",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
local Tab2 = Window:MakeTab({
	Name = "Drop",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

Tab:AddTextbox({
	Name = "The banana!",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("The banana")
	end
end 
})

Tab:AddTextbox({
	Name = "Pop It Rainbow!",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("Pop It Rainbow!")
	end
end 
})
Tab:AddTextbox({
	Name = "Lenay",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("Lenay")
	end
end 
})
Tab:AddTextbox({
	Name = "Munnehh",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("Munnehh")
	end
end 
})
Tab:AddTextbox({
	Name = "Trading Ben",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("Trading Ben")
	end
end 
})
Tab:AddTextbox({
	Name = "XOX",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("XOX")
	end
end 
})
Tab:AddTextbox({
	Name = "Mommeh Long Legs",
	Callback = function(txt)
      	for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer("Mommeh Long Legs")
	end
end 
})
Tab:AddTextbox({
	Name = "Custom",
	Callback = function(txt)
      _G.custombuy = txt
end
})
Tab:AddTextbox({
	Name = "numero",
	Callback = function(txt)
      for i = 1,txt do
		wait(0.01)
		game:GetService("ReplicatedStorage").RemoteEvents.BuyItemCash:FireServer(_G.custombuy)
	end
end
})

Tab1:AddButton({
	Name = "xray",
	Callback = function(txt)
     	game.Players.LocalPlayer.XRay.Value = true
		 end

})

Tab1:AddButton({
	Name = "night",
	Callback = function(txt)
     	local Info = TweenInfo.new(3, Enum.EasingStyle.Exponential)
	if game:GetService("Players").LocalPlayer:GetAttribute("IsDay") then
		game:GetService("TweenService"):Create(game:GetService("Lighting"), Info, {ClockTime = 12}):Play()
		game:GetService("Players").LocalPlayer:SetAttribute("IsDay", false)
	else
		game:GetService("TweenService"):Create(game:GetService("Lighting"), Info, {ClockTime = 0}):Play()
		game:GetService("Players").LocalPlayer:SetAttribute("IsDay", true)
	end
	end
})

Tab1:AddTextbox({
Name = "speed",
	Callback = function(txt)
     _G.Speed = txt
	game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = txt
	end
})
coroutine.wrap(function()
	while wait(0.01) do
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 16
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = _G.Speed
	end
end)()


Tab2:AddButton({
Name = "Drop The banana",
	Callback = function(txt)
    for i = 1,15 do
		game:GetService("ReplicatedStorage").RemoteEvents.Equip:FireServer("The banana")
		wait(0.35)
		game:GetService("ReplicatedStorage").RemoteEvents.Drop:FireServer("The banana")
		wait(0.35)
	end

	end
})
Tab2:AddButton({
Name = "Drop Pop It Rainbow!",
	Callback = function(txt)
    for i = 1,15 do
		game:GetService("ReplicatedStorage").RemoteEvents.Equip:FireServer("The banana")
		wait(0.35)
		game:GetService("ReplicatedStorage").RemoteEvents.Drop:FireServer("Drop Pop It Rainbow!")
		wait(0.35)
	end

	end
})

Tab2:AddTextbox({
Name = "Drop Custom",
	Callback = function(txt)
    	_G.dropcustom = txt
	for i = 1,15 do
		game:GetService("ReplicatedStorage").RemoteEvents.Equip:FireServer(_G.dropcustom)
		wait(0.35)
		game:GetService("ReplicatedStorage").RemoteEvents.Drop:FireServer(_G.dropcustom)
		wait(0.35)
	end
end

})

