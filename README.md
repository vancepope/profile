## Hi guys! :wave:

My name is Vance, I have worked in the industry as a Software Testing Engineer at ASML, and as a Web Developer for Berkshire Hathaway HomeServices California Properties. When I'm not coding, I am usually playing video games (currently Diablo 4).

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=vancepope&theme=react&show_icons=true&hide=css,html)

## :pushpin: My Projects

1. <a href="https://github.com/vancepope/blackjack" target="_blank">Black Jack</a>
    - Please click the link to see operational photos of the application
        - Code snippets have been provided below in the Details section
    - Black Jack console application built in Python
    - Utilizes Object Oriented Programming (OOP) methodologies
    - Uses Flask for testing class methods
    - Logs to a log file using the python logging module
    <br />
    <details>
    <summary>Details</summary>
    <br />
    
    ##### **TL;DR**: _Application uses classes to initialize several aspects of the game to present to the user. Upon the result of the game, the user is asked to play again if they choose. Test methods were written to provide coverage to limit defects._

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
                        - Used to display the cards to user for the player and dealer
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
                        - Deals the deck to the player and returns a Card
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
                    ![Code for Test Deck class](/images/testdeck.png "Code for Test Deck class")
            - TestHand
                - Test Methods
                    - test_add_card
                        - Mocks the addCard method and ensure a list is returned with the length of 1, that it is of type Card, and is printed as 'Ace of Diamonds'
                    ![Code for Test Hand class](/images/testhand.png "Code for Test Hand class")

            - TestBlackJack
                - Test Methods
                    - test_hit_stay
                        - Mocks the hitStay method and ensures that it return a string of 'hit'
                    - test_is_playing
                        - Instantiates the BlackJack class, calls the setter for isPlaying and asserts that they match.
                    ![Code for Test Black Jack class](/images/testblackjack.png "Code for Test Card class")
    </details>
        


2. <a href="https://github.com/vancepope/hello_flask" target="_blank">APIs w/ Flask</a>
    - Please click the link to see operational photos of the application
        - Code snippets have been provided below in the Details section
    - FlaskAPI application that utilizes ElephantSQL 
    - Builds an API for rooms, room temperatures, and a tic-tac-toe game
    <br />
    <details>
    <summary>Details</summary>
    <br />

    ##### **TL;DR**: _Application creates rooms and temperatures utilizing ElephantSQL queries. Test methods were written utilizing a test database to mock data and limit defects._

    - Routes
        - '/'
            - Returns a string of 'Hello Monty'
        - '/api/room'
            - Grabs the name variable from a JSON object
                - Creates room table if it doesn't exist
                    <img src="/images/createroom.png" alt="Query for room route">
                - Inserts room to the rooms table
                    - Returns room id
                    <img src="/images/roomreturnid.png" alt="Query for room route">
                - Returns JSON object notifying the user that the room has been created and an HTTP response code of 201
            <img src="/images/room.png" alt="Code for room route">

        - '/api/temperature'
            - Grabs the temperature and room id, and datetime from a JSON object
                - If datetime isn't provided in the object, the datetime.now method will be called
            - Creates temperature table if it doesn't exist
                <img src="/images/createtemp.png" alt="Query for temp route">
            - Inserts room id, temperature, and date
                <img src="/images/inserttemp.png" alt="Query for temp route">
            - Returns message notifying the user that the temperature was added and a response code of 201
            <img src="/images/temperature.png" alt="Query for temperature route">

        - '/api/room/<int:room_id>'
            - Grabs the id variable from the http path
            - Selects the room by id
                <img src="/images/selectroom.png" alt="Query for room by id route">
            - Returns the room and response code of 200
            <img src="/images/roombyid.png" alt="Code for room by id route">
        
        - '/api/avg_temp'
            - Queries the database for the average temperature
                <img src="/images/avgtempquery.png" alt="Query for avg temp route">
            - Returns JSON object containing average temperature and response code of 200
            <img src="/images/avgtemp.png" alt="Code for avg temp route">

        - '/api/day_count'
            - Queries the database for the number of days
                <img src="/images/numdays.png" alt="Query for number of days route">
            - Returns JSON object containing the number of days and response code of 200
        
        - '/api/tictactoe'
            - Displays a tic-tac-toe game built using HTML, CSS Grid, and JavaScript
            - Calls the render_template method from Flask to render grid.html
    </details>

