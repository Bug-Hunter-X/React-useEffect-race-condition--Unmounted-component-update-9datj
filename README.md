# React useEffect Race Condition: Unmounted Component Update

This repository demonstrates a common issue in React applications involving the `useEffect` hook and race conditions.  The problem arises when a component unmounts before an asynchronous operation (like a data fetch) inside `useEffect` completes. This leads to attempts to update the state of an unmounted component, resulting in errors.

## Problem
The `bug.js` file contains a React component that fetches data using `useEffect`.  If the component is unmounted before the fetch completes, an error occurs because the component tries to update its state after it has been removed from the DOM.

## Solution
The `bugSolution.js` file provides a solution using the `AbortController` to cleanly cancel the request if the component unmounts.  This prevents unnecessary updates and potential errors.

## How to reproduce
1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the behavior of the component.  Try navigating away from the component before the data fetch completes.