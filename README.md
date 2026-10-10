
# Pavithra Balamurugan. Portfolio

A personal portfolio website for Pavithra B., built with HTML, CSS, and JavaScript and served by an Express server. The contact form sends messages through Gmail using Nodemailer.

<img width="1240" height="7845" alt="image" src="https://github.com/user-attachments/assets/befe8085-a258-4e96-8985-4c9522487e6b" />

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
<img width="1349" height="672" alt="Screenshot 2026-10-09 154029" src="https://github.com/user-attachments/assets/d19595a4-18b5-481c-aa8f-8e080617aaeb" />
<img width="720" height="1600" alt="image" src="https://github.com/user-attachments/assets/4f095bd7-c7ca-4424-883e-1513e4c599cb" />


## Gmail Configuration for Contact Form

To receive messages submitted through the portfolio contact form, configure Gmail using a Google App Password.

### 1. Enable 2-Step Verification

1. Sign in to the Gmail account you want to use for receiving contact messages.
2. Open [Google Account Security](https://myaccount.google.com/security).
3. Enable **2-Step Verification** if it is not already enabled.

### 2. Generate a Google App Password

1. Open [Google App Passwords](https://myaccount.google.com/apppasswords).
2. Sign in again if prompted.
3. Create a new app password and name it `Portfolio`.
4. Copy the generated 16-character password.

**Note:** Google App Passwords require 2-Step Verification and may not be available for some account types or security configurations.

### 3. Configure the `.env` File

Create a file named `.env` in the project root directory, alongside `server.js` and `package.json`.

Add the following configuration:

```env
EMAIL=yourgmail@gmail.com
APP_PASSWORD=your_16_character_app_password
PORT=3000
```

Replace the example values with your own Gmail address and generated App Password. Remove any spaces from the App Password.

- `EMAIL`: Gmail account used to send and receive contact messages.
- `APP_PASSWORD`: Google-generated App Password, not your regular Gmail password.
- `PORT`: Local server port; defaults to `3000`.

### 4. Start the Application

Run the following commands in the project terminal:

```bash
npm install
node server.js
```

Open the website in your browser:

```text
http://localhost:3000
```

Submit the contact form to test the email functionality.

### 5. Security Guidelines

- Never upload your `.env` file to GitHub.
- Keep `.env` listed in `.gitignore`.
- Never share your Gmail password or App Password publicly.
- Use environment variables to manage sensitive credentials.
- For deployment, configure the same variables in your hosting provider's environment settings.

**Troubleshooting:** If you receive a `535-5.7.8 Username and Password not accepted` error, verify the Gmail address, generate a new App Password if necessary, and restart the server.

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
