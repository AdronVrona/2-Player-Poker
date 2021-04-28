# DAYpoker
**Authors: Adron Vrona, Dina Pekelis, Yuxiang Huang, Steve Lee**

## ITERATION 1

##### What user stories were completed this iteration? #####

Currently, we have a mostly functioning game loop that will play a standard heads-up version of the Texas Hold'em variant of poker. This includes giving users the option to do things such as bet, raise bets, call bets, check, see their hand, fold, etc. Any action that can be taken in a Texas Hold'em game is currently implemented. Additionally, a fully functioning pot has been implemented, that keep tracks of bets and allocates to the winner after each hand.

##### What user stories do you intend to complete next iteration? #####

The main thing that needs to be implemented next iteration is the actual system that can score poker hands and correctly award a "winning hand". The program currently just awards every hand that reaches the river to player 1 if nothing else is triggered (a running out of chips, folding, etc). With the implemented system, two hands will be shipped to a function, and the winning hand will be determined. Another thing that needs to be implemented is user graphics, so that cards are more interesting to look at with ASCII art. 

##### Is there anything that you implemented but doesn't currently work? #####

There are some issues with folding that will skip a players turn during the next hand. Additionally, going into negative chip values is possible with a certain combination of inputs. Finally, there are some if else paths that are supposed to print certain error messages, but are currently not triggering.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## ITERATION 2

##### What user stories were completed this iteration? #####

In this iteration, we fixed a lot of the bugs that was causing issues with previous user stories from last iteration, such as the ability to successfully bet, check, raise, etc. Users should now have the ability to play through an entire game of poker with someone else without running into a large bug that affects game performance. Additionally, in this iteration, we added the ability to see cards graphically (what you would see in a physical poker deck) for both cards in your hand and on each street, which adds visual clarity and more feel to the game. Although not completed, the basic coding logic for evaluating hand strength is loaded onto our repository. This code needs to be connected to our game loop and altered so that it can correctly evaluate the hand strength of our two players. 

##### What user stories do you intend to complete next iteration? #####

Next iteration, we will fully be able to evaluate the hand strength of our players and compare them to one another. We underestimated the coding difficulty in this task, but we've made significant headway over the course of this last iteration. Another thing we intend to add is the ability to see player stats that are aggregated over every hand, such as net winnings, largest bet, best hand made, etc. Finally, we want to add more customability and introduction before a player starts a game. We ideally want to make an intro screen that has graphics, gives instructions, allows them to provide inputs for game rules, etc. 

##### Is there anything that you implemented but doesn't currently work? #####

As previously mentioned, our code for evaluating hand strength is not currently adapted to work perfectly for choosing a given hand over another, but rather is the general logic for how hand rankings are chosen (the difference between full house and a better one vs a pair against two pair). Additionally, we need to adapt our code so that ideally our card graphics are printed side by side, which involves printing line by line of each card file that we need to print instead of printing entire files at a time. 


----------------------------------------------------------------------------------------------------------------------------------------------------------------------

## ITERATION 3

##### What user stories were completed this iteration? #####

In this iteration, finally completed the ability to score poker hand ranks. This was an absolute doozy, as we not only have to distinguish between different hand ranks, but also have to distinguish between hands within a give hand rank. This includes things such as selecting a higher straight as the winner if both players have their best hand as a straight. This requires the addition of many helper variables to choose between the same hand rank for our players. Additionally, in this iteration, we added a graphic intro screen, some more functionality in our main game loop (all in, gave the ability to choose hand number), and also added more bug fixes and code cleanup to elevate the quality of our project.

##### What user stories do you intend to complete next iteration? #####

There is no next iteration for this class, but I would like to work more on making the main game class structure better. I noticed that with the way it is currently coded, my game loop for players acting is very reliant on created counters and variables that keep the machine going. I think this has proven to be really unoptimal, as it makes testing really difficult, and doesn't allow me to partition all of the aspects of the game loop into different functions. My goal for the main game loop is to be able to make players perform an input by calling a function (such as "check()" or "bet()). I have these types of functions, but they currently rely on inner game loop and its local variables to work effectively. 

##### Is there anything that you implemented but doesn't currently work? #####

All of the most obvious bug fixes we've had before are completed. There is a non-zero possibility that there are really specific hand test cases that throw errors (this would mainly be with chopped pots if I were to guess), but all of the tests I designed for testing better hands was working as expected. I will likely take a look at this and try to see if there are any logic problems with the way it is coded, but at this point in time I am fairly confident in the methods used to score between hands. But I plan on making something poker related in my spare time, so this would be good for me to look at. 

##### What commands are needed to compile and run your code from the command line (or better yet, provide a script that people can use to run your program!) #####

A script is included named "playpoker.sh" that will compile and run the poker game in Java. To run this script, locate the directory installed from Github and type "./playpoker.sh"
