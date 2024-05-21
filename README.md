# Auth0 v5 boilerplate for nextjs


## Requirements
- Node.js 18.17 or later ( nextjs requirement )
- pnpm ( performand node package manager )

### Libraries
- shadcn/ui ( collection of re-usable components )

## Install nextjs
´´´bash
pnpm create next-app@latest <project name>
´´´
After executing the command you should select:
- Typescript: Yes
- EsLint: Yes
- Tailwind CSS: Yes
- src/ directory: No
- App Router: Yes
- import alias: No

Get into the created folder and open the project with your favorite editor.

## Use shadcn/ui
Add shadcn/ui to your project
´´´bash
pnpm dlx shadcn-ui@latest init
´´´
Answer the questions:
- style to use: New York
- base color: Slate
- CSS variables: Yes

Something interesting is that now you have a new folder and new file in ./lib/util.ts and an exported function named cn which we'll be used to dinamically add classes

### Adding a new component
Add components using the following example
´´´bash
pnpm dlx shadcn-ui@latest add <button>
´´´
You should replace <button> with any other components listed in the official shadcn/ui website

After excecuting the command you will get a new folder named ui inside components folder in the root of your project, and you will get inside the shandcn/ui component you installed before.

This is a different approach than a common component library, because it is not installed in node_modules, insted you can edit the component and costumize whatever you want.

## Nextjs structure

The app/ folder will have the routes. The file page.tsx inside components folder is the home page or entrypoint of our website.

## Suggestions
Every time you want to import a component or file, use the alias:

´´´typescript
import { button } from "@/components/ui/button"
´´´


