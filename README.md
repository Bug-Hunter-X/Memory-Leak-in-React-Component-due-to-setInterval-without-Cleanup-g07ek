# React setInterval Memory Leak

This example demonstrates a common error in React components: using `setInterval` within the `useEffect` hook without proper cleanup. This can lead to memory leaks and unexpected behavior.

## Bug

The `MyComponent` uses `setInterval` to update the `count` every second. However, it does not return a cleanup function from the `useEffect` hook. This means that when the component unmounts, the `setInterval` continues to run, leading to a memory leak.

## Solution

The solution involves returning a cleanup function from `useEffect`, which clears the interval when the component unmounts.