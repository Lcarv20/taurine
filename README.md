setup tauri + tailwind + shadcn

1- 
```
bun create tauri-app@latest
``` 
and  cd the folder and install deps

2- add tailwindcss
```
bun install -D tailwindcss postcss autoprefixer
bunx tailwindcss init -p
```


go to src/styles.css and paste:
`@tailwind base;
@tailwind components;
@tailwind utilities;`


3 - go to tsconfig.json and inside `compilerOptions` paste:
```
"baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }
```

4- after run 
```
bun add -D @types/node
```

5- open `tailwind.config.js` and add 
```
import path from "path"
...

import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"
 
export default defineConfig({
  plugins: [react()],
  ...
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
})
```

5- init shadcn
```
bunx --bun shadcn-ui@latest init
```
NOTE: don't forget that the global css is under src/styles.css not src/index.css

6- try it out `bunx --bun shadcn-ui@latest add button`


