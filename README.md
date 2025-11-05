local MarketplaceService = game:GetService("MarketplaceService")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local HttpService = game:GetService("HttpService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local player = Players.LocalPlayer
local PlayerGui = player:WaitForChild("PlayerGui")
local GuiName = "Mod_Animal_Simulator_BoxMusic_" .. player.Name






-- Listas estáticas de músicas (Substituindo a chamada de API)
local Listaid = {
    105633366460252,
    129112111571462,
    71956674693421,
    104621031886653,
    126713629899826,
    7758971561,
    94494416095572,
    123744226884947,
    18841893567,
    100431599013708,
    92446612272052,
    111564073986749,
    74312901272425,
    75805949198978,
    131847084942844,
    108710061480904,
    82805460494325,
    74366765967475,
    105663787518318,
    85994915142182,
    76312991186384,
    123517126955383,
    96357207714662,
    106732317934236,
    115656438192853,
    79203556648142,
    282837838,
    121489264497741,
    18841888868,
    105560839345019,
    130867828528278,
    18392456,
    1222970641,
    5410085296,
    97413868131214,
    139202008782317,
    16190782786,
    74697049223758,
    104575671082804,
    69370423,
    118507373399694,
    14366981664,
    15689443663,
    93958751571254,
    120102995443063,
    79953696595578,
    85182585406642,
    16775242837,
    8836490857,
    93245387354226,
    96766736102830,
    126786072288744,
    6070263388,
    72811197789142,
    75146085667327,
    132973772452511,
    140563236804727,
    70961757130479,
    92715012838361,
    92492039534399,
    126372814380356,
    132563559976693,
    91853707949855,
    1836654054,
    66666666,
    82757474758500,
    103524199324615,
    112930367758222,
    128419110610708,
    1837006787,
    109606503605402,
    139218946376655,
    7396636752421,
    127219133263020,
    9828726,
    77766610441787,
    81244086617866,
    123809083385992,
    109691993069247,
    87909146687252,
    16831103945,
    18640530697,
    125286594503659,
    73962723234161,
    1837014531,
    120885023497936,
    139334528864199,
    72320758533508,
    130437050908450,
    87554448466409,
    87766662,
    137155874195108,
    1189399253,
    1846088038,
    7024028859,
    11287191099,
    135911328646170,
    77356972740459,
    7491553701,
    86685635786943,
    75982342509801,
    70782176012619,
    92295159623916,
    116874163291138,
    93218265275853,
    98296077509691,
    104567749101480,
    128214703292900,
    104449595639237,
    125498129824026,
    80012111977834,
    6937042327,
    122761529841977,
    13530439660,
    71392021424658,
    122389825417820,
    122854357582130,
    120747304076792,
    111318048787674,
    16831108393,
    120871403922972,
    138790348719069,
    97557092981429,
    9124780123,
    85833437298815,
    39382284,
    1836654190,
    131689610122547,
    1837111443,
    0,
    104846670980072,
    1839907924,
    132517043416676,
    693704232,
    87658459636001,
    1841683877,
    112748273890049,
    71934965392436,
    16190783444,
    113184121463834,
    96974354995715,
    114727662968481,
    184183877,
    9087418452,
    102402883551679,
    119936139925486,
    15689445424,
    105423792227242,
    137234649215284,
    135090256319340,
    15689448519,
    9245561450,
    10944727000,
    98337901681441,
    127512475318182,
    80348640826643,
    70803329,
    120138115344262,
    117236780703437,
    104828343009296,
    81299332131868,
    100697759026652,
    129345087920607,
    118322804860765,
    17422207760,
    80402505796221,
    1466979183,
    131299433678658,
    6111493245,
    8018464523,
    113324443761127,
    127063071194532,
    13349855413,
    104805787203934,
    97765714111493,
    76164415716559,
    88250097972862,
    16831107981,
    104596909675653,
    97567416166163,
    74326888232570,
    17647322226,
    139693447546059,
    79399386956664,
    110035574248336,
    118939,
    112399975284703,
    96028783423401,
    73774331093132,
    123580060732562,
    121516877792091,
    9044520045,
    128534750062152,
    110772573905578,
    106661099930720,
    11295853276,
    6937042,
    483713947,
    16190784875,
    11222313,
    109840843335222,
    39392828,
    107683146338584,
    17422156627,
    139667113842953,
    121239777513594,
    83566915633358,
    116733221731811,
    93058983119992,
    78744747224727,
    106958630419629,
    95554192381753,
    135690618125311,
    120785124326826,
    137963518593865,
    137172267069591,
    126257401176561,
    77188110491285,
    4659217874,
    1840776993,
    93751275110337,
    6783714255,
    88339486019486,
    112222,
    127868004681532,
    90627119202018,
    123229005251213,
    76194666472201,
    92940982117958,
    132082397247824,
    85075816659415,
    84053362849165,
    85706053877701,
    111611224392490,
    125200420795517,
    83032125898517,
    74564219749776,
    6769,
    71995582569283,
    15689450026,
    133432990940095,
    130781619138449,
    9791154706,
    129212629624727,
    5410082468,
    90567839325615,
    877666629,
    131107293184621,
    128876013372054,
    6519381623,
    89269071829332,
    101378669026310,
    122127808613347,
    105854178411388,
    98839453510161,
    94844025129456,
    103504594968244,
    86511617909610,
    7202579511,
    81700399219236,
    1836847994,
    100379372434844,
    95046091312570,
    6917155909,
    6887728970,
    105044304109159,
    142376088,
    121205882949035,
    81917683155285,
    91233243522140,
    124677276108632,
    4823353998,
    18841891575,
    83914052148279,
    5458852845,
    16190782181,
    86412047196482,
    15689457467,
    97201084418448,
    87233041213837,
    139834501955751,
    666666666,
    6383462613,
    5189952246,
    122925258674975,
    80946196913756,
    99999,
    3982579260,
    5410082097,
    107986977620509,
    1736474219,
    118297487529239,
    1844750628,
    6562534895,
    101456813429584,
    99128910197696,
    79965043381389,
    18396858335,
    1836789357,
    105102042077619,
    128129091062553,
    117634275895085,
    17359243329,
    1839246711,
    72444649335619,
    81552567379452,
    91332435,
    135123528451977,
    5410084802,
    112512564227744,
    97486851158533,
}

local listMusics = {
    {name="LOGOKIDS Prismz", Obj="105633366460252"},
    {name="MONTAGEM SUCESSO", Obj="129112111571462"},
    {name="scary", Obj="71956674693421"},
    {name="Empina na onda (feito por keven)", Obj="104621031886653"},
    {name="MORTAL", Obj="126713629899826"},
    {name="CRYSTAL CASTLES - LENI ( SLOWED )", Obj="7758971561"},
    {name="Ghost Fight (Hard Bounce Flip)", Obj="94494416095572"},
    {name="All I Wanted Was You", Obj="123744226884947"},
    {name="Darskuu - JXRSXY WAVE", Obj="18841893567"},
    {name="Montagem Pesadelo", Obj="100431599013708"},
    {name="MTG ZUM ZUM ZUM VIRAL FUNK BH", Obj="92446612272052"},
    {name="lump lumps", Obj="111564073986749"},
    {name="Cold Cannon", Obj="74312901272425"},
    {name="Forsaken Dominion", Obj="75805949198978"},
    {name="Embora", Obj="131847084942844"},
    {name="//MACH:BREAKER", Obj="108710061480904"},
    {name="Viver bem", Obj="82805460494325"},
    {name="Eu nao estou louco FUNKO", Obj="74366765967475"},
    {name="oiioiiooi", Obj="105663787518318"},
    {name="505 timess", Obj="85994915142182"},
    {name="Pancadão", Obj="76312991186384"},
    {name="MONTAGEM SKY HIGH", Obj="123517126955383"},
    {name="stronger than ya chara response", Obj="96357207714662"},
    {name="Fat Rat", Obj="106732317934236"},
    {name="A Engimatical Encounter", Obj="115656438192853"},
    {name="no way but today good", Obj="79203556648142"},
    {name="tigerstrpes246's Place", Obj="282837838"},
    {name="my phone", Obj="121489264497741"},
    {name="d3r - love bomb", Obj="18841888868"},
    {name="Useless", Obj="105560839345019"},
    {name="kawaii", Obj="130867828528278"},
    {name="wrecked jeep", Obj="18392456"},
    {name="Gasolina  (Clean)", Obj="1222970641"},
    {name="Jay Cosmic - Ocean Eyes", Obj="5410085296"},
    {name="National Anthem of the U.S.S.R.", Obj="97413868131214"},
    {name="tambien adios", Obj="139202008782317"},
    {name="Lil Kuudere, sukoyomi - Alone", Obj="16190782786"},
    {name="Vei Next Solto (Slowed)", Obj="74697049223758"},
    {name="Tele", Obj="104575671082804"},
    {name="gang kitteh", Obj="69370423"},
    {name="melodia de verão (tiktok edit)", Obj="118507373399694"},
    {name="SAKU - GTA (Nightcore)", Obj="14366981664"},
    {name="shonci x HR - sinistra", Obj="15689443663"},
    {name="So clean", Obj="93958751571254"},
    {name="Stray", Obj="120102995443063"},
    {name="Batidão na Aldeia (Musica Oficial)", Obj="79953696595578"},
    {name="V8 speed up", Obj="85182585406642"},
    {name="DJ Sol - GATA ONLY (FloyyMenor ft. Cris MJ) 🖤📱", Obj="16775242837"},
    {name="(Removed for copyright)", Obj="8836490857"},
    {name="swurve swurving", Obj="93245387354226"},
    {name="Closest", Obj="96766736102830"},
    {name="SILVERADO", Obj="126786072288744"},
    {name="Gangstas Paradise (Loop)", Obj="6070263388"},
    {name="SAVAGE GHOST SLOWED Phonk (Super Slowed)", Obj="72811197789142"},
    {name="bing", Obj="75146085667327"},
    {name="Moscow", Obj="132973772452511"},
    {name="Song title_Song title", Obj="140563236804727"},
    {name="MONTAGEM RENICHT CALAMITY [LOOP}", Obj="70961757130479"},
    {name="OFFLINE", Obj="92715012838361"},
    {name="Em dezembro de 81 (Lxz)", Obj="92492039534399"},
    {name="edit", Obj="126372814380356"},
    {name="FOOTBALL FUNK!", Obj="132563559976693"},
    {name="Trying", Obj="91853707949855"},
    {name="She's So Dumb", Obj="1836654054"},
    {name="ID 666!", Obj="66666666"},
    {name="The Sky", Obj="82757474758500"},
    {name="yoy799 she loves me", Obj="103524199324615"},
    {name="HandSky", Obj="112930367758222"},
    {name="ORA | Confident", Obj="128419110610708"},
    {name="You Ain't Hot Enough", Obj="1837006787"},
    {name="Hammer of Justice", Obj="109606503605402"},
    {name="aw YEA", Obj="139218946376655"},
    {name="MONTAGEM LUTA ÉPICA", Obj="7396636752421"},
    {name="okay tyler", Obj="127219133263020"},
    {name="LUKN88's Place", Obj="9828726"},
    {name="Dopamine Rat", Obj="77766610441787"},
    {name="โยกย้าย", Obj="81244086617866"},
    {name="FUNK ALL THE TIME", Obj="123809083385992"},
    {name="Mix Plan B 2025 | DJ Angelisai ft DJBrad | Team 🐮", Obj="109691993069247"},
    {name="Cool", Obj="87909146687252"},
    {name="Ka$tro - I Gave You Everything", Obj="16831103945"},
    {name="JÁ QUE ME ENSINOU A BEBER (DOUGLAS X GUSBEAST)", Obj="18640530697"},
    {name="M3M0R1ES", Obj="125286594503659"},
    {name="Arrepia XL 2", Obj="73962723234161"},
    {name="Tired Of You", Obj="1837014531"},
    {name="WannaBeHer", Obj="120885023497936"},
    {name="See you again", Obj="139334528864199"},
    {name="SAD!", Obj="72320758533508"},
    {name="Sa hara", Obj="130437050908450"},
    {name="SOLDIER", Obj="87554448466409"},
    {name="Model 399", Obj="87766662"},
    {name="unleaked bypassed song", Obj="137155874195108"},
    {name="Lil Peep - Save That", Obj="1189399253"},
    {name="Morning Mood (f.\"peer Gynt Suite No.1\")", Obj="1846088038"},
    {name="Dexter King - Only You (feat. Alexis Donn)", Obj="7024028859"},
    {name="eu sou pinxadão ", Obj="11287191099"},
    {name="عراقي | ماريدك بعد تهواني", Obj="135911328646170"},
    {name="MONTAGEM BALANÇO - Super slowed", Obj="77356972740459"},
    {name="(Removed for copyright)", Obj="7491553701"},
    {name="Auto toma", Obj="86685635786943"},
    {name="Gothic Song", Obj="75982342509801"},
    {name="Arrepia XL 5", Obj="70782176012619"},
    {name="100℅ Forrozin De Vaquejada Tema Dj Raimundo Pedras", Obj="92295159623916"},
    {name="BRAZILIAN DRIFT MUSIC", Obj="116874163291138"},
    {name="these are jeans", Obj="93218265275853"},
    {name="Lola😈🥵Tumba La Casa😏🥵DJ Raul FT Angelisai", Obj="98296077509691"},
    {name="introduce", Obj="104567749101480"},
    {name="Sto", Obj="128214703292900"},
    {name="Black Knife", Obj="104449595639237"},
    {name="Brazilian Phonk Fiesta", Obj="125498129824026"},
    {name="MONTAGEM BIONICA DIAMANTE (Slowed)", Obj="80012111977834"},
    {name="bell", Obj="6937042327"},
    {name="SHADOWS", Obj="122761529841977"},
    {name="0to8,1xmxxd - stop posting about baller - sped up", Obj="13530439660"},
    {name="UNFORESEEABLE", Obj="71392021424658"},
    {name="Moonlighthood", Obj="122389825417820"},
    {name="NUMB 67", Obj="122854357582130"},
    {name="Spooky Halloween", Obj="120747304076792"},
    {name="PASSO BEM SOLTO SUBMUNDO", Obj="111318048787674"},
    {name="Blessed Mane - Death Is No More", Obj="16831108393"},
    {name="CUTEMAKMAKFUNK (Slowed)", Obj="120871403922972"},
    {name="partyyy!!!", Obj="138790348719069"},
    {name="DOOM ETERNAL", Obj="97557092981429"},
    {name="Sparo loop", Obj="9124780123"},
    {name="jumpstyle", Obj="85833437298815"},
    {name="stokeerr's Place", Obj="39382284"},
    {name="Never Grow Up", Obj="1836654190"},
    {name="GATINHA", Obj="131689610122547"},
    {name="For the Summer", Obj="1837111443"},
    {name="Stop", Obj="0"},
    {name="Want To Love", Obj="104846670980072"},
    {name="ABC (a)", Obj="1839907924"},
    {name="MONTAGEM ELECTRONICA - Mega slowed", Obj="132517043416676"},
    {name="dicealt84702's Place", Obj="693704232"},
    {name="VITRIOL", Obj="87658459636001"},
    {name="Favela Funk 60", Obj="1841683877"},
    {name="No Era Amor", Obj="112748273890049"},
    {name="MESMERIZER / メズマライザー (Clown Remix)", Obj="71934965392436"},
    {name="nMisaki - Dubidubidu (Uptempo Remix)", Obj="16190783444"},
    {name="Remember the Soul", Obj="113184121463834"},
    {name="Seguuura", Obj="96974354995715"},
    {name="Montagem Tomada", Obj="114727662968481"},
    {name="106846365 S", Obj="184183877"},
    {name="love on love on me yeah | ZO ", Obj="9087418452"},
    {name="Red Chains", Obj="102402883551679"},
    {name="BEM SOLTO BRAZIL!", Obj="119936139925486"},
    {name="Din1c - Dionic 2", Obj="15689445424"},
    {name="klnoLOZ303", Obj="105423792227242"},
    {name="TUNG TUNG SAHUR FUNK", Obj="137234649215284"},
    {name="Starvation", Obj="135090256319340"},
    {name="Din1c - can you", Obj="15689448519"},
    {name="Parry Gripp - Chicken Nugget Dreamland", Obj="9245561450"},
    {name="elephant_sound_effect_1", Obj="10944727000"},
    {name="Mente ma", Obj="98337901681441"},
    {name="BAD", Obj="127512475318182"},
    {name="V7 (XL & NGI)", Obj="80348640826643"},
    {name="DriveBlox Unlimited Fan Club", Obj="70803329"},
    {name="MONTAGEM BANDIDO 2.0", Obj="120138115344262"},
    {name="The World Between Us", Obj="117236780703437"},
    {name="montagem do silvio", Obj="104828343009296"},
    {name="onsd", Obj="81299332131868"},
    {name="Schnuffel", Obj="100697759026652"},
    {name="Nakshatrame | Malayalam Christmas Song", Obj="129345087920607"},
    {name="Millonario🤑✨DJ Raul", Obj="118322804860765"},
    {name="calif9rnia - spoil ya", Obj="17422207760"},
    {name="Cute Christmas Song", Obj="80402505796221"},
    {name="Masha And the bear", Obj="1466979183"},
    {name="Some Type Of Way", Obj="131299433678658"},
    {name="(Removed for copyright)", Obj="6111493245"},
    {name="Bing Chilling", Obj="8018464523"},
    {name="out of legaue", Obj="113324443761127"},
    {name="shawty", Obj="127063071194532"},
    {name="Andrew_0218's Place", Obj="13349855413"},
    {name="transgender", Obj="104805787203934"},
    {name="TREM FANTASMA FUNK", Obj="97765714111493"},
    {name="Perdóname", Obj="76164415716559"},
    {name="FE!N", Obj="88250097972862"},
    {name="Prismo - Solo", Obj="16831107981"},
    {name="Phonk da Rua", Obj="104596909675653"},
    {name="pisada XL 2", Obj="97567416166163"},
    {name="DebitoDiSonno (Key After Key)", Obj="74326888232570"},
    {name="Kerosene", Obj="17647322226"},
    {name="Fininha", Obj="139693447546059"},
    {name="Creep", Obj="79399386956664"},
    {name="dark_mov", Obj="110035574248336"},
    {name="yash's Place", Obj="118939"},
    {name="ANH KẾT EM RỒI", Obj="112399975284703"},
    {name="Funk Sigcuro (Ultra Slowed)", Obj="96028783423401"},
    {name="RATIONAL", Obj="73774331093132"},
    {name="AS ABOVE, SO BELOW", Obj="123580060732562"},
    {name="Montagem Primo", Obj="121516877792091"},
    {name="Every God is Gone", Obj="9044520045"},
    {name="🥵One Of Girls x Die For You🥵DJ RAUL FT DJ BRAD", Obj="128534750062152"},
    {name="D.A.D.", Obj="110772573905578"},
    {name="DJ RAUL - Love Story x Dernier Dance (Indila)🌹", Obj="106661099930720"},
    {name="SOMBRIO ", Obj="11295853276"},
    {name="Make-A-Morph", Obj="6937042"},
    {name="Ozuna - Falsas Mentiras", Obj="483713947"},
    {name="Din1c X QWERRXR - Infinite", Obj="16190784875"},
    {name="piedude90's Place", Obj="11222313"},
    {name="Underworld", Obj="109840843335222"},
    {name="nesu1zn5w8r7raz5qhy1's Place", Obj="39392828"},
    {name="Minha Estória (Musica Oficial)", Obj="107683146338584"},
    {name="HR - WASSA", Obj="17422156627"},
    {name="KATANAZ!", Obj="139667113842953"},
    {name="FriendWind", Obj="121239777513594"},
    {name="CÉU AZUL", Obj="83566915633358"},
    {name="BRAZIL DO FUNK", Obj="116733221731811"},
    {name="MONTAGEM ECLIPSE ESTELAR", Obj="93058983119992"},
    {name="Boss Fight!", Obj="78744747224727"},
    {name="crazy-lol (XL & NGI)", Obj="106958630419629"},
    {name="The Flames On Fire", Obj="95554192381753"},
    {name="cinema", Obj="135690618125311"},
    {name="Who's So Autonomous?", Obj="120785124326826"},
    {name="Poder", Obj="137963518593865"},
    {name="【Disney再現歌ってみた】This is Halloween Japanese", Obj="137172267069591"},
    {name="MorningLight☆GrayArea☆ホームページタイマー", Obj="126257401176561"},
    {name="I Know!", Obj="77188110491285"},
    {name="Cry Man meme - By SmukRun (Super Loud)", Obj="4659217874"},
    {name="Science Mysteries", Obj="1840776993"},
    {name="MOMENTS", Obj="93751275110337"},
    {name="CyyberGunShotSFX", Obj="6783714255"},
    {name="montagem pose", Obj="88339486019486"},
    {name="worldsofwood fdk'o;asfkgo'wf", Obj="112222"},
    {name="FUNK DANCE OF EPHORIA LA LA!", Obj="127868004681532"},
    {name="Montagem Mysterious", Obj="90627119202018"},
    {name="Smooth Time", Obj="123229005251213"},
    {name="AUTOMOTIVO DA OESTE {By GAZ1NH X yPke}", Obj="76194666472201"},
    {name="SUPRA", Obj="92940982117958"},
    {name="V2 daquela", Obj="132082397247824"},
    {name="no feelinngs", Obj="85075816659415"},
    {name="A última chance", Obj="84053362849165"},
    {name="Circus", Obj="85706053877701"},
    {name="Be Closer", Obj="111611224392490"},
    {name="tomagi mo tão Anime ver.", Obj="125200420795517"},
    {name="GRAVEYARD (HARDTEKK)", Obj="83032125898517"},
    {name="Automotivo Blondie (Pke Gaz1nh)", Obj="74564219749776"},
    {name="Figure2", Obj="6769"},
    {name="Pumpdafight (Over Slowed)", Obj="71995582569283"},
    {name="jugsta - skeletons", Obj="15689450026"},
    {name="name", Obj="133432990940095"},
    {name="smile smiles", Obj="130781619138449"},
    {name="WanderScript", Obj="9791154706"},
    {name="Eu Duvido (Musica Oficial)", Obj="129212629624727"},
    {name="Snavs - Us", Obj="5410082468"},
    {name="D1spl4y", Obj="90567839325615"},
    {name="rich", Obj="877666629"},
    {name="my garage door", Obj="131107293184621"},
    {name="Rampage cowbell", Obj="128876013372054"},
    {name="(Removed for copyright)", Obj="6519381623"},
    {name="Hoje e Baile No Morro", Obj="89269071829332"},
    {name="the skeletons last breath", Obj="101378669026310"},
    {name="RAGE SYSTEM", Obj="122127808613347"},
    {name="AMOGUS.BABOBOI JUMPSTYLE", Obj="105854178411388"},
    {name="dsc: .lunarleaf.", Obj="98839453510161"},
    {name="Cupid Hates My Guts", Obj="94844025129456"},
    {name="Dark Night", Obj="103504594968244"},
    {name="Cute cat music audio", Obj="86511617909610"},
    {name="Ed Sheeran - Bad Habits 11", Obj="7202579511"},
    {name="montagem Celestial", Obj="81700399219236"},
    {name="On Top Of The World", Obj="1836847994"},
    {name="RAMPAGE SONG", Obj="100379372434844"},
    {name="pai", Obj="95046091312570"},
    {name="RecordScratch_1", Obj="6917155909"},
    {name="(Removed for copyright)", Obj="6887728970"},
    {name="tralalero-tralala", Obj="105044304109159"},
    {name="Parry Gripp - Raining Tacos", Obj="142376088"},
    {name="Code Red", Obj="121205882949035"},
    {name="omegalife bounce", Obj="81917683155285"},
    {name="MONTAGEM PODER IV (SLOWED)", Obj="91233243522140"},
    {name="MyTheme", Obj="124677276108632"},
    {name="chanoq90's Place", Obj="4823353998"},
    {name="d3r, m1v, asteria - no escape", Obj="18841891575"},
    {name="MTG MIND GAME", Obj="83914052148279"},
    {name="(Removed for copyright)", Obj="5458852845"},
    {name="HR - EEYUH!", Obj="16190782181"},
    {name="d3r, 6arelyhuman - toxic", Obj="86412047196482"},
    {name="kirkiimad - ily (original version)", Obj="15689457467"},
    {name="LABUBU FUNK (ULTRA SLOWED)", Obj="97201084418448"},
    {name="Winter", Obj="87233041213837"},
    {name="HALLOWEEN FUNK", Obj="139834501955751"},
    {name="unicornpheoberose's #####", Obj="666666666"},
    {name="Король и шут- Кукла колдуна (не полная версия)", Obj="6383462613"},
    {name="(Removed for copyright)", Obj="5189952246"},
    {name="Ona", Obj="122925258674975"},
    {name="I need you", Obj="80946196913756"},
    {name="Rahaga", Obj="99999"},
    {name="sossa21049's Place", Obj="3982579260"},
    {name="Bad Computer & Danyka Nadeau - Chasing Clouds", Obj="5410082097"},
    {name="ASGORE", Obj="107986977620509"},
    {name="Flamingo Sings \"Wannabe\" by The Spice Girls", Obj="1736474219"},
    {name="MONTAGEM NOVA MÁGICA 1.0", Obj="118297487529239"},
    {name="Oversized", Obj="1844750628"},
    {name="Казахстан угрожает нам бомбардировкой", Obj="6562534895"},
    {name="MONTAGEM BALANÇO", Obj="101456813429584"},
    {name="Mutilation 1.4", Obj="99128910197696"},
    {name="SchoolDay", Obj="79965043381389"},
    {name="faz a propaganda", Obj="18396858335"},
    {name="Wheels Of Madness", Obj="1836789357"},
    {name="RITMO SELVAGEM", Obj="105102042077619"},
    {name="Mega El Desorden", Obj="128129091062553"},
    {name="CELL!", Obj="117634275895085"},
    {name="Ride or Die PT.2 - Tokischa, Villano Antillano", Obj="17359243329"},
    {name="Jumpstyle", Obj="1839246711"},
    {name="CAR CRUSHERS 2 FUNK", Obj="72444649335619"},
    {name="Toque Phonk", Obj="81552567379452"},
    {name="Prokiller Hokage", Obj="91332435"},
    {name="VG | back to friends - sombr", Obj="135123528451977"},
    {name="Pixel Terror & EMELINE - Chroma", Obj="5410084802"},
    {name="LIT!", Obj="112512564227744"},
    {name="Yegale", Obj="97486851158533"},
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
		"https://raw.githubusercontent.com/nick0022/DataGui/refs/heads/main/README.md",
		"https://raw.githubusercontent.com/nick0022/DataGui/refs/heads/main/README.md"
	}

	for _, url in ipairs(urls) do
		local okHttp, result = pcall(function()
			return game:HttpGet(url)
		end)
		if okHttp and result and result ~= "" then
			code = result
			print("[🌐 Mod Loader] Código baixado!")
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
		id = Listaid[currentIndex]
	end

	if not id then return end

	-- Envia para o servidor tocar a música
	playEvent:FireServer(id)

	-- Busca informações da música no catálogo Roblox
	local success, info = pcall(function()
		return MarketplaceService:GetProductInfo(id)
	end)

	-- Atualiza o texto do rótulo
	if success and info and info.Name then
		GL1["Name_id"].Text = "♪ Tocando: " .. info.Name
	else
		GL1["Name_id"].Text = "♪ Tocando: Faixa " .. tostring(currentIndex)
	end

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
		currentIndex = #Listaid
	end
	playCurrentTrack()
end)

-- Botão próxima
GL1["Input_Angle_R"].MouseButton1Click:Connect(function()
	currentIndex += 1
	if currentIndex > #Listaid then
		currentIndex = 1
	end
	playCurrentTrack()
end)


local isMinimized = false
local isMinimized_L = true

-- Minimizar o player inteiro
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


	-- Função para criar a lista de nomes (Modificada para usar apenas a lista estática)
	function getnamesbox(list)
		-- Como a lista já está completa e estática, apenas a retornamos.
		-- A lógica de buscar ProductInfo para cada ID foi removida.
		return listMusics
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
