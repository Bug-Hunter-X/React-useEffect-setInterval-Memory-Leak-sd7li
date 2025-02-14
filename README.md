# React useEffect setInterval Memory Leak
This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook without proper cleanup. This leads to memory leaks and unexpected behavior.

## Bug Description
The `MyComponent` component uses `setInterval` to update a counter every second.  However, it fails to include a cleanup function in the `useEffect` hook. This means that every time the component renders (even if unmounted), a new `setInterval` is created, resulting in multiple timers running simultaneously and eventually causing memory leaks.

## Solution
The solution involves using the return value of `useEffect` to provide a cleanup function that will clear the `setInterval` when the component unmounts or when the dependencies change. 