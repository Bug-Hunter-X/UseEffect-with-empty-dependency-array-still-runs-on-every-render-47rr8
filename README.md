# React 19 useEffect Bug

This repository demonstrates a peculiar bug encountered in React 19 where a `useEffect` hook with an empty dependency array still re-runs on every render. This contradicts the expected behavior, causing unnecessary re-renders and potential performance issues.

## Bug Description

The `useEffect` hook, intended to run only once after the initial render, unexpectedly runs on every subsequent render even with an empty dependency array (`[]`). This results in the console log message appearing on each render, indicating the effect is not correctly optimizing.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the console output, and notice that the 'Effect running!' message appears on every click, indicating the effect re-runs on every render.

## Solution

The solution involves refactoring the `useEffect` hook to use functional updates to prevent unnecessary re-renders. By ensuring that the state update relies only on the previous state, re-renders are correctly optimized by React's internal mechanisms.

## Additional Notes

This unexpected behavior in React 19 highlights the potential intricacies involved when using `useEffect`.  Always ensure your dependencies are accurately specified and consider using functional updates for state modifications within `useEffect` to minimize unwanted re-renders.