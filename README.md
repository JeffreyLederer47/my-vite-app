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
I ran *npm run build* and the build was successful.

I modified vite.config.ts and tsconfig.json files to support absolute paths. (See code in this repository.)
When I use absolute path:
```
import Header from '@components/Header.tsx';
```
I get the following error:
```
src/App.tsx:5:20 - error TS2307: Cannot find module '@components/Header.tsx' or its corresponding type declarations.
```

I am not sure what is the issue

