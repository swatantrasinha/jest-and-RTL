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
<p>
    <ins>Lec05_Comp.tsx</ins>
    
```javascript
        const Lec05_Comp = () => {
          return (
            <div>
                <p>First React Test Case</p>
                <img src="https://googlechrome.github.io/samples/picture-element/images/butterfly.webp" title="butterfly" /> 
            </div>
      )
    }

    export default Lec05_Comp      
```    
</p>
<p>
 <ins>Lec05_Comp.test.tsx</ins>
    
```javascript
     
        import { render, screen } from "@testing-library/react"
        import '@testing-library/jest-dom'
        import Lec05_Comp from "./Lec05_Comp"


        test('Test First React App', () => {
            render(<Lec05_Comp />)
            screen.logTestingPlaygroundURL()
            const requiredText = screen.getByText(/First React Test Case/i)
            const imgTitle = screen.getByTitle('butterfly')
            expect(requiredText).toBeInTheDocument()
            expect(imgTitle).toBeInTheDocument()
          })
```
    
</p>
</details>

<details>
    <summary> <ins>Lecture 06: Test Input box </ins> </summary>
    <img width="646" height="543" alt="image" src="https://github.com/user-attachments/assets/d9490e07-455f-4ea4-b018-62c0081317a5" />
    
<p>
    <ins>Lec06_Comp.tsx</ins>
    
```javascript
        const Lec06_Comp = () => {
          return (
            <div>
              <input type='text' placeholder='Enter Username' name='username' id='user-id' />
            </div>
          )
        }

    export default Lec06_Comp
```

<ins>Lec06_Comp.test.tsx</ins>

```javascript
    import { render, screen } from "@testing-library/react"
    import '@testing-library/jest-dom'
    import Lec06_Comp from "./Lec06_Comp"


    test('Test First React App', () => {
        render(<Lec06_Comp />)
        // screen.logTestingPlaygroundURL()
        const checkInput = screen.getByRole('textbox')
        expect(checkInput).toBeInTheDocument()
        const checkInputPlaceholder = screen.getByPlaceholderText('Enter Username')
        expect(checkInputPlaceholder).toBeInTheDocument()
        expect(checkInput).toHaveAttribute('name', 'username')
        expect(checkInput).toHaveAttribute('id', 'user-id')
        expect(checkInput).toHaveAttribute('type', 'text')
      })

```
</p>

</details>    


<details>
    <summary> <ins> Lec 07: Test Case Run Options </ins></summary>
    <img width="646" height="462" alt="image" src="https://github.com/user-attachments/assets/70918507-e9e7-483b-ac2e-6816f79aadf5" />
<p>
        
When we give below command in watch mode :    

> npm test -- --watch

It shows options like   
<img width="374" height="116" alt="image" src="https://github.com/user-attachments/assets/e3d029dd-fe5f-42ef-8f5a-2da223aa6b55" />

</p>

</details>



<details>
    <summary> <ins> Lec 08: Test grouping with describe function </ins></summary>
    <p>
        <img width="638" height="406" alt="image" src="https://github.com/user-attachments/assets/4acc47de-5b66-47c1-a7f6-745b0c8fd9d6" />
    </p>
</details>

