### React

Create a fish pond in React:

* [ ] Install this prompts dependencies by running `npm install` from the root of this directory
* [ ] Start the app by running `npm start` from the root of this directory
* [ ] Refactor the `FishTable` and `FishTableRow` components to dynamically render the passed in `fishData`

### Available Resources for this Prompt
* React Docs
* MDN

Understand the existing code:

    1. index.js:
        - has the `fishData`
        - render the root custom element `FishTable` with the prop (aka attribute) of 'fishes'
    2. FishTable:
        - a React component that returns a table with 3x `FishTableRow` (this is just a function. React component can be written as a simple function, and the return value is the markup)
    3. FishTableRow:
        - a React component that returns a given table row. It has an internal state of `showDescription` (React component can also be written as a class instead of a function. This way, a component can have its own state)
        - it already has the onClick callback written
        - it already has the logic to show or hide the description depending on `showDescription`

Render fishData dynamically:

    We know that `FishTable` is passed the `fishData` as a prop called fishes, but it doesn't currently do anything with it. We should have `FishTable` pass each fish into its corresponding `FishTableRow`

    1. Modify `FishTable` to pass the prop `fishes` (A React component written as a function is always passed an argument of props, an object containing all of the props it is passed https://reactjs.org/docs/components-and-props.html)
    2. Map the fishes, which is an array of objects, to an array of elements instead of hard-coding the `FishTableRow` 3 times. Each is passed the corresponding `fish` data
    3. Replace the hard-coded name/description/image with the passed in prop `fish` data (React component written as a class can access its props via `this.props`)
