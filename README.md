local MarketplaceService = game:GetService("MarketplaceService")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local HttpService = game:GetService("HttpService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local player = Players.LocalPlayer
local PlayerGui = player:WaitForChild("PlayerGui")
local GuiName = "Mod_Animal_Simulator_BoxMusic_" .. player.Name

-- 🔹 Lista local de músicas
local listMusics = {
	{name = "LOGOKIDS Prismz", Obj = 105633366460252},
	{name = "MONTAGEM SUCESSO", Obj = 129112111571462},
	{name = "scary", Obj = 71956674693421},
	{name = "Empina na onda (feito por keven)", Obj = 104621031886653},
	{name = "MORTAL", Obj = 126713629899826},
	{name = "CRYSTAL CASTLES - LENI ( SLOWED )", Obj = 7758971561},
	{name = "Ghost Fight (Hard Bounce Flip)", Obj = 94494416095572},
	{name = "All I Wanted Was You", Obj = 123744226884947},
	{name = "Darskuu - JXRSXY WAVE", Obj = 18841893567},
	{name = "Montagem Pesadelo", Obj = 100431599013708},
	{name = "MTG ZUM ZUM ZUM VIRAL FUNK BH", Obj = 92446612272052},
	{name = "lump lumps", Obj = 111564073986749},
	{name = "Cold Cannon", Obj = 74312901272425},
	{name = "Forsaken Dominion", Obj = 75805949198978},
	{name = "Embora", Obj = 131847084942844},
	{name = "//MACH:BREAKER", Obj = 108710061480904},
	{name = "Viver bem", Obj = 82805460494325},
	{name = "Eu nao estou louco FUNKO", Obj = 74366765967475},
	{name = "oiioiiooi", Obj = 105663787518318},
	{name = "505 timess", Obj = 85994915142182},
	{name = "Pancadão", Obj = 76312991186384},
	{name = "MONTAGEM SKY HIGH", Obj = 123517126955383},
	{name = "stronger than ya chara response", Obj = 96357207714662},
	{name = "Fat Rat", Obj = 106732317934236},
	{name = "A Engimatical Encounter", Obj = 115656438192853},
	{name = "no way but today good", Obj = 79203556648142},
	{name = "tigerstrpes246's Place", Obj = 282837838},
	{name = "my phone", Obj = 121489264497741},
	{name = "d3r - love bomb", Obj = 18841888868},
	{name = "Useless", Obj = 105560839345019},
	{name = "kawaii", Obj = 130867828528278},
	{name = "wrecked jeep", Obj = 18392456},
	{name = "Gasolina (Clean)", Obj = 1222970641},
	{name = "Jay Cosmic - Ocean Eyes", Obj = 5410085296},
	{name = "National Anthem of the U.S.S.R.", Obj = 97413868131214},
	{name = "tambien adios", Obj = 139202008782317},
	{name = "Lil Kuudere, sukoyomi - Alone", Obj = 16190782786},
	{name = "Vei Next Solto (Slowed)", Obj = 74697049223758},
	{name = "Tele", Obj = 104575671082804},
	{name = "gang kitteh", Obj = 69370423},
	{name = "melodia de verão (tiktok edit)", Obj = 118507373399694},
	{name = "SAKU - GTA (Nightcore)", Obj = 14366981664},
	{name = "shonci x HR - sinistra", Obj = 15689443663},
	{name = "So clean", Obj = 93958751571254},
	{name = "Stray", Obj = 120102995443063},
	{name = "Batidão na Aldeia (Musica Oficial)", Obj = 79953696595578},
	{name = "V8 speed up", Obj = 85182585406642},
	{name = "DJ Sol - GATA ONLY (FloyyMenor ft. Cris MJ)", Obj = 16775242837},
	{name = "swurve swurving", Obj = 93245387354226},
	{name = "Closest", Obj = 96766736102830},
	{name = "SILVERADO", Obj = 126786072288744},
	{name = "Gangstas Paradise (Loop)", Obj = 6070263388},
	{name = "SAVAGE GHOST SLOWED Phonk (Super Slowed)", Obj = 72811197789142},
	{name = "bing", Obj = 75146085667327},
	{name = "Moscow", Obj = 132973772452511},
	{name = "Song title_Song title", Obj = 140563236804727},
	{name = "MONTAGEM RENICHT CALAMITY [LOOP]", Obj = 70961757130479},
	{name = "OFFLINE", Obj = 92715012838361},
	{name = "Em dezembro de 81 (Lxz)", Obj = 92492039534399},
	{name = "edit", Obj = 126372814380356},
	{name = "FOOTBALL FUNK!", Obj = 132563559976693},
	{name = "Trying", Obj = 91853707949855},
	{name = "She's So Dumb", Obj = 1836654054},
	{name = "ID 666!", Obj = 66666666},
	{name = "The Sky", Obj = 82757474758500},
	{name = "yoy799 she loves me", Obj = 103524199324615},
	{name = "HandSky", Obj = 112930367758222},
	{name = "ORA | Confident", Obj = 128419110610708},
	{name = "You Ain't Hot Enough", Obj = 1837006787},
	{name = "Hammer of Justice", Obj = 109606503605402},
	{name = "aw YEA", Obj = 139218946376655},
	{name = "okay tyler", Obj = 127219133263020},
	{name = "LUKN88's Place", Obj = 9828726},
	{name = "Dopamine Rat", Obj = 77766610441787},
	{name = "โยกย้าย", Obj = 81244086617866},
	{name = "FUNK ALL THE TIME", Obj = 123809083385992},
	{name = "Mix Plan B 2025", Obj = 109691993069247},
	{name = "Cool", Obj = 87909146687252},
	{name = "Ka$tro - I Gave You Everything", Obj = 16831103945},
	{name = "JÁ QUE ME ENSINOU A BEBER", Obj = 18640530697},
	{name = "M3M0R1ES", Obj = 125286594503659},
	{name = "Arrepia XL 2", Obj = 73962723234161},
	{name = "Tired Of You", Obj = 1837014531},
	{name = "WannaBeHer", Obj = 120885023497936},
	{name = "See you again", Obj = 139334528864199},
	{name = "SAD!", Obj = 72320758533508},
	{name = "Sa hara", Obj = 130437050908450},
	{name = "SOLDIER", Obj = 87554448466409},
	{name = "Model 399", Obj = 87766662},
	{name = "unleaked bypassed song", Obj = 137155874195108},
	{name = "Lil Peep - Save That", Obj = 1189399253},
	{name = "Morning Mood", Obj = 1846088038},
	{name = "Dexter King - Only You", Obj = 7024028859},
	{name = "eu sou pinxadão", Obj = 11287191099},
	{name = "MONTAGEM BALANÇO - Super slowed", Obj = 77356972740459},
	{name = "Auto toma", Obj = 86685635786943},
	{name = "Gothic Song", Obj = 75982342509801},
	{name = "Arrepia XL 5", Obj = 70782176012619},
	{name = "100% Forrozin De Vaquejada", Obj = 92295159623916},
	{name = "BRAZILIAN DRIFT MUSIC", Obj = 116874163291138},
	{name = "these are jeans", Obj = 93218265275853},
	{name = "Lola Tumba La Casa", Obj = 98296077509691},
	{name = "introduce", Obj = 104567749101480},
	{name = "Sto", Obj = 128214703292900},
	{name = "Black Knife", Obj = 104449595639237},
	{name = "Brazilian Phonk Fiesta", Obj = 125498129824026},
	{name = "MONTAGEM BIONICA DIAMANTE", Obj = 80012111977834},
	{name = "bell", Obj = 6937042327},
	{name = "SHADOWS", Obj = 122761529841977},
	{name = "0to8,1xmxxd - stop posting about baller", Obj = 13530439660},
	{name = "UNFORESEEABLE", Obj = 71392021424658},
	{name = "Moonlighthood", Obj = 122389825417820},
	{name = "NUMB 67", Obj = 122854357582130},
	{name = "Spooky Halloween", Obj = 120747304076792},
	{name = "PASSO BEM SOLTO SUBMUNDO", Obj = 111318048787674},
	{name = "Blessed Mane - Death Is No More", Obj = 16831108393},
	{name = "CUTEMAKMAKFUNK (Slowed)", Obj = 120871403922972},
	{name = "partyyy!!!", Obj = 138790348719069},
	{name = "DOOM ETERNAL", Obj = 97557092981429},
	{name = "Sparo loop", Obj = 9124780123},
	{name = "jumpstyle", Obj = 85833437298815},
	{name = "stokeerr's Place", Obj = 39382284},
	{name = "Never Grow Up", Obj = 1836654190},
	{name = "GATINHA", Obj = 131689610122547},
	{name = "For the Summer", Obj = 1837111443},
	{name = "Stop", Obj = 0},
	{name = "Want To Love", Obj = 104846670980072},
	{name = "ABC (a)", Obj = 1839907924},
	{name = "MONTAGEM ELECTRONICA", Obj = 132517043416676},
	{name = "dicealt84702's Place", Obj = 693704232},
	{name = "VITRIOL", Obj = 87658459636001},
	{name = "Favela Funk 60", Obj = 1841683877},
	{name = "No Era Amor", Obj = 112748273890049},
	{name = "MESMERIZER", Obj = 71934965392436},
	{name = "nMisaki - Dubidubidu", Obj = 16190783444},
	{name = "Remember the Soul", Obj = 113184121463834},
	{name = "Seguuura", Obj = 96974354995715},
	{name = "Montagem Tomada", Obj = 114727662968481},
	{name = "106846365 S", Obj = 184183877},
	{name = "love on love on me yeah", Obj = 9087418452},
	{name = "Red Chains", Obj = 102402883551679},
	{name = "BEM SOLTO BRAZIL!", Obj = 119936139925486},
	{name = "Din1c - Dionic 2", Obj = 15689445424},
	{name = "klnoLOZ303", Obj = 105423792227242},
	{name = "TUNG TUNG SAHUR FUNK", Obj = 137234649215284},
	{name = "Starvation", Obj = 135090256319340},
	{name = "Din1c - can you", Obj = 15689448519},
	{name = "Parry Gripp - Chicken Nugget", Obj = 9245561450},
	{name = "elephant_sound_effect_1", Obj = 10944727000},
	{name = "Mente ma", Obj = 98337901681441},
	{name = "BAD", Obj = 127512475318182},
	{name = "V7 (XL & NGI)", Obj = 80348640826643},
	{name = "DriveBlox Unlimited Fan Club", Obj = 70803329},
	{name = "MONTAGEM BANDIDO 2.0", Obj = 120138115344262},
	{name = "The World Between Us", Obj = 117236780703437},
	{name = "montagem do silvio", Obj = 104828343009296},
	{name = "onsd", Obj = 81299332131868},
	{name = "Schnuffel", Obj = 100697759026652},
	{name = "Nakshatrame", Obj = 129345087920607},
	{name = "Millonario DJ Raul", Obj = 118322804860765},
	{name = "california spoil ya", Obj = 17422207760},
	{name = "Cute Christmas Song", Obj = 80402505796221},
	{name = "Masha And the Bear", Obj = 1466979183},
	{name = "Some Type of Way", Obj = 131299433678658},
	{name = "bing chilling", Obj = 132799308298378},
	{name = "BEM SOLTO BRAZIL (Slowed)", Obj = 119935980067657},
}

-- Carrega o módulo Regui
local Regui
-- 1️⃣ Tenta carregar localmente
local success, module = pcall(function()
	return require(script.Parent:FindFirstChild("Mod_UI"))
end)

if success and module then
	Regui = module
	print("[✅ Mod Loader] Carregado localmente com sucesso!")
else
	-- 2️⃣ Tenta baixar remoto
	local ok, code
	local urls = {
		"https://raw.githubusercontent.com/AdrainRazini/mastermod/refs/heads/main/module/dataGui.lua",
		"https://animal-simulator-server.vercel.app/lua/DataGui.lua"
	}

	for _, url in ipairs(urls) do
		local okHttp, result = pcall(function()
			return game:HttpGet(url)
		end)
		if okHttp and result and result ~= "" then
			code = result
			print("[🌐 Mod Loader] Código baixado de: " .. url)
			break
		else
			warn("[⚠️ Mod Loader] Falha ao baixar de:", url)
		end
	end

	-- 3️⃣ Executa o código remoto se baixado
	if code then
		local okLoad, result = pcall(function()
			return loadstring(code)() 
		end)
		if okLoad and result then
			Regui = result
			print("[✅ Mod Loader] Módulo remoto carregado com sucesso!")
		else
			warn("[❌ Mod Loader] Erro ao executar código remoto:", result)
		end
	else
		warn("[❌ Mod Loader] Nenhuma das fontes pôde ser carregada.")
	end
end

assert(Regui, "Regui não foi carregado!")



-- Impede duplicação da GUI
if PlayerGui:FindFirstChild(GuiName) then
	Regui.Notifications(PlayerGui, {Title="Alert", Text="Neutralized Code", Icon="fa_rr_information", Tempo=10})
	return
end

-- Configuração de som via evento remoto
local playEvent = ReplicatedStorage:WaitForChild("Events"):WaitForChild("PLAYEvent")

-- Índice da faixa atual
local currentIndex = 1
local isPlaying = false
local Loading = false

--==========================--
-- GUI PRINCIPAL
--==========================--
local GL1 = {}
local Data_Icon = Regui.Icons

GL1["Scren"] = Instance.new("ScreenGui")
GL1["Scren"].Parent = PlayerGui
GL1["Scren"].Name = GuiName

GL1["frame"] = Instance.new("Frame")
GL1["frame"].Parent = GL1["Scren"]
GL1["frame"].Size = UDim2.new(0, 360, 0, 150)
GL1["frame"].Position = UDim2.new(0.5, -180, 0.8, -65)
GL1["frame"].BackgroundColor3 = Color3.fromRGB(35, 35, 35)
GL1["frame"].BorderSizePixel = 0
GL1["frame"].BackgroundTransparency = 0.1

-- Cantos arredondados
local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 10)
corner.Parent = GL1["frame"]

