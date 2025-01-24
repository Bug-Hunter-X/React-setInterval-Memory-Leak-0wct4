# React setInterval Memory Leak
This repository demonstrates a common React bug involving memory leaks caused by improper use of the `setInterval` function within the `useEffect` hook. The `bug.js` file contains the buggy code.  The `bugSolution.js` file shows the corrected code.

## Problem
The original `MyComponent` uses `setInterval` to update the count every second. However, it fails to clear the interval when the component unmounts. This leads to a memory leak, as the interval continues to run even after the component is no longer rendered.  This is because the return function in `useEffect` (which is where cleanup happens) is missing.

## Solution
The solution involves using the cleanup function provided by `useEffect` to clear the interval using `clearInterval` before the component unmounts. This prevents the memory leak and ensures that the interval is correctly stopped when it's no longer needed.