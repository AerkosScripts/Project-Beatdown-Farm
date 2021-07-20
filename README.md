getgenv().autoTap = false;
getgenv().autoRebirth = false;
getgenv().autoUpgrade = false;
getgenv().buyEgg = false;
getgenv().MissionType = "Pizza", false;				
function DoTap()											
	spawn(function()
		while autoTap == true do 
			game:GetService("ReplicatedStorage").Events.ClickEvent:InvokeServer()
			wait()
		end
	end)
end
DoTap()

function DoRebirth()
	spawn(function()
		while autoRebirth == true do
			local args = {[1] = 5000000000000}
			game:GetService("ReplicatedStorage").Events.Rebirth:InvokeServer(unpack(args))
			wait(1)
		end
	end)
end

DoRebirth()

function DoUpgrade()
	spawn(function()
		while autoUpgrade == true do 
			local args = {[1] = "RebirthButton",[2] = "Buy1"}
			game:GetService("ReplicatedStorage").Events.Upgrade:InvokeServer(unpack(args))
			wait()
		end
	end)
end

function BuyEgg()
	spawn(function()
		while buyEgg == true do
			local args = {[1] = "Youtuber Egg",[2] = "Buy1"}
			game:GetService("ReplicatedStorage").Events.BuyEgg:InvokeServer(unpack(args))
			wait()
		end
	end)
end

BuyEgg()



_G.ToggleColor = Color3.fromRGB(255,0,0)
_G.ButtonColor = Color3.fromRGB(0,255,0)
_G.SliderColor = Color3.fromRGB(0,0,255)

local library = loadstring(game:HttpGet(('https://pastebin.com/raw/FsJak6AT')))() -- It's obfuscated, I won't let you see my ugly coding skills. =)

local w = library:CreateWindow("Clicking Simulator")

local b = w:CreateFolder("Farming")

local c = w:CreateFolder("Pet")

local d = w:CreateFolder("Project Beatdown")

b:DestroyGUI()
	
b:Toggle("Auto Tap",function(bool)
    getgenv().autoTap = bool
    print('Auto Tap is: ', bool)
    if bool then
        DoTap();
    end
end) 

b:Toggle("Auto Rebirth",function(bool)
    getgenv().autoRebirth = bool
    print('Auto Rebirth is: ', bool)
    if bool then
        DoRebirth()
    end
end)

b:Toggle("Auto Upgrade",function(bool)
    getgenv().autoUprgade = bool
    print('Auto Upgrade is: ', bool)
    if bool then
        DoUpgrade()
    end 
end)

c:Toggle("Buy Egg",function(bool)
    getgenv().buyEgg = bool
    print('Buy Egg is: ', bool)
    if bool then
        BuyEgg()
    end 
end)

d:Button("Cash Farm", function(bool)
	getgenv().MissionType = bool
	loadstring(game:HttpGet(("https://pastebin.com/raw/HGvTt4Ef")))()
end)

	
