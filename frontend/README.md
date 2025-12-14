# Frontend - AI Mental Coach

A modern Next.js frontend application that provides a chat interface for the AI Mental Coach backend.

## Prerequisites

- Node.js 18+ and npm (or yarn/pnpm)
- The backend API running on `http://localhost:8000` (see `/api/README.md` for setup instructions)

## Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

## Running the Application

### Development Mode

1. Make sure the backend API is running (see `/api/README.md`):
```bash
# From the project root
uv run uvicorn api.index:app --reload
```

2. Start the Next.js development server:
```bash
npm run dev
```

3. Open your browser and navigate to `http://localhost:3000`

The frontend will automatically connect to the backend API running on `http://localhost:8000`.

### Production Build

1. Build the application:
```bash
npm run build
```

2. Start the production server:
```bash
npm start
```

## Configuration

### API URL

By default, the frontend connects to `http://localhost:8000`. To change this, you can:

1. Set the `NEXT_PUBLIC_API_URL` environment variable:
```bash
NEXT_PUBLIC_API_URL=http://your-api-url npm run dev
```

2. Or create a `.env.local` file in the frontend directory:
```
NEXT_PUBLIC_API_URL=http://your-api-url
```

## Features

- **Modern Chat Interface**: Clean, responsive design with smooth animations
- **Real-time Messaging**: Send messages and receive AI responses instantly
- **Auto-scrolling**: Messages automatically scroll to the latest
- **Loading States**: Visual feedback while waiting for responses
- **Error Handling**: Graceful error messages if the backend is unavailable
- **Responsive Design**: Works on desktop and mobile devices

## Project Structure

```
frontend/
├── app/
│   ├── layout.tsx          # Root layout component
│   ├── page.tsx            # Main chat page component
│   ├── page.module.css     # Styles for the chat page
│   └── globals.css         # Global styles
├── package.json            # Dependencies and scripts
├── tsconfig.json           # TypeScript configuration
├── next.config.js          # Next.js configuration
└── README.md              # This file
```

## Troubleshooting

### Backend Connection Issues

If you see an error message about the backend not being available:

1. Verify the backend is running on `http://localhost:8000`
2. Check that the `OPENAI_API_KEY` environment variable is set for the backend
3. Ensure CORS is properly configured (the backend should already have this set up)

### Port Already in Use

If port 3000 is already in use, Next.js will automatically try the next available port (3001, 3002, etc.). Check the terminal output for the actual URL.
