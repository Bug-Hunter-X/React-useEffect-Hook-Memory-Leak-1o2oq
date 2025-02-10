# React useEffect Hook Memory Leak

This repository demonstrates a common error in React's `useEffect` hook: an incorrect dependency array that leads to memory leaks. 

The `bug.js` file contains the faulty code. The `useEffect` hook sets up an interval to update the count every second. However, the dependency array is empty (`[]`), meaning the effect runs only once after the component mounts.  Even when the component unmounts, the interval continues to run because it wasn't cleared in the cleanup function.

The `bugSolution.js` file shows the corrected code.  The dependency array includes `count`, ensuring the effect runs only when the count changes and is cleaned up appropriately when the component unmounts.