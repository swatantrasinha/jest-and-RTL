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
    
<ins>How to group test cases ?</ins>   

<img width="725" height="644" alt="image" src="https://github.com/user-attachments/assets/f0767c89-4872-4c66-bfd3-0eb6213c0060" />

<in>Note: </ins> 

- decribe.only --> will only runs the test cases inside this describe   

- decribe.skip --> will skip all the test cases inside this describe
  
- nested describe --> if test cases inside a describe grouping is too much we can group them with nested describe 

</p>
</details>


<details>
<summary> <ins> Lec 09: Test on change event | event fire </ins></summary>
<p>   
<img width="640" height="366" alt="image" src="https://github.com/user-attachments/assets/a2ddae13-f1e3-4797-99af-82a9fa2fdef7" />   

<ins>Lec09_Comp.tsx</ins>

```javascript
import { useState } from 'react'

const Lec09_Comp = () => {
    const [data, setData] = useState("")
  return (
    <div>
        <h1>Test onChange Event with Input Textbox</h1>
        <div>
            <input type="text" value={data} onChange={(e) => setData(e?.target?.value)} />
        </div>
    </div>
  )
}
export default Lec09_Comp
```

<ins>Lec09_Comp.test.tsx</ins>

```javascript
import {fireEvent, render, screen} from '@testing-library/react'
import Lec09_Comp from "./Lec09_Comp";


test('onChange event testing', () => {
    render(<Lec09_Comp/>)
    const input:HTMLInputElement= screen.getByRole('textbox')
    fireEvent.change(input, {target:{value:'abc'}})
    expect(input?.value).toBe('abc')
})
```

</p>
</details>


<details>
<summary> <ins> Lec 10: Click event test case with button | event fire </ins></summary>
<p> 
<img width="646" height="357" alt="image" src="https://github.com/user-attachments/assets/b9fe95d4-4117-44bc-9d53-47a25e963ca4" />

<ins>Lec10_Comp.tsx</ins>
```javascript
import { useState } from 'react'

const Lec10_Comp = () => {
    const [data, setdata] = useState("")
  return (
    <div>
        <h1>Test click Event with Button</h1>
        <div>
            <button onClick={() => setdata('updated data')}>Update Data</button>
        </div>
        {data && (<h2>{data}</h2>)}
    </div>
  )
}
export default Lec10_Comp
```

<ins>Lec10_Comp.test.tsx</ins>
```javascript
import { fireEvent, render, screen } from "@testing-library/react"
import '@testing-library/jest-dom'
import Lec10_Comp from "./Lec10_Comp"


test('click event testing', () => {
    render(<Lec10_Comp />)
    const btn= screen.getByRole('button')
    fireEvent.click(btn)
    expect(screen.getByText('updated data')).toBeInTheDocument()
})
```

</p>
</details>

<details>
<summary> <ins> Lec 11: File and Folder naming convention </ins></summary>
<p> 
<img width="891" height="590" alt="image" src="https://github.com/user-attachments/assets/f3b7374b-66da-4477-9e3b-dac9e75f1c56" />
</p>
    
1. Below file name syntax are also considered testcase file:      
<img width="275" height="131" alt="image" src="https://github.com/user-attachments/assets/2d36f746-5c8a-415c-abb6-1f4fd1dd7658" />

2. if we create a folder with name  "__tests__", then all files within this folder will be considered as testcase file even if its only .js (need not to be .test or .spec )
  
</details>


<details>
<summary> <ins> Lec 12: beforeEach | beforeAll | afterAll | afterEach hooks </ins></summary>
<p> 
<img width="890" height="438" alt="image" src="https://github.com/user-attachments/assets/5fe13a36-2af2-407e-8b8d-f866f3f2012c" />
    
<ins> Note:</ins> Generally used for DB clean, environment setup, variables reset etc   


- beforeAll: executed once before execution of all the testcases
     
- beforeEach: executed each time before exection of every testcase
  
- afterAll: executed once after exection all the testcases
  
- afterEach: executed each time after exection of every testcase   
    
</p>
</details>

<details>
<summary> <ins> Lec 13: Snapshot Testing | update Snapshots </ins></summary>
<p> 
<img width="835" height="544" alt="image" src="https://github.com/user-attachments/assets/01360122-b305-4e66-9b20-ac540cff96cf" />   

