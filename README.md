# d2bot
# 好东西大家分享
// Paladin config file

/* Brief instructions:
 * Notepad++ is HIGHLY recommended to use for editing these files. Visit http://notepad-plus-plus.org/
 * To comment out something, put // in front of that line
 * !!!Never comment out something you're not sure about, set it to false or disable as noted in description if you don't want to use it.
 * true and false are case sensitive. Good: Config.SomeVar = true; Bad: Config.SomeVar = True;
 */
/*
*****************************************************************************************
****
* 善使善善功血 Ctrl+F
*
* 使使 NOTEPAD++ 编编这你常常是编编血。
*
* 的脚施文血用 =true ，为为 =false 。以以是使这。
*
* 常是清在是在你后，详请详详请值血血请是传请，药为文常传请血没为没常传请。敌对对对模去为中
。 *
*****************************************************************************************
****
*/
function LoadConfig() {
	/* Sequence config
	 * Set to true if you want to run it, set to false if not.
	 * If you want to change the order of the scripts, just change the order of their lines by using cut and paste.
	 */
	 
	// User addon script. Read the description in libs/bots/UserAddon.js
	Scripts.UserAddon = false; // 你必须先将这个设置为false。 false!!!YOU MUST SET THIS TO FALSE IF YOU WANT TO RUN BOSS/AREA SCRIPTS!!!

	// Battle orders script - Use this for 2+ characters (for example BO barb + sorc)
	Scripts.BattleOrders = false;
		Config.BattleOrders.Mode = 0; // 0 = give BO, 1 = get BO
		Config.BattleOrders.Wait = false; // Idle until the player that received BO leaves.
		Config.BattleOrders.Getters = []; // List of players to wait for before casting Battle Orders (mode 0). All players must be in the same area as the BOer.

	// Team MF system
	Config.MFLeader = false; // Set to true if you have one or more MFHelpers. Opens TP and gives commands when doing normal MF runs.

	// Boss/area scripts

	// *** act 1 ***
	Scripts.Corpsefire = false;  //  邪窟洞穴尸体发火
		Config.Corpsefire.ClearDen = false;  //  是否全清
	Scripts.Mausoleum = false;   //  大陵墓
		Config.Mausoleum.KillBloodRaven = true;  //  是血杀
		Config.Mausoleum.ClearCrypt = false;  //  是否清理傍边的另外一个墓穴
	Scripts.Rakanishu = false;   //  拉卡尼休
		Config.Rakanishu.KillGriswold = true;  
	Scripts.UndergroundPassage = false;  //  地底通道
	Scripts.Coldcrow = false;
	Scripts.Tristram = false;   //  催斯特瑞姆
		Config.Tristram.PortalLeech = false; //   设置  true 为其他跟随者打开一个传送门Set to true to open a portal for leechers.
	Scripts.Pit = false;  // 胎膜高地地穴
		Config.Pit.ClearPit1 = true; // 是否清理第一层
	Scripts.Treehead = false;  //  应该是黑暗森林大树旁边的几个猩猩
	Scripts.Smith = false;
	Scripts.BoneAsh = false;
	Scripts.Countess = true;  //  女伯爵
		Config.Countess.KillGhosts = false; //  是否清理各层鬼怪，传说hr 掉了高。
	Scripts.Andariel = true;  // 安达利尔
	Scripts.Cows = false;  // 牛关

	// *** act 2 ***
	Scripts.Radament = false;  //  城里地下水道里的 Radament
	Scripts.Coldworm = false;
		Config.Coldworm.KillBeetleburst = false;
		Config.Coldworm.ClearMaggotLair = false; // Clear all 3 levels
	Scripts.AncientTunnels = false;  //  古代通道
		Config.AncientTunnels.OpenChest = false; // 是否在遗失的城市开启特殊箱子Open special chest in Lost City
		Config.AncientTunnels.KillDarkElder = false;
	Scripts.Summoner = true; //召唤者
		Config.Summoner.FireEye = true;   // 是否击杀火之眼
	Scripts.Tombs = false; // 古墓
	Scripts.Duriel = true;  // 督瑞尔

	// *** act 3 ***
	Scripts.Stormtree = false;
	Scripts.KurastTemples = false;
	Scripts.Icehawk = false;
	Scripts.Endugu = false;
	Scripts.Travincal = false;  // 崔凡克
		Config.Travincal.PortalLeech = false; // Set to true to open a portal for leechers.
	Scripts.Mephisto = true;  // 莫非斯托
		Config.Mephisto.MoatTrick = false; // 脆弱的sor 隔河杀
		Config.Mephisto.KillCouncil = true;  // 是否击杀会议瘸子
		Config.Mephisto.TakeRedPortal = true;  // 是否用红门到act4

	// *** act 4 ***
	Scripts.OuterSteppes = false;
	Scripts.Izual = false;  // 衣卒尔
	Scripts.Hephasto = false;  // 铁匠
	Scripts.Vizier = false; // Intended for classic sorc, kills Vizier only.
	Scripts.FastDiablo = false;  // 快速diable 测试下了chaos 不到2分钟
	Scripts.Diablo = true;  // 常规diablo脚本
		Config.Diablo.Entrance = false; // 是否从门处开始清理 false 从五角星开始 Start from entrance
		Config.Diablo.SealWarning = "Leave the seals alone!";  // 其他人开封印发的消息
		Config.Diablo.EntranceTP = "Entrance TP up";  // 入口处开门发的消息
		Config.Diablo.StarTP = "Star TP up";  // 五角星处开门发的消息
		Config.Diablo.DiabloMsg = "Diablo"; // 等待daible时候的消息
	Scripts.SealLeader = false; // 清理一个安全的区域给小号吸经验，相对应的小号需要运行sealleecher脚本，这个脚本在下方Clear a safe spot around seals and invite leechers in. Leechers should run SealLeecher script. Don't run with Diablo or FastDiablo.

	// *** act 5 ***
	Scripts.Pindleskin = true;  // 暴躁外皮
		Config.Pindleskin.UseWaypoint = false; // 没有红门用小站
		Config.Pindleskin.KillNihlathak = true;  // 是否击杀你那塞克
		Config.Pindleskin.ViperQuit = false; // 遇到bug蛇后结束脚本 End script if Tomb Vipers are found.
	Scripts.Nihlathak = false;  // 你那塞克
		Config.Nihlathak.ViperQuit = false; // 遇到bug蛇后结束脚本End script if Tomb Vipers are found.
	Scripts.Eldritch = false; // 和下面两个选项一起 a5第一个场景3个固定的boss
		Config.Eldritch.OpenChest = false;
		Config.Eldritch.KillShenk = true;
		Config.Eldritch.KillDacFarren = false;
	Scripts.Eyeback = false;
	Scripts.SharpTooth = false;
	Scripts.ThreshSocket = false;
	Scripts.Abaddon = false;
	Scripts.Frozenstein = false;  //冰冻魔怪
		Config.Frozenstein.ClearFrozenRiver = true;  // 全清冰河
	Scripts.Bonesaw = false;
		Config.Bonesaw.ClearDrifterCavern = false;
	Scripts.Snapchip = false;
		Config.Snapchip.ClearIcyCellar = true;
	Scripts.Worldstone = false; // 世界之石大殿
	//Scripts.Baal = true; // 常规巴尔脚本
		Config.Baal.HotTPMessage = "Hot TP!";  // 到达王座开启一个危险的门
		Config.Baal.SafeTPMessage = "Safe TP!"; // 清理后开启安全的门
		Config.Baal.BaalMessage = "Baal!"; //等待进入大殿时发出的消息
		Config.Baal.SoulQuit = false; // 检测到灵魂杀手后结束脚本 End script if Souls (Undead Soul Killers) are found.
		Config.Baal.DollQuit = false; // 检测到电鬼后结束脚本 End script if Dolls (Undead Stigyan Dolls) are found.
		Config.Baal.KillBaal = true; // Kill Baal. Leaves game after wave 5 if false.

	/* 跟班部分 // ### leeching section ###
	* Unless stated otherwise, leader's character name isn't needed on order to run.
	* Don't use more scripts of the same type! (Run AutoBaal OR BaalHelper, not both)
	*/

	Config.Leader = ""; // 除了一些特别的功能需要填入队长的名字，否则此处空白可自动检测，可自动检测的功能包括auto baal，wakka，mfhelper Leader's ingame character name. Leave blank to try auto-detection (works in AutoBaal, Wakka, MFHelper)
	// 如果你要使用一个手动操作加几个祖东运行的跟班这种模式，那么跟班的配置文件中这里是必填项，跟班的控制命令参考follower.js中的内容
	Config.QuitList = [""]; // List of character names to quit with. Example: Config.QuitList = ["MySorc", "MyDin"];
	Config.QuitListMode = 0; // 0 = use character names; 1 = use profile names (all profiles must run on the same computer).

	Scripts.TristramLeech = false; // Enters Tristram, attempts to stay close to the leader and will try and help kill.
	Scripts.TravincalLeech = false; // Enters portal at back of Travincal.
		Config.TravincalLeech.Helper = true; // If set to true the character will teleport to the stairs and help attack.
	Scripts.MFHelper = false; // 该功能没测试 Run the same MF run as the MFLeader. Leader must have Config.MFLeader = true
	Scripts.Wakka = false; //混沌避难所小号跑路跟随leader 升级脚本 // Walking chaos leecher with auto leader assignment, stays at safe distance from the leader
	Scripts.SealLeecher = false; // 小号吸经验用的，对应的leader需要运行sealleader脚本 Enter safe portals to Chaos. Leader should run SealLeader.
	Scripts.DiabloHelper = false; // 多人游戏里帮手运行的chaos脚本，不开封印之打怪 Chaos helper, kills monsters and doesn't open seals on its own.
		Config.DiabloHelper.Wait = 120; // 等待leader的时间，单位秒 Seconds to wait for a runner to be in Chaos. If Config.Leader is set, it will wait only for the leader.
		Config.DiabloHelper.Entrance = true; // 是否从门处开始清理，如果false则从五角星开始清理。Start from entrance. Set to false to start from star.
		Config.DiabloHelper.SkipTP = false; // 不等待leader的传送门，直接自己跑到chaos门口清理完小怪等待leader Don't wait for town portal and directly head to chaos. It will clear monsters around chaos entrance and wait for the runner.
		Config.DiabloHelper.SkipIfBaal = false; // 队伍中有人在干baal，自动结束脚本End script if there are party members in a Baal run.
	//这个脚本我解释下，用法为你在chaos中吃鸡退出了，其他队伍人员吧dia干掉了，你重新加入游戏的人检测到有人干baal就会结束当前脚本，不用白跑堂chaos了。
	Scripts.AutoBaal = false; // 这个和baalheaper的区别，这个是给小号升级经验，helper是一起打 。Baal leecher with auto leader assignment
		Config.AutoBaal.FindShrine = false; // 自动寻找经验神殿，1=检测到hot tp信息后去找，2=检测到leader就去找。false = disabled, 1 = search after hot tp message, 2 = search as soon as leader is found
		Config.AutoBaal.LeechSpot = [15115, 5050]; // 站立的坐标 X, Y coords of Throne Room leech spot
		Config.AutoBaal.LongRangeSupport = false; // 在远处安全的位置丢技能 Cast long distance skills from a safe spot
	Scripts.BaalHelper = false; // baal 帮手脚本
		Config.BaalHelper.Wait = 120; // 等待leader的时间，单位秒 Seconds to wait for a runner to be in Throne
		Config.BaalHelper.KillNihlathak = false; // 在等待的时间去干你那塞克 Kill Nihlathak before going to Throne
		Config.BaalHelper.FastChaos = false; // 在等待的时间快速干掉diablo Kill Diablo before going to Throne
		Config.BaalHelper.DollQuit = false;  // 检测到灵魂杀守护结束脚本 End script if Dolls (Undead Soul Killers) are found.
		Config.BaalHelper.KillBaal = true; // 是否击杀baal，如富哦此处设置了否，请在quitlist选项中输入队长角色名Kill Baal. If set to false, you must configure Config.QuitList or the bot will wait indefinitely.
		Config.BaalHelper.SkipTP = false; // 不等待队长tp，直接自己跑到网左前。Don't wait for a TP, go to WSK3 and wait for someone to go to throne. Anti PK measure.
	Scripts.Follower = false; // 该脚本可以使用运行脚本的人围绕着leader进行猎杀，类似一个高级佣兵，可以跟随leader进洞，切换场景。Script that follows a manually played leader around like a merc. For a list of commands, see Follower.js

	// 特殊脚本部分 // *** special scripts ***
	Scripts.WPGetter = false; // wp 自动猜缺失的小站 Get missing waypoints
	Scripts.GetKeys = false;  // 自动猎杀三个掉火炬key的boss Hunt for T/H/D keys
	Scripts.OrgTorch = false; //器官火炬脚本
		Config.OrgTorch.MakeTorch = true; // 使用成套器官开启红门并击杀boss获得火炬。Convert organ sets to torches
		Config.OrgTorch.WaitForKeys = true; // 允许脚本从其他档案名称所创建的bot处获取key。Enable Torch System to get keys from other profiles. See libs/TorchSystem.js for more info
		Config.OrgTorch.WaitTimeout = 15; // 脚本开始前等待多久分钟其他专门打key的bot运送key 到这个游戏中。Time in minutes to wait for keys before moving on
		Config.OrgTorch.UseSalvation = true; // 猎杀超级墨菲时候开启救赎光环Use Salvation aura on Mephisto (if possible)
		Config.OrgTorch.GetFade = false; // 猎杀前是否激活fade技能，你必须收线用于last wish 这个道具 Get fade by standing in a fire. You MUST have Last Wish or Treachery on your character being worn.
	Scripts.Rusher = false; // 自动pass功能司机需要运行的脚本 Rush bot. For a list of commands, see Rusher.js
		Config.Rusher.WaitPlayerCount = 0; // 等待游戏总人数到达几人后开始pass，设置为0不等待，设置为8满员开车。Wait until game has a certain number of players (0 - don't wait, 8 - wait for full game).
		Config.Rusher.Radament = false; // 是否a2技能任务 Do Radament quest.
		Config.Rusher.LamEsen = false; // 是否a3蓝衣森之书任务 Do Lam Esen quest.
		Config.Rusher.Izual = false; // 是否a4衣卒尔任务 Do Izual quest.
		Config.Rusher.Shenk = true; // 时候a5打孔任务 Do Shenk quest.
		Config.Rusher.Anya = true; // 是否救安雅 Do Anya quest.
		Config.Rusher.LastRun = ""; // 司机进行到那个任务结束脚本，任务清单请查看 \d2bs\kolbot\sdk 目录下的 rusherruns.txt 文件。引号填入任务名称。不是任务序列号，列如你可以填入 "baal"。End rush after this run. List of runs: http://pastebin.com/Uez3nZ6g
	Scripts.Rushee = false; // 自动pass 功能小弟需要运行的脚本，必须与rusher脚本配合使用。Automatic rushee, works with Rusher. Set Rusher's character name as Config.Leader
		Config.Rushee.Quester = false; //是否进门拾取任务物品 Enter portals and get quest items.
		Config.Rushee.Bumper = false; // 该人物是否为bumper，即所谓的keychar 在资料片a5中去完成古代人和baal任务带领全队通关当前难度 Do Ancients and Baal. Minimum levels: 20 - norm, 40 - nightmare
	Scripts.CrushTele = false; // classic rush teleporter. go to area of interest and press "-" numpad key
	Scripts.Questing = false; // 自动清理一些有用的任务，技能状态，打孔等。solves missing quests (skill/stat+shenk)
	Scripts.Gamble = false; // 赌博系统，主要用于低等级的人物赌博，其他bot会进来自动送钱。Gambling system, other characters will mule gold into your game so you can gamble infinitely. See Gambling.js
	Scripts.Crafting = false; // Crafting system, other characters will mule crafting ingredients. See CraftingSystem.js
	Scripts.GhostBusters = false; // 灵魂猎杀脚本 Kill ghosts in most areas that contain them
	Scripts.Enchant = false;  // 强化脚本
		Config.Enchant.Triggers = ["chant", "cows", "wps"]; // 命令定义，其中包含强化命令，开牛关命令以及给与小站功能 Chat commands for enchant, cow level and waypoint giving
		Config.Enchant.GetLeg = false; // 是否去找退，设置false会在城里找腿。Get Wirt's Leg from Tristram. If set to false, it will check for the leg in town.
		Config.Enchant.AutoChant = false; // 是否自动强化角色身边的其他人物雇佣兵召唤物等。Automatically enchant nearby players and their minions
		Config.Enchant.GameLength = 20; // 游戏最大时间 Game length in minutes
	Scripts.IPHunter = false; //找ip脚本
		Config.IPHunter.IPList = []; // List of IPs to look for. example: [165, 201, 64]
		Config.IPHunter.GameLength = 3; // Number of minutes to stay in game if ip wasn't found
	Scripts.KillDclone = false; // 去神秘避难所击杀dc的脚本，必须是一个已经出现dc的游戏。Kill Diablo Clone by using Arcane Sanctuary waypoint. Diablo needs to walk the Earth in the game.
	Scripts.ShopBot = false; // shopbot 脚本，启动后忽略除shopbot.nip之外的拾取文件。Shopbot script. Automatically uses shopbot.nip and ignores other pickits.
		// Supported NPCs: Akara, Elzix, Fara, Drognan, Ormus, Asheara, Anya. Multiple NPCs are also supported, example: ["Elzix", "Fara"]
		// Use common sense when combining NPCs. Shopping in different acts will probably lead to bugs.
		Config.ShopBot.ShopNPC = "Anya"; // 需要shop的npc，名称在上方。
		// Put item classid numbers or names to scan (remember to put quotes around names). Leave blank to scan ALL items. See libs/config/templates/ShopBot.txt
		Config.ShopBot.ScanIDs = [];  // 扫描的物品id，留空则扫描所有的物品。详见 libs/config/templates/ShopBot.txt
		Config.ShopBot.CycleDelay = 0; //shop是扫描商店的延迟时间，高点或许减少窗口崩溃的几率。Delay between shopping cycles in milliseconds, might help with crashes.
		Config.ShopBot.QuitOnMatch = false; // Leave game as soon as an item is shopped.
	Scripts.ChestMania = false; // 开箱子专业脚本，下面可以定义需要扫荡的地图。Open chests in configured areas. See sdk/areas.txt
		Config.ChestMania.Act1 = [13, 14, 15, 16, 18, 19]; // List of act 1 areas to open chests in
		Config.ChestMania.Act2 = [55, 59, 65, 66, 67, 68, 69, 70, 71, 72]; // List of act 2 areas to open chests in
		Config.ChestMania.Act3 = [79, 80, 81, 92, 93, 84, 85, 90]; // List of act 3 areas to open chests in
		Config.ChestMania.Act4 = []; // List of act 4 areas to open chests in
		Config.ChestMania.Act5 = [115, 116, 119, 125, 126, 127]; // List of act 5 areas to open chests in
	Scripts.ClearAnyArea = false; // 清理任意地图脚本，需要在下方定义地图id。 Clear any area. Uses Config.ClearType to determine which type of monsters to kill.
		Config.ClearAnyArea.AreaList = []; // List of area ids to clear. See sdk/areas.txt

	// *** Guest scripts ***
    // 另一个baal跟班的打手脚本，（与上面的baalhelper脚本选择一个使用）这个区别在于根据聊天命令判断进门实际，可用在非同一台机器的teambot中，具体设置参考上方的baal设置。
	// Baal Assistant by YourGreatestMember
	Scripts.BaalAssistant = false; // Used to leech or help in baal runs.
		Config.BaalAssistant.Wait = 120; // Seconds to wait for a runner to be in the throne / portal wait / safe TP wait / hot TP wait...
		Config.BaalAssistant.KillNihlathak = false; // Kill Nihlathak before going to Throne
		Config.BaalAssistant.FastChaos = false; // Kill Diablo before going to Throne
		Config.BaalAssistant.Helper = true; // Set to true to help attack, set false to to leech.
		Config.BaalAssistant.GetShrine = false; // Set to true to get a experience shrine at the start of the run.
		Config.BaalAssistant.GetShrineWaitForHotTP = false; // Set to true to get a experience shrine after leader shouts the hot tp message as defined in Config.BaalAssistant.HotTPMessage
		Config.BaalAssistant.SkipTP = false; // Set to true to enable the helper to skip the TP and teleport down to the throne room.
		Config.BaalAssistant.WaitForSafeTP = false; // Set to true to wait for a safe TP message (defined in SafeTPMessage)
		Config.BaalAssistant.DollQuit = false; // Quit on dolls. (Hardcore players?)
		Config.BaalAssistant.SoulQuit = false; // Quit on Souls. (Hardcore players?)
		Config.BaalAssistant.KillBaal = true; // Set to true to kill baal, if you set to false you MUST configure Config.QuitList or Config.BaalAssistant.NextGameMessage or the bot will wait indefinitely. 
		Config.BaalAssistant.HotTPMessage = ["Hot"]; // Configure safe TP messages.
		Config.BaalAssistant.SafeTPMessage = ["Safe", "Clear"]; // Configure safe TP messages.
		Config.BaalAssistant.BaalMessage = ["Baal"]; // Configure baal messages, this is a precautionary measure.
		Config.BaalAssistant.NextGameMessage = ["Next Game", "Next", "New Game"];	// Next Game message, this is a precautionary quit command, Reccomended setting up: Config.QuitList

	// Town settings
	Config.HealHP = 50; // 血量地狱设定百分比找医生补满。Go to a healer if under designated percent of life.
	Config.HealMP = 0; // 魔法低于设定百分比找医生补满。 Go to a healer if under designated percent of mana.
	Config.HealStatus = false; // 中毒诅咒是否回家解除 。Go to a healer if poisoned or cursed
	Config.UseMerc = true; // 是否用pet，非资中总是false。Use merc. This is ignored and always false in d2classic.
	Config.MercWatch = false; //pet战斗中死亡是否立即回程复活。 Instant merc revive during battle.

	// Potion settings
	Config.UseHP = 75; // 血量少于百分比何红药。Drink a healing potion if life is under designated percent.
	Config.UseRejuvHP = 40;  // 血量多少大紫。Drink a rejuvenation potion if life is under designated percent.
	Config.UseMP = 30; // 魔法多少喝蓝药。Drink a mana potion if mana is under designated percent.
	Config.UseRejuvMP = 0; // 魔法多少喝大紫。Drink a rejuvenation potion if mana is under designated percent.
	Config.UseMercHP = 75; // 佣兵多少血量喝红药，Give a healing potion to your merc if his/her life is under designated percent.
	Config.UseMercRejuv = 10; // 佣兵多少血量喝大紫 Give a rejuvenation potion to your merc if his/her life is under designated percent.
	Config.HPBuffer = 0; // 背包保存多少红药 Number of healing potions to keep in inventory.
	Config.MPBuffer = 0; // 背包保存多少蓝药 Number of mana potions to keep in inventory.
	Config.RejuvBuffer = 0; // 背包保存多少大紫。Number of rejuvenation potions to keep in inventory.

	// Chicken settings 吃鸡设置
	Config.LifeChicken = 30; // 吃鸡多少血量退出游戏 Exit game if life is less or equal to designated percent.
	Config.ManaChicken = 0; // 吃鸡多少蓝退出游戏 Exit game if mana is less or equal to designated percent.
	Config.MercChicken = 0; // pet 多少血退出游戏。Exit game if merc's life is less or equal to designated percent.
	Config.TownHP = 0; // 血量多少百分比回家补给。Go to town if life is under designated percent.
	Config.TownMP = 0; // 蓝多少百分比回家补给。Go to town if mana is under designated percent.

	/* Inventory lock configuration. !!!READ CAREFULLY!!!
	 * 0 = item is locked and won't be moved. If item occupies more than one slot, ALL of those slots must be set to 0 to lock it in place.
	 * Put 0s where your torch, annihilus and everything else you want to KEEP is.
	 * 1 = item is unlocked and will be dropped, stashed or sold.
	 * If you don't change the default values, the bot won't stash items.
	 */
	//背包设定，0位锁定，1位为bot可使用
	Config.Inventory[0] = [1,1,1,1,1,1,0,0,0,0];
	Config.Inventory[1] = [1,1,1,1,1,1,0,0,0,0];
	Config.Inventory[2] = [1,1,1,1,1,1,0,0,0,0];
	Config.Inventory[3] = [1,1,1,1,1,1,0,0,0,0];

	Config.StashGold = 100000; // 多少钱存起来 Minimum amount of gold to stash.

	/* Potion types for belt columns from left to right.
	 * Rejuvenation potions must always be rightmost.
	 * Supported potions - Healing ("hp"), Mana ("mp") and Rejuvenation ("rv")
	 */
	//药水设定hp红 mp蓝 re紫
	Config.BeltColumn[0] = "hp";
	Config.BeltColumn[1] = "hp";
	Config.BeltColumn[2] = "mp";
	Config.BeltColumn[3] = "rv";

	/* Minimum amount of potions. If we have less, go to vendor to purchase more.
	 * Set rejuvenation columns to 0, because they can't be bought.
	 */
	// 设定数量，低于设定数量找npc补满。
	Config.MinColumn[0] = 3;
	Config.MinColumn[1] = 3;
	Config.MinColumn[2] = 0;
	Config.MinColumn[3] = 0;

	// 拾取文件设定。//Pickit config. Default folder is kolbot/pickit.
	Config.PickitFiles.push("kolton1.nip");
	Config.PickitFiles.push("LLD.nip");
	Config.PickRange = 40; // 拾取距离// Pick radius
	Config.FastPick = false; // 是否在攻击时进行拾取//Check and pick items between attacks

	// Additional item info log settings. All info goes to \logs\ItemLog.txt
	Config.ItemInfo = false; // 是否启用物品日志文件。 Log stashed, skipped (due to no space) or sold items.
	Config.ItemInfoQuality = []; // 记录卖出的最低等级物品品质 The quality of sold items to log. See NTItemAlias.dbl for values. Example: Config.ItemInfoQuality = [6, 7, 8];

	// Item identification settings
	Config.CainID.Enable = false; // 是否使用凯恩进行物品鉴定。Identify items at Cain
	Config.CainID.MinGold = 2500000; // Minimum gold (stash + character) to have in order to use Cain.
	Config.CainID.MinUnids = 3; // 最少有几件未鉴定的物品才使用凯恩进行鉴定。Minimum number of unid items in order to use Cain.
	Config.FieldID = false; // Identify items in the field instead of going to town.
	Config.DroppedItemsAnnounce.Enable = false;	// Announce Dropped Items to in-game newbs
	Config.DroppedItemsAnnounce.Quality = []; // Quality of item to announce. See NTItemAlias.dbl for values. Example: Config.DroppedItemsAnnounce.Quality = [6, 7, 8];

	// Repair settings
	Config.CubeRepair = false; // 是否用合成公式进行物品修理，建议避免使用。Repair weapons with Ort and armor with Ral rune. Don't use it if you don't understand the risk of losing items.
	Config.RepairPercent = 40; // Durability percent of any equipped item that will trigger repairs.

	// Gambling config
	Config.Gamble = true;
	Config.GambleGoldStart = 2000000;  // 多少钱开始赌博。
	Config.GambleGoldStop = 500000;  // 多少钱停止赌博。

	// List of item names or classids for gambling. Check libs/NTItemAlias.dbl file for other item classids.
	Config.GambleItems.push("Amulet");  // 520 项链
	Config.GambleItems.push("Ring");   // 522 戒指
	Config.GambleItems.push("Circlet");  // 418投缳
	Config.GambleItems.push("Coronet");   //419宝冠
	Config.GambleItems.push("KiteShield");   //偏向盾
    //合成设定 更多设置请查阅 Templates/Cubing.txt文件
	/* Cubing config. All recipe names are available in Templates/Cubing.txt. For item names/classids check NTItemAlias.dbl
	 * The format is Config.Recipes.push([recipe_name, item_name_or_classid, etherealness]). Etherealness is optional and only applies to some recipes.
	 */
	Config.Cubing = true; // 是否启用合成系统 Set to true to enable cubing.

	// Ingredients for the following recipes will be auto-picked, for classids check libs/NTItemAlias.dbl
    //以下的所有合成均会自动拾取杂货，打孔的材料除外
	
	// 宝石部分
	Config.Recipes.push([Recipe.Gem, "Flawless Amethyst"]); // 560 完美紫Make Perfect Amethyst 
	Config.Recipes.push([Recipe.Gem, "Flawless Topaz"]); // 565 完美黄Make Perfect Topaz
	Config.Recipes.push([Recipe.Gem, "Flawless Sapphire"]); // 570 完美蓝Make Perfect Sapphire
	Config.Recipes.push([Recipe.Gem, "Flawless Emerald"]); // 575 完美绿Make Perfect Emerald
	Config.Recipes.push([Recipe.Gem, "Flawless Ruby"]); // 580 完美红 Make Perfect Ruby
	Config.Recipes.push([Recipe.Gem, "Flawless Diamond"]); // 585 完美钻 Make Perfect Diamond
	Config.Recipes.push([Recipe.Gem, "Flawless Skull"]); // 600 完美骷髅 Make Perfect Skull

	//Config.Recipes.push([Recipe.Token]); // 洗点勋章 Make Token of Absolution
     
	//符文部分
	//Config.Recipes.push([Recipe.Rune, "Pul Rune"]); // Upgrade Pul to Um
	//Config.Recipes.push([Recipe.Rune, "Um Rune"]); // Upgrade Um to Mal
	//Config.Recipes.push([Recipe.Rune, "Mal Rune"]); // Upgrade Mal to Ist
	//Config.Recipes.push([Recipe.Rune, "Ist Rune"]); // Upgrade Ist to Gul
	//Config.Recipes.push([Recipe.Rune, "Gul Rune"]); // Upgrade Gul to Vex
	
    //成色部分
	Config.Recipes.push([Recipe.Safety.Amulet]);                      // 安全项链 Safety Caster Amulet	
	Config.Recipes.push([Recipe.Caster.Amulet]);                      // 施法项链 Craft Caster Amulet
	Config.Recipes.push([Recipe.Caster.Ring]);                         // 施法戒指 Craft Caster Ring
	//Config.Recipes.push([Recipe.Caster.belts, "vampirefangbelt"]);     // 施法腰带 Craft Caster belts
	Config.Recipes.push([Recipe.Caster.boots, "wyrmhideboots"]);      // 施法鞋子 Craft Caster boots
	Config.Recipes.push([Recipe.Blood.Ring]);                         // 吸血戒指 Craft Blood Ring
	Config.Recipes.push([Recipe.Blood.Helm, "Armet"]);                // 吸血头盔 Craft Blood Armet
	Config.Recipes.push([Recipe.Blood.belts, "mithrilcoil"]);        // 吸血腰带 Craft Blood belts
	//Config.Recipes.push([Recipe.Blood.boots, "lightplatedboots"]);    // 吸血鞋子 Craft Blood boots
	Config.Recipes.push([Recipe.Blood.Gloves, "Vampirebonegloves"]); // 吸血手套 Craft Blood Vambraces	
	//Config.Recipes.push([Recipe.HitPower.Gloves, "Vambraces"]);        // 打击手套 Craft Hit Power Vambraces
    Config.Recipes.push([Recipe.HitPower.Ring, ]);                    // 打击戒指 Craft Hit Power ring

	// The gems not used by other recipes will be used for magic item rerolling.
    // 蓝色物品部分
	//Config.Recipes.push([Recipe.Reroll.Magic, "Diadem"]); // 421 洗全冠 Reroll magic Diadem
	//Config.Recipes.push([Recipe.Reroll.Magic, "Grand Charm"]); // 605 洗GC Reroll magic Grand Charm (ilvl 91+)
    
	//黄色部分
	//Config.Recipes.push([Recipe.Reroll.Rare, "Diadem"]); // 421 洗黄色全冠 Reroll rare Diadem

	//打孔部分
	/* Base item for the following recipes must be in pickit. The rest of the ingredients will be auto-picked.
	 * Use Roll.Eth, Roll.NonEth or Roll.All to determine what kind of base item to roll - ethereal, non-ethereal or all.
	 */
	//以下合成的基础材料拾取规则和你所需要的成品拾取规则必须写入拾取文件，剩下的宝石自动拾取，不用写入拾取文件。
	//如需添加其他物品请查阅libs/NTItemAlias.dbl文件中的物品的classid
	Config.Recipes.push([Recipe.Socket.Weapon, "Thresher", Roll.Eth]); // 255 锐利 Socket ethereal Thresher
	Config.Recipes.push([Recipe.Socket.Weapon, "Cryptic Axe", Roll.Eth]); // 256 神秘 Socket ethereal Cryptic Axe
	Config.Recipes.push([Recipe.Socket.Weapon, "greatpoleaxe", Roll.Eth]); // 257 GP Socket ethereal greatpoleaxe
	Config.Recipes.push([Recipe.Socket.Weapon, "giantthresher", Roll.Eth]); // 258 GT  Socket ethereal giantthresher
    Config.Recipes.push([Recipe.Socket.Armor, "Archon Plate", Roll.Eth]); // 443 ap甲 Socket ethereal Archon Plate
    Config.Recipes.push([Recipe.Socket.Armor, "sacredarmor", Roll.Eth]); // 442 ap甲 Socket ethereal Archon Plate
    //Config.Recipes.push([Recipe.Socket.Armor, "greathauberk", Roll.Eth]); // 436 ap甲 Socket ethereal Archon Plate
    //Config.Recipes.push([Recipe.Socket.Armor, "krakenshell", Roll.Eth]); // 439 ap甲 Socket ethereal Archon Plate
    //Config.Recipes.push([Recipe.Socket.Armor, "balrogskin", Roll.Eth]); // 437 ap甲 Socket ethereal Archon Plate

	// 暗金物品升级部分
	//Config.Recipes.push([Recipe.Unique.Armor.ToExceptional, "Heavy Gloves", Roll.NonEth]); // Upgrade Bloodfist to Exceptional
	//Config.Recipes.push([Recipe.Unique.Armor.ToExceptional, "Light Gauntlets", Roll.NonEth]); // Upgrade Magefist to Exceptional
	//Config.Recipes.push([Recipe.Unique.Armor.ToElite, "Sharkskin Gloves", Roll.NonEth]); // Upgrade Bloodfist or Grave Palm to Elite
	//Config.Recipes.push([Recipe.Unique.Armor.ToElite, "Battle Gauntlets", Roll.NonEth]); // Upgrade Magefist or Lavagout to Elite
	//Config.Recipes.push([Recipe.Unique.Armor.ToElite, "War Boots", Roll.NonEth]); // Upgrade Gore Rider to Elite

	//制作符文之语
	/* Runeword config. All recipes are available in Templates/Runewords.txt
	 * Keep lines follow pickit format and any given runeword is tested vs ALL lines so you don't need to repeat them
	 */
	Config.MakeRunewords = false; // 是否启用制作符文之语功能 。Set to true to enable runeword making/rerolling

	//Config.Runewords.push([Runeword.Insight, "Thresher"]); // 使用锐利做眼光 Make Insight Thresher
	//Config.Runewords.push([Runeword.Insight, "Cryptic Axe"]); // 使用神秘之斧做眼光 Make Insight Cryptic Axe

	//Config.KeepRunewords.push("[type] == polearm # [meditationaura] == 17"); //保留光环17的合格的rw，不合格继续做，这里的保留条件同样可以写在拾取文件中去。

	//Config.Runewords.push([Runeword.Spirit, "Monarch"]); // 用统治者做精神 Make Spirit Monarch
	//Config.Runewords.push([Runeword.Spirit, "Sacred Targe"]); // 用 st 做精神Make Spirit Sacred Targe

	//Config.KeepRunewords.push("[type] == shield || [type] == auricshields # [fcr] == 35"); //保留光环35fcr的，不合格继续做，这里的保留条件同样可以写在拾取文件中去。

	// 游戏公共设置部分 Public game options

	// If Config.Leader is set, the bot will only accept invites from leader. If Config.PublicMode is not 0, Baal and Diablo script will open Town Portals.
	Config.PublicMode = 1; // 组队模式，1为发送或受队伍邀请，2为仅接受组队邀请，3位仅发送组队邀请，0位关闭1 = invite and accept, 2 = accept only, 3 = invite only, 0 = disable
	// Party message settings. Each setting represents an array of messages that will be randomly chosen.
	// $name, $level, $class and $killer are replaced by the player's name, level, class and killer
	Config.Greetings = ["Hello, $name (level $level $class)"]; // 组队后发的欢迎信息 Example: ["Hello, $name (level $level $class)"]
	Config.DeathMessages = ["Watch out for that $killer, $name!"]; // 队伍有人死亡发的消息 Example: ["Watch out for that $killer, $name!"]
	Config.Congratulations = ["Congrats on level $level, $name!"]; // 队伍有人升级发的消息 Example: ["Congrats on level $level, $name!"]
	Config.ShitList = false; // Blacklist hostile players so they don't get invited to party.“黑名单”敌对的球员，所以他们不被邀请参加聚会
	Config.UnpartyShitlisted = false; // Leave party if someone invited a blacklisted player.如果有人邀请了列入黑名单的球员离开派对。

	// 通用设置部分 General config
	Config.AutoMap = false; // Set to true to open automap at the beginning of the game.
	Config.LastMessage = ""; // 游戏结束前发的消息 Message or array of messages to say at the end of the run. Use $nextgame to say next game - "Next game: $nextgame" (works with lead entry point)
	Config.MinGameTime = 60; // 游戏最小时间，脚本运行完没到时间就在城里等待。 Min game time in seconds. Bot will TP to town and stay in game if the run is completed before.
	Config.MaxGameTime = 0; // 游戏最大时间，设置好后，不管脚本是否运行完，到时间退出。Maximum game time in seconds. Quit game when limit is reached.
	Config.TeleSwitch = false; // 是否启用换手tp功能 Switch to slot II when teleporting more than 1 node.
	Config.OpenChests = true; // 是否在杀敌过程中打开宝箱Open chests. Controls key buying.
	Config.MiniShopBot = true; // 访问npc时候扫描商店物品 Scan items in NPC shops.
	Config.PacketShopping = false; // 访问商店时候，是否使用封包购物，可提高速度。Use packets to shop. Improves shopping speed.
	Config.TownCheck = false; // 药水没了是否回城补给 Go to town if out of potions
	Config.LogExperience = true; // 现实经验值Print experience statistics in the manager.
	Config.PingQuit = [{Ping: 0, Duration: 0}]; // 是否在达到设定的ping值多少秒后退出游戏。Quit if ping is over the given value for over the given time period in seconds.

	//神殿设置部分
	// Shrine Scanner - scan for shrines while moving.
	// Put the shrine types in order of priority (from highest to lowest). For a list of types, see sdk/shrines.txt
	// 神殿代码可以再这个文件中找到 sdk/shrines.txt，优先级从高到低。
	Config.ScanShrines = [18,15];

	// MF Switch
	Config.MFSwitchPercent = 0; // boss血量达到多少百分比后换手击杀。0位禁用。Boss life % to switch weapons at. Set to 0 to disable.
	Config.MFSwitch = 0; // MF武器位置，0为第一套武器，1为第二套武器。MF weapon slot: 0 = slot I, 1 = slot II

	//fastmod 设置部分，full packet casting 模式请不要用在近身肉搏角色身上。
	// Fastmod config
	Config.FCR = 125; // 0 - disable, 1 to 255 - set value of faster cast rate 
	Config.FHR = 86; // 0 - disable, 1 to 255 - set value of faster hit recovery 
	Config.FBR = 0; // 0 - disable, 1 to 255 - set value of faster block recovery 
	Config.IAS = 0; // 0 - disable, 1 to 255 - set value of increased attack speed 
	Config.PacketCasting = 2; // 是否使用封包释放技能，0禁用，1封包释放传送技能，2封包释放所有技能。0 = disable, 1 = packet teleport, 2 = full packet casting.
	Config.WaypointMenu = false; // Set to true for Single and private realms

	
	//敌对设置
	// Anti-hostile config
	Config.AntiHostile = false; // 是否开启敌对检测Enable anti-hostile
	Config.HostileAction = 0; // 敌对应对策略，0立即退出，1在身边退出，2干敌对玩家。0 - quit immediately, 1 - quit when hostile player is sighted, 2 - attack hostile
	Config.TownOnHostile = false; // Go to town instead of quitting when HostileAction is 0 or 1
	Config.RandomPrecast = false; // Anti-PK measure, only supported in Baal and BaalHelper and BaalAssisstant at the moment.
	Config.ViperCheck = false; // Quit if revived Tomb Vipers are sighted

	// DC设定 DClone config
	Config.StopOnDClone = true; // 发现DC立即回程 。Go to town and idle as soon as Diablo walks the Earth
	Config.SoJWaitTime = 10; // 发现sell soj 在城镇等待时间，分钟。0为禁用。Time in minutes to wait for another SoJ sale before leaving game. 0 = disabled
	Config.KillDclone = true; // 前往Palace Cellar3次尝试击杀dc，请注意身上不能带usc。Go to Palace Cellar 3 and try to kill Diablo Clone. Pointless if you already have Annihilus.
	Config.DCloneQuit = false; // 1 = quit when Diablo walks, 2 = quit on soj sales, 0 = disabled

	// 忽略怪物设置Monster skip config
	// Skip immune monsters. Possible options: "fire", "cold", "lightning", "poison", "physical", "magic".
	// You can combine multiple resists with "and", for example - "fire and cold", "physical and cold and poison"
	// 这是一个例子，忽略冰免疫和物理免疫的怪。 Config.SkipImmune = ["physical and cold"]
	Config.SkipImmune = [];
	// Skip enchanted monsters. Possible options: "extra strong", "extra fast", "cursed", "magic resistant", "fire enchanted", "lightning enchanted", "cold enchanted", "mana burn", "teleportation", "spectral hit", "stone skin", "multiple shots".
	// You can combine multiple enchantments with "and", for example - "cursed and extra fast", "mana burn and extra strong and lightning enchanted"
	// 你可以设定跳过拥有某种技能的怪。
	Config.SkipEnchant = [];
	// Skip monsters with auras. Possible options: "fanaticism", "might", "holy fire", "blessed aim", "holy freeze", "holy shock". Conviction is bugged, don't use it.
	// 你可以设定跳过某些地图的怪。
	Config.SkipAura = [];

	/* Attack config
	 * To disable an attack, set it to -1
	 * Skills MUST be POSITIVE numbers. For reference see http://pastebin.com/baShRwWM
	 */
	// 技能设定 纤细技能代码请查阅  \d2bs\kolbot\sdk 
	// 常见的角色技能设置文件可以在这里找到Templates\Attacks.txt
	Config.AttackSkill[0] = -1; // Preattack skill. Not implemented yet.
	Config.AttackSkill[1] = 112; // Primary skill to bosses.
	Config.AttackSkill[2] = 113; // Primary aura to bosses
	Config.AttackSkill[3] = 112; // Primary skill to others.
	Config.AttackSkill[4] = 113; // Primary aura to others.
	Config.AttackSkill[5] = 101; // Secondary skill if monster is immune to primary.
	Config.AttackSkill[6] = 124; // Secondary aura.
	

	// Low mana skills - these will be used if main skills can't be cast.
	Config.LowManaSkill[0] = -1; // Low mana skill.
	Config.LowManaSkill[1] = -1; // Low mana aura.

	/* Advanced Attack config. Allows custom skills to be used on custom monsters.
	 *	Format: "Monster Name": [attack skill id, aura skill id]
	 *	Multiple entries are separated by commas
	 */
	Config.CustomAttack = {
		//"Monster Name": [-1, -1]
	};

	Config.BossPriority = false; // 是否优先击杀金怪Set to true to attack Unique/SuperUnique monsters first when clearing
	Config.ClearType = 0xF; // 清场模式 ，0xF为跳过普通怪，0为清场。Monster spectype to kill in level clear scripts (ie. Mausoleum). 0xF = skip normal, 0x7 = champions/bosses, 0 = all

	// Wereform setup. Make sure you read Templates/Attacks.txt for attack skill format.
	Config.Wereform = false; // 0 / false - don't shapeshift, 1 / "Werewolf" - change to werewolf, 2 / "Werebear" - change to werebear

	// Class specific config
	Config.AvoidDolls = false; // Try to attack Soul Killers from a greater distance with hammerdins.
	Config.Vigor = true; // Swith to Vigor when running
	Config.Charge = true; // Use Charge when running
	Config.Redemption = [50, 50]; // Switch to Redemption after clearing an area if under designated life or mana. Format: [lifepercent, manapercent]
	
	
	// AutoBuild System ( See /d2bs/kolbot/libs/config/Builds/README.txt for instructions )
	Config.AutoBuild.Enabled = false;			//	This will enable or disable the AutoBuild system
	
	Config.AutoBuild.Template = "BuildName";	//	The name of the build associated with an existing 
												//	template filename located in libs/config/Builds/

	Config.AutoBuild.Verbose = true;			//	Allows script to print messages in console
	Config.AutoBuild.DebugMode = true;			//	Debug mode prints a little more information to console and 
												//	logs activity to /logs/AutoBuild.CharacterName._MM_DD_YYYY.log
												//	It automatically enables Config.AutoBuild.Verbose
}
