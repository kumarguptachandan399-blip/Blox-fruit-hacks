-- ================= CONFIG =================
local link = "https://lootdest.org/s?yp5rU7xl"

-- ================= SERVICES =================
local TweenService = game:GetService("TweenService")
local GuiService = game:GetService("GuiService")
local Players = game:GetService("Players")
local Player = Players.LocalPlayer

-- ================= BLUR =================
local blur = Instance.new("BlurEffect")
blur.Size = 0
blur.Parent = game.Lighting
TweenService:Create(blur, TweenInfo.new(0.4), {Size = 10}):Play()

-- ================= GUI CUSTOM =================
local gui = Instance.new("ScreenGui")
gui.Name = "CustomKeyUI"
gui.ResetOnSpawn = false
gui.Parent = Player:WaitForChild("PlayerGui")

local card = Instance.new("Frame", gui)
card.Size = UDim2.new(0,0,0,0)
card.Position = UDim2.new(0.5,0,0.5,0)
card.AnchorPoint = Vector2.new(0.5,0.5)
card.BackgroundColor3 = Color3.fromRGB(255,255,255)
card.BackgroundTransparency = 0.85
card.BorderSizePixel = 0
Instance.new("UICorner", card).CornerRadius = UDim.new(0,22)

TweenService:Create(card, TweenInfo.new(0.5, Enum.EasingStyle.Quint), {
	Size = UDim2.new(0,420,0,300)
}):Play()

local title = Instance.new("TextLabel", card)
title.Text = "Get Keysystem"
title.Font = Enum.Font.GothamBold
title.TextSize = 24
title.BackgroundTransparency = 1
title.Size = UDim2.new(1,0,0,40)
title.Position = UDim2.new(0,0,0,20)

local linkBox = Instance.new("TextBox", card)
linkBox.Text = link
linkBox.ClearTextOnFocus = false
linkBox.TextEditable = false
linkBox.Position = UDim2.new(0,24,0,90)
linkBox.Size = UDim2.new(1,-48,0,45)
linkBox.BackgroundTransparency = 0.6
Instance.new("UICorner", linkBox).CornerRadius = UDim.new(0,14)

local function makeBtn(txt,y,color)
	local b = Instance.new("TextButton", card)
	b.Text = txt
	b.Font = Enum.Font.GothamBold
	b.TextSize = 16
	b.TextColor3 = Color3.new(1,1,1)
	b.BackgroundColor3 = color
	b.Size = UDim2.new(1,-48,0,50)
	b.Position = UDim2.new(0,24,0,y)
	Instance.new("UICorner", b).CornerRadius = UDim.new(0,16)
	return b
end

local copyBtn = makeBtn("Copy Key Link",150,Color3.fromRGB(80,130,245))
local openBtn = makeBtn("Open Link & Continue",210,Color3.fromRGB(60,200,140))

copyBtn.MouseButton1Click:Connect(function()
	linkBox.TextEditable = true
	linkBox:CaptureFocus()
	linkBox.CursorPosition = #linkBox.Text + 1
	linkBox.TextEditable = false
end)

-- ================= LOAD RAYFIELD + KEYSYSTEM =================
local function LoadRayfield()
	gui:Destroy()
	TweenService:Create(blur, TweenInfo.new(0.3), {Size = 0}):Play()
	task.delay(0.35,function() blur:Destroy() end)

	local Rayfield = loadstring(game:HttpGet("https://sirius.menu/rayfield"))()

	local Window = Rayfield:CreateWindow({
		Name = "CGroundHUB",
		LoadingTitle = "Loading Script Hub",
		LoadingSubtitle = "By Fredbear555",
		KeySystem = true,

		KeySettings = {
			Title = "KeysystemXD",
			Subtitle = "Enter Your Key",
			Note = "Get your key from Lootdest link",
			FileName = "CGroundKey",
			SaveKey = true,
			GrabKeyFromSite = true,
			Key = {"https://pastebin.com/raw/gT0ZPWbk"}
		}
	})

	-- ================= MAIN TAB =================
	local MainTab = Window:CreateTab("Main", nil)
	MainTab:CreateSection("Main")

	MainTab:CreateButton({
		Name = "The Forge OP",
		Callback = function()
			loadstring(game:HttpGet("https://pastebin.com/raw/T0CXhVpc"))()
		end
	})

	MainTab:CreateButton({
		Name = "Fish it Secret Instant",
		Callback = function()
			loadstring(game:HttpGet("https://pastefy.app/KU9erY4S/raw"))()
		end
	})

	MainTab:CreateButton({
		Name = "Doors Vynixius Hub",
		Callback = function()
			loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Vynixius/main/Doors/Script.lua"))()
		end
	})

	MainTab:CreateButton({
		Name = "Keyless The Forge Hub",
		Callback = function()
			loadstring(game:HttpGet("https://raw.githubusercontent.com/GiftStein1/pepehook-loader/main/loader.lua"))()
		end
	})

	MainTab:CreateButton({
		Name = "Notoriety Requiem",
		Callback = function()
			loadstring(game:HttpGet("https://scriptblox.com/raw/RUSH-HOUR-Notoriety-Requiem-Evolution-11364"))()
		end
	})

	MainTab:CreateButton({
		Name = "DomainX",
		Callback = function()
			loadstring(game:HttpGet("https://sirius.menu/domainx"))()
		end
	})

	MainTab:CreateButton({
		Name = "Blox Fruit HUB Auto Farm",
		Callback = function()
			loadstring(game:HttpGet("https://pastebin.com/raw/qC1fgwWE"))()
		end
	})

	MainTab:CreateButton({
		Name = "SansmobaHub Keyless",
		Callback = function()
			loadstring(game:HttpGet("https://raw.githubusercontent.com/DyyITT/SansMobaHub/main/Fishit-Free"))()
		end
	})

	MainTab:CreateButton({
		Name = "Backdoor ServerSide",
		Callback = function()
			loadstring(game:HttpGet("https://raw.githubusercontent.com/melinicovyra-cell/Roblox-script/main/Backdoor.%20Executor"))()
		end
	})

	MainTab:CreateButton({
		Name = "Fish it Secret Spam",
		Callback = function()
			loadstring(game:HttpGet("https://pastebin.com/raw/e3HLVYUu"))()
		end
	})

	MainTab:CreateButton({
		Name = "Fish it Force Secret",
		Callback = function()
			loadstring(game:HttpGet("https://pastebin.com/raw/DJ56UEBR"))()
		end
	})

	MainTab:CreateButton({
		Name = "Fish Polluton Hub Keyless",
		Callback = function()
			loadstring(game:HttpGet("https://api.luarmor.net/files/v3/loaders/b9162d4ef4823b2af2f93664cf9ec393.lua"))()
		end
	})

	-- ================= INFO TAB =================
	local InfoTab = Window:CreateTab("Info", nil)
	InfoTab:CreateParagraph({Title="Info",Content="By Fredbear555 In YT"})
	InfoTab:CreateParagraph({Title="Discord",Content="Not have"})
end

openBtn.MouseButton1Click:Connect(function()
	pcall(function()
		GuiService:OpenBrowserWindow(link)
	end)
	LoadRayfield()
end)
