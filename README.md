# Grading, Sample Exam and Questions-Bank

- [Grading](./grading.md)
- [Maximum points per week](./max-points-per-week.pdf)
- Sample Exam Questions: [Frontend](./Exam-part1.md)
- Sample Exam Questions: [Backend](./Exam-part2.md)

-----
## Questions-Bank
- [Backend - part 1](#backend---part-1)
- [Backend - part 2](#backend---part-2)
- [Backend - part 3](#backend---part-3)
- [Frontend - part 1](#frontend---part-1)
- [Frontend - part 2](#frontend---part-2)
- [Frontend - part 3](#frontend---part-3)

> Note:

- There are 3 levels of questions in the exam, here are some examples of levels 1 and 2.
- In some questions, you may be asked to identify issues with the code, even though the code works fine.
- Some questions have been removed


### Backend - Part 1:
----

**JavaScript Engines**

1. Explain the role of a JavaScript engine in the context of a Node.js application.
2. What is V8, and why is it important for Node.js?
3. Describe the event loop and how it functions in Node.js.

**Express.js Middleware**

4. What is middleware in Express.js, and why is it useful?
5. How do you use middleware to handle authentication in an Express.js application?
6. Provide an example of custom middleware and explain its purpose.

**Express.js Routers**

7. What is an Express.js router, and why would you use one?
8. How can you nest routers in Express.js, and what advantages does it offer?
9. Explain the difference between app-level and router-level middleware.

**Express.js Controllers**

10. What is the role of a controller in an Express.js application?
11. How do controllers help in maintaining separation of concerns in the MVC pattern?
12. Provide an example of a controller function in an Express.js application.

**Databases**

13. Compare and contrast MongoDB and SQL databases in terms of data structure.
15. Explain the purpose of Mongoose and Sequelize in Node.js applications.
16. What are the key differences between Mongoose and Sequelize?


**Authentication**

19. Describe the difference between authentication and authorization.
20. How does token-based authentication work, and why is it commonly used in web applications?
21. What is the purpose of a JWT (JSON Web Token) in authentication?

**Authorization and Roles**

23. How can you restrict access to specific routes or resources based on user roles?
24. Provide an example of creating and assigning roles in an Express.js application.

**Import vs. Require**

25. Compare ES6 `import` and CommonJS `require` statements for module importing in Node.js.
26. What are the benefits of using ES6 `import` over `require` in modern Node.js projects?
27. Explain the role of the `export` keyword when using ES6 modules.

**async/await vs. .then()**

28. Describe the advantages of using `async/await` over promise chaining with `.then()` for handling asynchronous operations.
29. Provide an example of how you can rewrite promise-based code using `async/await`.


**.env**

31. What is the purpose of a `.env` file in Node.js applications?
32. How can you securely store sensitive information, such as API keys, in a `.env` file?
33. Explain how you can access environment variables stored in a `.env` file within your Node.js code.

**MVC Pattern**

34. Define the MVC (Model-View-Controller) architectural pattern.
35. What are the responsibilities of the Model, View, and Controller components in MVC?
36. How does the MVC pattern help in structuring and organizing an Express.js application?

**RESTful API Design**

40. What are the key principles of RESTful API design?
41. Explain the purpose of HTTP status codes in a RESTful API.
42. How can you implement versioning in your API endpoints to ensure backward compatibility?

**Testing Express.js Applications**

43. Why is testing important in the development of Express.js applications?
44. Describe the differences between unit testing, integration testing, and end-to-end testing.
45. What testing tools and libraries are commonly used for testing Express.js applications?

**Cross-Origin Resource Sharing (CORS)**

49. What is CORS, and why is it necessary for web security?
50. How can you configure CORS in an Express.js application to allow or restrict cross-origin requests?

### Backend - Part 2:
----

**1. Middleware Function Explanation**

```javascript
const middleware = (req, res, next) => {
  // Explain what this middleware function does.
  // Include details about the parameters and their roles.
  next();
};
```

**2. Route Handling in Express**

```javascript
app.get('/api/users', (req, res) => {
  // Explain how this route handles incoming GET requests.
  // Include any response data or status codes that might be set.
});
```

**3. Async/Await Usage**

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    // Explain the purpose of using async/await in this function.
  } catch (error) {
    // Explain how errors are handled in this async function.
  }
}
```

**4. JWT Token Signing**

```javascript
const jwt = require('jsonwebtoken');
const token = jwt.sign({ userId: 123 }, 'secretKey');
// Explain how this code generates and signs a JWT token.
```

**5. Database Query with Mongoose**

```javascript
const user = await User.findOne({ username: 'john_doe' });
// Explain how this Mongoose query finds a user by their username.
```

**6. Error Handling Middleware**

```javascript
app.use((err, req, res, next) => {
  // Explain the purpose of this error handling middleware.
  // Include details about the parameters and their roles.
});
```

**7. Router Configuration in Express**

```javascript
const router = express.Router();

router.get('/products', (req, res) => {
  // Explain how this router handles GET requests to the /products route.
});
```

**9. Environment Variable Usage**

```javascript
const apiKey = process.env.API_KEY;
// Explain why it's important to use environment variables for sensitive information.
```

**10. Role-Based Authorization Middleware**

```javascript
const checkAdminRole = (req, res, next) => {
  if (req.user && req.user.role === 'admin') {
    next();
  } else {
    res.status(403).send('Access denied');
  }
};
// Explain how this middleware restricts access to admin-only routes.
```

**11. Express Route Parameters**

```javascript
app.get('/api/users/:id', (req, res) => {
  const userId = req.params.id;
  // Explain how route parameters are accessed and used in this route.
});
```


**15. CORS Configuration in Express**

```javascript
const corsOptions = {
  origin: 'https://client.example.com',
  methods: 'GET,HEAD,PUT,PATCH,POST,DELETE',
};
app.use(cors(corsOptions));
// Explain how CORS is configured to allow requests from a specific origin.
```



**17. Express.js Form Handling**

```javascript
app.post('/api/users', (req, res) => {
  const { username, email } = req.body;
  // Explain how this route handles POST requests with form data.
});
```


**19. Router Middleware in Express**

```javascript
router.use((req, res, next) => {
  // Explain the purpose of this middleware when used with Express.js routers.
  next();
});
```

**20. Custom Error Handling Function**

```javascript
function errorHandler(err, req, res, next) {
  // Explain how this custom error handling function is used in Express.js.
}
// Use of the errorHandler middleware in the Express.js app.
app.use(errorHandler);
```


### Backend - Part 3:
----


**1. Error in Middleware Function**

```javascript
app.use((req, res) => {
  // Find and explain the mistake in this middleware function.
  next();
});
```

**2. Routing Issue**

```javascript
app.get('/api/products/', (req, res) => {
  // Find and explain the routing issue in this code.
});
```

**6. Missing Import Statement**

```javascript
const app = express();

app.get('/', (req, res) => {
  // Find and explain the missing import statement issue.
});
```

**7. Incorrect Variable Assignment**

```javascript
const number = 42;
number = 50;
// Find and explain the incorrect variable assignment.
```

**10. Misplaced Parentheses**

```javascript
if (x > 5 {
  // Find and correct the misplaced parentheses.
  console.log('x is greater than 5');
}
```

**11. Invalid JSON Syntax**

```json
const data = { name: 'John', age: 30, };
// Find and correct the invalid JSON syntax.
```

**12. Undefined Variable**

```javascript
function printMessage() {
  console.log(msg);
}

printMessage();
// Find and explain the usage of an undefined variable.
```


**14. Spelling Mistake**

```javascript
const username = 'john_doe';
const email = 'john@example.com';

console.log(usename);
// Find and correct the spelling mistake.
```


**17. Wrong HTTP Method**

```javascript
app.get('/api/delete-user', (req, res) => {
  // Find and explain the mistake related to HTTP method.
});
```

**18. Invalid Object Property**

```javascript
const person = { name: 'Alice', age: 25 };
console.log(person.gender);
// Find and explain the usage of an invalid object property.
```


### Frontend - part 1

**SPAs (Single Page Applications):**

1. Explain what a Single Page Application (SPA) is and provide an example of when it's beneficial to use one.

2. Describe the advantages and disadvantages of SPAs compared to traditional multi-page applications.

3. How does routing work in a SPA, and why is it important for user navigation?

5. Discuss the role of a router library like React Router in building SPAs.

**Ajax:**

7. What are the primary use cases for making asynchronous Ajax requests in a React application?

8. Describe the components involved in an Ajax request-response cycle.

10. Explain the concept of cross-origin requests (CORS) and how it can affect Ajax requests.

**Virtual DOM:**

11. What is the Virtual DOM, and why is it important for React's performance?

12. How does React's reconciliation process utilize the Virtual DOM to efficiently update the actual DOM?

13. Discuss the benefits of using keys when rendering lists of components in React.

14. Describe a scenario where manually manipulating the Virtual DOM might be necessary.

15. Explain how the Virtual DOM helps minimize direct DOM manipulation in React.

**React Components:**

16. Define what a React component is and explain its role in building user interfaces.

19. What are prop-based components, and why are they important for building reusable UI elements?

20. Explain the concept of component composition and its advantages in React development.

**JSX (JavaScript XML):**

21. What is JSX, and why is it commonly used in React development?

22. How does JSX relate to regular JavaScript, and what transformation step is required for it to work in browsers?

23. Provide an example of JSX code that renders a simple React component.

24. Explain how JSX handles dynamic data and expressions within curly braces `{}`.

25. Describe the difference between JSX and HTML, especially when it comes to attribute names.

**Styling React Components:**

26. Discuss different approaches for styling React components, including inline styles, CSS modules, and CSS-in-JS libraries.

27. Explain the benefits of using CSS-in-JS libraries like styled-components or emotion.

28. Describe how the `className` attribute is used to apply CSS classes to React components.

29. What is the purpose of global CSS files in a React application, and how can they affect component styling?


**Props (Properties):**

31. Define props in React and explain how they facilitate the flow of data between parent and child components.

32. Provide an example of passing props to a child component and accessing them inside the child.

33. How can default props be specified for a React component, and when is this feature useful?

35. Discuss the limitations of props, including their immutability, and how state can be used as an alternative.

**Lists:**

36. Describe how to render a list of items in React using the `map` method and JSX.

37. What is a key in React, and why is it important when rendering lists of components?

38. Explain the differences between `map` and `forEach` when iterating over an array to render elements.

39. Discuss scenarios where using the `map` method with a unique key is crucial.

40. How can you conditionally render elements within a list based on specific criteria?

**Events:**


43. Explain how to prevent the default behavior of an event in React, such as preventing form submission.

45. Provide an example of using the `onClick` event to toggle the visibility of a component.

**State Management with useState:**

46. What is state in React, and how does it differ from props?

47. Describe the purpose of the `useState` hook in functional components.

48. Provide an example of declaring and updating state using `useState`.

49. Explain the rules and best practices for updating state based on the previous state.


**Side Effects with useEffect Hook:**

51. Define side effects in the context of React and why they require special handling.

52. Describe the purpose of the `useEffect` hook and when it should be used.

53. Provide an example of using `useEffect` to perform an asynchronous operation.

54. Explain how to clean up side effects using the `return` function within `useEffect`.

55. Discuss the concept of dependencies in `useEffect` and how they affect its behavior.

**useReducer Hook:**

56. What is the `useReducer` hook, and how does it differ from `useState`?

59. Explain the benefits of using `useReducer` for managing state in certain scenarios.

**Context API:**

61. What is the Context API in React, and how does it address prop drilling?

62. Describe the components of the Context API, including `Provider` and `Consumer`.

**Front End Authentication:**

66. Explain the concept of authentication in the context of web applications.

68. Provide an overview of user authentication flows, including registration, login, and logout.


**Custom Hooks:**

71. What are custom hooks in React, and why are they used?

72. Describe the structure and naming conventions for custom hooks.

74. Explain the benefits of creating custom hooks for code reuse and maintainability.


**MVC Pattern (Model-View-Controller):**

76. Define the Model-View-Controller (MVC) architectural pattern and its relevance to web development.

77. Explain how React components relate to the MVC pattern and which role they align with (Model, View, or Controller).

78. Provide an example of a React component that represents a view in the MVC


### Frontend - part 2


3. **Props and Rendering:**

   ```jsx
   function Greeting(props) {
     return <div>Hello, {props.name}!</div>;
   }
   ```
   
   Describe how you would use the `Greeting` component to render a personalized greeting in a React app.

4. **Event Handling:**

   ```jsx
   function Counter() {
     const [count, setCount] = useState(0);
     
     const handleIncrement = () => setCount(count + 1);
     
     return (
       <div>
         <p>Count: {count}</p>
         <button onClick={handleIncrement}>Increment</button>
       </div>
     );
   }
   ```
   
   Explain how the `handleIncrement` function and the `onClick` event work in this code.

5. **Conditional Rendering:**

   ```jsx
   function ConditionalRender({ condition }) {
     return condition ? <div>Show Me</div> : null;
   }
   ```
   
   How does this component conditionally render content based on the `condition` prop?

6. **Lists and Keys:**

   ```jsx
   function ListItems({ items }) {
     return (
       <ul>
         {items.map((item, index) => (
           <li key={index}>{item}</li>
         ))}
       </ul>
     );
   }
   ```
   
   Explain the purpose of the `key` attribute when rendering a list of items in React.

8. **State Management:**

   ```jsx
   function StateDemo() {
     const [count, setCount] = useState(0);
     
     return (
       <div>
         <p>Count: {count}</p>
         <button onClick={() => setCount(count + 1)}>Increment</button>
       </div>
     );
   }
   ```
   
   Explain how the `useState` hook manages the `count` state in this component.

10. **Context API:**

    ```jsx
    const ThemeContext = React.createContext('light');
    
    function ThemedButton() {
      return (
        <ThemeContext.Consumer>
          {theme => <button>{theme} Theme</button>}
        </ThemeContext.Consumer>
      );
    }
    ```
   
    Explain how the `ThemedButton` component consumes the theme context using the Context API.

11. **Use of Hooks:**

    ```jsx
    import { useState, useEffect } from 'react';
    
    function Timer() {
      const [seconds, setSeconds] = useState(0);
      
      useEffect(() => {
        const timer = setInterval(() => {
          setSeconds(seconds + 1);
        }, 1000);
        
        return () => clearInterval(timer);
      }, [seconds]);
      
      return <div>Seconds: {seconds}</div>;
    }
    ```
   
    Describe how the `useState` and `useEffect` hooks are used to create a timer in this component.

12. **Handling Forms:**

    ```jsx
    function FormExample() {
      const [inputValue, setInputValue] = useState('');
      
      const handleChange = (event) => {
        setInputValue(event.target.value);
      };
      
      return (
        <form>
          <input type="text" value={inputValue} onChange={handleChange} />
          <p>You typed: {inputValue}</p>
        </form>
      );
    }
    ```
   
    Explain how the `handleChange` function and the `onChange` event handler work together to update the form input.

13. **Conditional Styling:**

    ```jsx
    function Alert({ type }) {
      const styles = {
        success: { color: 'green' },
        error: { color: 'red' },
      };
      
      return <div style={styles[type]}>This is an {type} alert.</div>;
    }
    ```
   
    Describe how this component applies conditional styling based on the `type` prop.

14. **Context Provider:**

    ```jsx
    const MyContext = React.createContext();

    function MyProvider({ children }) {
      const value = 'Hello from Context!';

      return <MyContext.Provider value={value}>{children}</MyContext.Provider>;
    }
    ```
   
    Explain the purpose of the `MyProvider` component and how it provides context to its children.

15. **React Router:**

```jsx
import { BrowserRouter, Routes, Route } from 'react-router-dom'
    
function App() {
return (
    <div className="App">
      <BrowserRouter>
        <nav className="navbar">
        <h1>My Blog</h1>
        <div className="links">
            <Link to="/">Home</Link>
            <Link to="/create">New Blog</Link>
        </div>
        </nav>
        <div className="content">
          <Routes>
          <Route 
              path="/" 
              element={<Home />} 
            />
            <Route 
              path="/create" 
              element={<Create />} 
            />
            <Route 
              path="/blogs/:id" 
              element={ <BlogDetails />} 
            />
          </Routes>
        </div>
      </BrowserRouter>
</div>
  );
}
```
   
Explain how this code sets up routing using React Router, including the usage of `Link` and `Route` components.

### Frontend - part 3

1. **State Declaration:**

   ```jsx
   function Counter() {
     let count = 0;
     
     const increment = () => {
       count++;
     };
     
     return (
       <div>
         <p>Count: {count}</p>
         <button onClick={increment}>Increment</button>
       </div>
     );
   }
   ```
   
   What mistake is present in this code related to state management?

2. **Conditional Rendering:**

   ```jsx
   function Message({ showMessage }) {
     return showMessage && <p>Show this message</p>;
   }
   ```
   
   Is there anything wrong with the conditional rendering logic of this component.


4. **Undefined Variable:**

   ```jsx
   function Product({ product }) {
     return (
       <div>
         <h3>{product.name}</h3>
         <p>Price: ${price}</p>
       </div>
     );
   }
   ```
   
   Find the undefined variable that should be used in place of `price`.

5. **Incorrect State Update:**

   ```jsx
   function ToggleButton() {
     const [enabled, setEnabled] = useState(true);
     
     const toggle = () => {
       enabled= !enabled;
     };
     
     return (
       <button onClick={toggle}>{enabled ? 'Disable' : 'Enable'}</button>
     );
   }
   ```
   
   What mistake is made when updating the state in this component?

6. **Incorrect Use of useEffect:**

   ```jsx
   function Timer() {
     useEffect(() => {
       let seconds = 0;
       setInterval(() => {
         seconds++;
       }, 1000);
     });
     
     return <div>Seconds: {seconds}</div>;
   }
   ```
   
   Identify the issue with the `useEffect` in this code.

7. **Invalid Prop Assignment:**

   ```jsx
   function UserDetails({ user }) {
     user = null;
     
     return (
       <div>
         <h2>{user.name}</h2>
         <p>Email: {user.email}</p>
       </div>
     );
   }
   ```
   
   Find the problem with how the `user` prop is being assigned and used.

8. **Rendering Null:**

   ```jsx
   function DisplayMessage({ message }) {
     if (!message) {
       return null;
     }
     return <p>{message}</p>;
   }
   ```
   
   Identify what will happen when the `message` prop is `null`.

10. **Undefined Variable Scope:**

    ```jsx
    function UserProfile({ user }) {
      const fullName = user.firstName + ' ' + lastName;
      
      return (
        <div>
          <h2>{fullName}</h2>
          <p>Email: {user.email}</p>
        </div>
      );
    }
    ```
   
    Find the scope-related mistake in this code snippet.

11. **Conditional Rendering Logic:**

    ```jsx
    function PriceTag({ price }) {
      if (price >= 50) {
        return <p>High Price</p>;
      } else {
        return <p>Low Price</p>;
      }
    }
    ```
   
    Identify a simplification that can be made to the conditional rendering logic.

13. **Multiple Elements in JSX:**

    ```jsx
    function ItemsList({ items }) {
      return (
        <div>
          <h2>Items List</h2>
          {items.map(item => (
            <p key={item.id}>{item.name}</p>
          ))}
        </div>
      );
    }
    ```
   
    Identify if there are issues related to the requirement of a unique key for mapping.

15. **Use of `async` in Wrong Place:**

    ```jsx
    async function fetchData() {
      const response = await fetch('https://api.example.com/data');
      const data = await response.json();
      return data;
    }
    fetchData()
    ```
   
    Identify if there are issues related to the use of `async` in this function.

17. **Incorrect Usage of `map`:**

    ```jsx
    function RenderNames({ names }) {
      return names.map(name => <p>Name: {names}</p>);
    }
    ```
   
    Find the mistake in how the `map` function is used.

19. **Unused Variable:**

    ```jsx
    function UserDetails({ user }) {
      const address = user.address;
      
      return (
        <div>
          <h2>{user.name}</h2>
          <p>Email: {user.email}</p>
        </div>
      );
    }
    ```
   
    Find the unused variable that can be removed to simplify the code.

20. Mutating existing object

```JSX
function reducer(state, action) {
  switch (action.type) {
    case 'incremented_age': {
      // 🚩 Wrong: mutating existing object
      state.age++;
      return state;
    }
    case 'changed_name': {
      // 🚩 Wrong: mutating existing object
      state.name = action.nextName;
      return state;
    }
    // ...
  }
}
```

Is there anything wrong with the code?

