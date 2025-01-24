# Unhandled Promise Rejection in Node.js HTTP Server

This repository demonstrates a common error in Node.js where an unhandled promise rejection within an HTTP request handler causes the server to crash without proper error handling.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides a corrected version.

## Problem

The server uses `asyncOperation` which randomly fails or resolves. If it fails, the `.catch` block is executed, but the error is not handled properly at the server level leading to a crash.

## Solution

The solution involves adding a process event listener to catch unhandled promise rejections and log them gracefully.  This prevents unexpected crashes and allows for better debugging and monitoring.