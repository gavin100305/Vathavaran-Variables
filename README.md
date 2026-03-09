# Vathavaran Variables

> 🔐 A secure, full-stack environment variable management system for GitHub repositories with encryption, OAuth authentication, and a modern web interface.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [CLI Tool (Varte)](#cli-tool-varte)
- [API Endpoints](#api-endpoints)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

Vathavaran Variables is a comprehensive solution for managing environment variables across GitHub repositories. It provides a secure web interface and CLI tool to store, retrieve, and manage encrypted environment variables with GitHub OAuth authentication and role-based access control.

**Name Origin**: "Vathavaran" (वातावरण) means "environment" in Sanskrit and Hindi.

## ✨ Features

- 🔐 **End-to-End Encryption**: All environment variables are encrypted using CryptoJS before storage
- 🔑 **GitHub OAuth**: Seamless authentication via GitHub with automatic permission verification
- 🎨 **Modern Web Interface**: Beautiful, responsive React UI with Tailwind CSS and smooth animations
- 📦 **CLI Tool (Varte)**: Command-line tool for managing environment variables programmatically
- ☁️ **Serverless Support**: Cloudflare Workers integration for edge computing
- 🚀 **Express Backend**: RESTful API built with Node.js and Express.js
- 🔥 **Firebase Integration**: Firestore database for secure data persistence
- 🎭 **Theme Support**: Light and dark mode toggle
- 📱 **Responsive Design**: Works seamlessly on desktop and mobile devices
- 3️⃣ **3D Graphics**: Three.js integration for enhanced visual experience

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Web Browser                          │
│            (React Frontend - Vite)                      │
└──────────────────────┬──────────────────────────────────┘
                       │
         ┌─────────────┼─────────────┐
         │             │             │
    ┌────▼────┐  ┌────▼────┐  ┌────▼────────┐
    │ Express │  │ Firebase │  │  Cloudflare │
    │ Backend │  │ Auth     │  │   Workers   │
    │  API    │  │ Firestore│  │  Serverless │
    └────┬────┘  └──────────┘  └─────────────┘
         │
    ┌────▼────────────────┐
    │  CLI Tool (Varte)   │
    │   (Node.js)         │
    └─────────────────────┘
```

## 🛠️ Tech Stack

### Frontend
- **React** 19.2.0 - UI framework
- **Vite** (Rolldown) - Build tool and dev server
- **Tailwind CSS** 4.1.17 - Utility-first CSS framework
- **Framer Motion** 12.23.24 - Animation library
- **React Router** 7.9.6 - Client-side routing
- **Firebase** 12.6.0 - Authentication SDK
- **Three.js** 0.181.1 - 3D graphics library
- **Radix UI** - Headless UI components
- **Lucide React** - Icon library
- **Axios** - HTTP client

### Backend
- **Node.js** - Runtime environment
- **Express.js** 5.1.0 - Web framework
- **Firebase Admin SDK** - Backend Firebase integration
- **Dotenv** - Environment variable management
- **Cors** - Cross-Origin Resource Sharing
- **Cookie Parser** - Cookie handling
- **Axios** - HTTP client for GitHub API calls

### CLI Tool
- **Commander.js** - Command-line interface builder
- **Inquirer.js** - Interactive CLI prompts
- **CryptoJS** - Client-side encryption
- **Chalk** - Terminal string styling
- **Ora** - Loading spinners
- **Conf** - Configuration file management

### Serverless
- **Cloudflare Workers** - Edge computing platform
- **Wrangler** - Cloudflare development tool

### Database & Auth
- **Firebase Firestore** - NoSQL database
- **Firebase Authentication** - Auth service
- **GitHub OAuth** - GitHub authentication

## 📁 Project Structure

```
Vathavaran-Variables/
├── frontend/                    # React web application
│   ├── src/
│   │   ├── components/         # Reusable React components
│   │   │   └── ui/            # UI component library
│   │   ├── pages/             # Route pages
│   │   │   ├── Landing.jsx
│   │   │   ├── Auth.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Repo.jsx
│   │   │   ├── Docs.jsx
│   │   │   └── NotFound.jsx
│   │   ├── context/           # React Context (Theme, User)
│   │   ├── lib/               # Utility functions
│   │   ├── config/            # Firebase configuration
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── vite.config.js         # Vite configuration
│   ├── tailwind.config.js     # Tailwind CSS config
│   └── package.json
│
├── server/                      # Express.js backend API
│   ├── src/
│   │   ├── auth.js            # GitHub OAuth logic
│   │   ├── commands.js        # API command handlers
│   │   ├── encryption.js      # Encryption utilities
│   │   └── oauth.js           # OAuth flow management
│   ├── index.js               # Express app entry point
│   └── package.json
│
├── cli/                         # Varte CLI tool
│   ├── bin/
│   │   └── vathavaran.js      # CLI entry point
│   ├── src/
│   │   ├── auth.js
│   │   ├── commands.js
│   │   ├── encryption.js
│   │   └── oauth.js
│   ├── README.md
│   └── package.json
│
├── serverless/                  # Cloudflare Workers
│   └── my-worker/
│       ├── src/
│       │   └── index.js
│       ├── test/
│       │   └── index.spec.js
│       ├── wrangler.jsonc      # Cloudflare config
│       └── package.json
│
├── QUERIES.md                   # Database query documentation
├── README.md                    # This file
└── .env.example                # Example environment variables
```

## 🚀 Getting Started

### Prerequisites

- **Node.js** ≥ 18.0.0
- **npm** or **yarn** package manager
- **GitHub Account** (for OAuth)
- **Firebase Project** (for backend services)
- **Cloudflare Account** (for serverless functions)

### Environment Variables

Create a `.env` file in the `server` directory:

```env
# Firebase Configuration
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_CLIENT_EMAIL=your_client_email
FIREBASE_PRIVATE_KEY=your_private_key

# GitHub OAuth
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
GITHUB_REDIRECT_URI=http://localhost:3000/auth/callback

# Server Configuration
PORT=8000
NODE_ENV=development
```

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/wrestle-R/Vathavaran-Variables.git
cd Vathavaran-Variables
```

### 2. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

The frontend will start at `http://localhost:5173` (Vite default)

### 3. Backend Setup

```bash
cd ../server
npm install
npm run dev
```

The backend API will run at `http://localhost:8000`

### 4. CLI Tool Setup (Optional)

```bash
cd ../cli
npm install
npm link  # Makes 'varte' command available globally
```

### 5. Serverless Setup (Optional)

```bash
cd ../serverless/my-worker
npm install
npm run dev
```

## 💻 Usage

### Web Application

1. Navigate to `http://localhost:5173`
2. Click **Sign in with GitHub**
3. Authorize the application
4. View and manage your repositories' environment variables from the dashboard

### CLI Tool (Varte)

> Manage your environment variables directly from your terminal with seamless GitHub integration.

#### Installation

Install the CLI globally to access it from any directory.

```bash
npm install -g varte
```

#### Quick Start

Get up and running in three simple steps.

**Step 1: Login with GitHub**

```bash
varte login
```

**Step 2: Push your .env file**

```bash
varte push
```

**Step 3: Pull from anywhere**

```bash
varte pull
```

#### Commands

All available commands and their options.

##### push

Encrypt and upload your environment variables to the cloud.

```bash
varte push
varte push -f .env.production
varte push --owner myorg --repo myapp
```

**Options:**
- `-f, --file` - Path to env file (default: .env)
- `-o, --owner` - Repository owner
- `-r, --repo` - Repository name
- `-d, --directory` - Directory path
- `-n, --name` - Custom filename

##### pull

Download and decrypt your environment variables.

```bash
varte pull
varte pull --output .env.local
varte pull -d backend
```

**Options:**
- `-o, --owner` - Repository owner
- `-r, --repo` - Repository name
- `-d, --directory` - Directory path
- `--output` - Output file path

##### list

Display all stored environment files grouped by repository.

```bash
varte list
```

##### logout

Remove stored credentials from your machine.

```bash
varte logout
```

#### Examples

Common workflows and use cases.

**Deploy a new project**

```bash
git clone https://github.com/myorg/myapp.git
cd myapp
varte pull
npm install && npm start
```

**Multiple environments**

```bash
varte push -f .env.production -n production
varte push -f .env.staging -n staging
varte push -f .env.dev -n development
```

**Monorepo workflow**

```bash
# Push each service's env
varte push -d backend
varte push -d frontend

# Pull specific service
varte pull -d backend
```

#### Security

- 🔐 **End-to-End Encryption** - Variables are encrypted before leaving your machine
- 🔑 **GitHub OAuth** - Secure authentication—no passwords stored locally
- 📋 **Repository Permissions** - Only users with push access can store env files

## 🔌 API Endpoints

### Authentication

- `GET /api/auth/github` - Initiate GitHub OAuth flow
- `GET /api/auth/callback` - GitHub OAuth callback
- `GET /api/auth/user` - Get current authenticated user
- `POST /api/auth/logout` - Logout current user

### Environment Variables

- `POST /api/env/push` - Upload encrypted environment file
- `GET /api/env/pull/:owner/:repo/:envName` - Download environment variables
- `GET /api/env/list/:owner/:repo` - List all environment files for a repo
- `DELETE /api/env/delete/:id` - Delete an environment file
- `GET /api/env/search` - Search environment files

### Repository Management

- `GET /api/repo/list` - List user's repositories
- `GET /api/repo/:owner/:repo` - Get repository details
- `GET /api/repo/:owner/:repo/envs` - Get all environment files in repo

## 📊 Database Schema

### Firestore Collection: `envFiles`

```javascript
{
  id: String,              // Document ID
  userId: Number,          // GitHub user ID
  userName: String,        // GitHub username
  repoFullName: String,    // e.g., "owner/repo-name"
  repoName: String,        // e.g., "repo-name"
  directory: String,       // Directory path (empty for root)
  envName: String,         // e.g., ".env.production"
  content: String,         // Encrypted environment variables
  isEncrypted: Boolean,    // Always true
  createdAt: String,       // ISO 8601 timestamp
  updatedAt: String        // ISO 8601 timestamp
}
```

For detailed query documentation, see [QUERIES.md](./QUERIES.md).

## 🔐 Security

- ✅ **Encryption**: All sensitive data encrypted before storage using CryptoJS
- ✅ **Authentication**: GitHub OAuth 2.0 integration
- ✅ **Authorization**: Permission verification via GitHub API
- ✅ **CORS**: Configured with environment-specific origins
- ✅ **Secrets Management**: Environment variables stored securely

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

**Built with ❤️ for secure environment variable management**

