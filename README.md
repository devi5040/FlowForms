
# FlowForm

FlowForm is a form-processing service that lets you collect, manage, and securely store form submissions. Designed for flexibility, FlowForm can be used as a self-hosted solution or as a convenient, pre-hosted service, making it easy to connect your website forms with a single URL.

## Designs and Workflow

- **Designs**: [View on Figma](https://www.figma.com/design/0h7EP6qnrSbjwL1p9IZDI1/FlowForm?m=auto&t=BPyFMOGmc3UA0MrF-1)
- **Workflow (Simple)**: [View on Miro](https://miro.com/app/board/uXjVLI3IAnI=/?share_link_id=805282326065)

## Features

- **Easy Integration**: Seamlessly connect forms from your website to FlowForm with minimal setup.
- **Data Persistence**: Store form submissions securely in PostgreSQL using Prisma ORM.
- **User Authentication**: Supports Google OAuth2 and local login for managing access.
- **Session Management**: Persistent sessions using PostgreSQL, ensuring security and convenience.
- **RESTful API**: Access and manage forms, projects, and users through a structured API.
- **Swagger API Documentation**: Full API documentation for easy reference and testing.

---

## Getting Started

### Prerequisites

- **Node.js** and **npm**
- **PostgreSQL** for data storage
- Environment variables configured in a `.env` file:
  - `DATABASE_URL`: Connection string for PostgreSQL
  - `SESSION_SECRET`: Secret key for session management
  - `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET`: For Google OAuth

### Installation

#### Server

1. Clone the repository and navigate to the server folder:
   ```bash
   git clone https://github.com/yourusername/FlowForm.git
   cd FlowForm/server
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up the database using Prisma:
   ```bash
   npx prisma migrate dev --name init
   ```

4. Start the server:
   ```bash
   npm start
   ```

Your server should now be running on `http://localhost:3000`.

#### Client

1. Navigate to the client folder:
   ```bash
   cd ../client
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the client:
   ```bash
   npm start
   ```

Your client should now be running on `http://localhost:3001`.

---

## Usage

### Authentication

FlowForm supports both Google OAuth and local login for user authentication.

- **Google OAuth**: Authenticate users with their Google accounts.
- **Local Login**: Register and log in users with an email and password.

### API Endpoints

#### Authentication

- **POST /auth/login**: Log in with email and password.
- **POST /auth/signup**: Register a new user.
- **GET /auth/google**: Redirect to Google for authentication.
- **GET /auth/google/callback**: Google OAuth callback.
- **GET /auth/logout**: Log out the current user.

#### Forms

- **POST /forms**: Create a new form associated with a project.
- **GET /forms**: Retrieve all forms.
- **GET /forms/{id}**: Retrieve a specific form by ID.
- **PUT /forms/{id}**: Update a form by ID.
- **DELETE /forms/{id}**: Delete a form by ID.

#### Projects

- **POST /projects**: Create a new project.
- **GET /projects**: Retrieve all projects.
- **GET /projects/{id}**: Retrieve a specific project by ID.
- **PUT /projects/{id}**: Update a project by ID.
- **DELETE /projects/{id}**: Delete a project by ID.

### Data Security

FlowForm uses session-based authentication and stores data securely in PostgreSQL, ensuring that user data is only accessible to authorized users. Sessions are maintained securely using HTTP-only cookies and encrypted secrets.

### API Documentation

To access the Swagger API documentation, start your server and go to:
```
http://localhost:3000/api-docs
```

---

## Example Workflow

1. **Register or Login**: Register a new user or log in using Google or local credentials.
2. **Create a Project**: Start by creating a project to organize forms.
3. **Add Forms**: Create forms associated with projects to collect submissions.
4. **Retrieve and Manage Data**: Use the API to retrieve, update, or delete projects and forms as needed.

---

## Contributing

We welcome contributions! Feel free to submit issues, fork the repository, and make pull requests.

## License

This project is licensed under the MIT License.

---
