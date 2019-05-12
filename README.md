#google-books-search-mmrydz

This is a React-based Google Books Search app. It displays books based on user searches. The app also utilizes Node, Express and MongoDB so that users can save books to review or purchase later.

This application has 2 pages:
-----------------------------

Search - User can search for books via the Google Books API and render them here. User has the option to "View" a book, bringing them to the book on Google Books, or "Save" a book, saving it to the Mongo database.

Saved - Renders all books saved to the Mongo database. User has an option to "View" the book, bringing them to the book on Google Books, or "Delete" a book, removing it from the Mongo database.

The MongoDB database (googlebooks) uses the mongoose npm package. 

The mongoose Book Schema includes:
----------------------------------
title - Title of the book from the Google Books API

authors - The books's author(s) as returned from the Google Books API

description - The book's description as returned from the Google Books API

image - The Book's thumbnail image as returned from the Google Books API

link - The Book's information link as returned from the Google Books API

The documents in the books collection look like this:

{
  authors: ["Suzanne Collins"]
  description: "Set in a dark vision of the near future, a terrifying reality TV show is taking place. Twelve boys and twelve girls are forced to appear in a live event called The Hunger Games. There is only one rule: kill or be killed. When sixteen-year-old Katniss Everdeen steps forward to take her younger sister's place in the games, she sees it as a death sentence. But Katniss has been close to death before. For her, survival is second nature."
  image: "http://books.google.com/books/content?id=sazytgAACAAJ&printsec=frontcover&img=1&zoom=1&source=gbs_api"
  link: "http://books.google.com/books?id=sazytgAACAAJ&dq=title:The+Hunger+Games&hl=&source=gbs_api"
  title: "The Hunger Games"
}

This is a SPA (Single Page Application) that uses react-router-dom to navigate, hide and show the React components without changing the route within Express.
The layout includes two React Components for each page, Search and Saved.

Express routes include:
-----------------------
/api/books (get) - Returns all saved books as JSON.

/api/books (post) - Saves a new book to the database.

/api/books/:id (delete) - Deletes a book from the database by Mongo _id.

* (get) - Loads a single HTML page in client/build/index.html. 

The application was deployed to Heroku here: 

Create React App and current versions of React and React-Router-Dom were used for this assignment.

Demo:
-----

