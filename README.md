# Absolute Path in React

This is a minimal application I created to test absolute path. This is how the application was created:

```
npm create vite@latest my-vite-app -- --template react-ts
cd my-react-app
npm install
npm run dev
```

The application ran successfully. I then added the diretory *components* below src directory.
In the components directory, I created a tsx file *Header.tsx*:

```
const Header = () => {
    return (
        <p style={{fontWeight: 'bold'}}>Hello!</p>
    )
}
export default Header;
```
When I import the file into App.tsx using:
```
import Header from './components/Header.tsx';
```

I then modified vite.config.ts and tsconfig.json files to support absolute paths. (See code in this repository.)

I ran *npm run build* and the build was successful.

When I use absolute path:
```
import Header from '@components/Header.tsx';
```
I get the following error when I build using absolute path:
```
src/App.tsx:5:20 - error TS2307: Cannot find module '@components/Header.tsx' or its corresponding type declarations.
```
The application runs correctly with both relative paths and absolute paths (*npm run dev*)

I am not sure what is the issue.

I followed the code in this [web site](https://medium.com/@rimonamdadul301/steps-to-set-up-absolute-paths-in-a-react-project-3389a9b49c2b "Guide to absolute paths in React").

