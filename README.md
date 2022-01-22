# REDUX-BUCHELI-COURSE-STRATEGIES-PASSING-STORE-DATA-THROUGH-THE-TOP-LEVEL-REACT-COMPONENT

## REDUX-LESSONS-INSTRUCTOR-ANDRES-R.-BUCHELI

## Usage:

The file structure that you helped implement in the last exercise works nicely when we add in React components. Take a look at the src folder in your workspace and you will find
the following file structure (new files have a (+) next to their name):

```
src/
|-- index.js
|-- app/
    |-- App.js (+)
    |-- store.js
|-- components/
    |-- FavoriteButton.js (+)
    |-- Recipe.js (+)
|-- features/
    |-- allRecipes/
        |-- AllRecipes.js (+)
        |-- allRecipesSlice.js
    |-- favoriteRecipes/
        |-- FavoriteRecipes.js (+)
        |-- favoriteRecipesSlice.js
    |-- searchTerm/
        |-- SearchTerm.js (+)
        |-- searchTermSlice.js
 ```
 
 Aside from the generic components, each feature-related React component file is located in the same directory as the slice file that manages the data rendered by that component.
 For example, FavoriteRecipes.js and favoriteRecipesSlice.js are both in the src/features/favoriteRecipes/ directory.
 
 Open the src/app/App.js file where the top-level component, <App />, is stored. As in most React applications, this top-level component will render each feature-component and
 pass any data needed by those components as prop values. In Redux applications, the data passed to each feature-component includes:

* 1. The slice of the store‘s state to be rendered. For example, the state.searchTerm slice is passed to the <SearchTerm /> component.
* 2. The store.dispatch method to trigger state changes through user interactions within the component. For example, the <SearchTerm /> component will need to dispatch
setSearchTerm() actions.

This distribution of the store.dispatch method and the slices of state to all of the feature-components, via the <App /> component, begins in the index.js file. Open up the 
src/index.js file where you will see some standard React code for rendering the top-level <App /> component. You’ll notice that the store is missing and the <App /> component
isn’t receiving any props!
