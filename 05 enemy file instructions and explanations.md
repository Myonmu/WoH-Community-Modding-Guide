# Enemy Template
```
[enemy]
name=""
subtitle=""
type=""
location=""
ending=""
author=""
intro=""
can_run=""
weakness=""
health=""
power=""
damagevalue=""
damagetype=""
exp=""
prize_type=""
prize_name=""
hit01=""
hit02=""
hit03=""
art01=""
art02=""
artfreq=""
```

# THE ARCANE WORDS, WHAT DO THEY MEAN??

Above is the entirety of coding that is used to create a custom enemy in World of Horror (as of version 0.9.92).

ALL of them must be followed by ="", and all text, effects and number values must be typed inside the "quotation marks".

Make sure you do not miss any of the quotation marks, otherwise the game will read the code incorrectly, leading to errors, bugs, or even game crashes.

Below are the explanations of above instruction sets:

### \[enemy]

placed at the very beginning of the file, it makes the game understand that this is an enemy encounter file that can be read

### name

name of the enemy, keep it short as the character limit is about ~15 before the text exceeds available space. Note that World of Horror enemies' names are stylized in ALLCAPS

### subtitle #OPTIONAL 

subtitle for the enemy, shows on a black bar under the enemy name. You can squeeze about ~15 characters before the text exceeds available space. Note that World of Horror enemies' subtitles are usually (but not always) stylized in ALLCAPS, just like their names

### type

type of the enemy, currently available are:

- **human**: like HORRIBLE OLD MAN or TAKASHI-SAN. This class of enemy can be damaged or outright killed by several spells and items, and is most common class of enemies alongside eldritch
- **monster**: also known as 'beast', a generic label for animal, animal-like and mutant enemies.
- **ghost**: that one enemy type everyone hates, they cannot be harmed normally, instead you need to bow bow clap clap your way through (or bribe them with money or sever their ties).
- **eldritch**: a generic label for every alien horror and grotesque abomination there is. Some 'human' looking enemies also go there (like TIME WARPER) due to how warped they are.
- **undead**: walking corpses and other undead wraiths. Quite rare in the base game.
- **plant**: man-eating plants and various human-plant hybrids. Like undead, quite rare in the base game.
- **vampire**: the rarest of enemy types, with only three examples in base game (BLOODSUCKER, STALKER GIRL, PILLAR VAMPIRE).
- **circle**: ??, is the type used by TOGETHER (from Bulletin mystery) and NAMELESS HORROR (from Festival mystery).

### location

where the enemy has a chance to appear:

- **school**: this enemy will show up at the School (the place with Schoolyard and Library)
- **seaside**: this enemy will show up at the Seaside (the place with Hardware Store)
- **mansion**: this enemy will show up at the Mansion
- **downtown**: this enemy will show up at the Downtown (the place with everyone's favorite Dog Shop)
- **hospital**: this enemy will show up at the Hospital (where Doctor's Office and Pharmacy are located)
- **forest**: this enemy will show up at the Forest
- **village**: this enemy will show up at the Village
- **apartment**: this enemy will show up at the Apartment

### ending #OPTIONAL 

USED WITH CUSTOM MYSTERIES. Determines if defeating this mystery sends the player to a Custom Mystery's ending screen if set to: ending="1"

### author #OPTIONAL 

who created this enemy. Will show up during the encounter on the left side of the enemy screen.

### intro

introduction texts on black screen, shown to the player right before the encounter begins. The text autowraps and can be broken up into new lines with #, just like custom event texts.

###  can_run #OPTIONAL 

possible values are "1" (can run) and "0" (can't run, only bosses and few special enemies disallow this). If you do not include this in the file, the game will default the value to "1" (can run).

###  weakness #OPTIONAL 

this enemy will receive 1 damage extra from chosen source:

- **blunt**: weapons with \[BLUNT] tag, like Carpenter Hammer, Baseball Bat, Shovel...
- **sharp**: weapons with \[SHARP] tag, like Sharp Knife, Katana, Scalpel...
- **fire**: weapons with \[FIRE] tag, currently the only two weapons with this tag are Torch and DIY Flamethrower
- **magic**: weapons with \[MAGIC] tag, currently only the Small Candle possesses this tag
- **what**: unused, no weapons with this tag are currently in-game

### health #OPTIONAL 

anything from 1 to ??, the amount of health enemy has. If you do not include this in the file, the game will default enemy health to "10".

### power #OPTIONAL 

seems to be accepting any value from 0 to ??, the more power enemy has, the harder it is to hit it. If you do not include this in the file, the game will default enemy power to "10".

### damagevalue #OPTIONAL 

seems to be accepting any value from 0 to ??, how much damage the enemy does each turn. If you do not include this in the file, the game will default this value to "1".

### damagetype #OPTIONAL 

possible values are "STA", "REA", "ALL" (damages both STA and REA of player character), or "DOOM" (increases DOOM meter with each attack). If you do not include this in the file, the game will default this value to "STA".

### exp

amount of experience the player's character will receive after defeating this enemy.

### prize_type

a 'drop' the enemy has. Currently the only possible value is "item", or just leave it blank if you do not want to give any rewards

### prize_name

name of the prize dropped; currently only items can be given out as reward, you need to type in the item's name in ALLCAPS, for example: prize_name="STEAK KNIFE"

### hit01 (hit02, hit03)

messages displayed in log at the bottom of the screen after enemy's attack. The game does not includes enemy's name in this automatically, so you have to do it yourself, for example: hit01="EXAMPLE-CHAN slaps you!"

### art01 (art02)

filepaths to the enemy art files. art01 is the first frame, art02 is the second frame. The art is **512x184** pixels, and you must either keep the background transparent (via alpha channel) or draw your own background.

### artfreq

how many in-game 'ticks' happen before art01 is switched into art02; lower values means the change happens more often. Values below 30-40 make the enemy sprite behave very 'jittery'.