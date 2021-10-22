

## Summary


This plugin based on the "EnemyBook.js" made by Mr.Yoji Ojima.



This plugin allows

1. Open the Enemybook Scene
2. Displays more statuses that are not included in the "EnemyBook.js"
3. Add command "Enemy Info" and "Enemybook" in the battle scene
4. Create "Check Skill" and "Resister Skill"

You can display these statuses.

・Enemy Name  
・Enemy Sprite  
★Enemy's Index Number  
★Enemy's Level  
★Defeat Number  
・HP, MP, ATK, DEF, MAT, MDF, AGI, LUK  
★Skills - v1.30  
・Drop Items  
★Weak Elements, Resister Elements  
★Weak States, Resister States  
・Description  
★Achievement of Enemybook  
(★ sindicate new items.)  



## 5 Ways For Players To Use


### 1. Enemybook
Display      : All Enemies Resisterd in The Enemybook  
Player Action: Uses Item, Talks to people,  
               "Enemybook" command in the Battle Scene  

### 2. Enemy Info in the Battle Scene  
Display      : Battle Members List. Current Status Like Current HP.  
Player Action: "Enemy Info" command in the Battle Scene  
Settings     : Plugin Parameter 'Show Current Status In The "Enemy Info"' ON  

### 3. General Info of Battle Enemies  
Display      : Battle Members List. General Status (not current status).  
Player Action: "Enemy Info" command in the Battle Scene  
Settings     : Plugin Parameter 'Show Current Status In The "Enemy Info"' OFF  

### 4. Check Skill  
Display      : The target enemy's Current Status  
Player Action: Use "Check Skill" For Enemy  

### 5. Check Skill (General Data) - v1.24  
Display      : The target enemy's General Status  
Player Action: Use "Check Skill" For Enemy  
Settings     : Plugin Parameter 'Show General Status In "Check Skill"' ON  


## How To Use


Just set this plugin to Plugin Manager and call Plugin Command "EnemyBook open"!

