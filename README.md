
# Frontend Mentor - QR code component solution

This is my solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). 

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Setup Guide](#setup-guide)

## Overview
The QR Code Component is a simple webpage for beginners on Frontend Mentors to get started with the platform. My implementation of the project uses tailwindcss initially and later converts it into CSS. 
### Screenshot

![](./src/images/screenshots/desktop%20layout.png)

### Links

- Solution URL: [Github Repository](https://github.com/m6code/qr-code-component)
- Live Site URL: [QR Code Component on gh-pages](https://m6code.github.io/qr-code-component/)

## My process

### Built with

- Tailwindcss 
- CSS custom properties
- Vite
- CSS Grid

### What I learned

### Running Script in Parallel
**Option 1**
Use a package called [concurrently](http://npmjs.org/package/concurrently).
```bash
pnpm i concurrently --save-dev
```

Then setup your `npm run dev` task as so:
```json
"dev": "concurrently --kill-others \"npm run start-watch\" \"npm run wp-server\""
```

- add the following to the package.json file (replace the already dev script there)
```js
"dev": "concurrently --kill-others \"vite\" \"npx tailwindcss -i ./src/css/style.css -o ./dist/output.css --watch\""
```

**Option 2**
Invoke these scripts via npm run and chain them with double ampersand **`&&`**:
```bash
npm run pre-build && npm run build_logic && npm run post_build && npm run exit
```
Explanation
- Use **`&&`** (double ampersand) for sequential execution.
- Use **`&`** (single ampersand) for parallel execution.


### Useful resources
- Kevin Powell Video on Setting Custom Properties - [Here](https://www.youtube.com/watch?v=h3bTwCqX4ns&t=1218s)
  - CSS Resets
    - [Modern CSS Reset / Global Styles](https://www.joshwcomeau.com/css/custom-css-reset)
    - [A Modern CSS Reset - Andy Bell](https://andy-bell.co.uk/a-modern-css-reset)
- Running Multiple Scripts in Parallel - https://stackoverflow.com/questions/30950032/how-can-i-run-multiple-npm-scripts-in-parallel
- Flowbite Cards - [Tailwind CSS Cards - Flowbite](https://flowbite.com/docs/components/card/#horizontal-card)
- Centering a div with tailwind [How to Centre an Element in CSS with Tailwind | HackerNoon](https://hackernoon.com/how-to-centre-an-element-in-css-with-tailwind)
- Deploying vite app gh-pages Manually - https://www.youtube.com/watch?v=yo2bMGnIKE8
- Deploying with workflow on gh-pages - https://www.youtube.com/watch?v=XhoWXhyuW_I   & https://www.youtube.com/watch?v=jBZfo2Mj1mY
- Deploying vite app - https://vitejs.dev/guide/static-deploy.html

## Setup Guide
### Vite
1. run `pnpm create vite` : follow prompt and create vanila js app
2. cd into the project-name you selected above and run `pnpm install`
3. clean up vite defaults and setup project structure as you want
4. run `pnpm dev` to view site
### Tailwind CSS
1. run `pnpm install -D tailwindcss` : to install tailwind css
2. run `npx tailwindcss init` to generate the tailwind configuration file (`tailwind.config.js`)
3. within the configuration file add the following lines (tweak depending on your project structure)
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}" , "./index.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
4. create a `src/css/style.css` file and add the following lines
```css
@tailwind base; 
@tailwind components; 
@tailwind utilities;
```
5. run `npx tailwindcss -i ./src/css/style.css -o ./dist/output.css --watch` and then add
6. add `<link href="/dist/output.css" rel="stylesheet">` to the head of the `index.html` file.