-- Sombras suaves
local shadow = Instance.new("ImageLabel")
shadow.Parent = GL1["frame"]
shadow.ZIndex = -1
shadow.Image = "rbxassetid://1316045217"
shadow.ImageTransparency = 0.6
shadow.ScaleType = Enum.ScaleType.Slice
shadow.SliceCenter = Rect.new(10,10,118,118)
shadow.Size = UDim2.new(1, 20, 1, 20)
shadow.Position = UDim2.new(0, -10, 0, -10)
shadow.BackgroundTransparency = 1

-- ==========================
-- 🔝 Top Bar
-- ==========================
GL1["TopBar"] = Instance.new("Frame")
GL1["TopBar"].Parent = GL1["frame"]
GL1["TopBar"].Size = UDim2.new(1, 0, 0, 28)
GL1["TopBar"].BackgroundColor3 = Color3.fromRGB(25, 25, 25)
GL1["TopBar"].BorderSizePixel = 0

local topCorner = Instance.new("UICorner")
topCorner.CornerRadius = UDim.new(0, 10)
topCorner.Parent = GL1["TopBar"]

GL1["TopBar_Label"] = Instance.new("TextLabel")
GL1["TopBar_Label"].Parent = GL1["TopBar"]
GL1["TopBar_Label"].Size = UDim2.new(1, -60, 1, 0)
GL1["TopBar_Label"].Position = UDim2.new(0, 10, 0, 0)
GL1["TopBar_Label"].BackgroundTransparency = 1
GL1["TopBar_Label"].Text = "🎵 Player Music"
GL1["TopBar_Label"].TextColor3 = Color3.fromRGB(255, 255, 255)
GL1["TopBar_Label"].TextXAlignment = Enum.TextXAlignment.Left
GL1["TopBar_Label"].Font = Enum.Font.GothamBold
GL1["TopBar_Label"].TextScaled = true

