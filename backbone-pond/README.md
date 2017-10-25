## Backbone

Create a fish pond in Backbone:

* [ ] Inside of `fishModel.js`, create a `toggleDescription` function such that when a fish <tr> is clicked, the fish description will toggle on or off. DO NOT MODIFY any other files. 

### Available Resources for this Prompt
* Backbone Docs
* MDN

Understand the existing code:

    1. app.js:
        - has the `fishData`
        - creates a Backbone collection using the fishData and Fish as the model
        - creates a Backbone view passing in the Backbone collection
        - displays the view onto the page
    2. pondView.js:
        - for each of the model inside the collection, render a fishView inside a `table` element
    3. fishView.js:
        - Depending on a property called `displayInfo` on the corresponding model, display one template vs the other inside a `tr` tag
        - On click, call model's `toggleDescription` function
        - It listens for a "toggle:description" event on the model and re-render the view when it fires.
    4. fishModel.js:
        - a simple model with some properties

Define toggleDescription function:
    Currently there's no such function on the `fishModel`. We know that the `fishView` expect there to be such a function and will call it when the corresponding `fishView` is clicked. We know that this function should modify the `displayInfo` property on the model, and then also fire a "toggle:description" event in order to trigger a re-render.

    1. add `toggleDescription` to `fishModel` 
    2. fire a "toggle:description" event to trigger re-render of the corresponding view
