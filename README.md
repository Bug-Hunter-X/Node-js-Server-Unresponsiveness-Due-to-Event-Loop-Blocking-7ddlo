# Node.js Server Unresponsiveness Due to Event Loop Blocking

This repository demonstrates a common issue in Node.js where the event loop gets blocked, causing the server to become unresponsive. The issue is reproduced by simulating a long-running operation that blocks the event loop.

## Problem

The `bug.js` file contains a simple HTTP server that simulates a 5-second delay in processing each request.  When many requests are made concurrently, the event loop becomes blocked, leading to performance degradation and unresponsiveness.  This is because Node.js is single-threaded, and a long-running operation on the main thread prevents it from handling other events.

## Solution

The `bugSolution.js` file demonstrates a solution using asynchronous operations with `setTimeout` to prevent blocking the event loop. The use of `setTimeout` here ensures that the long operation does not block the event loop, allowing the server to remain responsive even under heavy load. 

## How to Run

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `node bug.js` to observe the blocking behavior.  Try sending multiple requests concurrently using tools like `curl` or a browser.
4. Run `node bugSolution.js` to observe the improved responsiveness.

This example highlights the importance of using asynchronous programming techniques in Node.js to prevent the event loop from blocking and maintain server responsiveness.