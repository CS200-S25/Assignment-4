# Assignment-4

There are three parts for assignment 3:
- [ ] Part 1 - Practice with GUIs
- [ ] Part 2 - Continuing your text-based adventure game

## Part 1: Practice with GUIs
In this part of the PSET, you will practice identifying components of given GUIs and recreate them using JavaFX. 
For the following GUI for a recipe management program:

![alt text](https://github.com/CS200-S25/Assignment-4/blob/main/GUI.jpg?raw=true)

1. Recreate this GUI using controls from JavaFX in a way that closely matches this image visually, you will get full credit if you use a control that closely resembles the element in the image even if it is not the same one.
2. Sketch a scene graph on paper of your resulting GUI (see section 6.1.2 for an example scene graph https://math.hws.edu/javanotes/c6/s1.html)

As a resource, it would be helpful to browse through a list of JavaFX controls: https://docs.oracle.com/javafx/2/ui_controls/jfxpub-ui_controls.htm and a list of JavaFX layouts: https://docs.oracle.com/javafx/2/layout/builtin_layouts.htm.

## Part 2: Continuing your text-based adventure game
Complete your text-based adventure game by updating two aspects: 1) incorporating your hierarchy of classes representing the items that are available in your game into the rest of your game, 2) updating the health points for a player based on damage occured from animals in rooms. 

For 1) your Game class must be updated with the following addition to `parseCommand()` which will require you to create a new method for `drop()` and `eat()`. If a user drops an item from their inventory (by typing the string corresponding to the item) then the item is added to the treasure chest of the current room. If a user eats a food item, then their health should increase.

```
public void parseCommand(String input) {
        
        String[] wordList = input.split("[\s]");
        String verb;
        String noun;
        
        if(wordList.length < 2 || wordList.length > 2) {
            System.out.println("Only 2 word commands allowed!");
        } else {
            verb = wordList[0];
            noun = wordList[1];
            switch (verb) {
                case "take":
                    take(noun); 
                    break;
                case "drop":
                    drop(noun); // THIS IS A NEW ADDITION
                    break;
                case "eat":
                    eat(noun); // THIS IS A NEW ADDITION
                    break;
                case "go":
                    movePlayer(noun);
                    break;
                default:
                    System.out.println(verb + " is not a known verb!");
            }
        }
    }
```

For 2) you must also update your game to reduce a player's health by the damage of the animal when the player enters a room with that animal.

## COLLABORATION
This assignment is an individual assignment. You can discuss this assignment with your peers, TA and instructor. You cannot show code to your peers, you each write your own solutions. You can show code to the TAs and instructor. Additionally, you cannot use generative AI or online resources that are not linked from our course website to complete this assignment.  

## SUBMISSION
Submit the following files to Gradescope for Assignment 1:
* take a picture of your solutions to Part 1 and upload a .png or .jpeg file to Gradescope
* upload your code for the recipe management GUI and all of the files for your game to Gradescope

Note: You can resubmit your assignment as many times as needed until the deadline. Every time you resubmit, make sure you submit *all* of the files for your assignment every time.
