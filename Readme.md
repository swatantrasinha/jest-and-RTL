# Code Step By Step

## Introduction

This is course for learning how to write testcase using jest and RTL.

<details>
    <summary> <ins>Types of Testing</ins> </summary>
    <img width="944" height="599" alt="image" src="https://github.com/swatantrasinha/jest-and-RTL/blob/main/screenshots/001-type_Of_Testing.png" />
</details>

<details>
    <summary> <ins> Our Focus Area </ins> </summary>
    <img width="944" height="599" alt="image" src="https://github.com/swatantrasinha/jest-and-RTL/blob/main/screenshots/002-Our_Focus_Area.png" />
</details>

<details>
    <summary> <ins>Lecture 03: Write Basic Test Case</ins> </summary>
    <img width="944" height="599" alt="image" src="https://github.com/user-attachments/assets/7c9ba42d-36a7-43c5-9238-c7ed698fd68e" />

Refer to : [jest Docs](https://jestjs.io/docs/api)

<ins>sum.ts</ins>

```javascript
export const sum  = (a:number ,b: number) => a+b
```

<ins>sum.test.ts</ins>
```javascript
import { sum } from "./sum";

test('testing for sum function', () => {
    const input1= 2
    const input2= 3
    const output= 5
    expect(sum(input1, input2)).toBe(output)   
})
```
</details>


<details>
    <summary> <ins>Lecture 04: Understand React Test Structure </ins> </summary>
    <img width="684" height="348" alt="image" src="https://github.com/user-attachments/assets/9fe79f92-f1c1-4169-a3a4-6a6c7e71cf5c" />

    
<ins>App.tsx</ins>

    ```javascript
    function App() {
      return (
        <>
          <h1>Learn React</h1>
          <p>Code Step By Step</p>  
        </>
      )
    }

    export default App
    ```

  <ins>App.test.tsx</ins>

  ```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom';

import App from '../App'

test('renders learn react link', () => {
  render(<App />)
  // screen.logTestingPlaygroundURL()
  const linkElement = screen.getByText(/Learn React/i)
  expect(linkElement).toBeInTheDocument()
})

test('renders learn react link', () => {
  render(<App />)
  // screen.logTestingPlaygroundURL()
  const paraElement = screen.getByText(/Code Step By Step/i)
  expect(paraElement).toBeInTheDocument()
})
```
</details>


<details>
    <summary> <ins>Lecture 05: Write First React Testcase </ins> </summary>
     <img width="681" height="383" alt="image" src="https://github.com/user-attachments/assets/f427770e-6ff8-4608-9732-383c8f0c2227" />
    
    <ins>App.tsx</ins>
    
</details>


