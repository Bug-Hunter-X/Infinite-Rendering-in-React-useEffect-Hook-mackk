# Infinite Rendering in React useEffect Hook

This repository demonstrates a common React bug: infinite rendering caused by a missing dependency array in the `useEffect` hook.  The `useEffect` hook, without a dependency array, will re-run after every render, creating an infinite loop. This example shows how to correctly use the dependency array to fix the issue.

## Bug Description

The provided `MyComponent` uses `useEffect` without a dependency array, causing it to re-render continuously. This is because the effect is executed after every render, triggering another re-render, resulting in an infinite loop and a potential crash.

## Solution

The solution involves adding a dependency array to `useEffect`.  The array should list all values that the effect's logic depends upon.  In this case, the `count` state variable is the only dependency. By only re-running the effect when `count` changes, infinite rendering is prevented.