Enemies that have name is registerd when player encount on the battle.  
(For the enemy you don't want to resister but has name, need setting.)  

But by default, there are too many items to display and lack to space.Please remove some items by set on Plugin Parameter.


## Other functions


### ○2Ways to Display Element Icon

1. Type Tag in the Element Name 
  example：\i[64]Fire

2. Use Plugin Parameter - v1.04
  Please "Use Element Icon In Plugin Parameter" Plugin Parameter set to ON and type icon numbers split with space in "Element Icons".

  example：76 64 65 66 67 68 69 70 71

### ○Unknown Enemy "???"

If player open the Enemybook when the enemy isn't resistered yet, Enemybook displays "???" on name and status.You can change "???" word by setting Plugin Parameter.

### ○Current Status Setting And Enemy Info Command

When you use "Enemy Info" command, it displays general data by default. When you set Plugin Parameter Show Current Status In The "Enemy Info" ON, It displays Current Data. Not only Current HP, But also ATK and Element Rate change.
You can change setting in game playing by Plugin Command.

### Current States And Check Skill - v1.24

When you use "Check Skill", it displays current enemy's data by default. you can change to display General Status by setting Plugin Parameter  Show General Status In "Check Skill" ON.



### ○Resister Timing

You can set resister timing by setting Plugin Parameter "Resister Timing".

0: Never  
1: When the battle start  
2: When the battle end  

### ○Display Item "???" that player don't get yet  - v1.22

You can Display Item Name "???" that player don't get yet by Plugin Parameter "Hide Item Until Get".


## Plugin Commands


### ○EnemyBook.js Commands

EnemyBook open 
  Open the Enemybook Scene.
EnemyBook add 3
  Register Enemy id 3.
EnemyBook remove 4
  Remove Enemy id 4 from the Enemybook.
EnemyBook complete
  Register all enemies.
EnemyBook clear
  Remove all enemies from the Enemybook.

### ○Oter plugin Command

EnemyBook showInBattle
  Show "Enemy Info" command in battle.
EnemyBook hideInBattle
  Hide "Enemy Info" command in battle.
EnemyBook showCurrentStatus
  Show Current Status when player uses "Enemy Info" Command.
EnemyBook showGeneralStatus
  Show General Status when player uses "Enemy Info" Command.

### ○v1.06

EnemyBook getAchievement per 12  
  Substitute enemybook achievement(%) for variable id 12.  
EnemyBook getAchievement num 14  
  Substitute enemybook achievement(number) for variable id 14.  
EnemyBook isRegistered 5 96  
  Set Switch id 96 whether enemy id 5 is Resisterd or not.  
EnemyBook getDefeatNumber 3 24    
  Substitute Defeat Number of Enemy id 3 to variable 24.  

### ○v1.16
EnemyBook openEnemy 16  
  Open the enemy 16 page.  

### ○v1.17
EnemyBook showAllInBattle  
  Show "Enemybook" Command in the battle.  
EnemyBook hideAllInBattle  
  Hide "Enemybook" Command in the battle.  

### ○v1.20  
EnemyBook clearDefeatNumber  
  Clear the defeat number of all Enemies.  

### ○v1.22
EnemyBook clearEnemyDrop  
  Clear the enemy drop of all Enemies.  


Enemy Note Tag


### ○EnemyBook.js note Tag

 - By 1.27 Version updating, describe line number increased.
Please set Plugin Parameter "Describe Line Number" the line number
you want to display. Max number is infinity.  

&lt;desc1:burabura&gt;  
  This is the description line 1.  
&lt;desc2:buraburaburabura&gt;  
  This is the description line 2.  
&lt;desc3:buraburabura&gt;  
  This is the description line 3.  
 

&lt;book:no&gt;
  When you type this tag to enemy note, the enemy is not be able to
  registerd.

### ○Other tags

&lt;bookLevel:3&gt;
  Display the enemy level 3 to Enemybook.
  If you write nothing, level will not be displayed.

&lt;bookCanCheck&gt; - v1.04
  Player can see status by "Check Skill" if the enemy has &lt;book:no&gt; tag.


Skill Note Tag


&lt;addToEnemyBook&gt;  
  This skill become to "Register Skill".  
  This skill resister target to the Enemybook.  
  If the enemy can be resisterd, Succeed Message will be displayed.  
  If not, Missed Message will displayed.  

&lt;checkEnemyStatus&gt;  
  This skill become to "Check Skill".  
  This skill displays target's status.  
  If the enemy can be resisterd, status will be displayed.  
  If not, Missed Message will displayed.  

  ### ○v1.21  
  You can displey unknown enemy's status "???" When you set Plugin Parameter 'Hide Unknown's Status On "Check Skill"' ON,  

You can set message of these 2 skills by setting Plugin Parameters.  


## State Note Tag


&lt;book:no&gt;  
  You can hide state in the Enemybook.  


## TPB

In the Time Progress Battle, battlers doesn't charge when the EnemyBook opens.
Players can think a lot when they open the EnemyBook.

## Update Log

### Version 1.42
  Fixed the bug that if you used the plugin command "EnemyBook openEnemy" in Battle Scene, start the Battle from turn 0.

### Version 1.41
  Change to be able to use variables  in "openEnemy" command by using "v[id]" argument.

### Version 1.39
  Fixed the bug that display normal color even though set hue when it is Side View.

### Version 1.38
  Fixed the bug when plugin parameter "Display Hit Rate" turn on.
  Fixed the bug that "Display Skills Number" is counted double.
  Add new parameter "Evade Rate".

### Version 1.36
  Fixed the bug that it get error and stop the game when turn Touch UI off in option and open the Enemy Book.

### Version 1.35
  Create for RPGMakerMZ.

### Version 1.34
  Change to be able to change Enemy Photo Offset Y.

### Version 1.33
  Change to be able to change background image opacity by setting plugin
  parameter.

### Version 1.32
  Change to be able to display background image by setting plugin parameter.

### Version 1.30
  Translate this help to English.


## Term of Use


 - Credit - Unnecessary
 - Use in any game engine - not allowed
   You can use this plugin in RPGMakerMV only.
   
 - Commercial use - OK
 - Non-commercial use - OK
 - Edits for your project needs - OK
 - Redistribution - OK

This plugin is edited based in RPGMaker material.
Please see the RPGMaker Term of Use.
    https://tkool.jp/support/index.html