```javascript
import App from "../App";
import { render } from "@testing-library/react";

test('snapshot for App component', () => {
    const container = render(<App />)
    expect(container).toMatchSnapshot()
})
```

when we run above test case file   

> yarn run test Lec12_Comp.test.tsx   


It will show in terminal that - 1 snapshot is created as below:   

<img width="618" height="241" alt="image" src="https://github.com/user-attachments/assets/3a119c0a-df42-4d93-8c91-90c7f03b0077" />   


In App.tsx if we change something say :   

~Learn React JS</h1>~   
to below:   

Learn React JS with typescript   

and then again run test case :    

> yarn run test Lec12_Comp.test.tsx   


It will show that test case is failed as there is snapshot mismatch   

<img width="750" height="572" alt="image" src="https://github.com/user-attachments/assets/633ec65a-f1d8-4c06-90f3-cf46b9bc20d6" />

 Also,it will ask to update the snapshot using   
> yarn test -u   

If we give this command and run test case again it will pass   

</p>
</details>

<details>
<summary> <ins> Lec 14: Important points | What we should test </ins></summary>
<p>
   
   <img width="764" height="336" alt="image" src="https://github.com/user-attachments/assets/8ae1b971-586f-4ef7-87f8-4cdcaeb3e590" />      
   <hr />

   <img width="774" height="471" alt="image" src="https://github.com/user-attachments/assets/a8347168-f4a8-4a1e-8b13-bc07ed308c20" />   
   <hr />

  <img width="841" height="319" alt="image" src="https://github.com/user-attachments/assets/fa5d0167-75d5-45d5-954f-0faf7e18bcfc" />
   <hr />

   <img width="770" height="281" alt="image" src="https://github.com/user-attachments/assets/0d853c3b-9cff-4ca8-b8ca-dab9ae4755ee" />
   <hr />
    

</p>
</details>


<details>
<summary> <ins> Lec 15: Class Component Method Testing </ins></summary>
<p> 
<img width="826" height="318" alt="image" src="https://github.com/user-attachments/assets/1a4a99f8-d4b3-4c3e-8fed-9609d836f0bd" />
<hr />
</p>
</details>


<details>
<summary> <ins> Lec 16: Functional Component method testing </ins></summary>
<p> 
<img width="826" height="318" alt="image" src="https://github.com/user-attachments/assets/9d4c2f04-545f-404e-a4c4-a84a3b065798" />
<hr />

<ins>Lec16_Comp.tsx</ins>

```javascript
import { useState } from 'react'
import handleOtherMethod from './helper_lec16'

const Lec16_Comp = () => {
    const [data, setData] = useState("")

    const handleTestData = () => {
        setData('hello')
    }

  return (
    <div>
        <h1> Functional Component Method Testing</h1>
        <button data-testid="btn1" onClick={handleTestData}>Update</button>
        <button onClick={handleOtherMethod}>Print</button>
        <h2>{data}</h2>
    </div>
  )
}

export default Lec16_Comp
```
<ins>helper_lec16.ts</ins>

```javascript
const handleOtherMethod = () => {
    return "hi"
}
export default handleOtherMethod;
```

<hr/>

<ins>Lec16_Comp.test.tsx</ins>

```javascript
import {fireEvent, render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec16_Comp from './Lec16_Comp'
import handleOtherMethod from './helper_lec16'

test('method testing case 1', () => {
    render(<Lec16_Comp />)
    const btn = screen.getByTestId('btn1')
    fireEvent.click(btn)
    expect(screen.getByText('hello')).toBeInTheDocument()
})

test('method testing case 2', () => {
    expect(handleOtherMethod()).toMatch("hi")
})
```

<hr/>

Note:   
1. Here, method handleTestData is making changes in UI/DOM so method with "testing case 1" we checked its functionality.
2. However, method handleOtherMethod is not causing any change in UI/DOM. So we have put it outside the React component becuase if its inside the React component we cant test it indedpendently
   (We coudl have done it by putting in component if it was React class-based component. Because for class based component we can call the method using instance).
</p>
</details>

