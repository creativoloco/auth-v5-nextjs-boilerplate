# Auth0 v5 boilerplate for nextjs

## Requirements
- Node.js 18.17 or later ( nextjs requirement )
- pnpm ( performand node package manager )

### Libraries
- shadcn/ui ( collection of re-usable components )

## Install nextjs
```bash
pnpm create next-app@latest <project name>
```
After executing the command you should select:
- Typescript: Yes
- EsLint: Yes
- Tailwind CSS: Yes
- `src/` directory: No
- App Router: Yes
- import alias: No

Get into the created folder and open the project with your favorite editor.

## Use shadcn/ui
Add shadcn/ui to your project
```bash
pnpm dlx shadcn-ui@latest init
```
Answer the questions:
- style to use: New York
- base color: Slate
- CSS variables: Yes

Something interesting is that now you have a new folder and new file in `./lib/util.ts` and an exported function named `cn` which we'll be used to dinamically add classes.

### Adding a new component
Add components using the following example
```bash
pnpm dlx shadcn-ui@latest add <button>
```
You should replace `<button>` with any other components listed in the official shadcn/ui website

After excecuting the command you will get a new folder `./ui` inside components folder in the root of your project, and you will get inside the shandcn/ui component you installed before.

This is a different approach than a common component library, because it is not installed in `node_modules`, instead you can edit the component and costumize whenever you want.

## Nextjs structure

The `./app/` folder will have the routes. The file `page.tsx` inside components folder is the home page or entrypoint of our website.

## Routes
Every time you want to create a route you should create a new folder inside `./app/` with the desired route name.

In this example we are going to create the `dashboard` route
Also you should create a file named `page.tsx` to define the entrypoint of this new route.

```bash
mkdir ./app/dashboard
touch ./app/dashboard/page.tsx
```

Inside the `page.tsx` you should export a component using **default** function

```typescript
const DashboardPage = () => {
  return <div>Dashboard page</div>
}

export default DashboardPage
```

### File conventions
In nextJs you should care how are you naming your files and folders. Here I will cover just the basic, but if you are interesting to going deeper, please check the official documentation in nextJs website.

#### Filename conventions
- `page.tsx` is the entrypoint of each route.
- `layout.tsx` sharing component to hold multiple segments 

#### Foldername conventions
- `(routename)` makes this route accesible without writing the route name. It means that you will be able to access sub-routes without writing the parent route. Check nextJs documentation for more details.
- `_routename` ignore completly the contents of the folder. Useful when you have components that you are not going to share.

## Fonts
To use family fonts in next-js you should follow the structure bellow

```typescript
import {Poppins} from "next/font/google"

// configure the font
const font = Poppins({
  subsets: ["latin"],
  weight: ["600"]
})

// use the font
export default function Home() {
  return (
    // if you are using chadcn/ui the cn function will help to combine classes
    <h1 className={ cn("your-classes", font.className) }>
      Home
    </h1>
  )
}
```

***Suggestions***
Every time you want to import a component or file, use the alias "@" to refer the root of the application:

```typescript
import { button } from "@/components/ui/button"
```

