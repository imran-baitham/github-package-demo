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

```jsx
'use client'

import React, { useState, useEffect } from 'react'

const Product = () => {
  const [currentDate, setCurrentDate] = useState(new Date())

  useEffect(() => {
    const timer = setInterval(() => {
      setCurrentDate(new Date())
    }, 1000) // Update every second

    return () => {
      clearInterval(timer) // Cleanup the interval on component unmount
    }
  }, []) // Empty dependency array

  console.log(currentDate)
  const currentYear = currentDate.getFullYear()
  const currentMonth = currentDate.getMonth()
  const startYear = 2000
  const years: number[] = []
  const months: string[] = [
    'January',
    'February',
    'March',
    'April',
    'May',
    'June',
    'July',
    'August',
    'September',
    'October',
    'November',
    'December',
  ]

  for (let year = currentYear; year >= startYear; year--) {
    years.push(year)
  }

  const currentYearIndex = years.findIndex((year) => year === currentYear)

  return (
    <main className="wrapper_container wrapper grid grid-cols-4 gap-y-10">
      {years.map((year, index) => (
        <div key={year}>
          <h3 className="text-[#4d6172] font-[700] text-[26px]">{year}</h3>
          <ul>
            {months
              .slice(
                index === currentYearIndex ? 0 : 0,
                index === currentYearIndex ? currentMonth + 1 : months.length,
              )
              .map((month, monthIndex) => (
                <li key={month} className="text-[#f37056] pb-3 text-sm">
                  {index === currentYearIndex && monthIndex === currentMonth ? (
                    <strong>{month}</strong>
                  ) : (
                    month
                  )}
                </li>
              ))}
          </ul>
        </div>
      ))}
    </main>
  )
}

export default Product

```
