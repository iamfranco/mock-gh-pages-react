# Deploy a React Vite site to Github Pages

Open `vite.config.js` and add `base: "/<repo>/",`, so for example:
```ts
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  base: 'mock-gh-pages-react', // <--
  plugins: [react()],
})
```

Install `gh-pages` by
```
npm install gh-pages --save-dev
```

Add to `package.json`
```json
"homepage": "https://<username>.github.io/<repo>/",
...
"scripts": {
   ...
      "predeploy": "npm run build",
      "deploy": "gh-pages -d dist",
   ...
}
```

and then whenever we want to deploy to GitHub Pages, run the command:
```
npm run deploy
```

so that it'll be deployed to a new branch `gh-pages`.