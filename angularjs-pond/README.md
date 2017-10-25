### AngularJS

Create a fish pond in AngularJS:

* [ ] Install this prompts dependencies by running `npm install` from the root of this directory
* [ ] Start the app by running `npm start` from the root of this directory
* [ ] Refactor the `fishTable` and `fishTableRow` components to dynamically render the data in `fishData`
* [ ] Modify `fishTableRow` such that visibility of the description toggles when a fish is clicked. The description should start out not visible.

### Available Resources for this Prompt
* AngularJS Docs
* MDN

### Ray Notes

Understand the existing code:

    1. index.html:
        - There's an ng-app called "fish-pond" (this will be the root angular module)
        - There's a custom element called `app`, which must be a component defined somewhere
    2. main.js:
        - Contains the data in a variable called `fishData`
        - defines "fish-pond" angular module used in ng-app
        - defines the component `app` which passes `fishData` as a binding called `fishes` to `fish-table` component
    3. fishTable.js:
        - Defines a component called `fishTable` (remember the whole camel-case vs dash-case thing)
        - the component's template contains 3x `fish-table-row`
    4. fishTableRow.js:
        - defines a component called `fishTableRow` with a binding of `fish` (this was not passed in by `fishTable` component yet)
        - `fishTableRow` component template has a ng-click that calls `toggleDescription`, which is defined on its controller
        - the other info about the fish is hard-coded
        - there is an ng-if that will conditionally display the description based on a controller variable called `showDescription`

Dynamicaly render fishData:
    We know that fishData is already passed to `fishTable` component, but it's not used in any way. We also know that instead of coding 3x `fish-table-row` in the template, we can use ng-repeat to dynamically pass the corresponding fishData at that index.

    1. modify fishTable.js to use ng-repeat for `fish-table-row`
    2. modify fishTable.js to pass in a binding called `fish` to the `fish-table-row` (`fishTableRow` component already has this `fish` binding defined, so we just need to pass it this property when creating this component)
    3. modify fishTableRow.js to not hard-code the fish info, and use the passed in `fish` data

Toggle description when a row is clicked:
    This is actually already done. The ng-click has the `toggleDescription` handler, which toggles the controller property called `showDescription` already



