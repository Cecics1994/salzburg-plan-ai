# Salzburg Card Explorer: AI Trip Planner

A mobile-first web app for planning a trip to Salzburg, Austria: discover attractions, build an itinerary (step-by-step or by describing your trip in plain language), and buy the Salzburg Card.

**Live demo:** https://salzburg-plan-ai.pages.dev <!-- TODO: replace with your Cloudflare Pages URL -->

> Best viewed on a phone, or with your browser's mobile device emulation (the layout is capped at 480px).

<!-- TODO: add 2–3 screenshots, e.g. docs/home.png, docs/plan.png, docs/place.png -->

## Features

- **Attraction discovery**: browse Salzburg sights with descriptions, prices, opening hours and accessibility info
- **Trip planning wizard**: guided flow for building an itinerary
- **Chat mode**: describe your ideal trip in natural language and get a personalized plan
- **Salzburg Card purchase flow**: card info, selection and checkout screens
- **Maps**: Google Maps integration for locating places

## Tech stack

React 18 · TypeScript · Vite · Tailwind CSS · shadcn/ui · React Router · TanStack Query · React Hook Form + Zod · Google Maps (`@vis.gl/react-google-maps`)

AI backend design: an [n8n](https://n8n.io) workflow (`n8n-convoluted.json`) that takes a trip request via webhook, gathers data through HTTP requests, and returns a generated itinerary.

## My role

<!-- TODO: describe your contribution, e.g. product idea, UX flows, AI/n8n workflow, specific pages -->

This was a team project, originally developed at [momenator/salzburg-plan-ai](https://github.com/momenator/salzburg-plan-ai). This fork is my maintained copy with a fixed, publicly hosted deployment.

## Project status

This is a prototype. The frontend is complete and static. In the deployed demo, chat mode simulates the AI response; it is not connected to the n8n workflow.

## Running locally

```sh
npm ci
npm run dev        # http://localhost:8080
npm run build      # production build in dist/
```

Optional: create `.env.local` with `VITE_GOOGLE_MAPS_API_KEY=<your key>` to enable maps.

## Deployment

Hosted on Cloudflare Pages: build command `npm run build`, output directory `dist`, environment variable `VITE_GOOGLE_MAPS_API_KEY`. Client-side routes (e.g. `/place/mirabell`) work out of the box because Pages serves `index.html` for unknown paths when no `404.html` is present.
