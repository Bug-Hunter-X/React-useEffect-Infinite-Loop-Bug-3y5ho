# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving the `useEffect` hook.  The example shows an infinite loop caused by a missing dependency in the `useEffect` hook's dependency array.

## Bug Description
The `useEffect` hook, when used without a dependency array, runs after every render. If the effect modifies state or props, it creates an infinite re-render loop. This is because each render triggers the effect, which then updates the state, causing another render, and so on.

## Bug Reproduction
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console log and the infinite loop.

## Solution
The solution is to add the relevant state variables to the dependency array. In this case, adding `count` ensures the effect only runs when the `count` value changes.