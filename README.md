# AI Event Planner

An AI-powered event management application built with React that allows users to create, manage and organise their events. The application integrates the OpenRouter API to generate engaging event descriptions based on user-provided event details.

## Features

- **User Registration:** Create an account to access the application.
- **User Login:** Log in to access your personal event dashboard.
- **Protected Routes:** Restrict access to event management pages to authenticated users.
- **Event Dashboard:** View and manage your upcoming events in one place.
- **Create Events:** Add events with a name, date, time, description and location.
- **Edit Events:** Update existing event information.
- **Delete Events:** Remove events that are no longer needed.
- **AI-Generated Descriptions:** Use the OpenRouter API and GPT-4o model to generate event descriptions automatically.
- **User-Specific Events:** Each user can view and manage their own events.
- **Persistent Storage:** Store user and event information using browser local storage.

## Technology Stack

| Technology | Purpose |
|---|---|
| React 19 | Frontend development and UI components |
| JavaScript (ES6+) | Application logic |
| Vite | Development server and build tool |
| React Router | Client-side navigation and routing |
| React Context API | Global authentication and event state management |
| Local Storage | Persist user and event information |
| OpenRouter API | AI-powered event description generation |
| GPT-4o | Generate event descriptions |
| CSS | Application styling |

## Getting Started

Follow these instructions to run the application locally.

### Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/)
- npm (included with Node.js)
- A code editor such as Visual Studio Code
- An OpenRouter API key for AI description generation

### 1. Clone the Repository

```bash
git clone https://github.com/MoipatiThoobe/AI-Event-Planner.git
```

### 2. Navigate to the Project Directory

```bash
cd AI-Event-Planner
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure Environment Variables

Create a `.env` file in the root directory of the project.

Add your OpenRouter API key:

```env
VITE_OPENROUTER_API_KEY=your_openrouter_api_key
```

Replace `your_openrouter_api_key` with your actual API key.

You can obtain an API key from [OpenRouter](https://openrouter.ai/).

**Important:** Never commit your `.env` file or expose a private API key in a public repository. Vite exposes variables prefixed with `VITE_` in the client-side application bundle. For production, route AI requests through a backend server that securely stores the API key.

### 5. Start the Development Server

```bash
npm run dev
```

Open the local URL provided by Vite in your browser (usually `http://localhost:5173`).

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts the Vite development server |
| `npm run build` | Builds the application for production |
| `npm run preview` | Previews the production build locally |
| `npm run lint` | Runs ESLint to identify code quality issues |

## Project Structure

```text
AI-Event-Planner/
│
├── public/
│
├── src/
│   ├── components/
│   │   ├── Navbar.jsx
│   │   └── ProtectedRoute.jsx
│   │
│   ├── context/
│   │   ├── AuthContext.jsx
│   │   └── EventContext.jsx
│   │
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── EditEvent.jsx
│   │   ├── EventForm.jsx
│   │   ├── Help.jsx
│   │   ├── Login.jsx
│   │   └── Register.jsx
│   │
│   ├── App.jsx
│   ├── App.css
│   └── main.jsx
│
├── .env
├── .gitignore
├── eslint.config.js
├── index.html
├── package.json
├── package-lock.json
└── vite.config.js
```

## AI Integration

The application integrates with the OpenRouter API to provide AI-powered event description generation.

When creating an event, users can enter an event title and select the **Generate Description** option.

The application sends the available event information to the OpenRouter API, which uses the GPT-4o model to generate a relevant description.

The generated description is automatically populated into the event form, allowing users to review and edit it before saving.

The AI integration uses the following API endpoint:

```text
https://openrouter.ai/api/v1/chat/completions
```

## State Management

The application uses React Context API to manage shared application state.

- **AuthContext:** Manages the current user's authentication state.
- **EventContext:** Handles event creation, retrieval, updating and deletion.

Event information is persisted using browser local storage, allowing events to remain available after refreshing the application.

Events are associated with individual user IDs to ensure that users only see and manage their own events.

## Future Improvements

Potential enhancements include:

- Implementing backend authentication and secure password management.
- Integrating a database for persistent event storage.
- Moving AI API requests to a secure backend service.
- Adding event reminders and notifications.
- Implementing event search, filtering and sorting.
- Deploying the application to a cloud hosting platform.

## Author

**Moipati Thoobe**

- GitHub: [@MoipatiThoobe](https://github.com/MoipatiThoobe)

---

*Built as a full-stack development learning project exploring React, state management, authentication, CRUD functionality and generative AI integration.*
