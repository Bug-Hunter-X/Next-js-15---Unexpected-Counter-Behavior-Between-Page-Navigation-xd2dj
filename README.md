# Next.js 15 - Unexpected Counter Behavior

This repository demonstrates an unexpected behavior in a Next.js 15 application when navigating between pages.  The counter on the `/about` page continues to increment even after leaving and returning to that page.  This issue appears to be related to the `useEffect` cleanup function not properly clearing the interval.

## Bug Report

The `/about` page uses `useEffect` with `setInterval` to increment a counter.  The `return` statement in `useEffect` is intended to clear the interval when the component unmounts.  However, the counter continues to increment, indicating that the interval is not being properly cleared.

## Solution

The solution involves ensuring that the `setInterval` is correctly cleared when the component unmounts, even if the component's state changes.

## Setup

1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm run dev` to start the development server.