<details>
<summary> <ins> Lec 17: RTL Query </ins></summary>
<p> 
<img width="822" height="357" alt="image" src="https://github.com/user-attachments/assets/afb03d5e-8439-40c6-af53-81df7f4fd334" />
<hr/>
<img width="822" height="278" alt="image" src="https://github.com/user-attachments/assets/3c0b1094-7b37-411d-9bf8-70696b315c96" />
<hr/>
<img width="822" height="287" alt="image" src="https://github.com/user-attachments/assets/87468576-af16-404d-8687-89d88924f9ed" />
<hr />
<img width="822" height="391" alt="image" src="https://github.com/user-attachments/assets/ccd9f1a6-8996-47ae-8fe9-f1db32d0b856" />
<hr/>
</p>
</details>

<details>
<summary> <ins> Lec 18: getByRole Query </ins></summary>
<p> 
<img width="824" height="471" alt="image" src="https://github.com/user-attachments/assets/ebd9ffbf-2281-4bc8-840f-dbffd90d02a3" />
<hr />
<ins>Note:</ins> semantic tags have defined roles   

e.g For textbox --> screen.getByRole('textbox')

</p>
</details>

<details>
<summary> <ins> Lec 19: Multiple elements and Custom Role </ins></summary>
<p>
<img width="873" height="393" alt="image" src="https://github.com/user-attachments/assets/813a01f0-ac69-418e-a24c-379c517a0543" />
<hr />

<ins> Lec19_Comp.tsx </ins>
```javascript

const Lec19_Comp = () => {
  return (
    <div>
       <h1>RTL Query: getByRole - Multiple Item with Role</h1>
      <h2>Custom Role</h2>
      <button>Click 1</button>
      <button>Click 2</button>
      
      <label htmlFor='input1'>User Name</label>
      <input type='text' id='input1' />

       <label htmlFor='input2'>User Age</label>
      <input type='text' id='input2' />
      
    </div>
  )
}

export default Lec19_Comp
```

<ins> Lec19_Comp.test.tsx </ins>
```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec19_Comp from './Lec19_Comp'


 test('getByRole testing  ', () => {
    render(<Lec19_Comp />)
    const btn1= screen.getByRole("button", {name: "Click 1"})
    const btn2= screen.getByRole("button", {name: "Click 2"})

    const input1= screen.getByRole("textbox", {name: "User Name"})
    const input2= screen.getByRole("textbox", {name: "User Age"})

    expect(btn1).toBeInTheDocument()
    expect(btn2).toBeInTheDocument()
    expect(input1).toBeInTheDocument()
    expect(input2).toBeInTheDocument()
 })
```
In the above code, there are multiple buttons and textboxes so we did .getByRole and then filtered by name attribute
This is working as button and textbox are semantic elements.   

However if we try for non-semantic like div       

```javascript
 <div>dummy text</div>
```
and in testcase file    
```javascript
 const dv1= screen.getByRole("div")
 expect(dv1).toBeInTheDocument()

```

This will throw error like below:     

❌ **Error:** TestingLibraryElementError: Unable to find an accessible element with the role "div"   

We can correct this by using **custom role**   


```javascript
// <div>dummy text</div>
<div role='dummy'>dummy text</div>
```

And in the test-case file   

```javascript
 // const dv1= screen.getByRole("div")
const dv1= screen.getByRole("dummy")
expect(dv1).toBeInTheDocument()
```

</p>
</details>

<details>
<summary> <ins> Lec 20: getAllByRole </ins></summary>
<p>
<img width="873" height="347" alt="image" src="https://github.com/user-attachments/assets/c3f029b3-2acf-40cd-bccb-f42cbad26bb9" />
<hr />
For multiple elements --> we saw in Lec19 how we can use attributes like name to filter element with same role.    
    
But how to handle when the attribute(say name) attribute is also same ?   

Here, we can use **getAllByRole**   

<ins>Lec20_Comp.tsx</ins>
```javascript
const Lec20_Comp = () => {
  return (
    <div>
        <h1>RTL Query:  getAllByRole</h1>
        <div className="btns-conatiner">
            <button>Click Me</button>
            <button>Click Me</button>
            <button>Click Me</button>
        </div>

        <div className="dropdown-container">
            <option>1</option>
            <option>2</option>
            <option>3</option>
            <option>4</option>
            <option>5</option>
        </div>
 
    </div>
  )
}

export default Lec20_Comp
```

