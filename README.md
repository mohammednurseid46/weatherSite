# Weather App

A modern, standardized weather condition app built with React + TypeScript and Express, powered by the OpenWeatherMap API.

## Features

- Current weather with detailed conditions (temperature, wind, humidity, pressure, visibility)
- 24-hour forecast (3-hour intervals)
- 5-day daily forecast
- City search and geolocation support
- Metric / Imperial unit toggle
- Responsive, dark-themed UI
- API key secured on the backend

## Architecture

```
weather-app/
├── server/              # Express API proxy
│   ├── index.ts         # Server entry point
│   ├── routes/          # API route handlers
│   └── services/        # OpenWeatherMap API integration
├── src/                 # React frontend
│   ├── api/             # API client functions
│   ├── components/      # UI components
│   ├── hooks/           # Custom React hooks
│   ├── styles/          # Global styles
│   └── utils/           # Formatting utilities
├── shared/              # Shared TypeScript types
└── .env                 # API key (not committed)
```

## Setup

### Prerequisites

- [Node.js](https://nodejs.org/) 18+
- An [OpenWeatherMap API key](https://openweathermap.org/api) (free tier works)

### Installation

```bash
# Install dependencies
npm install

# Create your environment file
cp .env.example .env
# Edit .env and add your OPENWEATHER_API_KEY
```

### Development

```bash
# Start both frontend and backend in dev mode
npm run dev
```

- Frontend: http://localhost:3000
- Backend API: http://localhost:3001

### Production Build

```bash
npm run build
npm start
```

## API Endpoints

| Endpoint | Params | Description |
|----------|--------|-------------|
| `GET /api/weather/current` | `city` or `lat`+`lon`, `units` | Current weather |
| `GET /api/weather/forecast` | `city` or `lat`+`lon`, `units` | 5-day / 3-hour forecast |

### Units

- `metric` — Celsius, m/s (default)
- `imperial` — Fahrenheit, mph
- `standard` — Kelvin, m/s

## Tech Stack

- **Frontend:** React 18, TypeScript, Vite, CSS Modules
- **Backend:** Express, TypeScript, Axios
- **API:** OpenWeatherMap (v2.5 — Current Weather + 5-Day Forecast)
- **Tooling:** tsx (dev), concurrently