-- Botão de minimizar
GL1["MinimizeBtn"] = Instance.new("TextButton")
GL1["MinimizeBtn"].Parent = GL1["TopBar"]
GL1["MinimizeBtn"].Size = UDim2.new(0, 25, 1, 0)
GL1["MinimizeBtn"].Position = UDim2.new(1, -25, 0, 0)
GL1["MinimizeBtn"].BackgroundColor3 = Color3.fromRGB(220, 60, 60)
GL1["MinimizeBtn"].Text = "-"
GL1["MinimizeBtn"].TextColor3 = Color3.fromRGB(255,255,255)
GL1["MinimizeBtn"].TextScaled = true
GL1["MinimizeBtn"].Font = Enum.Font.GothamBold

local btnCorner = Instance.new("UICorner")
btnCorner.CornerRadius = UDim.new(0, 6)
btnCorner.Parent = GL1["MinimizeBtn"]

-- Botão lista lateral
GL1["MinimizeBtn_List"] = Instance.new("TextButton")
GL1["MinimizeBtn_List"].Parent = GL1["TopBar"]
GL1["MinimizeBtn_List"].Size = UDim2.new(0, 25, 1, 0)
GL1["MinimizeBtn_List"].Position = UDim2.new(1, -55, 0, 0)
GL1["MinimizeBtn_List"].BackgroundColor3 = Color3.fromRGB(70, 70, 200)
GL1["MinimizeBtn_List"].Text = "≡"
GL1["MinimizeBtn_List"].TextColor3 = Color3.fromRGB(255,255,255)
GL1["MinimizeBtn_List"].TextScaled = true
GL1["MinimizeBtn_List"].Font = Enum.Font.GothamBold

