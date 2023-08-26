# Lighthouse Labs | Mid-Term Kick-off

[Vimeo Video Recording](https://vimeo.com/858081846/68a1a0bf1c?share=copy)

* [X] Setting the Stage
* [X] The Mid-Terms Project
* [X] Project Planning and Management
* [X] The Node Skeleton

## Setting the Stage

* A group project (to be assigned by SSCs)
* 10 different options pick from
* Stack includes:
    * EJS
    * Express / Node
    * CSS
    * HTML5
    * ES6+ (browser JS)
        * jQuery
    * PostgreSQL
    * Git
* Recommend:
    * Bootstrap, Bulma, MaterialCSS, Foundation (use a CSS framework)

## How are we handling Users / Authentication?

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

1. Read requirements carefully and write **User Stories**.

As a ______, I want to _______, because I _______.
As a signed-in seller *user*, I want to to be able to create a *product*, because I want to be able to display it on the site for sale.
As a signed-in seller *user*, I want to to be able to mark one of my products as sold, because I want to make sure people don't reach out about products I don't have.

2. **Nouns** - Database Tables

`users` | `products`

3. **Entity Relationship Diagram** (ERD)

* What columns belong in each table?
* How are these tables related?

4. **Routes**

CRUD | BREAD

  method|path
C  POST  /posts
R  GET   /posts/:id
U  POST  /posts/:id
D  POST  /posts/:id/delete


Index   GET   /posts
Create  GET   /posts/new        # SHOWING the form
Read    GET   /posts/:id
Update  POST  /posts/:id
Delete  POST  /posts/:id/delete
Edit    GET   /posts/:id/edit   # SHOWING the form
Save    POST  /posts            # SUMBITTING CREATE FORM

Index   GET     /posts
Create  GET     /posts/new        # SHOWING the form
Read    GET     /posts/:id
Update  PUT     /posts/:id
Delete  DELETE  /posts/:id
Edit    GET     /posts/:id/edit   # SHOWING the form
Save    POST    /posts            # SUMBITTING CREATE FORM

5. Wireframes

* (check your ERD when planning form fields)
* Reference all GET method routes... which ones will the user see?
* Make a plan for each page the user sees

6. Set-up GitHub

* Create a `/planning`
* Make sure everyone is added as contributes
* Agree to a branching / merging flow

7. Set-up the project structure

* Consider naming conventions
* Consider code-style
* Consider where things belong (which folders)

8. Workflow (Trello) and Comms (Discord)

* Know who is on what!?
