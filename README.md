# Create npm package

```bash
code ~/.npmrc

mkdir github-package-demo

cd github-package-demo

npm init -y

code .

```

## Simple Create file index.js past this simple code

```js
module.exports = function () {
  console.log('Hello from GitHub Package Registry!')
}
```

## create .npmrc file in your package

```bash
touch npmrc

```

## when u create npmrc file in file paste this like i do in my package

```bash
@imran-baitham:registry=https://npm.pkg.github.com
```

## Add this code in package.json file

```json
 "repository": {
    "url": "git://github.com/imran-baitham/github-package-demo.git" // package name
  }
```

## Push the code to Github and publish your package

```bash
npm publish
```

create react app like i do and also connect the github package using npmrc create .npmrc file

```bash
@imran-baitham:registry=https://npm.pkg.github.com // replace this with your package
```

## install package in your project

```bash
yarn add @imran-baitham/github-package-demo
```

## use your package

```js
import logo from './logo.svg'
import './App.css'
import greeting from '@imran-baitham/github-package-demo'

greeting()
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  )
}

export default App
```
