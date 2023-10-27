# Mystery Template

```
[mystery]
name=""
author=""
art=""
description=""
custom_ui=""
mystery_sound=""
combat_sound=""

(OPTIONAL) [restricted_locations]
downtown=0
apartment=0
hospital=0
school=0
seaside=0
forest=0
mansion=0
village=0

(OPTIONAL) [card_a] & [card_b]
name=""
trigger=""
art=""
flavor=""
tags=""
a_effect=""
a_value=
b_effect=""
b_value=

[intro]
art=""
text_one=""
text_two=""
text_thr=""
text_fou=""

[progress]
location=""
background=""
one_loc=""
one_txt=""
one_frc=""
two_loc=""
two_txt=""
two_frc=""
thr_loc=""
thr_txt=""
thr_frc=""
fou_loc=""
fou_txt=""
fou_frc=""
fiv_loc=""
fiv_txt=""
fiv_frc=""
six_loc=""
six_txt=""
six_frc=""
sev_loc=""
sev_txt=""
sev_frc=""
eig_loc=""
eig_txt=""
eig_frc=""
nin_loc=""
nin_txt=""
nin_frc=""
ten_loc=""
ten_txt=""
ten_frc=""

[ending_a]
end_title=""
end_img="
end_txta=""
end_txtb=""
end_txtc=""
end_txtd=""

[ending_b]
end_title=""
end_img=""
end_txta=""
end_txtb=""
end_txtc=""
end_txtd=""

[big_ending]
end_txt=""
end_txta=""
end_txtb=""
end_txtc=""

[ending_c]
end_title=""
end_img=""
end_txta=""
end_txtb=""
end_txtc=""
end_txtd=""

```

# FUNNY ALL CAPS TITLE HERE

The above is the complete list of all instructions a custom mystery .ito file can have (as of 0.9.92), and which World of Horror's executable will read for your custom event to take effect.

Almost all of them must be followed by ="", and all text, effects and number values must be typed inside the "quotation marks".

The only exception is if you want to make the Mystery shorter than 10 Investigations, more about it below.

Below are the explanations of above instruction sets. Please note that unlike other files, Mystery file has several separate sections, each with similar code strings.

## \[mystery]

placed at the very beginning of the .ito file, it lets the game know that everything below it is a mystery's code.

### name

name of the mystery as it will be visible on the Mystery Board and Custom Mysteries Tab in-game.

### author

name of the mystery's author; it will show under the Mystery's name in Custom Mysteries Tab in-game (but not on Mystery Board).

### art

icon that will be shown besides Mystery's name in Custom Mysteries Tab in-game (but not on Mystery Board). The icon is a .png with size of 31x31px. The file path is taken from the level of the mystery.ito, so consider putting it in a subfolder, for example 'mymystery/mymysteryicon.png'
description: a short text description of the Mystery, it will be shown for the player when you move the cursor over the Mystery's title in Custom Mystery Tab in-game.

### custom_ui #OPTIONAL 

whether this mystery uses custom town layout image file.png, leave blank to use default World of Horror city layout. the size is 512x288 pixels and contains a green (transparency) area for background image set below in \[progress] section. Check the custom example mystery 'woh_mystery_onsen' to better see how a custom UI looks.

###  mystery_sound #OPTIONAL 

music theme OR custom music file used during investigation phase of the mystery

### combat_sound #OPTIONAL 

music theme OR custom music file used during combat encounters of the mystery. The viable strings for this and mystery_sound are:

- **path_to_file**: game will launch music from the set filepath; note that unlike other filepaths, this one does NOT include the mystery's folder, but has to be inside it. (simply: my_mystery_music.mp3, and not: my_mystery\my_mystery_music.mp3)
- **computer**: melancholic tune with heavy cover in combat phase and rising 'noise' at the end. In vanilla WoH, used during Beckoning Bulletin and Peculiar Painting mysteries.
- **demon**: low, droning tune that is used during Old God choice screen when setting up a new Customized Playthrough.
- **forest**: slowly building up tune with heavy cover in combat phase. In vanilla WoH, used predominantly in forest mysteries (Freaky Feature, Fearful Festival etc), slowed down version is also present during Lighthouse climb (endgame).
- **investigation**: a pulsating tune. In vanilla WoH, used during Abnormal Arms, Freakish Flood and Rotten Ramen mysteries, and during the Endless Mode.
- **paleroom**: short, beeping tune. In vanilla WoH, used during Contagious Coma and Wordless Ward mysteries.
- **school**: creepy, appregio-laden tune. In vanilla WoH, used during Crimson Cape, Morbid Mermaids and School Scissors mysteries.
- **seaside**: pulsating and high-paced tune with some 'sea waves' effects. In vanilla WoH, used during Evolving Eels and Moonlight Sailors mysteries.
- **theme**: short tune with long notes and underlying beeping. In vanilla WoH, used during Household Hell mystery.