local btnCorner2 = Instance.new("UICorner")
btnCorner2.CornerRadius = UDim.new(0, 6)
btnCorner2.Parent = GL1["MinimizeBtn_List"]

-- ==========================
-- 🎵 Nome da música
-- ==========================
GL1["Name_id"] = Instance.new("TextLabel")
GL1["Name_id"].Parent = GL1["frame"]
GL1["Name_id"].Size = UDim2.new(1, -20, 0, 25)
GL1["Name_id"].Position = UDim2.new(0, 10, 0, 30)
GL1["Name_id"].BackgroundTransparency = 1
GL1["Name_id"].Text = "♪ Tocando: (nenhuma faixa)"
GL1["Name_id"].TextColor3 = Color3.fromRGB(255, 255, 255)
GL1["Name_id"].Font = Enum.Font.GothamSemibold
GL1["Name_id"].TextScaled = true
GL1["Name_id"].TextXAlignment = Enum.TextXAlignment.Left

-- ==========================
-- 💿 Ícone do CD
-- ==========================
GL1["CD_Icon"] = Instance.new("ImageLabel")
GL1["CD_Icon"].Parent = GL1["frame"]
GL1["CD_Icon"].Size = UDim2.new(0, 90, 0, 90)
GL1["CD_Icon"].Position = UDim2.new(0, 15, 0.5, -15)
GL1["CD_Icon"].Image = "rbxassetid://70716433051234"
GL1["CD_Icon"].BackgroundTransparency = 1

