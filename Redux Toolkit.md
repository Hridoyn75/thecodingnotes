
# PN: Redux Toolkit

Easy handnote for Redux Toolkit



## Step 1: Installation

It's time to Installation

```bash
  npm install react-redux @reduxjs/toolkit
```

## Step 2: Creating a Redux Slice

In Redux Toolkit, a slice is a collection of reducer logic and actions for a specific part of your state. It includes a reducer function and action creators. 

```bash
  import { createSlice } from '@reduxjs/toolkit';


  const counterSlice = createSlice({
  name: 'counter',
  initialState: 0,
  reducers: {
    increment(state) {
      return state + 1;
        },
        decrement(state) {
        return state - 1;
        },
    },
    });
    
export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;
    

```

## Step 3: Configuring the Redux Store

Open the src/index.js file and import the necessary functions: 

```bash
import { Provider } from 'react-redux';
import { configureStore } from '@reduxjs/toolkit';
import counterReducer from './features/counterSlice';



const store = configureStore({
  reducer: {
    counter: counterReducer,
  },
});


ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);


```
    
## Step 4: Accessing State and Dispatching Actions

Now you can use the state and dispatch actions in your React components.
Import the necessary functions in your component file:

```bash
import { useSelector, useDispatch } from 'react-redux';
import { increment, decrement } from '../features/counterSlice';

const counter = useSelector((state) => state.counter);
const dispatch = useDispatch();



<button onClick={() => dispatch(increment())}>Increment</button>
<span>{counter}</span>
<button onClick={() => dispatch(decrement())}>Decrement</button>



```    


#### That's it! You've set up React Redux Toolkit and created a basic Redux slice. You can now build upon this foundation to manage more complex state in your React application.

#### Remember to import and use the appropriate functions and components wherever needed. React Redux Toolkit provides additional features like creating async actions and managing immutable updates, so be sure to explore the official documentation for more advanced usage and customization options.

# Happy coding!
