# React 18 useEffect Hook Dependency Issue

This repository demonstrates a common issue encountered when using the `useEffect` hook in React 18 and later versions.  The problem arises from incorrectly specifying dependencies in the `useEffect` hook, leading to unexpected behavior or stale closures.

## Problem Description
The `bug.js` file contains a component that increments a counter. The `useEffect` hook is intended to log the current value of the counter to the console after each update. However, due to a missing dependency, the `useEffect` hook only runs once during initial render. This is because the `useEffect` hook closure captures the initial `count` value (0), and it doesn't update when `count` changes.

## Solution
The `bugSolution.js` file shows the corrected code where the `count` variable is added to the dependency array of the `useEffect` hook.  This ensures that the effect re-runs whenever the `count` value changes, which fixes the stale closure issue.