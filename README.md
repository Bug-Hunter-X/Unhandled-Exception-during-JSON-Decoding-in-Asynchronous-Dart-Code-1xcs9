# Unhandled Exception during JSON Decoding in Asynchronous Dart Code

This repository demonstrates a common error in Dart asynchronous programming:  failure to handle exceptions that might occur during JSON decoding after a successful API call. The `bug.dart` file showcases the problematic code, while `bugSolution.dart` provides a corrected version.

## Problem

The original code uses a `try-catch` block to handle network errors. However, it neglects the possibility of exceptions arising from `jsonDecode` if the API response is not valid JSON.  This leads to a runtime error if the API response is malformed.

## Solution

The solution involves adding another `try-catch` block within the `if (response.statusCode == 200)` section to handle potential `FormatException` exceptions from `jsonDecode`. This ensures that the application gracefully handles both network errors and JSON parsing errors.

## How to Run

1. Clone this repository.
2. Run `dart bug.dart` to see the original error.
3. Run `dart bugSolution.dart` to see the corrected code in action.