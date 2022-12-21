**I will be using %text% to mark elements which are to be replaced with your own code/arguments**
#### **layout**
***
The scripts are written in a single line, you can have multiple scripts which run after eachother by seperating the scripts with semicolons.  
You can also use commas to write multiple lines in the same scope.

Example:  
`print "yes"; print "quite"` - this would print "yes" and then print "quite".  
`if $var == true: print "yeah", print "okay"; print "nah"` - if var is true, prints "yeah" and "okay", then prints "nah"
#### **Statements**
***
**if statement**  
`if %expression%:` 
- If statement, code behind this element will be ran if expression is true.  

Examples:  
`if $var == true: print "valid!"` - prints valid if var is true  
`if $var: if $var2 == false: print "yes"; if $var == false: print "no";` - prints yes if var is true and var2 is false, otherwise prints no

***
**loop**  
`loop %number or table%:`  
- Loops X times or loops through table.
- when looping through a table you can access the $key and $value variables inside of the loop
- when looping X times you can access $iteration

Examples:  
`loop 5: print $iteration` - loops 5 times and prints the current iteration every loop.  
`loop {1,4,6}: print $value` - loops through the given table and prints out the numbers inside.  
`loop 10: if $iteration == 4: print "Fourth loop"` - loops 10 times, if the current iteration is 4, prints "fourth loop"

***
**Repeat**  
`repeat %delay%:`  
`repeat %delay% %times%:`  
- Repeat some code every %delay% frames.
- When the times argument is given it will only run the script that many times.

Examples:  
`repeat 5 30: print "test"` - Defines a script that runs every 5 frames, 30 times.  
`repeat 60: loop 5: print "yes"` - Defines a script that runs every 60 frames and prints "yes" 5 times.

#### **Variables**
Variables can be used in scripts by putting a dollar sign in front of the variable name.  
`print $variable` would print whatever $variable has assigned to it, or null if not defined.
***
**Default variables**  
`$player` - Gets the current player entity id  
`$playerx` - Gets the current player X position  
`$playery` - Gets the current player Y position  
***
**Variable assignment**  
Variables can be assigned by using a equals sign, similar to other programming languages.  
Defined variables are globally available for the rest of the run. 
Meaning when you defined a variable you can use it again in future scripts.

Examples:  
`$var = 1; if $var == 1: print "true"` - set $var to 1, then run another script which checks if $var is 1 and prints "true"  
`counter = 0; repeat 60: $counter = $counter + 1` - creates a counter variable which increments by 1 every 60 frames.

### **Functions** 
Certain functions are exposed to the scripts, as without them you wouldn't be able to do much.  
These functions are usually straight up exposed from the Noita API so for documentation on them you might have to look on the Noita wiki.

`print %message%:` Prints a given message to the game console and standard output.  
`load %path% %pos_x% %pos_y%:` Loads an entity from a given file path and positions it at the specified coordinates.  
`kill %entity%:` Kills an entity unless it is the player or entity 1.  
`isalive %entity%:` Returns a boolean indicating whether the given entity is alive.  
`addchild %parent% %child%:` Adds a child entity to a parent entity.  
`getx %entity%:` Returns the x-coordinate of an entity's transform.  
`gety %entity%:` Returns the y-coordinate of an entity's transform.  
`setx %entity% %x%:` Sets the x-coordinate of an entity's transform.  
`sety %entity% %y%:` Sets the y-coordinate of an entity's transform.  
`getrotation %entity%:` Returns the rotation of an entity's transform.  
`setrotation %entity% %rotation%:` Sets the rotation of an entity's transform.  
`getwidth %entity%:` Returns the width of an entity's transform.  
`getheight %entity%:` Returns the height of an entity's transform.  
`setwidth %entity% %width%:` Sets the width of an entity's transform.  
`setheight %entity% %height%:` Sets the height of an entity's transform.  
`getinradius %x% %y% %radius%:` Returns a list of entities within a given radius of a given point.  
`getinradiuswithtag %x% %y% %radius% %tag%:` Returns a list of entities with a given tag within a given radius of a given point.  
`getclosest %x% %y%:` Returns the closest entity to a given point.  
`getclosestwithtag %x% %y% %tag%:` Returns the closest entity with a given tag to a given point.  
`getwithtag %tag%:` Returns a list of entities with a given tag.  
`gettags %entity%:` Returns a list of tags associated with a given entity.  
`physicsapplyforce %entity% %x% %y%:` Applies a force to an entity's physics component.  
`physicsapplytorque %entity% %torque%:` Applies a torque to an entity's physics component.  
`printimportant %title% %description%:` Prints an important message to the game console with a given title and description.  
`playsound %bank% %event% %x% %y%:` Plays a sound from a given bank and event at a given location.  
`setcomponentvalue %component% %name% %value%:` Sets a value for a given component of an entity.  
`getcomponent %entity% %name% %tag%:` Returns a component of an entity  
`getcomponentvalue %component% %name%:` Returns the value of a given component of an entity.  
`getfirstcomponent %entity% %name% %tag%:` Returns the first component of an entity  