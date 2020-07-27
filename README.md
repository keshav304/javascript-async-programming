# javascript-async-programming-
Asynchronous programming makes it possible to express waiting for long-running actions without 
freezing the program during these actions. JavaScript environments typically implement this style of programming using callbacks,
functions that are called when the actions complete. An event loop schedules such callbacks to be called when appropriate, 
one after the other, so that their execution does not overlap.

Programming asynchronously is made easier by promises, objects that represent actions that might complete in the future, and async functions, 
which allow you to write an asynchronous program as if it were synchronous.

#Three ways to write asyn code in javascript
1. Asyn/await
2. Callbacks
3. Promises

**#1 What is AJAX?**

AJAX = Asynchronous JavaScript And XML.

AJAX is not a programming language.

AJAX just uses a combination of:

A browser built-in XMLHttpRequest object (to request data from a web server)
JavaScript and HTML DOM (to display or use the data)

AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. 
This means that it is possible to update parts of a web page, without reloading the whole page.


**#How AJAX works?**
1. An event occurs in a web page (the page is loaded, a button is clicked)
2. An XMLHttpRequest object is created by JavaScript
3. The XMLHttpRequest object sends a request to a web server
4. The server processes the request
5. The server sends a response back to the web page
6. The response is read by JavaScript
7. Proper action (like page update) is performed by JavaScript



**#2 Callback function**

A JavaScript Callback Function is a function that is passed as a parameter to another JavaScript function, 
and the callback function is run inside of the function it was passed into.
JavaScript Callback Functions can be used synchronously or asynchronously.



```
<script> 

// add() function is called with arguments a, b 
// and callback, callback will be executed just 
// after ending of add() function 
function add(a, b , callback){ 
document.write(`The sum of ${a} and ${b} is ${a+b}.` +"<br>"); 
callback(); 
} 
	
// disp() function is called just 
// after the ending of add() function 
function disp(){ 
document.write('This must be printed after addition'); 
} 
	
// Calling add() function 
add(5,6,disp);	 
	
</script> 
```


**#3 Promises in javascript**
Promises are used to handle asynchronous operations in JavaScript. They are easy to manage when dealing with
multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code.

Prior to promises events and callback functions were used but they had limited functionalities and created unmanageable code.
Multiple callback functions would create callback hell that leads to unmanageable code.
Events were not good at handling asynchronous operations.

Promises are the ideal choice for handling asynchronous operations in the simplest manner. 
They can handle multiple asynchronous operations easily and provide better error handling than callbacks and events.

**Benefits of Promises**

* Improves Code Readability
* Better handling of asynchronous operations
* Better flow of control definition in asynchronous logic
* Better Error Handling
* A Promise has four states:


fulfilled: Action related to the promise succeeded
1. rejected: Action related to the promise failed
2. pending: Promise is still pending i.e not fulfilled or rejected yet
3. settled: Promise has fulfilled or rejected
4. A promise can be created using Promise constructor.

Syntax

```
var promise = new Promise(function(resolve, reject){
     //do something
});
```
Parameters

* Promise constructor takes only one argument,a callback function.
* Callback function takes two arguments, resolve and reject
* Perform operations inside the callback function and if everything went well then call resolve.
* If desired operations do not go well then call reject.

```
function func1() {
    return new Promise(function (resolve, reject) {
        setTimeout(() => {
            const error = true;
            if (!error) {
                console.log('Function: Your promise has been resolved')
                resolve();
            }
            else {
                console.log('Function: Your promise has not been resolved')
                reject('Sorry not fulfilled');
            }
        }, 2000);
    })
}

func1().then(function(){
    console.log(" Thanks for resolving")
}).catch(function(error){
    console.log("the promise is rejected Reason: " + error)
})
```
