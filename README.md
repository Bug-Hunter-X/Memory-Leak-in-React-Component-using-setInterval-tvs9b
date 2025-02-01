# React setInterval Memory Leak

This repository demonstrates a common mistake when using the `setInterval` function within a React component's `useEffect` hook, leading to a memory leak. The solution showcases the correct usage with a cleanup function to avoid memory leaks.

## Bug
The original `MyComponent` uses `setInterval` to update the counter every second. However, it lacks a cleanup function in the `useEffect` hook. This means that whenever the component unmounts, the interval continues to run in the background, leading to unnecessary resource consumption and potential memory leaks.

## Solution
The solution demonstrates the correct approach by using the return value of `useEffect` to implement a cleanup function. This function is called when the component unmounts or when the effect dependencies change, ensuring that the `setInterval` is cleared.