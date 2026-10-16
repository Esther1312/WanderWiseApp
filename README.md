# WanderWise

WanderWise is an interactive web application for smart tourist route planning in cities. It lets users pick attractions on a map and generates an optimized visiting route based on distance and travel time, so they can see as many attractions as possible in a limited amount of time.

The route is computed with a **genetic algorithm**, an approach well suited to the Traveling Salesman Problem (TSP), which is NP-hard. The project was developed as my Bachelor's thesis in Computer Science (2025).

## Features

- **Authentication:** sign up, log in and password reset with Supabase Auth
- **Cities and attractions:** browse available cities and their tourist attractions, loaded from a Supabase (PostgreSQL) database
- **Search:** real-time search for cities and attractions, plus map search with the Mapbox geocoder
- **Interactive map:** select attractions directly on the map (Mapbox GL JS)
- **Route optimization:** a genetic algorithm in TypeScript generates the best order to visit the selected attractions, using distances and travel times from OpenRouteService
- **Route visualization:** the optimized route is shown on the map, with total distance and duration
- **Favorites:** save routes to your account, view them later, delete them or replan them
- **Responsive design:** works on desktop and mobile
- **Error handling and feedback:** error boundary and toast notifications

## How the genetic algorithm works

- **Individual:** one possible route, an ordered list of the selected attractions
- **Fitness function:** evaluates a route by total distance and travel time (shorter is better)
- **Operators:** selection, crossover and mutation evolve the population over multiple generations
- **Result:** the best route found is returned and displayed on the map

The optimizer is implemented in TypeScript (src/genetic/optimizer.ts) and runs client-side in the browser, so routes are generated quickly without a dedicated backend.

## Tech stack

| Area | Technologies |
|---|---|
| Frontend | React 18, TypeScript, Vite, Tailwind CSS, React Router v6, Zustand |
| Backend | Supabase (PostgreSQL, Auth, Row-Level Security) |
| Maps and APIs | Mapbox GL JS, OpenRouteService API, Google Places API |
| Tooling | ESLint, Prettier |

## Getting started

1. Clone the repository:
```bash
   git clone https://github.com/Esther1312/wanderwise.git
   cd wanderwise
```
2. Install dependencies:
```bash
   npm install
```
3. Create a `.env` file in the project root with your own keys (Supabase, Mapbox, OpenRouteService, Google Places). These are not included in the repository.
4. Start the development server:
```bash
   npm run dev
```

## Author

**Estera-Daniela Prioteasa**
Computer Science graduate, University Politehnica of Bucharest
Bachelor's thesis