<ins>Lec20_Comp.test.tsx</ins>
```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec20_Comp from './Lec20_Comp'


 test('getByRole testing  ', () => {
    render(<Lec20_Comp />)
    const btns = screen.getAllByRole('button')

    for(let i=0; i<btns.length; i++){
        expect(btns[i]).toBeInTheDocument()
    }

    const options= screen.getAllByRole('option')
    for(let i=0; i<options.length; i++){
        expect(options[i]).toBeInTheDocument()
    }
 })
```

</p>
</details>

<details>
<summary> <ins> Lec 21: getByLabelText - textbox and checkbox testing with get by label text </ins></summary>
<p>
<img width="827" height="337" alt="image" src="https://github.com/user-attachments/assets/359ea71e-0ab4-4fa6-8922-1e76e8f38e64" />   

<ins>Lec21_Comp.tsx</ins>

```javascript
const Lec21_Comp = () => {
  return (
    <div>
         <h1>RTL Query : getByLabelText - textbox and checkbox testing </h1>

         <div className='textbox-container'>
            <label htmlFor='user-name'>Username</label>
            <input type='text' id='user-name' defaultValue={`abc`} />
         </div>

          <div className='checkbox-container'>
            <label htmlFor='skills'>Skills</label>
            <input type='checkbox' id='skills' defaultChecked={true} />
         </div>
      
    </div>
  )
}

export default Lec21_Comp
```

<ins>Lec21_Comp.test.tsx</ins>

```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec21_Comp from './Lec21_Comp'


 test('textbox getByLabelText', () => {
    render(<Lec21_Comp />)
    const input = screen.getByLabelText('Username')
    expect(input).toBeInTheDocument()    
    expect(input).toHaveValue('abc')    
 })


  test('checkbox getByLabelText', () => {
    render(<Lec21_Comp />)
    const checkbox = screen.getByLabelText('Skills')
    expect(checkbox).toBeInTheDocument()    
    expect(checkbox).toBeChecked()   
 })
```

</p>
</details>

<details>
<summary> <ins> Lec 22: getAllByLabelText with multiple elements </ins></summary>
<p>
<img width="827" height="337" alt="image" src="https://github.com/user-attachments/assets/05d313ff-d474-464c-bd9a-20f1dd2d14d5" />   

<ins>Lec22_Comp.tsx</ins>

```javascript
const Lec22_Comp = () => {
  return (
    <div>
          <h1>RTL Query : getAllByLabelText</h1>
         <div className="textboxes-container">
             <div className='textbox-container1'>
                <label htmlFor='user-name1'>Username</label>
                <input type='text' id='user-name1' defaultValue={`aaa`} />
            </div>

            <div className='textbox-container2'>
                <label htmlFor='user-name2'>Username</label>
                <input type='text' id='user-name2' defaultValue={`bbb`} />
            </div>

            <div className='textbox-container3'>
                <label htmlFor='user-name3'>Username</label>
                <input type='text' id='user-name3' defaultValue={`ccc`} />
            </div>
         </div>

            <div className="checkboxes-container">
             <div className='checkbox-container1'>
                <label htmlFor='skill1'>Skills</label>
                <input type='checkbox' id='skill1' defaultChecked={true} />
            </div>

            <div className='checkbox-container2'>
                <label htmlFor='skill2'>Skills</label>
                <input type='checkbox' id='skill2' defaultChecked={true} />
            </div>

            <div className='checkbox-container3'>
                <label htmlFor='skill3'>Skills</label>
                <input type='checkbox' id='skill3' defaultChecked={true} />
            </div>
         </div>


        

    </div>
  )
}

export default Lec22_Comp
```

<ins>Lec22_Comp.test.tsx</ins>
```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec22_Comp from './Lec22_Comp'


 test('textbox getByLabelText', () => {
    render(<Lec22_Comp />)
    const inputs = screen.getAllByLabelText('Username')
    for (let i = 0; i < inputs.length; i++) {
        expect(inputs[i]).toBeInTheDocument()
    }
 })


  test('checkbox getByLabelText', () => {
    render(<Lec22_Comp />)
     const checkboxes = screen.getAllByLabelText('Skills')
    for (let i = 0; i < checkboxes.length; i++) {
        expect(checkboxes[i]).toBeInTheDocument()    
        expect(checkboxes[i]).toBeChecked() 
    }
 })
```

