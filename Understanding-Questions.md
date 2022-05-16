# Understanding Questions:
1. What are the steps of execution from the pressing of the 1 button to the rendering of our updated value? List what part of the code excutes for each step.
* The user presses the 1 button.
* 
...
The CalcButton component with a value prop set to 1, which is responsible for rendering the div with the button, has an onClick method which is triggered.

 That onClick method invokes the function that the component has received through props. This function lives in App.js and the return of this function is the invocation of dispatch by passing in the invocation of the action creator function: addOne.

 An action object is returned from addOne, then dispatch calls our reducer function taking in the current state of our application and the action object. The ADD_ONE case inside of our reducer is then triggered, which modifies our state by making a shallow copy of it, and changing the 'total' key to be a value of the current 'total' key value + 1.

 Since our state changed, our app re-renders and our TotalDisplay component reads the new value of the 'total' key from our state object.

* TotalDisplay shows the total plus 1.