(note that in-built tracks are synchronized between mystery and combat phases, allowing for smooth transition. Research's pending if and how to do it with own custom music!)

##  \[restricted_locations] #OPTIONAL 

if included and set to 0, the specified location will have blacked-out icon and will be inaccessible during custom mystery. The location tags are the same as elsewhere (downtown, apartment, school etc).
*you cannot set HOME (Resting area) as inaccessible

## \[card_a] & \[card_b] #OPTIONAL 

used to specify up to 2 custom, temporary (will be removed at mystery's conclusion) statuses, to simulate injuries, curses, allies etc.

### name

name you want to give this card, it will show as such in Allies/Perks Tab in-game; in vanilla game such card names are in ALLCAPS.

### trigger

under what circumstances this card is added to the Allies/Perks Tab

- start: card will be added at the very start of the custom mystery
- (empty): card will be only triggered by specifying it via a reward option of a Custom Event forced by this mystery. Refer to '02 ito file instructions and explanations' file to see how to set this linkage properly

### art

filepath to the .png file containing art of this card. filesize is 170x96 pixels

### flavor

flavor text for the status card and its pseudo-tag, both separated by three # line breaks

### tags

flavor tags you wanna set up, in base game such tags are confined within \[SQUARE BRACKETS]
*now that the string set via 'tags' will be displayed between two sections of 'flavor' strings, that's what those three # line breaks are used for!

### a_effect/b_effect

effect(s) this status card will bestow upon player character; you can set 2 effects per card

### a_value/b_value

adds X value for effect described above, precede with a - to substract instead. Unlike all other value settings, DO NOT INCLUDE DOUBLE QUOTATIONS "" FOR THESE VALUES (a_value=1 instead of a_value="1"). Effects possible are as follow:

- **investigation_doom**: adds X doom per Investigation
- **investigation_exp**: adds X experience points per Investigation
- **investigation_stamina**: adds X stamina per Investigation
- **investigation_reason**: adds X reason per Investigation
- **combat_doom**: adds X doom at the start of a Combat encounter
- **combat_exp**: adds X experience points at the start of a Combat encounter
- **combat_stamina**: adds X stamina at the start of a Combat encounter
- **combat_reason**: adds X reason at the start of a Combat encounter
- **onetime_doom**: adds X doom when this Card is present; when the mystery ends, this value is removed too
- **onetime_exp**: adds X doom when this Card is present; when the mystery ends, this value is removed too
- **onetime_stamina**: adds X doom when this Card is present; when the mystery ends, this value is removed too
- **onetime_reason**: adds X doom when this Card is present; when the mystery ends, this value is removed too
- **damage_deal**: boosts damage you deal during Combat encounters by X
- **damage_receive**: boosts damage you receive during Combat encounters by X
- **strength**: adds X to your character's Strength when this Card is present; when the mystery ends, this value is removed too
- **dexterity**: adds X to your character's Dexterity when this Card is present; when the mystery ends, this value is removed too
- **perception**: adds X to your character's Perception when this Card is present; when the mystery ends, this value is removed too
- **knowledge**: adds X to your character's Knowledge when this Card is present; when the mystery ends, this value is removed too
- **charisma**: adds X to your character's Charisma when this Card is present; when the mystery ends, this value is removed too
- **luck**: adds X to your character's Luck (hidden stat) when this Card is present; when the mystery ends, this value is removed too

## \[intro]

the game will use the code below this bracket for Mystery Intro.

### art

image that will be shown during Mystery's intro. The intro image is a .png with size of 218x207px. The game will use a rectangular 'window' to place the image in, rounding the corners a few pixels deep. The file path is taken from the level of the mystery.ito, so consider putting it in a subfolder, for example 'mymystery/myintro.png'

### text_one

short 'lore' description about the mystery's central topic.

### text_two #OPTIONAL 

same as above. If you include this line, the first description will provide a > button for the player to reach this text. If you don't, the game's intro will end with just one panel, and > button will not be drawn.

### text_thr #OPTIONAL 

same as above. 

### text_fou #OPTIONAL 

same as above. 

## \[progress]

the game will use the code below this bracket for Mystery's investigations.

### location

this string will be used on the 'ending location' button at the very end of mystery. The game will render it as 'INVESTIGATE#location' (# is in-game line break automatically applied by game), for example location="MY HOUSE" will show as 'INVESTIGATE#MY HOUSE'.

### background

image specified here will be used as the background. The background image is a .png with size of 512x148px. The file path is taken from the level of the mystery.ito, so consider putting it in a subfolder, for example 'mymystery/mybackground.png'

### one_loc 

(two_loc, three_loc and so forth)

the in-game Location that needs to be investigated by the Player to progress the mystery. Available strings are:

- **downtown**: player needs to investigate DOWNTOWN
- **apartment**: player needs to investigate APARTMENTS (yes, the string is in singular, the location's name is in plural)
- **school**: player needs to investigate SCHOOL
- **hospital**: player needs to investigate HOSPITAL
- **seaside**: player needs to investigate SEASIDE
- **forest**: player needs to investigate FOREST
- **mansion**: player needs to investigate MANSION
- **village**: player needs to investigate VILLAGE
- **ending**: this will cause the game to draw Ending Button that uses the text in 'location' string. If you don't want to use this, you can use "ending=1" in a forced Custom Event or Custom Enemy encounter. If you do not include such triggers either, the game will conclude the mystery using previous numbered step's information instead. There's no minimum limit for investigations; it is therefore possible to make a mystery that ends right at the beginning.
### one_txt 

(two_txt, thr_txt etc etc)

the text displayed above Locations panel, under the Doom meter. It will be shown preceding the investigation of the location defined by one_loc. Game auto-wraps overflowing text; you can also use # to create line breaks

### one_frc 

(two_frc, thr_frc...)

event defined here will be forced to show in-game, overriding any random event or enemy encounter. The file path starts FROM THE LEVEL OF GAME ITSELF, so if you put it in your own subfolder, the path should read: 'mystery/mymystery/myforcedevent.ito'. You cannot force events from the base game, or custom events from 'custom' folder. You can use this to give the player an event that changes the mystery's ending, for example, via 'ending_trigger' reward. Check file '02 ito file instructions and explanations' for extra info.

**How to implement a 'boss fight' with the current system: On last investigation, force an event that will trigger an enemy encounter, and set that encounter as inescapable (can_run="0") and with ending enforcement (ending="1")

## \[ending_a] 

(\[ending_b] and \[ending_c] use the same set of strings, but will process them separately when the player reaches them): the game will use the code below this bracket to show Ending A.
end_title: will show up at the top-right of the ending screen. in base game, these are rendered in ALL CAPS, for example 'OPHTHALMOLOGY (I)'.

### end_img

image specified here will be used as the image for left-half of the ending screen. The ending image is a .png with size of 227x277px. The file path is taken from the level of the mystery.ito, so consider putting it in a subfolder, for example 'mymystery/myending.png'

### end_txta

will provide some text below the end title for the player.

### end_txtb

same as above, and the game will draw a > button for the player to reach this text.

### end_txtc

same as above.

### end_txtd

same as above.

## \[big_ending]

the game will use the code below this bracket for Mystery's Ending Summary (where you get experience, curse effects, etc).

### end_txt

this text will be shown above mystery's summary if there's only 1 Ending (you didn't set up any trigger_ending via custom event rewards)

### end_txta

this text will be shown above mystery's summary if player reaches Ending A of custom mystery (if your mystery has exactly 1 ending, it will use "end_txt" instead!)

### end_txtb

this text will be shown above mystery's summary if player reaches Ending B of custom mystery

### end_txtc

this text will be shown above mystery's summary if player reaches Ending C of custom mystery