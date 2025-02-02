# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  lack of error handling when dealing with user input, specifically, when parsing a user ID.

The `bug.js` file contains the flawed code. The `bugSolution.js` file provides a corrected version.

## Bug
The issue lies in the `/users/:id` route handler. It tries to parse `req.params.id` as an integer, but doesn't handle the case where the ID is not a valid integer, leading to potential crashes or unexpected behavior.

## Solution
The solution improves the code by incorporating error handling. It explicitly checks if `parseInt(userId)` returns `NaN` (Not a Number) and handles this case appropriately, returning a 400 Bad Request error in case of an invalid ID. It also adds a more robust check if the user exists in the `users` array.