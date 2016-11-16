Var Week1 = {
D1: 
  What's the difference between git pull and git merge?
    git pull is a git fetch + git merge in one command. It updates your local repository with the github repository, including  commits from the github repository.
    git merge also updates the local repository to match the repository being merged into, but if you don't first run a git fetch from your github repository your local repository will not know if there are any additional changes/commits to be updated and therefore git merge will state that the working directory is up to date. 

  1 What will this code print?

    var outer = 'abc';
    var fn = function() {
        var inner = 'def';
        console.log(outer);
    };
    fn();
    console.log(inner);

    answer: 
    'abc'
    error
    referenceError inner is not defined.


  2 What will this code print?
    var name = 'Joe';
    var fn = function() {
        console.log(name);
        var name = 'Bhaumik';
        console.log(name);
    };
    fn();
    console.log(name);

    answer:
    'joe'-- got wrong-- real answer is undefined because of hoisting name within function scope!!
    'Bhaumik'
    'joe'

D2:
  How would you access the person's name in this object?
    var person = {
        friends: ['Emma', 'Martin', 'Mel'],
        details: {
            name: 'Joe',
            location: 'Leicester'
        }
    };

    answer:
    person.details.name

  Create an object which has a sayHello method which logs "Hello World".
  var obj = {
    sayHello: function(){
      console.log('Hello World');
    }
  }

D3:
  How would you call the get() and increment() methods on the counter?
  Can you implement a set() method which resets the value of i. For example, calling counter.set(5) resets i to 5.

   var counter = (function(){
               var i = 0;

               return {
                       get: function(){
                            return i;
                       },
                       increment: function() {
                            return ++i;
                       },
                       set: function(val){
                         i = val;
                         return i;
                       }
               };
       }());
  ***Answer:
  console.log(counter.get());
  console.log(counter.increment());
  console.log(counter.set(5));

D4:
  1. Create an example DOM ((Document Object Model is the browser's representation of the current state of the HTML content of a page) and highlight the element which this jQuery selector would find:
  $('#one.two div:nth-child(3) + input[type=range]');


  Answer:
  div:nth-chil(3) is all div elements that are the third child of their parents

   + selector means the element that is right next to another element. In this case the div that is next to the element input[type=range]

  input[type=range] - means all input elements with the attribute type=range

   #one.two means element with both an ID of #one and a class of two

   space between the selectors means descenents so in this case all div:nth-child(3) that are decendants of #one.two

  answer ****
  <!DOCTYPE html>
  <html>
  <head>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
  <script>
  $(document).ready(function(){
    $('#one.two div:nth-child(3) + input[type=range]').css("box-shadow", "1px 1px 1px red");
  });
  </script>

  </head>
  <body>

     <div id="one" class="two">
         <div>eer</div>
         <div>ewrnljnwenr</div>
         <div>mewlrlkmer</div>
        <input type="range"></input>
     </div>
     
  </body>
  </html>


  2. In what scenarios is event delegation useful?

  Answer:
  Event delegation allows us to attach a single event listener, to a parent element, that will fire for all descendants matching a selector, whether those descendants exist now or are added in the future.

  Therefore, this is useful for creating a list. If you put an event listener on li's in your list, if li's are added after the page loads, these li's will not have event lisenters on them. Therefore, we use event delegation and put the listener on the ul because the ul will always be loaded at the start of the page and any li's that are loaded before or after the page will always remain children of the ul so they will have the event listener attached.

  3. Describe the bubbling phase of a DOM event.

  Answer:
  Bubbling is for example if we have multiple selectors that are parent/children of each other. When an event fires on one of the children it then moves up its parent elements whic will also fire the event listener. To prevent the browser from bubbling up and not displaying the text of the item we clicked on, we use event.stopPropagation. This allows for only the inner element we clicked to trigger the event listener. It wont run again for the parent elements. 


  4. Write code which will use jQuery's event delegation to listen for clicks on any buttons which are children of a div.

  Answer:
  $('div').on('click', button)

  How would you use jQuery to change the background color of a div when you hover over it?
  Answer:

    $(document).ready(function(){
       $("div").hover(function(){
           $(this).css("background-color", "yellow");
           }, function(){
           $(this).css("background-color", "pink");
       });
    });

  ---------------------------------------------------------------------------------------------------------------------------------
var Week2 ={
D3:
  1. What advantages does AJAX provide compared to refreshing when you want new information?
  Answer***
  AJAX is asynchronis javascript and XML. It allows us to make one or more calls to the server after the page loads. This allows us to bring new information onto our page as the user interacts with the page, instead of reloading the page with all the content(even the content that didn't change). I believe this approach is faster because the entire page with data does not need to load at once. It is also easier/simpler for the user to follow.  

  2. What is the role of an API in a modern web app?
  Answer***
  An API is an Application Program Interface that uses a standard protocal and subroutines for building software and applications. API's make it easer for developers to use certain techniologies and information in building aplications. In a modern web app, API's allow the developer to use information and technology from other apps so that they don't have to create that content themselves. They can focus on using that content in a new way as well as perfecting their app usage while relying on other apps features without having to understand the technology behind how that app got that data.

  3. Write code which makes an AJAX request to log out the most recent Gist posted to GitHub.
  (cURL is a command-line tool for transferring data using arious protocols. It can be used to interact with the Redmine EST API. )

  I really don't understand this question. 

  //I am able to see my gists at this url:
  https://api.github.com/users/davellaj/gists

  //This is from the API documentation
  var gitHubUrl = 'https://api.github.com';

  //This I found in google searches but I do not know even how to test out this code!
  $auth.logout().then(function() {

   // send a request to your server to perform server-side logout
    $http.post('/logout').succcess(function() {
      console.log('Successfully logged out');    
    });;

  });


  var Week3 = {
Monday:
 Which feature of ES6 do you think you will find most useful?

	answer**

Tuesday: 
How would you run one promise after another one completes?

How would you run two promises at the same time, waiting for them both to complete?

How do you wrap an async function which takes a callback in a promise interface?






  }
