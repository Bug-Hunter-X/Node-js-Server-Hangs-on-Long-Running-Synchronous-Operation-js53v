# Node.js Server Hang

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler can cause the server to hang. The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version that uses asynchronous operations to prevent blocking.

## Problem

The original code performs a 5-second synchronous `while` loop within the request handler. During this time, the event loop is blocked, preventing the server from responding to other requests or handling events such as closing the connection.  This results in a hung server and unresponsive application.

## Solution

The solution utilizes asynchronous operations (using `setTimeout` to simulate an asynchronous task) to avoid blocking the event loop. This allows the server to continue processing other requests while the long-running task is executed.