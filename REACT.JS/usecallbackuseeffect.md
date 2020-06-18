## Usecallback within UseEfffect

Usecallback is a hook that receive a function and dependencies, and return a memoized version of the function.
This means that the function will have the same identification through the rendereziations.
Is usefull to use in conjunption with useEffect to make asyncronous call, ass a api call.
Specialy for fetche the data before mounting the component.

```html
const fetchData = useCallback( () => { apiCall(params).then(response => {
setLocalState(response.data); }); }, [params]); useEffect(() => { fetchData();
}, [fetchData]);
```

This avoid to end in a render loop on the `useEffect` if we call there the `apiCall`,
because will change the state and re-render calling `useEffect` again.
And is also good to pass the `fetchData` as depency for `useEffect` and not declarate a function inside it.
