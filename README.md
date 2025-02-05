Travel Tracker

A simple travel tracker application built using Node.js, Express, PostgreSQL, and EJS. The application allows users to track countries they have visited by adding country names and viewing their list of visited countries.

Features

Display a list of visited countries.

Add a new country to the visited countries list.

Validate country names and prevent duplicates.

Requirements

Ensure the following are installed on your system:

Node.js

PostgreSQL

npm (Node Package Manager)

Installation

cd travel-tracker

Install dependencies:

npm install

Set up the PostgreSQL database:

Create a database named world.

Create two tables:

CREATE TABLE countries (
  country_code VARCHAR(3) PRIMARY KEY,
  country_name VARCHAR(255) NOT NULL
);

CREATE TABLE visited_countries (
  id SERIAL PRIMARY KEY,
  country_code VARCHAR(3) REFERENCES countries(country_code)
);

Populate the countries table with relevant data, including country_code and country_name.

Update the database credentials in the index.js file:

const db = new pg.Client({
  user: "your_postgres_username",
  host: "localhost",
  database: "world",
  password: "your_postgres_password",
  port: 5432,
});

Start the application:

npm start

Open your browser and navigate to:

http://localhost:3000

File Structure

travel-tracker/
├── public/               # Static files (CSS, JS, images)
├── views/                # EJS templates
├── index.js              # Main server file
├── package.json          # Project dependencies and scripts
└── README.md             # Project documentation

Usage

Home Page: Displays the list of visited countries and the total count.

Add Country: Enter a country name to add it to the list.

If the country name is invalid or already exists, an error message will be displayed.

Contributing

Contributions are welcome! To contribute:

Fork the repository.

Create a new branch:

git checkout -b feature-name

Commit your changes:

git commit -m "Add new feature"

Push to the branch:

git push origin feature-name

Open a Pull Request.

License

This project is licensed under the MIT License.
___________________________________________________________________________________________________________________
Happy tracking! 🌍

