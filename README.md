# Stale Closure Bug in React useEffect with setInterval

This repository demonstrates a common but subtle bug in React applications involving the use of `setInterval` within a `useEffect` hook.  The bug arises from a stale closure, leading to incorrect updates of state.

## Bug Description
The provided `MyComponent` uses `setInterval` to increment a counter every second.  However, the closure over `count` within the `setInterval` callback is stale. This means that the callback always uses the initial value of `count`, rather than its updated value. As a result, the counter does not increment correctly.

## Bug Solution
The solution involves using the functional update form of `setCount` to ensure that the latest value of `count` is used in each interval.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter; it won't increment properly due to the stale closure.
5. Review `bugSolution.js` to see the corrected code.