-- ==========================
-- ▶️ Botões de controle
-- ==========================
GL1["Input_Angle_L"] = Instance.new("ImageButton")
GL1["Input_Angle_L"].Parent = GL1["frame"]
GL1["Input_Angle_L"].Size = UDim2.new(0, 45, 0, 45)
GL1["Input_Angle_L"].Position = UDim2.new(0, 100, 0.5, 10)
GL1["Input_Angle_L"].BackgroundTransparency = 1
GL1["Input_Angle_L"].Image = Data_Icon.fa_rr_angle_left

GL1["Input_Bnt"] = Instance.new("ImageButton")
GL1["Input_Bnt"].Parent = GL1["frame"]
GL1["Input_Bnt"].Size = UDim2.new(0, 45, 0, 45)
GL1["Input_Bnt"].Position = UDim2.new(0, 140, 0.5, 10)
GL1["Input_Bnt"].BackgroundTransparency = 1
GL1["Input_Bnt"].Image = Data_Icon.fa_bx_play_circle

GL1["Input_Angle_R"] = Instance.new("ImageButton")
GL1["Input_Angle_R"].Parent = GL1["frame"]
GL1["Input_Angle_R"].Size = UDim2.new(0, 45, 0, 45)
GL1["Input_Angle_R"].Position = UDim2.new(0, 180, 0.5, 10)
GL1["Input_Angle_R"].BackgroundTransparency = 1
GL1["Input_Angle_R"].Rotation = 180
GL1["Input_Angle_R"].Image = Data_Icon.fa_rr_angle_left

