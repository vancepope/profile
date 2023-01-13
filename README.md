## Hi guys! :wave:

My name is Vance, I am now a Software Testing Engineer at _nology. I have worked in the industry as a Web Developer for Berkshire Hathaway HomeServices California Properties. When I'm not coding, I am usually playing video games (currently Pokémon Violet).

<details>
<summary> :computer: Check out what I've been coding on</summary>
<br />

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=vancepope&theme=react&show_icons=true&hide=css,html)

## :pushpin: My Projects

1. <a href="https://github.com/vancepope/blackjack" target="_blank">Black Jack</a>
    - Please click the link to see operational photos of the application
        - Code snippets have been provided below for each section
    - Black Jack console application built in Python
    - Utilizes Object Oriented Programming (OOP) methodologies
    - Uses Flask for testing class methods
    - Logs to a log file using the python logging module
        - Classes
            - Card
            - Deck
            - Hand
            - BlackJack
            - TestCard
            - TestDeck
            - TestHand
            - TestBlackJack
        - Methods
            - Card
                - Methods
                    - __repr__
                        - Used to display the cards to user for the player and deaker
                    - __str__
                        - Displays the cards in a string format
                    <img src="/images/card.png" height="400" alt="Code for Card class">

            - Deck
                - Inherits cards, suits and values lists from Card
                - Methods
                    - Getters and Setters
                        - getCards
                        - getSuits
                        - getValues
                        - getDeck
                        - setDeck
                    - creatDeck
                        - Creates the deck
                    - shuffle
                        - Uses the random class to shuffle the deck.
                    - deal
                        - deals the deck to the player and returns a Card
                    <img src="/images/deck.png" height="%50" width="%50" alt="Code for Deck class">

            - Hand
                - Inherits the deck list and the values list from Deck
                - Methods
                    - addCard
                        - Adds a Card to the hand list
                    - ace
                        - Keeps track of aces and assigns an ace the value of 1 or 11 if there is an ace and the value is greater than 21
                    <img src="/images/hand.png" height="%50" width="%50" alt="Code for Hand class">

            - BlackJack
               - This is the main class
               - Getters and Setters
                    - getName 
                    - getIsPlaying
                    - setName
                    - setIsPlaying
                - Methods
                    - hit
                        - Adds a card to the hand list and adjusts the value of an ace accordlingly if the player decides to 'hit'
                    - hitStay
                        - Prompts the user to ask if the user would like hit and to add a card to his hand or would like to stay.
                        - Checks for only the words 'hit' or 'stay'
                            - If the response from the user is different from the check, the user is prompted again to provide the necessary response.
                    - showCards
                        - Displays the dealer's and player's hands along with their values in formatted print statements
                    - play
                        - Prompts the user to enter his/her name
                        - Utilizes a while loop to play multiple games
                        - Checks if the player's hand value ≤ 17 and starts a while loop to allow the player to raise said value if they choose.
                        - Checks the values of the dealer's hand 
                            - If the value is ≤ 21, a while loop will start until the value ≥ 17
                        - Uses condition statements to decide who the winner is of each game
                        - Prompts the user if they would like to play another game.
                    <img src="/images/blackjack1.png" height="907" alt="Code for Black Jack class">
                    <img src="/images/blackjack2.png" height="758" alt="Code for Black Jack class Part 2">

            - TestCard
                - Test Methods
                    - test___repr__
                        - Uses the Mock functionality to mock the __repr__ method and make sure that the values of '10' and 'Diamonds' are represented like '10 of Diamonds'
                - Code
                    ![Code for Test Card class](/images/testcard.png "Code for Test Card class")

            - TestDeck
                - Fixtures
                    - create_deck
                        - Appends the card and suit list to the deck list of Cards and returns it.
                - Test Methods
                    - test_create_deck
                        - Mocks the create_deck method and ensures the results are the same
                    - test_deal 
                        - Mocks the deal method and ensures the new card is of type Card and that the string is printed as 'Ace of Diamonds'
                - Code
                    ![Code for Test Deck class](/images/testdeck.png "Code for Test Deck class")
            - TestHand
                - Test Methods
                    - test_add_card
                        - Mocks the addCard method and ensure a list is returned with the length of 1, that it is of type Card, and is printed as 'Ace of Diamonds'
                - Code
                    ![Code for Test Hand class](/images/testhand.png "Code for Test Hand class")

            - TestBlackJack
                - Test Methods
                    - test_hit_stay
                        - Mocks the hitStay method and ensures that it return a string of 'hit'
                    - test_is_playing
                        - Instantiates the BlackJack class, calls the setter for isPlaying and asserts that they match.
                - Code
                    ![Code for Test Black Jack class](/images/testblackjack.png "Code for Test Card class")


2. <a href="https://github.com/vancepope/hello_flask" target="_blank">APIs w/ Flask</a>
    - FlaskAPI application that utilizes ElephantSQL 
</details>