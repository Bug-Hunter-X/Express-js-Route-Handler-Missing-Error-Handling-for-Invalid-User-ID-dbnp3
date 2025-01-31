# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, this example shows a route that fetches a user by ID but fails to handle cases where the ID is not a valid number. This can lead to crashes or unexpected responses.

## Bug

The `bug.js` file contains the erroneous code. It attempts to parse the user ID from the request parameters as an integer without validating whether the parameter is actually a number. If the `userId` is not a number (e.g., if it's a string), `parseInt(userId)` will return `NaN`, causing unexpected behavior and a potential crash.

## Solution

The `bugSolution.js` file provides a corrected version of the code. It includes explicit error handling to check if the `userId` is a valid number. If it's not, a 400 Bad Request response is sent to the client.  If the ID is valid but no user is found, a 404 Not Found response is sent.