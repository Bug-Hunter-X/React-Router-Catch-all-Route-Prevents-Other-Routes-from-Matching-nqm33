# React Router Catch-all Route Bug

This repository demonstrates a common issue with React Router v6's `Routes` component where a catch-all route (`path="*"`) unintentionally overrides more specific routes.  This often occurs when the catch-all route is declared before more specific routes within the `Routes` component.  This leads to only the catch-all route being matched, regardless of the URL.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that navigating to `/about` still shows the 404 page instead of the About component.

## Solution

The solution involves ensuring that the catch-all route is placed *after* all other more specific routes.  By doing this, React Router will correctly match more specific routes first before falling back to the catch-all route when no other route matches.