3. <a href="https://github.com/vancepope/zoo_flask" target="_blank">Zoo Flask</a>
    - Please click the link to see operational photos of the application and test plan
        - Code snippets have been provided below in the Details section
    - Logs HTTP response and application info to a log file using the python logging module
    - Utilizes Test Driven Development (TDD) to build an API for creating enclosures for different animals
    <br />
    <details>
    <summary>Details</summary>
    <br />

    ##### **TL;DR**: _Application builds an animal and enclosure API utilizing ElephantSQL queries. Tests have been written to test functionality and prevent defects._

    - Methods
        - create_enclsures
            - Receives group_name from JSON object
            - Creates Enclosure table if it doesn't exist
                <img src="/images/querycreateenclosures.png" alt="Create Enclosure Table">
            - Inserts group_name into the Enclosures table if a group_name doesn't exist
                <img src="/images/insertenclosure.png" alt="Add Enclosure">
            - Returns JSON object notifying the user that the enclosure was created
            <img src="/images/codecreateenclosure.png" alt="Create Enclosure Code">

        - create_animals
            - Receives name, quantity, enclosure_id from JSON object
            - Creates Animals table if it doesn't exist
                <img src="/images/querycreateanimals.png" alt="Create Animals Table">
            - Inserts name, quantity, enclosure_id into the Animals table if a name doesn't exist
                <img src="/images/queryinsertanimal.png" alt="Add Animal">
            - Returns JSON object notifying the user that the enclosure was created
            <img src="/images/codecreateanimals.png" alt="Create Animals Code">

        - get_animal
            - Receives id from HTTP path
            - Selects the correct animal by id
                <img src="/images/queryselectanimalbyid.png" alt="Get Animal">
            - Returns JSON object to the client side
            <img src="/images/codegetanimal.png" alt="Get Animal Code">   

        - get_enclosure
            - Receives enclosure_id from HTTP path
            - Selects the correct enclosure by enclosure_id
                <img src="/images/queryselectenclosuresbyid.png" alt="Get Enclosure">
            - Returns JSON object to the client side
            <img src="/images/codegetenclosure.png" alt="Create Animals Code">

        - get_animals
            - Selects all animals within the Animals table
                <img src="/images/queryselectanimals.png" alt="Get All Animals">
            - Appends the result to a data list of JSON objects
            - Returns the data list to the client side
            <img src="/images/codegetanimals.png" alt="Get Animals Code">

        - get_enclosures
            - Selects all enclosure within the Enclosures table
                <img src="/images/queryselectenclosures.png" alt="Get All Enclosures">
            - Appends the result to a data list of JSON objects
            - Returns the data list to the client side
            <img src="/images/codegetanimals.png" alt="Get Animals Code">

        - add_enclosure
            - Receives group_name from HTTP Body
            - Insert name into Enclosures if it doesn't exist
                <img src="/images/insertenclosure.png" alt="Add Enclosure">
            - Returns a JSON object notifying the user that the enclosure has been created
            <img src="/images/codeaddenclosure.png" alt="Add Enclosure Code">

        - add_animal
            - Receives name from HTTP Body
            - Insert name into Animals if it doesn't exist
                <img src="/images/queryinsertanimal.png" alt="Add Animal">
            - Returns a JSON object notifying the user that the enclosure has been created
            <img src="/images/codeaddanimal.png" alt="Add Animal Code">

        - display animals
            - Executes an inner join on enclosures and animals
                <img src="/images/querydisplayanimals.png" alt="Display Animal">
            - Appends the result to a data list of JSON objects
            - Returns data list to the client side
            <img src="/images/codedisplayanimals.png" alt="Display Animals Code">

    - Test Methods
        - test_connection
            - Uses fixture called connection to create Enclosures table if it doesn't exist
            - Inserts enclosure based on the sample date provided within the fixture if it doesn't exist
            - Prints and logs the expected output and actual output
            - Asserts that the length of the result > 0
            <img src="/images/testconnection.png" alt="Test Connection">

        - test_create_animals
            - Uses fixture called create_animals to create Animals table if it doesn't exist
            - Prints and logs the expected output and actual output
            - Asserts that the length of the result > 0
            <img src="/images/testcreateanimals.png" alt="Test Create Animals">

        - test_create_enclosures
            - Uses fixture called create_enclosures to create Enclosures table if it doesn't exist
            - Prints and logs the expected output and actual output
            - Asserts that the length of the result > 0
            <img src="/images/testcreateenclosures.png" alt="Test Create Enclosures">

        - test_add_enclosure
            - Uses fixture called add_enclosure to insert an enclosure based on the data provided if the enclosure doesn't already exist
            - Selects enclosures from the enclosure tables
            - Prints and logs the expected output and actual output
            - Asserts that the length of the result < 1
            <img src="/images/testaddenclosure.png" alt="Test Add Enclosure">

        - test_add_animal
            - Uses fixture called add_animal to insert an animal based on the data provided if the animal doesn't already exist
            - Selects enclosures from the animals tables
            - Prints and logs the expected output and actual output
            - Asserts that the length of the result < 1
            <img src="/images/testaddanimal.png" alt="Test Add Animal">

        - test_display_animals
            - Executes an inner join on the Enclosure and Animals tables
            - Appends the results to a data list of JSON objects
            - Asserts that the data > 0 and the type is list
            - Prints and logs the expected output and actual output
            <img src="/images/testdisplayanimals.png" alt="Test Display Animals">
    </details>

