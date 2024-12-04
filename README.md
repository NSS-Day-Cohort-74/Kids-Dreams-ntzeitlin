# Events and Debugging Assessment

Time to assess how well you have learned to use the debugging tools in Chrome Dev Tools, and writing click event listeners. This application is to show kids with illnesses and the memories the would like to make. Celebrities sign up to help kids make memories.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Event Listeners to Create

1. When the kid name is clicked, it should display their wish.
1. When the celebrity name is clicked, it should display their sport.
1. The pairings list should should contain the pairing in the following format.
    ```html
    {child name} will be making memories with {celebrity name}, a {celebrity sport} star, by {child wish}
    ```

Below is an animation showing how the application should look when complete and how the event listeners should work.

<img src="./images/debugging-events-assessment.gif" width="700px">

## Setup

Your instruction team will provide a link for you to create your assessment repository. Once your repo is created, clone it to your machine.

1. Make sure you are in your `workspace` directory.
1. `git clone {github repo SSH string}`.
1. `cd` into the directory it creates.
1. `code .` to open the project code.
1. Use the `serve` command to start the web server.
1. Open the URL provided in Chrome.

Make sure your Developer Tools are open at all times while working on this project. Use the messages provided in the Console to determine what code needs to be fixed or implemented, and use breakpoints in the Sources tab to step through your code as you debug.

## Vocabulary and Understanding

Before you click the "Complete Assessment" button on the Learning Platform, add your answers below each question and make a commit.

1. When a child is clicked on in the browser, which module contains the code that will execute on that event happening? Can you explain the algorithm of that logic?
   > When a child is clicked on, the Kids.js module executes the code within its EventListener. First an event listener is added to the DOM. Then, the EventListener sends the DOM's click event as an argument to a callback function within the EventListener. The EventListener gets the target of the click event and checks whether the target html element's dataset's type parameter is equal to "child". If they are equal, a window alert is thrown using string interpolation to accurately display the clicked child's wish. 

2. In the **Pairings** module, why must the `findCelebrityMatch()` function be invoked inside the `for..of` loop that iterates the kids array?
   > The findCelebrityMatch() function returns the celebrity object that matches the foreign celebrity ID contained by the current kid object. In order to find the correct celebrity the function takes two arguments, the current kid object and the celebrity database array, iterating through the celebrity database array compairing each celebrity object's primary ID with the current kid object's foreign celebrity ID. When/If there is a match, it returns the correct celebrityObject. The kids array for...of... loop then continues to iterate through the full list of kids, returning a matched celebrity for each kid and then generates the appropriate html string for each kid-celebrity pair. If it was not inside a forof loop, only one kid-celebrity pair html element would be generated.

3. In the **CelebrityList** module, can you describe how the name of the sport that the celebrity plays can be displayed in the window alert text?
   > The window alert text is generated using a string literal within an EventListener method's callback function. The EventListener's callback function takes a clickEvent as an argument. The clickEvent contains a target property which contains a specific html element. That html element contains a dataset property containing State values stored in the element tag. Dataset includes any html element tags that start with 'data-'. In this instance, the name of the sport played by the celebrity is stored in a 'data-sport' tag. The eventlistener's callback function interpolates the value of the tag, adding it to the string. 

4. Can you describe, in detail, the algorithm that is in the `main` module?
   > In this application, the main.js module orchestrates the display of information on the site's index.html. First, it imports the necessary functions from various modules. Then, it targets the html tag with the container ID and stores it in a mainContainer variable. Then, using string interpolation, the HTML is generated and stored in the applicationHTML variable. During html generation, function calls are made to dynamically generate information, and associated click eventlisteners, to be displayed on the homepage. The applicationHTML variable is then sent to the DOM by accessing the mainContainer's innerHTML property. 