</p>
</details>

<details>
<summary> <ins> Lec 23: getByPlaceholderText and getAllByPlaceholderText </ins></summary>
<p>
<img width="825" height="392" alt="image" src="https://github.com/user-attachments/assets/75a4422f-7402-4224-b5b0-0416d807ff3e" />   

<ins>Lec23_Comp.tsx</ins>
```javascript
const Lec22_Comp = () => {
  return (
    <div>
         <h1>RTL Query : getByPlaceholderText and getAllByPlaceholderText </h1>
         <div>
            <input type='text' placeholder='enter username' defaultValue={'abc'} />
         </div>

         <div className="input-container">
            <input type='text' placeholder='enter name' defaultValue={'xyz'} />
            <input type='text' placeholder='enter name' defaultValue={'xyz'} />
            <input type='text' placeholder='enter name' defaultValue={'xyz'} />
         </div>
        
    </div>
  )
}

export default Lec22_Comp
```

<ins>Lec23_Comp.test.tsx</ins>
```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec23_Comp from './Lec23_Comp'


 test('textbox getByPlaceholderText', () => {
    render(<Lec23_Comp />)
    const input = screen.getByPlaceholderText('enter username')
    expect(input).toBeInTheDocument() 
    expect(input).toHaveValue('abc') 
 })


  test('textbox getAllByPlaceholderText', () => {
    render(<Lec23_Comp />)
    const inputs = screen.getAllByPlaceholderText('enter name')
    for (let i = 0; i < inputs.length; i++) {
        expect(inputs[i]).toBeInTheDocument() 
        expect(inputs[i]).toHaveValue('xyz') 
    }
 })
```

</p>
</details>

<details>
<summary> <ins> Lec 24: getByText and getAllByText </ins></summary>
<p>
<img width="830" height="407" alt="image" src="https://github.com/user-attachments/assets/ebbc7b42-f1ed-4a05-9fcc-62a8ba88bdab" />   
    
<ins>Lec24_Comp.tsx</ins>
    
```javascript
const Lec24_Comp = () => {
  return (
    <div>
       <h1>RTL Query : getByText and getAllByText</h1>
       <button>Login</button>
       <p className="para-cls" id='p1'>para tag testing</p>
       <h2>Heading Level 2</h2>
       <h2>Heading Level 2</h2>
    </div>
  )
}
export default Lec24_Comp

```


<ins>Lec24_Comp.test.tsx</ins>
    
```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec24_Comp from './Lec24_Comp'


 test('getByText - single button testing', () => {
    render(<Lec24_Comp />)
    const btn = screen.getByText('Login')
    expect(btn).toBeInTheDocument()
 })

  test('getByText - single p tag testing', () => {
    render(<Lec24_Comp />)
    const paraTag = screen.getByText('para tag testing')
    expect(paraTag).toBeInTheDocument() 
    expect(paraTag).toHaveClass('para-cls') 
    expect(paraTag).toHaveAttribute('id') // check if attribute exists
    expect(paraTag).toHaveAttribute('id','p1') // // check if attribute exists with specific value
 })

  test('getByText - h1Tag testing', () => {
    render(<Lec24_Comp />)
    const h1Tag = screen.getByText('RTL Query : getByText and getAllByText')
    expect(h1Tag).toBeInTheDocument() 
 })

   test('getAllByText - h2Tags testing', () => {
    render(<Lec24_Comp />)
    const h2Tags = screen.getAllByText('Heading Level 2')
    for (let i = 0; i < h2Tags.length; i++) {
      expect(h2Tags[i]).toBeInTheDocument() 
    }
 })

```
</p>
</details>

<details>
<summary> <ins> Lec 25: getByTestId and getAllByTestId </ins></summary>
<p>
<img width="830" height="407" alt="image" src="https://github.com/user-attachments/assets/ebbc7b42-f1ed-4a05-9fcc-62a8ba88bdab" />   
    
<ins>Lec25_Comp.tsx</ins>
    
```javascript
```

<ins>Lec25_Comp.test.tsx</ins>

```javascript
```
</p>
</details>






