# CS611-Legends

Name
-------------------------------------------------------------------------------------------------
--Bhagyasri Kota--
--U63334155--


Files
-------------------------------------------------------------------------------------------------
***Added space for more readability***
1. Main.java - Main class used start the run and call the game selection class

2. GameSelection.java - called from main and used to select from the list of games available at hand to play. Had the music included for the game.

3. LegendsMonsterAndHeroes.java-has start function to begin the Legends game.Creates LNMLayout class from within this class to make it immutable. Intializes the gameConfig attributes and calls functions to play game

4. RolePlayGame.java - abstract Super class of LegendsMonsterAndHeroes.java and child class to games class. Creates gameconfig instance from within the constructor to store the properties of the game.

5. Game.java - abstract super class to RolePlayGame created to maintain the inheritance for all different type of games such as boardgames and card games.

6. GameLayout.java - abstract class contains the basic functions to define any game's layout and to reset layout.

7. LNMGameLayout - child class to GameLayout.java and implements the specific design and displays the structure of LNM map and other necessary displays like controls etc.,

8. Cell.java - abstract super class to other cells of the game. Has list of cell types from cellType class and abstract functions to be performed in the cells.

9. CellType.java - Enum class, contains the values of the types of cell available to play in the game and their values used in the game.

10. CommonPlace.java - child class to cell class. Has the logic to create monsters of similar game level based on a random chance and if not allows Hero to explore their inventory and corresponding cell design

11. InaccessibleCell.java - child class to cell class. Has logic to restrict the Heros from entering the cell and corresponding cell design

12. Market.java - child class to cell class. Has inventory of potions, spells, armors and weapons created as soon as market object is created once and used everywhere. Has logic to display and sell the inventory.

13. MarketInventory.java - abstract class and super class to potion, spell, armor etc., Implements buy/sellable interface. 

14. FileToList.java - parser created to read from the files and convert to list for mapping.

15. GameDesign.java - Contains design structure to display information as a table on console and other game related ASCII art.

16. GameConfig.java - Contains attributes of the game set at the start either from user inputs or GameConstants declared. Used throughout the execution of the game. Created from game.class

17. GameConstant.java - contains all the static variables set as final to be used throughout the game.

18. GameFunctions.java - contains static functions which can be used anywhere f.e., conversion from i,j to cell value format. Not just particular to this but any kind of game.

19. GameMusic.java - contains logic to start, loop and stop the music during program execution. Is called from the GameSelection class.

20. isAttackable.java - interface used for object which can to be used to attack like weapons and spells. Contains method definition to hit.

21. isBuySellable.java - interface used for object which can to be bought or sold like weapons, armors, potions and spells. Contains method definition to buy and sell.

22. isCastable.java - interface used for object which can be casted like spells. Contains method definition to cast spells.

23. isUsable.java - interface used for object which can be used like potions, armors. Contains method definition to use.

24. Armors.java - Created to call parser to load the config file, read from the output 2d list and map the armors to the Armor class

25. Spells.java - Created to call parser to load the config file, read from the output 2d list and map the spells to the Spell class

26. Potions.java - Created to call parser to load the config file, read from the output 2d list and map the potions to the Potion class

27. Weapons.java - Created to call parser to load the config file, read from the output 2d list and map the weapons to the Weapon class

28. Armor.java - Armor class has mapper function to create armor object called from Armors class. Implements the use, sell, buy(from interfaces) and get details as a list methods.

29. Potions.java - Potion class has mapper function to create potion object called from Potions class. Implements the use, sell, buy(from interfaces) and get details as a list methods.

30. PotionTypes.java - Enum to contain all the types of potions and their respective naming conventions as values.

31. Spells.java - Spell class has mapper function to create spell object called from Spells class. Implements the cast, sell, buy(from interfaces) and get details as a list methods.

32. SpellTypes - Enum contains all the types of spells and their respective naming conventions as values.

33. Weapon.java - Weapon class has mapper function to create weapon object called from Weapons class. Implements the hit, sell, buy(from interfaces) and get details as a list methods.

34. MarketInventoryType.java - Enum contains all the types of inventory available at market that can be bought or sold and their respective naming conventions as values.

35. Hero.java - Hero class has attributes of all heroes and HeroType.Child class and contains mapper function to create object. Contains function to perform of attack, check inventory, display info, level up etc.,

36. HeroInventory.java - created from the constructor of Hero class as 1-1 relation. Contains list of type of inventory bought by Hero.

37. HeroType.java - Enum contains all the types of Heroes available and their respective naming conventions as values.

38. Monsters.java - Created to call parser to load the config file, read from the output 2d list and map the monsters to the Monster class

39. Monster.java - Monster class has attributes of all monsters and monster types. Child class to gameCharacter and contains mapper function to create object. Contains function to perform of attack.

40. MonsterTypes.java - Enum contains all the types of monsters available and their respective naming conventions as values.

41. GameCharacter.java - abstract super class to hero and Monster class. Has attributes belonging to all the game characters.



Notes:
-------------------------------------------------------------------------------------------------
1. Files to be parsed should be stored in ConfigFiles, for parser class to read class along with the .wav file for music to be played

2. Bonus Implementations:
	a. Parser created to parse files and load. No changes have been done to the files. Code taken care to remove empty lines and extra spaces as well(FileToList.java)
	b. ASCII art implemented at the beginning to display the welcome message and for the game map and cell structures
	c. Music will be played as soon as the game is run until completion or quit.
	d. Colorful UI is implemented on the game's map to display different cell in different colors.
	e. Builder Design pattern implemented to create objects of potion, spell, armor and weapon from market to create market inventory to potions(uses parser to read from file and map all the potions to potion class created from within), spells, armors and weapons class which inturn create the objects. Also, created heroInventory from hero class to keep it immutable and consistent and maintain 1-1 relation
	f. ASCII Animation added after the welcome design.

3. The code can be run in terminal but not on eclipse or IntelliJ workspace since the path is not consistent for the both. Followed the convention mentioned on piazza but modified the path to System.getProperty("user.dir") + "/ConfigFiles/" since adding src to the path will cause issues on terminal.

4. Platform Used - MAC


How to run:
-------------------------------------------------------------------------------------------------
1. Navigate to the directory after downloading the project
2. Run the following instructions on command line:
	javac *.java
	java Main.java
