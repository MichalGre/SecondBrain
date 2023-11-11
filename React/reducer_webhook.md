
Extremly simple example of reducer webhook usage.

```javascript

const emailReducer = (state, action) => {
  if (action.type === "KEY_PRESSED") {
    return { val: action.val, isValid: action.val.includes("@") };
  }
  return { val: "", isValid: false }; // returning the new state
};

const Comp = (props) => { 
    const [emailState, dispatchEmail] = useReducer(emailReducer, {
        isValid: false,
        val: "",
    });
};
```
Dispatching the state change:

```javascript

dispatchEmail({ type: "KEY_PRESSED", val: event.target.value });

```