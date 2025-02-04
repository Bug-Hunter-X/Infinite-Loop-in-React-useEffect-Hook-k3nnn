# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug causes an infinite loop due to a missing dependency array, leading to performance issues and potential crashes.

## Bug Description

The `useEffect` hook, when used without a dependency array, runs after every render. If the effect itself causes a re-render (e.g., by modifying state), it creates an infinite loop. This example shows a counter component that increments infinitely because the useEffect has no dependencies, meaning the effect function will run on every re-render, thus causing an infinite loop.

## Solution

The solution involves correctly specifying the dependency array. In this case, the counter should only update when the count variable changes. By adding `[count]` as a dependency, the effect only runs when the value of `count` changes.