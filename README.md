# Lighthouse Labs | Mid-Term Kick-off

[GitHub Repository Branch](https://github.com/WarrenUhrich/midterm-kickoff) | [Vimeo Video Recording](https://vimeo.com/858081846/68a1a0bf1c?share=copy)

* [X] Setting the Stage
* [X] The Mid-Terms Project
* [X] Project Planning and Management
* [X] The Node Skeleton

## Setting the Stage

* A group project (to be assigned by SSCs)
* Reach out to your group right away, get started on planning thru' the weekend!
* 10 different options pick from
* Multi-page approach (no Ajax, just standard forms and pages) should be your default
    * If you're feeling confident, you can try single-page app (one page, and Ajax grabs new info)
    * You don't have to just pick one—consider a hybrid approach to get the best of both worlds
* Stack includes:
    * EJS
    * Express / Node
    * CSS
    * HTML5
    * ES6+ (browser JS)
        * jQuery
    * PostgreSQL
    * Git
* Recommended:
    * Any one of: [Bootstrap](https://getbootstrap.com/), [Bulma](https://bulma.io/), [Materialize](https://materializecss.com/), [Foundation](https://get.foundation/)
    * CSS frameworks will save you a ***lot*** of time and help you reach your MVP sooner!

## How are we Handling Users / Authentication?

***Don't*** set-up a whole registration and sign-in set of pages, forms, and routes.

```js
app.get('/login/:id', (req, res) => {

    // EITHER use session:
    req.session.user_id = req.params.id;

    // OR use (plain-text) cookie:
    res.cookie('user_id', req.params.id);

    // Do ONE of the above, and then send'em
    // somewhere else!
    res.redirect('/profile');
});
```

## Planning Your Project!

### 1. Read requirements carefully and write **User Stories**.

* As a \_\_\_\_\_\_, I want to \_\_\_\_\_\_, because I \_\_\_\_\_\_.

* As a signed-in seller *user*, I want to to be able to create a *product*, because I want to be able to display it on the site for sale.

* As a signed-in seller *user*, I want to to be able to mark one of my products as sold, because I want to make sure people don't reach out about products I don't have.

### 2. **Nouns** - Database Tables

Read your user stories carefully. Extract any nouns you'll want as tables or data, as these are important!

`users` | `products`

### 3. **Entity Relationship Diagram** (ERD)

Review your nouns and user stories, consider:

* What columns belong in each table?
* How are these tables related?

Use a tool like [Draw.IO / Diagrams.net](https://app.diagrams.net/) to create this diagram.

### 4. **Routes**

When working on routes, consider your ERD. Which "CRUD" operations do you need in order to fulfill your project's requirements on each table?

`CRUD` | `BREAD`

Remember that CRUD or BREAD on their own cover common operations you might perform on data. They do ***not** cover all routes you might use in a website to facilitate these actions. Observe, the following is incomplete:

```
    method    path

C   POST      /posts
R   GET       /posts/:id
U   POST      /posts/:id
D   POST      /posts/:id/delete
```

A more complete coverage of the routes you might need might look like so:

```
        method   path

Index   GET      /posts
Create  GET      /posts/new        # SHOWING the form
Read    GET      /posts/:id
Update  POST     /posts/:id
Delete  POST     /posts/:id/delete
Edit    GET      /posts/:id/edit   # SHOWING the form
Save    POST     /posts            # SUMBITTING CREATE FORM
```

Or, if you'd like to use RESTFUL verbs (see the [method-override npm package](https://www.npmjs.com/package/method-override)), something like this:

```
        verb     path

Index   GET      /posts
Create  GET      /posts/new        # SHOWING the form
Read    GET      /posts/:id
Update  PUT      /posts/:id
Delete  DELETE   /posts/:id
Edit    GET      /posts/:id/edit   # SHOWING the form
Save    POST     /posts            # SUMBITTING CREATE FORM
```

### 5. Wireframes

* Reference all your planned GET method routes... which ones will the user see?
* Check your ERD when planning out any form's fields
* Make a plan for each page the user sees

Consider using the industry standard tool, [Figma](https://www.figma.com/).

### 6. Set-up GitHub

* Create a `/planning` directory to place the documents above into for reference throughout the project
* Make sure everyone is added as contributers
* Agree to a branching / merging flow and process (are you using Pull Requests?)

### 7. Set-up the Project Structure (Together!)

* Consider naming conventions
* Consider code-style
* Consider where things belong (which folders)
* Use the [node-skeleton](https://github.com/lighthouse-labs/node-skeleton) repo to get started and establish these

### 8. Workflow (Trello) and Comms (Discord)

* Know who is on what!? Use a Kanban board on a site like [Trello](https://trello.com/) to keep track
* How often will you meet? Touch base daily!
* Ping team members when merging `main` so that they know to pull the latest changes

**Tip**: Kanban boards usually have at least three columns:

1. To-Dos (try to limit tasks to something that might take up to 3-6 hours)
2. In-Progress (only claim one task at a time, work until completion)
3. Completed (congrats! 🙌)
