# React useEffect Cleanup Function Not Called on Unmount

This repository demonstrates a common issue with React's `useEffect` hook where the cleanup function isn't called when the component unmounts.  This often happens due to incorrect use of the dependency array or when the component unmounts too quickly for the cleanup to execute.

The `bug.js` file contains the buggy code. The `bugSolution.js` file shows the correct implementation.

## Problem

The `useEffect` hook in `bug.js` includes a cleanup function. However, under certain circumstances (like rapidly switching between components), the cleanup function might not always execute as expected, leading to unexpected behavior or memory leaks. 

## Solution

The `bugSolution.js` file demonstrates the solution: Ensuring that the effect's dependency array correctly reflects the data used within the effect.  This prevents the cleanup function from being called unnecessarily.  In some scenarios, removing the dependency array completely may be necessary.

## Reproduction

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the console output to see if the cleanup function executes reliably during unmounts.