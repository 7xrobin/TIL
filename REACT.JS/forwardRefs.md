ForwardRef it a react atribute to able to pass a Dom reference from a component for one of its children.

`html
const FancyButton = React.forwardRef((props, ref) => (
  <button ref={ref} className="FancyButton">
    {props.children}
  </button>
));
`


You can now get a ref directly to the DOM button:

`
const ref = React.createRef();
<FancyButton ref={ref}>Click me!</FancyButton>;
`
