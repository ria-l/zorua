# Project initialization

Used [Easy & Free Vite Deployment to Firebase [React, TS, Google Cloud]](https://www.youtube.com/watch?v=1MlVEWX8q8c) as a reference

## Installing Vite and React

1. In parent dir, run `npm create vite @latest`
   1. Use React with Typescript
2. cd into created dir
3. `npm install`

## Installing firebase

1. `npm i -g firebase-tools`
2. `firebase login`
3. `firebase init`
   1. select hosting
      - Project information:
      - Project ID: zorua570
      - Project Name: zorua
      - Firebase console is available at https://console.firebase.google.com/project/zorua570/overview
   2. Use dist for public directory
4. `firebase deploy --only hosting` to deploy
   - https://zorua570.web.app/

## Development

View prod site: run `npm run build` and `npm run preview`

Live updates for dev: `npm run dev`

## Github

1. `git init`