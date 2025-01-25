# React Memory Leak: setInterval in useEffect without Cleanup

This repository demonstrates a common React memory leak scenario involving the `setInterval` function within the `useEffect` hook.  Improperly used, `setInterval` can lead to memory leaks by continuing to run even after the component unmounts. This example showcases the bug and its solution. 

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks a cleanup function within the `useEffect` hook to stop the interval when the component unmounts. This results in a persistent interval, consuming resources even after the component is no longer displayed.

## Solution
The `bugSolution.js` file presents the corrected code.  The solution includes a cleanup function within the `useEffect` hook that uses `clearInterval` to stop the interval before the component unmounts, effectively resolving the memory leak.