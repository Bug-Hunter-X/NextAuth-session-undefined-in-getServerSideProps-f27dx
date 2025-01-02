# NextAuth Session Undefined in getServerSideProps

This repository demonstrates a common issue when using NextAuth.js with getServerSideProps.  The authentication process completes successfully, but the session object remains undefined within the getServerSideProps function.  The client-side rendering correctly receives the session details, highlighting a server-side issue.

## Problem

The `session` object is undefined in `getServerSideProps` of the `/about` page, even though the user is successfully authenticated.  This results in conditional rendering failing server-side, causing a potentially unexpected user experience.

## Solution

The solution involves ensuring the correct import path and the use of `unstable_getServerSession` for server-side session access.  The client-side rendering remains unaffected by this change, maintaining the expected user experience.  Please refer to `aboutSolution.js` for the corrected code.

## Reproduction

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Navigate to `/about` after logging in.  Observe that the session is correctly displayed on the client-side but not on the initial server-side render.  The client-side rendering is updated correctly after fetching.