# IMPORTANT FOREWARNING PLEASE READ FIRST!!!

Unlike all custom stuff that works by adding stuff, the already existing .jn files are read by the game to provide (all?) in-game text. Meaning, you're editing core part of the game.

ALWAYS back up your translated files, and ALWAYS keep the backup of original English texts somewhere safe. In case you screw up, you will have the ability to go back fix things (otherwise you will have to uninstall and install WoH again).

Also, future updates will probably include changes to game's texts (typo fixes, line adjustments etc), so expect the .jn files to be overwritten in case a hotfix/update is released by panstasz (you did backup your translation, right? Right??)

# GENERAL HOW TO

All files have .jn filetype; it seems to be another custom filetype made by panstasz. They can be easily opened by any plainstext editor, even Windows Notepad

The files themselves are stored in: C:\Program Files (x86)\Steam\steamapps\common\WOH\language

I strongly recommend getting something that comes with word and line counter, for example Notepad++. Why?

Because all files are long, long lists of strings. This means you gotta know which string relates to what place/menu/event, otherwise you will be very lost and confused (especially that the files also contain un-released stuff as well).

Panstasz uses |10 |20 |30 and so on to indicate which line this is, probably because he does that by hand (the madman). I recommend you leave these in too.

# SUPPORTED UNICODE BLOCKS

The game uses Silver font from poppyworks.itch.io and therefore available Unicode blocks depend on the font's supported blocks.

The list can be found here: https://itch.io/t/488011/currently-supported-unicode-blocks

The font iself supports many accented characters, and panstasz periodically updates the in-game sheet with new letters. For the most part, common Scandinavian and Romance umlauts/accented letters are supported.

# .JN FILE LISTING AS OF 0.9.9d

#### woh_addy.jn
Home, City interface, Locations, student gossip lines (Schoolyard), Endgame (Lighthouse).

#### woh_chal.jn

Challenges' menu, Endless mode texts, Ending screens, Mystery and game summaries, Cook Book item and Threat Level texts and few misc in-mystery Investigation strings.

#### woh_chara.jn

Characters (except Juri Okusawa), character selection menu, Backstories, Difficulty effects, character outfits (wardrobe at home), misc Home strings, Random character strings, and Student Allies names and bonuses.

#### woh_comb.jn

Combat inferface, combat action logs, special combat actions, combat tutorial, Item/Ally interfaces, Equipment screen and game tutorial.

#### woh_dec.jn

Stuff added in version 0.9.92 of World of Horror.

#### woh_enm.jn

Enemy names, types, attack strings, intros and assess dialogues.

#### woh_event.jn

In-game events and event interface/buttons.

#### woh_go.jn

A block of gibberish.

#### woh_halo.jn

Preparation for Investigation items (personalized for each playable character), Options menu strings, miscellaneous YOU tab strings, Level Up strings and few misc in-mystery Investigation strings, Meat Cleaver's damage bonus string.

#### woh_home.jn

Home interface, Mailbox strings, Monument location strings, Mystery board, Mode selection screen, Old God selection screen, Old God effects, Investigation Chibi Screen labels, Scissors Tutorial Mode Intro.

#### woh_ichi.jn

A block of gibberish. In the middle, Eimi and Uchida Ally strings and T'Cithura and Kaibara Villagers dual-enemy strings.

#### woh_mod.jn

Reward strings for custom events, kept separately from others for some reason

#### woh_mys.jn

Mysteries (intros, investigation blocks, ending panels etc, except Freakish Fable) and Endless mode intro.

#### woh_ni.jn

A larger block of numbers. Latter half contains Freakish Fable mystery.

#### woh_palette.jn

In-game color palette names.

#### woh_perk.jn

Perks, Treatments, Curses/Injuries, Town Statuses.

#### woh_san.jn

Juri Okusawa's character info and some 'teacher' strings related to ??. 

#### woh_small.jn

Weapon labels and stats, Items, Ally chat dialogues, Allies.

#### woh_spells.jn

Spell labels, Spells and few extra Allies.

#### woh_ui.jn

Game interface, Main Menu, Extras Menu, New Game Menu, Difficulty Levels, Extra Options (Character Selection button), Options Menu and labels, Mystery Completion Summary strings, In-game action log (bottom panel), Card Pack Selection Screen, Game Intro texts, Achievements Menu and misc strings.

#### woh_ver.jn

Current (0.9.92) stable game version (not hotfixes) in-game pop-up above the main menu

#### woh_yon.jn

Another block of numbers.