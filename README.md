# Spiral Sounds

Spiral Sounds is a small online vinyl store built as a learning project. It brings together a vanilla JavaScript frontend, an Express API and a SQLite database to display records and manage a user's shopping cart.

## Features

- Browse vinyl records and filter them by genre or search for a title, artist or genre.
- Register, log in and log out with a session-based account.
- Add records to a personal cart, see the item count and total, and remove items.
- Use the checkout button to clear the cart and display a confirmation message. This is a demonstration: it does not process payments or store orders.

## What I practised

- Building an Express server and organising an API into routes, controllers and middleware.
- Connecting a Node.js application to SQLite and using parameterised SQL queries, joins, aggregates and transactions.
- Validating account details, hashing passwords with bcrypt and protecting cart routes with sessions.
- Using JavaScript modules, `fetch`, async/await and DOM manipulation to connect the interface to the API.
- Managing cart quantities and keeping data associated with the signed-in user.

## Getting started

You will need Node.js and npm installed. From the project directory, run:

```bash
npm install
npm start
```

Open [http://localhost:8000](http://localhost:8000). The repository includes `database.db`, which the app opens relative to the project directory, so start the server from that directory.

The `createTable.js` script creates only the products table, and `seedTable.js` inserts the records from `data.js`. The app also needs `users` and `cart_items` tables; the scripts do not create those tables. Seeding an existing database adds the products again, so avoid running it against the supplied database unless you intend to add duplicates.

## Project structure

```text
server.js          Express app and session configuration
routes/            API route definitions
controllers/       Request handling and database queries
middleware/        Authentication check for protected routes
db/                SQLite connection helper
public/            HTML, CSS, browser JavaScript and images
database.db        SQLite database
```

The session secret can be set with the `SPIRAL_SESSION_SECRET` environment variable. The current session configuration and checkout flow are intended for local learning and would need further work before production use.
