# PurgeCSS removes important dynamic Tailwind classes

This bug occurs when using dynamic class names generated during runtime that PurgeCSS can't detect. These dynamic classes are often important for application functionality, but PurgeCSS removes them during the build process because they aren't explicitly referenced in the static HTML.

## Bug Description:

The application uses dynamic classes generated at runtime with Tailwind CSS utilities. PurgeCSS removes these classes, causing the application to fail. The problem is that static analysis cannot detect these classes.

## Solution:

The solution implemented below provides a way to tell PurgeCSS which dynamic classes to keep using the `safelist` option. This prevents the removal of essential dynamic classes.

## Steps to Reproduce:

1.  Clone the repository.
2.  Run `npm install`.
3.  Run `npm run build`.
4.  Observe the missing styles in the application.

## Files:

- `bug.js`: Contains the buggy code.
- `bugSolution.js`: Contains the solution code.
