# BOOK_READER

#### Video Demo: <(https://youtu.be/Si8hKdXFBRM)>

BE DELUSIONAL
Video Demo: 
Description:
Welcome to "BE DELUSIONAL," a personal web application built as the final project for CS50x. This website serves as the digital home for my book, which focuses on core themes of discipline, motivation, and consistency. The main goal of this platform is to provide readers with a clean, immersive environment to explore the book's chapters, switch seamlessly between languages, and interact with the content through an integrated review system.

The website uses a responsive layout styled with custom dark tones to ensure a comfortable reading experience across both mobile devices and desktop computers. It combines front-end design elements with a robust back-end using Python, Flask, and SQLite.

What Each File Contains and Does
Every file in the project folder has a specific job that keeps the application running smoothly:

app.py: This is the core Python file and the heart of the backend. It initializes the Flask application, handles routing for the home page, individual chapters, the about page, language switching, and the admin dashboard. It also contains the database connection logic to safely interact with SQLite.

project.db: The SQLite database file created to store user-submitted reviews. It holds a single reviews table containing columns for the review id, the reader's name, the review_text (limited to 50 words), and the created_at timestamp.

templates/layout.html: The master template that defines the common structural layout for every page on the site. It includes the navigation bar, footer elements, and the standard HTML boilerplate, ensuring consistent design and navigation across the entire site.

templates/index.html: The homepage template. It showcases the book cover image (which adapts automatically based on the chosen language), displays an introductory message outlining the book's themes, features a dropdown menu for selecting different chapters, and includes a form for readers to submit their own brief reviews.

templates/chapter.html: The dynamic template responsible for rendering individual chapters. When a user clicks on a chapter from the dropdown menu, this template loads the corresponding text and title safely based on the selected language.

templates/about.html: A dedicated static page providing more background information about the project and its goals.

templates/admin_login.html: The login portal for the site administrator. It presents a password prompt to securely restrict access to the review management panel.

templates/admin.html: The dashboard panel visible only to authenticated users. It lists all reader reviews in a clean, organized table along with timestamps and a dedicated delete button to remove unwanted or spam feedback.

static/style.css: The custom CSS stylesheet that controls the overall visual appearance of the website. It establishes the custom dark background color (#0f1e3a), font styles, fluid typography sizing, navbar layouts, and responsive rules for images and input forms.

requirements.txt: A text file listing all external Python packages required to run the project, specifically Flask, making it simple to install dependencies using pip.

Design Choices and Alternatives
While building this project, I evaluated several design and architectural choices to ensure the website remained simple, fast, and user-friendly:

Choice of Flask over other frameworks: I chose Flask because it gives me full control over the application structure without forcing unnecessary complexity. Since this is a database-backed web app with a straightforward routing requirement, Flask offered the ideal balance of lightweight execution and powerful extension capabilities.

Multi-Language Structure: I wanted the book to be accessible to a broader audience, which is why I implemented English and Turkish language switching. Instead of building entirely separate HTML files for every language, I structured the content dictionaries and templates to dynamically pull the correct language text based on the user's active session state.

Word Count Restriction on Reviews: To prevent spam and keep the review section clean and concise, I implemented both client-side JavaScript counting and server-side validation limiting reviews to a maximum of 50 words. This ensures that user feedback stays punchy and meaningful.

Database Management: I opted to use a local SQLite database (project.db) because it is lightweight, serverless, and integrates natively with Python via the sqlite3 module, making it an ideal choice for a standalone web application of this scale.