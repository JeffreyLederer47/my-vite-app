# Absolute Path in React

This is a minimal application I created to test absolute path. This is how the application was created:

```
npm create vite@latest my-vite-app -- --template react-ts
cd my-react-app
npm install
npm run dev
```

The application ran successfully. I then added the directory *components* below src directory.
In the components directory, I created a tsx file *Header.tsx*:

```
const Header = () => {
    return (
        <p style={{fontWeight: 'bold'}}>Hello!</p>
    )
}
export default Header;
```

I then modified vite.config.ts tsconfig.json, tsconfig.node.json and tsconfig.app.json files to support absolute paths. (See code in this repository.)


When I use absolute path:
```
import Header from '@components/Header.tsx';
```

It ran *npm run build* and the build was successful. The secret (could not find it documented anywhere) is add CompilerOptions paths to tsconfig.node.json and tsconfig.app.json as well as tsconfig.json.

I am running this on a Windows 11 computer, latest version of Nodejs and npm installed.



