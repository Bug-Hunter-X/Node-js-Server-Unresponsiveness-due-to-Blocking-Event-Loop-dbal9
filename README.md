# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications: blocking the event loop with a long-running synchronous operation.  This leads to the server becoming unresponsive to new requests. The `server.js` file contains the buggy code, and `serverSolution.js` provides a solution using asynchronous operations.

## Problem
The original `server.js` contains a `while` loop that keeps the CPU busy for 5 seconds.  During this time, the event loop is blocked, preventing the server from handling any new incoming requests.  This results in unresponsive behavior and potentially timeouts for clients.

## Solution
The solution in `serverSolution.js` demonstrates the correct way to handle long-running tasks in Node.js: using asynchronous operations or offloading the work to a worker thread or a different process.  This allows the event loop to remain responsive and handle new requests without blocking.