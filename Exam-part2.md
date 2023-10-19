# Exam - Part 2: Backend

**Backend: Question A (70 points)**

1. How does express fit in the MERN stack?
2. How do you use middleware to handle authentication in an Express.js application?
3. How do controllers help in maintaining separation of concerns in the MVC pattern?
4. Describe the difference between authentication and authorization.
5. How does token-based authentication work, and why is it commonly used in web applications?
6. Describe the advantages of using **async/await** over promise chaining with **.then()** for handling asynchronous operations.
7. What testing tools and libraries are commonly used for testing Express.js applications?
8. Compare the process of testing an API server with **Postman** and **Supertest**.

**Backend: Question B (65 points)**

Refer to the following snippet:

1. To which HTTP method, **ACTION1**, **ACTION2** and **ACTION3** belong? Justify?
2. Explain this line of code: **books[bookIndex] = { id: bookId, ...updatedBook}**

```javascript
app.ACTION1("/api/books/:id", (req, res) => {
  const bookId = parseInt(req.params.id);

  const bookIndex = books.findIndex((book) => book.id === bookId);

  if (bookIndex !== -1) {
    books.splice(bookIndex, 1);
    res.json({ message: "Book message 1" });
  } else {
    res.status(404).json({ message: "Book message 2" });
  }
});
```

```javascript
app.ACTION2("/api/books", (req, res) => {
  const book = {
    id: books.length + 1,
    title: req.body.title,
    author: req.body.author,
  };

  books.push(book);
  res.status(201).json(book);
});
```

<!-- Force page break -->
<div style="page-break-after: always;"></div>
<!-- Force page break -->

```js
app.ACTION3("/api/books/:id", (req, res) => {
  const bookId = parseInt(req.params.id);
  const book = req.body;

  const bookIndex = books.findIndex((book) => book.id === bookId);

  if (bookIndex !== -1) {

    books[bookIndex] = { id: bookId, ...book };
    res.json(books[bookIndex]);
  } else {
    res.status(404).json({ message: "Book message" });
  }
});
```

**Backend: Question C (65 points)**

1. Is there anything wrong with this code? if so how can you fix it?
```js
const app = express();
app.use(cors());

app.use(errorHandler);
app.use(express.urlencoded({ extended: false }));

app.use("/api/goals", goalRoutes);
app.use("/api/users", userRoutes);

app.get("/", (req, res) => res.send("Hello"));
app.use(express.json());

app.listen(port, () => console.log(`Server started on port ${port}`));
```

2. Explain the purpose of this middleware when used with Express.js routers.

```javascript
app.use((err, req, res, next) => {
// .
});
```


3. What are the potential consequences if **node_modules/** and **.env** are not included in the **.gitignore** file?

4. Refer to the snippet below extracted from **package.json** file:
- How can you execute the **start:backend** script?
- Why are **jest** and **express** located under different categories in the `dependencies`?

```json
{
  "scripts": {
       "start:backend": "cross-env NODE_ENV=production node backend/index.js",
       "dev": "cross-env NODE_ENV=development node backend/index.js"
  },
  "devDependencies": {
       "cross-env": "^7.0.3",
       "jest": "^29.7.0"
  },
  "dependencies": {
       "dotenv": "^16.3.1",
       "express": "^4.18.2"
  }
}
```

5. Refer to the snippet below extracted from **.env** (written by one of your classmates):
- Explain what he meant by this line **JWT_SECRET = 64bytesofrandomness**. *Please provide a detailed response, NOT a superficial answer.*
- Explain how you can access the **MONGO_URI** environment variable, from a node module.

```sh
JWT_SECRET = 64bytesofrandomness
MONGO_URI=mongodb//usr:pssw@cluster.mongodb.net
```

<h2>Part 3: Bonus</h2>

> To be eligible for a bonus through self-assessment, you need to be fair in your judgment.

1. On a scale of 1 to 5, evaluate your performance in **this exam**. (**5 points**)
2.  Using a scale of 1 to 5, assess your performance in the **web development course**. (**5 points**)
3.  Using a scale of 1 to 5, assess your performance in the **project course**. (**5 points**)
4. What **qualities** (characteristics) define a full stack developer? (**10 points**)
5. Define **soft skills** and elaborate on their importance within a work environment.  (**5 points**)






