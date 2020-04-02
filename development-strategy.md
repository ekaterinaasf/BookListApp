# Book List application

This project is created to store books in a convenient way with theirs titles, author and ISBN information. Customer can add new books, remove existing and fill in all required information. In case of incorrect usage or if some actions were finished, application will alert with the appropriate event at the top of this application.

## 1. Book Class: Represents a Book

We need to create a class `Book` to address to the book information. It consists of three variables title, author and isbn.

## 2. UI Class: Handle UI Tasks

We need to create a class `UI` to handle all actions necessary to apply in User Interface. There are methods to display, add, delete books, show alerts and empty all fields.

### displayBooks method

This method is going through all stored in Store books and add them into book list via `UI.addBookToList` method from the same class.

### addBookToList method

This method is taking book data as an argument and create a table inside pre-defined DOM element with all information regarding book.

### deleteBook method

This method take a DOM element as an argument and removing it from the book list.

### showAlert(message, className) method

This method is generating alerts at the top of the application and remove it 3 seconds afterwards using `setTimeout` method.

### clearFields method

This method is remove all information from the input field for all three book parameters: author, title and isbn.

## 3. Store Class: Handles Storage

We need to create a `Store` class to keep already available information to not lose it while refreshing the page.

### getBooks() method

This method should return an array of books that exist in local storage.

### addBook(book) method

This method take new book item as an argument and add at the end of book array received via the `Store.getBooks` method.

### removeBook(isbn) method

This method is received as an argument an isbn of book that has to be removed from the storage. It received book array via `Store.getBooks` method and going through it finds the element to delete.

## 4. Event: Display Books

As soon as DOM content of the page is loaded `UI.displayBooks` is executed.

## 5. Event: Add a Book

This part is developed as a function applied to `submit` event for the form with `"#book-form"` id using event listener.

### Get form values

Initially we should receive book parameters (title, author, isbn) from the DOM form using `document.querySelector`.

### Validate

As the step two, we need to validate if all three parameters are filled by the customer and if not,
`UI.showAlert` has to alert customer. And then apply all necessary actions for book instantiation.

#### Instatiate book

We need to create an instance of `Book class`

#### Add Book to UI

    We are using `UI.addBookToList` method here.

#### Add book to store

    Use `Store.addBook` method.

#### Show success message

    Use `UI.showAlert` method with the "success" parameter.

#### Clear fields

    Finally, we need to empty fields with `UI.clearFields` method.

## 6. Event: Remove a Book

This block is responsible for the correct book item deletion process.

### Find DOM element

We use `document.querySelector` with a `"#book-list"` id for that.

### Remove book from UI

Use `UI.deleteBook` method to remove book from the User Interface.

### Remove book from store

Use `Store.removeBook` to remove book item from the storage.

### Show success message

Finally, show to the customer that acton is finished successfully via `UI.showAlert` method
