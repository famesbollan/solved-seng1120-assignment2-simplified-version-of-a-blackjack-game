Download Link: https://assignmentchef.com/product/solved-seng1120-assignment2-simplified-version-of-a-blackjack-game
<br>
Your task in this assignment is to re-use some classes from Assignment 1 and implement a simplified version of a <strong>Blackjack</strong> game. Here are the basic steps in the implementation of Assignment 2:

<ol>

 <li>Implement a class Card, which will represent instances of playing cards. Card will have three private member</li>

</ol>

variables: string face, int value and bool faceUp. face will store the string, e.g. “10-H” (for 10 of hearts); value will store the value of the card in points, e.g. 10; and faceUp will indicate if the card is placed facing up or down (this is important for the Blackjack game itself. These variables will need getters and setters. Card will also need an overloaded cout &lt;&lt; operator that outputs the value of the string.

<ol start="5">

 <li>In addition, you will produce a <u>class template</u> for each of:

  <ul>

   <li>Node, which stores Cards and is used as a component in the construction of</li>

   <li>LinkedList</li>

  </ul></li>

 <li>Implement the <u>class template</u> Queue, which uses LinkedList.</li>

 <li>Implement the class DeckOfCards, which is a <u>common class</u> (i.e. not a template) that uses a Queue instance as member variable. The front of the queue will be the top of the deck. The back of the queue will be the bottom of the deck. DeckOfCards will store all cards of the game, initially. In the constructor of DeckOfCards, you need to use enqueue() to populate the underlying queue first. DeckOfCards will also have a function shuffle(), implemented as follows:

  <ul>

   <li>Separate the 52 cards in the deck into 4 groups of 12. The order does not matter, and you can use 4 instances of DecksOfCards for that.</li>

   <li>Then, choose one deck at random, pick the top card, and place it at the bottom of one of the other decks. Repeat 1000 times and merge the 4 decks back to form the main one.</li>

   <li>To use the C++ random number generator, please have a look at:</li>

   <li><a href="http://www.cplusplus.com/reference/cstdlib/rand/">http://www.cplusplus.com/reference/cstdlib/rand/</a></li>

  </ul></li>

 <li>Implement the class HandOfCards, which is also a common class, and uses a Queue as the underlying data structure. HandOfCards will have the following functionality:</li>

</ol>

<ul>

 <li>Constructor, which creates an empty HandOfCards.</li>

 <li>int count() counts the value of the hand stored in the list (but only the cards facing up). Each card 2-10 have their face value. J, Q and K are worth 10 points each. A is worth 11 points (<em>this is a simplification of the traditional Blackjack rules</em>).</li>

 <li>int countAll() counts the value of the hand stored in the list (all cards facing both up and down).</li>

 <li>string value() returns a string displaying the sequence of cards stored in HandOfCards. Face-down cards must be displayed with “?-?” symbol.</li>

 <li>void faceUp() makes all cards in the hand face-up.</li>

 <li>Overloaded output operator (i.e. ‘&lt;&lt;’) outputs the content of the HandOfCards in a form suitable for printing.</li>

 <li>void add(Card, boolean) takes a single Card and a boolean arguments and adds the card in HandOfCards, either facing-up (true) or down (false).</li>

</ul>




As usual, we provide the demo file, which will:




<ol>

 <li>Create a new instance of DeckOfCards storing a full deck of cards (to be implemented in the constructor). Then it will shuffle its contents.</li>

 <li>Create two instances of HandOfCards, named player and dealer.</li>

 <li>Loop through the player and the dealer, giving them one card each, facing up. Cards are taken from the top of the deck of cards, using the function draw().</li>

 <li>Gives a second card to the player, facing up, and a second card to the dealer, facing down.</li>

 <li>Display each hand’s content – for player and the dealer – one hand per line, followed by the number of points.</li>

 <li>Check if someone has won the game.</li>

 <li>Ask if the player wants to hit or stand. If “hit”, the player receives another card from the deck, faceup, and goes back to step (5). If the answer is stand, go to step (8).</li>

 <li>At this point, the player has “stood” in the last loop. Now it is the time to do the dealer’s play. If the count of the dealer’s hand is &lt;=16, give it a new card, face-up. The dealer must take cards until the hand is 17 or more.</li>

 <li>Make all cards in the dealer’s hand face-up and display the contents of both hands along with the count for each hand.</li>

 <li>Check who has the highest count among the two hands (but not over 21) and state the winner.</li>

</ol>







For more information about the Blackjack game itself, please have a look at:

<a href="https://en.wikipedia.org/wiki/Blackjack">https://en.wikipedia.org/wiki/Blackjack</a>




<strong>A typical output of the game is presented below: </strong>




&gt;&gt;./BlackjackDemo.exe

Player: 4-C 6-D (10 points)

Dealer: 8-C ?-? (8 points)




Player, do you want to Hit (1) or Stand (2)?

1




Player: 4-C 6-D 5-C (15 points)

Dealer: 8-C ?-? (8 points)




Player, do you want to Hit (1) or Stand (2)?

1




Player: 4-C 6-D 5-C 5-S (20 points)

Dealer: 8-C ?-? (8 points)




Player, do you want to Hit (1) or Stand (2)?

2




Player: 4-C 6-D 5-C 5-S (20 points) Now the dealer’s strategy Dealer: 8-C 2-H 4-D 5-H (19 points) is executed and the final    score is 19.

THE PLAYER WON!