-- ==========================
-- 📜 Frame lateral (lista)
-- ==========================
GL1["frame_List"] = Instance.new("Frame")
GL1["frame_List"].Parent = GL1["frame"]
GL1["frame_List"].Size = UDim2.new(0, 160, 1, 0)
GL1["frame_List"].Position = UDim2.new(1, 8, 0, 0)
GL1["frame_List"].BackgroundColor3 = Color3.fromRGB(45, 45, 45)
GL1["frame_List"].BorderSizePixel = 0
GL1["frame_List"].Visible = false

local listCorner = Instance.new("UICorner")
listCorner.CornerRadius = UDim.new(0, 10)
listCorner.Parent = GL1["frame_List"]

GL1["Loading_Icon"] = Instance.new("ImageLabel")
GL1["Loading_Icon"].Parent = GL1["frame_List"]
GL1["Loading_Icon"].Size = UDim2.new(0, 80, 0, 80)
GL1["Loading_Icon"].AnchorPoint = Vector2.new(0.5, 0.5)
GL1["Loading_Icon"].Position = UDim2.new(0.5, 0, 0.5, 0)
GL1["Loading_Icon"].Image = Data_Icon.fa_bx_loader
GL1["Loading_Icon"].BackgroundTransparency = 1



--==========================--
-- FUNÇÕES PRINCIPAIS
--==========================--

local function playCurrentTrack(selectedObj)
	local id

	-- Se veio do seletor, use o ID dele
	if selectedObj then
		id = selectedObj
	else
		-- Caso contrário, use o índice atual
		id = listMusics[currentIndex].Obj
	end

	if not id then return end

	-- Envia para o servidor tocar a música
	playEvent:FireServer(id)

	-- Atualiza o texto do rótulo
	GL1["Name_id"].Text = "♪ Tocando: " .. listMusics[currentIndex].name

	isPlaying = true
	GL1["Input_Bnt"].Image = Data_Icon.fa_bx_pause_circle
end


local function pauseTrack()
	playEvent:FireServer("0") -- Envia sinal para parar o som
	GL1["Name_id"].Text = "⏸️ Pausado"
	isPlaying = false
	GL1["Input_Bnt"].Image = Data_Icon.fa_bx_play_circle
end


-- Clique Play/Pause
GL1["Input_Bnt"].MouseButton1Click:Connect(function()
	if isPlaying then
		pauseTrack()
	else
		playCurrentTrack()
	end
end)

-- Botão anterior
GL1["Input_Angle_L"].MouseButton1Click:Connect(function()
	currentIndex -= 1
	if currentIndex < 1 then
		currentIndex = #listMusics
	end
	playCurrentTrack()
end)

-- Botão próxima
GL1["Input_Angle_R"].MouseButton1Click:Connect(function()
	currentIndex += 1
	if currentIndex > #listMusics then
		currentIndex = 1
	end
	playCurrentTrack()
end)