4. <a href="https://github.com/vancepope/mongo_flask" target="_blank">Mongo Flask</a>
    - Please click the link to see operational photos of the application
        - Code snippets have been provided below in the Details section
    - Machinery Parts application built using Flask
    - Utilizes MongoDB to create a parts store database
    - Pytest methods accompanied by mocked methods to simulate MongoDB CRUD operations
    <br />
    <details>
    <summary>Details</summary>
    <br />

    ##### **TL;DR**: _Application builds a machinery parts API utilizing MongoDB to perform CRUD operations. Tests with mocked MongoDB methods have been written to review outcomes and maintain overall quality of life._

    - Methods
        - index
            - Executes query to find all collections
            - Appends the result to a list
            - Returns a JSON object if the list contains items
            - If not, it returns a JSON object notifying the user that the query was not successful
            <img src="/images/app-index.png" alt="App Index">

        - get_part
            - Executes query to find collection by part_id
            - Returns a JSON object containing the collection
            - If not, notifies the user that the search was unsuccessful
            <img src="/images/app-get-part.png" alt="App Get Part">

        - create_part
            - Inserts a JSON object into the database
            - Returns JSON containing the ObjectId generated by MongoDB
            <img src="/images/app-create-part.png" alt="App Create Part">

        - update_part
            - Updates the database using the part_id from the response
            - Returns a Success status if the matched_count > 0
            - If not, returns a Item not found error code
            <img src="/images/app-update-part.png" alt="App Update Part">

        - delete_part
            - Deletes an entry from the database using the ObjectId provided from the response
            - Returns a Success status code if the deleted_count > 0
            - If not, returns an Item not found error code
            <img src="/images/app-delete-part.png" alt="App Delete Part">

    - Mocked MongoDB methods
        - find
            - Simulates a successful response from pymongo.collection.Collection.find method
            - Sets return_value to a list of BSON objects 
            - Sets returncode to 200
            <img src="/images/mock-find.png" alt="Mock Find">

         - find_fail
            - Simulates an unsuccessful response from pymongo.collection.Collection.find method
            - Sets return_value to a list contaioning a JSON object with a Item not found error
            - Sets returncode to 404
            <img src="/images/mock-find-fail.png" alt="Mock Find Fail">
        
        - find_one
            - Simulates a successful response from pymongo.collection.Collection.find_one method
            - Sets return_value to a list of BSON objects 
            - Sets returncode to 200
            <img src="/images/mock-find-one.png" alt="Mock Find One">

        - find_one_fail
            - Simulates an unsuccessful response from pymongo.collection.Collection.find_one method
            - Sets return_value to a list contaioning a JSON object with a Item not found error
            - Sets returncode to 404
            <img src="/images/mock-find-one-fail.png" alt="Mock Find One Fail">

        - insert_one
            - Simulates a successful response from pymongo.collection.Collection.insert_one method
            - Sets return_value to a list of an BSON object containing the ObjectId of the collection inserted
            - Sets returncode to 200
            <img src="/images/mock-insert-one.png" alt="Mock Insert One">

        - update_one
            - Simulates a successful response from pymongo.collection.Collection.update_one method
            - Sets return_value to a list contaioning a JSON object with a Success status
            - Sets returncode to 200
            <img src="/images/mock-update-one.png" alt="Mock Update One">

        - update_one_fail
            - Simulates an unsuccessful response from pymongo.collection.Collection.update_one method
            - Sets return_value to a list contaioning a JSON object with a Item not found error
            - Sets returncode to 404
            <img src="/images/mock-update-one.png" alt="Mock Update One">

        - delete_one
            - Simulates a successful response from pymongo.collection.Collection.delete_one method
            - Sets return_value to a list contaioning a JSON object with a Success status
            - Sets returncode to 200
            <img src="/images/mock-delete-one.png" alt="Mock Delete One">

        - delete_one_fail
            - Simulates a successful response from pymongo.collection.Collection.delete_one method
            - Sets return_value to a list contaioning a JSON object with a Item not found error
            - Sets returncode to 404
            <img src="/images/mock-delete-one.png" alt="Mock Delete One">

    - Test Methods
        - test_index
            - Asserts that the response from the mocked find method that the return_value has a length > 0
            - Asserts that a returncode of 200 was received
            <img src="/images/test-index.png" alt="Test Index">

        - test_index_fail
            - Asserts that the response from the mocked find method that the return_value has an Item not found error
            - Asserts that a returncode of 404 was received
            - Prints Expected and Actual output
            <img src="/images/test-index-fail.png" alt="Test Index Fail">

        - test_get_part
            - Asserts that the response from the mocked find_one method that the return_value has a length > 0
            - Asserts that a returncode of 200 was received
            - Prints Expected and Actual output
            <img src="/images/test-get-part.png" alt="Test Find One">

        - test_get_part_fail
            - Asserts that the response from the mocked find_one method that the return_value has an Item not found error
            - Asserts that a returncode of 404 was received
            - Prints Expected and Actual output
            <img src="/images/test-get-part-fail.png" alt="Test Find One Fail">

        - test_update_one
            - Asserts that the response from the mocked update_one method that the return_value has a Success status
            - Asserts that a returncode of 200 was received
            <img src="/images/test-update-part.png" alt="Test Update One">

        - test_update_one_fail
            - Asserts that the response from the mocked update_one method that the return_value has an Item not found error
            - Asserts that a returncode of 404 was received
            - Prints Expected and Actual output
            <img src="/images/test-update-part-fail.png" alt="Test Update One Fail">

        - test_delete_one
            - Asserts that the response from the mocked delete_one method that the return_value has a Success status
            - Asserts that a returncode of 200 was received
            <img src="/images/test-delete-part.png" alt="Test Delete One">

        - test_index_fail
            - Asserts that the response from the mocked delete_one method that the return_value has an Item not found error
            - Asserts that a returncode of 404 was received
            - Prints Expected and Actual output
            <img src="/images/test-delete-part-fail.png" alt="Test Delete One Fail">
    </details>
