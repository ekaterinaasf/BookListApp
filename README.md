# BookListApp

This project is created to store books in a convenient way with theirs titles, author and ISBN information. Customer can add new books, remove existing and fill in all required information. In case of incorrect usage or if some actions were finished, application will alert with the appropriate event at the top of this application.

## DOM

| tag name  | attributes                                                         | role                                  |
| --------- | ------------------------------------------------------------------ | ------------------------------------- |
| `<div>`   | `class="container mt-4"`                                           | the container for list of books       |
| `<h1>`    | `class="display-4 text-center"`                                    | the container title                   |
| `<form>`  | `id="book-form"`                                                   | form for book information to input    |
| `<div>`   | `class="form-group"`                                               | the container for book title          |
| `<input>` | `type="text" id="title" class="form-control"`                      | the field to input book title         |
| `<div>`   | `class="form-group"`                                               | the container for book author         |
| `<input>` | `type="text" id="author" class="form-control"`                     | the field to input book author        |
| `<div>`   | `class="form-group"`                                               | the container for book isbn           |
| `<input>` | `type="text" id="isbn" class="form-control"`                       | the field to input book isbn          |
| `<input>` | `type="submit" value="Add Book" class="btn btn-primary btn-block"` | element to submit info                |
| `<table>` | `class="table table-striped mt-5"`                                 | the table to demonstrated saved books |

## Styling

In tis project is used pre-defined set of styles loaded from [here]("https://bootswatch.com/4/yeti/bootstrat.min.css")

## Listeners

| type                 | attached to    | callback                                                                              |
| -------------------- | -------------- | ------------------------------------------------------------------------------------- |
| `'click'`            | `"#book-list"` | `UI.deleteBook, Store.removeBook, UI.showAlert`                                       |
| `"submit"`           | `"#book-form"` | `event.preventDefault, UI.showAlert, UI.addBookToList, Store.addBook, UI.clearFields` |
| `"DOMContentLoaded"` | `document`     | `UI.displayBooks`                                                                     |

## Handlers

| syntax        | parameters                                                        | return value | behavior                     |
| ------------- | ----------------------------------------------------------------- | ------------ | ---------------------------- |
| `class UI`    | `displayBooks, addBookToList, deleteBook, showAlert, clearFields` | no           | class to handle UI           |
| `class Store` | `getBooks, addBook, removeBook`                                   | no           | class to handle book storage |
