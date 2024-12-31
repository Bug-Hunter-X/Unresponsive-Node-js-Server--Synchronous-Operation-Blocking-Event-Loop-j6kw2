# Unresponsive Node.js Server: Synchronous Operation Blocking Event Loop

This repository demonstrates a common Node.js issue: an unresponsive server caused by a long-running synchronous operation within the request handler.  The event loop is blocked, preventing the server from responding to other requests.

## Problem

The `server.js` file contains a simple HTTP server. However, the request handler includes a `while` loop that simulates a 5-second delay.  During this time, the server becomes completely unresponsive to new requests.

## Solution

The `server-fixed.js` file demonstrates how to resolve this issue.  Asynchronous operations (like `setTimeout`) are used to prevent blocking the event loop.  This allows the server to remain responsive, even during long-running tasks.