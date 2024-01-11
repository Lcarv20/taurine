setup tauri + tailwind + shadcn

1- `bun create tauri-app@latest` cd the folder and install deps
2- `
bun install -D tailwindcss postcss autoprefixer
bunx tailwindcss init -p
`

go to src/styles.css and paste:
`@tailwind base;
@tailwind components;
@tailwind utilities;`


3 - go to tsconfig.json and inside compilerOptions paste:
`"baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }`

after run `bun add -D @types/node`
open tailwind.config.js and add 
`import path from "path"
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
`
4- `bunx --bun shadcn-ui@latest init`
NOTE: don't forget thast the global css is under src/styles.css not index.css

5- try it out `bunx --bun shadcn-ui@latest add button`