local isMinimized = false
local isMinimized_L = true

-- Minimizar o player inteiro
GL1["MinimizeBtn"].MouseButton1Click:Connect(function()
	isMinimized = not isMinimized
	GL1["CD_Icon"].Visible = not isMinimized
	GL1["Input_Angle_L"].Visible = not isMinimized
	GL1["Input_Bnt"].Visible = not isMinimized
	GL1["Input_Angle_R"].Visible = not isMinimized
	GL1["Name_id"].Visible = not isMinimized

	if isMinimized then
		GL1["frame"]:TweenSize(UDim2.new(0, 360, 0, 28), "Out", "Sine", 0.25, true)
	else
		GL1["frame"]:TweenSize(UDim2.new(0, 360, 0, 150), "Out", "Sine", 0.25, true)
	end
end)

-- Minimizar apenas a lista lateral
GL1["MinimizeBtn_List"].MouseButton1Click:Connect(function()
	isMinimized_L = not isMinimized_L

if isMinimized_L then
		GL1["frame_List"]:TweenSize(UDim2.new(0, 25, 1, 0), "Out", "Sine", 0.25, true)
	else
		GL1["frame_List"]:TweenSize(UDim2.new(0, 180, 0, 150), "Out", "Sine", 0.25, true)
	end
	
	GL1["frame_List"].Visible = not isMinimized_L
end)

--==========================--
-- EFEITOS VISUAIS
--==========================--
Regui.applyCorner(GL1["frame"])
Regui.applyDraggable(GL1["frame"], GL1["frame"])

-- Hover
local function applyHover(button)
	button.MouseEnter:Connect(function()
		button.ImageTransparency = 0.2
	end)
	button.MouseLeave:Connect(function()
		button.ImageTransparency = 0
	end)
end

applyHover(GL1["Input_Bnt"])
applyHover(GL1["Input_Angle_L"])
applyHover(GL1["Input_Angle_R"])

-- Rotação do CD
RunService.RenderStepped:Connect(function(dt)
	-- Rotação do CD
	if isPlaying then
		GL1["CD_Icon"].Rotation = (GL1["CD_Icon"].Rotation + dt * 60) % 360
	end

	-- Rotação do Loading
	if Loading then
		GL1["Loading_Icon"].Visible = true
		GL1["Loading_Icon"].Rotation = (GL1["Loading_Icon"].Rotation + dt * 120) % 360 -- você pode deixar mais rápido que o CD
		GL1["frame_List"].Transparency = 1
	else
		GL1["Loading_Icon"].Visible = false
	end
end)


-- Função para criar a lista de nomes
function getnamesbox(list)
	local existingIds = {}

	-- Marca todos os IDs já existentes em listMusics
	for _, music in ipairs(listMusics) do
		existingIds[music.Obj] = true
	end

	-- Processa novos IDs, evitando duplicatas
	for _, id in ipairs(list) do
		if not existingIds[tostring(id)] then
			local success, info = pcall(function()
				return MarketplaceService:GetProductInfo(id)
			end)

			local newMusic = {}
			if success and info then
				newMusic = {name = info.Name, Obj = tostring(id)}
			else
				newMusic = {name = "???", Obj = tostring(id)}
			end

			table.insert(listMusics, newMusic)        -- adiciona direto na lista principal
			existingIds[tostring(id)] = true          -- marca como existente
		end
	end

	return listMusics -- retorna a lista atualizada
end

-- Preenche a lista
local Lista_N
task.spawn(function()
	Loading = true
	Lista_N = getnamesbox(Listaid)

	-- Agora que a lista está pronta, cria o seletor
	local selectorMusics = Regui.CreateSelectorOpitions(GL1["frame_List"], {
		Name = "Selecionar Música",
		Options = Lista_N,
		Type = "Instance",
		Size_Frame = UDim2.new(1, 0, 0, 150)
	}, function(selectedObj)
		playCurrentTrack(selectedObj)
	end)
	Loading = false
end)
