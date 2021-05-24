# Hooks



## useCallback

Memoize the creation of a function inside a component. Because functions are objects (references), this will maintain any equality check when passing the returned function to child components. This is especially useful when passing callbacks to memoized components.

```jsx
// This is a variation of an example in the post linked below
function Search({ searchText }) {
   let handler = useCallback(e => {
    // will only create a new function when searchText changes
  }, [searchText]); 

  // If Search re-renders but searchText has not changed, the function won't change
  // and it won't break memoization
  return <SearchResults searchText={searchText} clickHandler={handler} />

}

function Results({ searchText, clickHandler }) {
  let results = useSearchResults(searchText);

  return <div>
    <h2>{title}</h2>
    <button onClick={clickHandler}>Click It</button>
  </div>
}

const SearchResults = React.memo(Results);
```

Read [this post](https://dmitripavlutin.com/dont-overuse-react-usecallback/).

