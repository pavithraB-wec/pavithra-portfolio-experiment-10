# Pavithra B. Portfolio

A personal portfolio website for Pavithra B., built with HTML, CSS, and JavaScript and served by an Express server. The contact form sends messages through Gmail using Nodemailer.

## Requirements

- Node.js 18 or later
- npm
- A Gmail account with a Google App Password for contact form email

## Getting Started

Install the project dependencies:

```sh
npm install
```

Create a `.env` file in the project root, using `.env.example` as a template:

```env
EMAIL=yourgmail@gmail.com
APP_PASSWORD=your_16_character_gmail_app_password
PORT=3000
```

`EMAIL` is the Gmail account used to send and receive contact messages. `APP_PASSWORD` is a Google App Password for that account, not its regular sign-in password. `PORT` is optional and defaults to `3000`.

Start the server:

```sh
npm start
```

Open [http://localhost:3000](http://localhost:3000) (or the configured port) in your browser.

## Contact Form

The browser submits contact form data to `POST /contact`. The server validates the name, email, and message, then emails the message to the configured `EMAIL` address. Configure valid Gmail credentials in `.env` for email delivery; without them, the portfolio itself can still be viewed, but sending the form will fail.

## Project Structure

```text
.
|-- public/
|   |-- index.html   # Portfolio page
|   |-- script.js    # Browser interactions and contact form
|   `-- style.css    # Page styles and responsive layout
|-- server.js        # Express static server and contact endpoint
|-- .env.example     # Environment variable template
`-- package.json     # Dependencies and npm scripts
```