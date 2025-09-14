# Code Step By Step

## Introduction

This is course for learning how to write testcase using jest and RTL.

<details>
    <summary> <ins>Types of Testing</ins> </summary>
    <img width="944" height="599" alt="image" src="https://github.com/swatantrasinha/jest-and-RTL/blob/main/screenshots/001-type_Of_Testing.png" />
</details>

<hr/>

<details>
    <summary> <ins> Our Focus Area </ins> </summary>
    <img width="944" height="599" alt="image" src="https://github.com/swatantrasinha/jest-and-RTL/blob/main/screenshots/002-Our_Focus_Area.png" />
</details>

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

<details>
<summary> <ins> Lec 11: File and Folder naming convention </ins></summary>
<p> 
<img width="891" height="590" alt="image" src="https://github.com/user-attachments/assets/f3b7374b-66da-4477-9e3b-dac9e75f1c56" />
</p>
    
1. Below file name syntax are also considered testcase file:      
<img width="275" height="131" alt="image" src="https://github.com/user-attachments/assets/2d36f746-5c8a-415c-abb6-1f4fd1dd7658" />

2. if we create a folder with name  "__tests__", then all files within this folder will be considered as testcase file even if its only .js (need not to be .test or .spec )
  
</details>

<hr/>

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

<hr/>

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

<hr/>

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

<hr/>

<details>
<summary> <ins> Lec 15: Class Component Method Testing </ins></summary>
<p> 
<img width="826" height="318" alt="image" src="https://github.com/user-attachments/assets/1a4a99f8-d4b3-4c3e-8fed-9609d836f0bd" />
<hr />
</p>
</details>

<hr/>

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

-------------

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

<hr/>

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

<hr/>

<details>
<summary> <ins> Lec 18: getByRole Query </ins></summary>
<p> 
<img width="824" height="471" alt="image" src="https://github.com/user-attachments/assets/ebd9ffbf-2281-4bc8-840f-dbffd90d02a3" />
<hr />
<ins>Note:</ins> semantic tags have defined roles   

e.g For textbox --> screen.getByRole('textbox')

</p>
</details>

<hr/>

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

<hr/>

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

<hr/>


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

<hr/>

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

<hr/>

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

<hr/>


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

<hr/>

<details>
<summary> <ins> Lec 25: getByTestId and getAllByTestId </ins></summary>
<p>
<img width="830" height="407" alt="image" src="https://github.com/user-attachments/assets/ebbc7b42-f1ed-4a05-9fcc-62a8ba88bdab" />   
    
<ins>Lec25_Comp.tsx</ins>
    
```javascript

const Lec25_Comp = () => {
  return (
    <div>
       <h1>RTL Query : getByTestId and getAllByTestId</h1>
       <div data-testid='div-test-id'>This is div element</div>
       <h2 data-testid='h2-test-id'>Heading Level 2</h2>
       <p data-testid='para-test-id'>This is para1 element</p>
       <p data-testid='para-test-id'>This is para2 element</p>
    </div>
  )
}
export default Lec25_Comp

```

<ins>Lec25_Comp.test.tsx</ins>

```javascript
import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec25_Comp from './Lec25_Comp'


 test('getByTestId - div ele testing', () => {
    render(<Lec25_Comp />)
    const divEle = screen.getByTestId('div-test-id')
    expect(divEle).toBeInTheDocument()
 })

  test('getByTestId - h2 ele testing', () => {
    render(<Lec25_Comp />)
    const h2Ele = screen.getByTestId('h2-test-id')
    expect(h2Ele).toBeInTheDocument()
 })

   test('getAllByTestId - multiple para ele testing', () => {
    render(<Lec25_Comp />)
    const paraElements = screen.getAllByTestId('para-test-id')
    for (let i = 0; i < paraElements.length; i++) {
       expect(paraElements[i]).toBeInTheDocument()
    }
 })
```

<ins>Note:</ins>   
1. Here in the third testcase we are using getAllByTestId means assuming that multiple elements will have same test-id.   

2. data-testid is just a custom attribute name.   
It can be element-testid, component-testid etc. We will see how to use it in next lecture(Overriding data-testid)      
</p>
</details>

<hr/>


<details>
<summary> <ins> Lec 26: Overriding data-testid </ins></summary>
<p>
<img width="1125" height="467" alt="image" src="https://github.com/user-attachments/assets/bcae7dfb-3647-41df-a5a6-0c6f650529d9" />   
   
<ins>Lec26_Comp.tsx</ins>

```javascript
const Lec26_Comp = () => {
  return (
    <div>
       <h1>RTL Query : Overriding data-testid</h1>
       {/* <div data-testid='test-div'>This is div element</div> */}
       <div element-id='test-div'>This is div element</div>
    </div>
  )
}
export default Lec26_Comp

```

<ins>Lec26_Comp.test.tsx</ins>

```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec26_Comp from './Lec26_Comp'

configure({testIdAttribute: 'element-id'})

 test('test div with element-id', () => {
    render(<Lec26_Comp />)
    const divEle = screen.getByTestId('test-div')
    expect(divEle).toBeInTheDocument()
 })

```
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 27: getByDisplayValue and getAllByDisplayValue </ins></summary>
<p>
<img width="829" height="417" alt="image" src="https://github.com/user-attachments/assets/130fab1e-910d-4720-bca0-8cd097f85f11" />
</p>

<ins>Lec27_Comp.tsx</ins>
```javascript

const Lec27_Comp = () => {
  return (
    <div>
       <h1>RTL Query : getByDisplayValue and getAllByDisplayValue </h1>
       <div>
          <input type="text" defaultValue='abc' />
       </div>

       <div>
        <textarea defaultValue='hello world' />
       </div>

       <div>
        <input type="radio" defaultValue='male' />
       </div>

        <div>
        <input type="text" defaultValue='enter query' />
        <input type="text" defaultValue='enter query' />
       </div>
    </div>
  )
}
export default Lec27_Comp

```

<ins>Lec27_Comp.test.tsx</ins>
```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec27_Comp from './Lec27_Comp'

configure({testIdAttribute: 'element-id'})

 test('textbox- testing using getByDisplayValue', () => {
    render(<Lec27_Comp />)
    const inputEle = screen.getByDisplayValue('abc')
    expect(inputEle).toBeInTheDocument()
 })

test('textArea - testing using getByDisplayValue', () => {
    render(<Lec27_Comp />)
     const textAreaEle = screen.getByDisplayValue('hello world')
    expect(textAreaEle).toBeInTheDocument()
 })

 test('radioButton - testing using getByDisplayValue', () => {
    render(<Lec27_Comp />)
     const radioBtnEle = screen.getByDisplayValue('male')
    expect(radioBtnEle).toBeInTheDocument()
 })

  test('textbox- testing using getAllByDisplayValue', () => {
    render(<Lec27_Comp />)
    const inputList = screen.getAllByDisplayValue('enter query')
    for (let i = 0; i < inputList.length; i++) {
        expect(inputList[i]).toBeInTheDocument()
    }
 })
```
</details>

<hr/>

<details>
<summary> <ins> Lec 28: getByTitle and getAllByTitle </ins></summary>
<p>   
<img width="829" height="417" alt="image" src="https://github.com/user-attachments/assets/3a27d207-8eb3-4e81-911b-f9d08a7d6f5f" />   

<ins>Lec28_Comp.tsx</ins>

```javascript
const Lec28_Comp = () => {
  return (
    <div>
       <h1>RTL Query : getByTitle and getAllByTitle </h1>
       <div>
          <button title="click to open">Click Me</button>
       </div>
       <div>
        <span title='black spade suit'>&#x2660;</span>
       </div>

       <div>
        <span title='black star'>&#x2605;</span>
        <span title='black star'>&#x2605;</span>
       </div>
    </div>
  )
}
export default Lec28_Comp

```

<ins>Lec28_Comp.test.tsx</ins>

```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec28_Comp from './Lec28_Comp'

configure({testIdAttribute: 'element-id'})

 test('button- testing with getByTitle', () => {
    render(<Lec28_Comp />)
    const btnEle = screen.getByTitle('click to open')
    expect(btnEle).toBeInTheDocument()
 })

  test('span- testing with getByTitle', () => {
    render(<Lec28_Comp />)
    const spanEle = screen.getByTitle('black spade suit')
    expect(spanEle).toBeInTheDocument()
 })

   test('span elements - testing with getAllByTitle', () => {
    render(<Lec28_Comp />)
    const spanList = screen.getAllByTitle('black star')
    for (let i = 0; i < spanList.length; i++) {
      expect(spanList[i]).toBeInTheDocument()
    }
   })

```
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 29: getByAltText and getAllByAltText </ins></summary>
<p>   
<img width="1141" height="571" alt="image" src="https://github.com/user-attachments/assets/c2ac8a47-feb9-45a9-b436-f18583ec8ede" />

<ins>Lec29_Comp.tsx</ins>

```javascript
const Lec29_Comp = () => {
  return (
    <div>
       <h1>RTL Query : getByAltText and getAllByAltText </h1>
       <div>
          <img alt='dummy image' src='https://images.unsplash.com/photo-1579353977828-2a4eab540b9a?w=900' />
       </div>

        <div>
          <img alt='lemon and knife' src='https://images.unsplash.com/photo-1600716051809-e997e11a5d52?q=80&w=2650' />
          <img alt='lemon and knife' src='https://images.unsplash.com/photo-1600716051809-e997e11a5d52?q=80&w=2650' />
       </div>
    </div>
  )
}
export default Lec29_Comp

```

<ins>Lec29_Comp.test.tsx</ins>
```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec29_Comp from './Lec29_Comp'

configure({testIdAttribute: 'element-id'})

 test('image - testing with getByAltText', () => {
    render(<Lec29_Comp />)
    const imgEle = screen.getByAltText('dummy image')
    expect(imgEle).toBeInTheDocument()
 })


  test('images - testing with getAllByAltText', () => {
    render(<Lec29_Comp />)
    const imagesList = screen.getAllByAltText('dummy image')
    for (let i = 0; i < imagesList.length; i++) {
      expect(imagesList[i]).toBeInTheDocument()
    }
    
 })
```
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 30: Priority Order for RTL Queries </ins></summary>
<p>
    
The priority order is same as mentioned in the offocial docs of RTL. See below :   
    
<img width="1409" height="727" alt="image" src="https://github.com/user-attachments/assets/f0c035eb-c672-460e-86f5-c563f0770629" />

</p>
</details>

<hr/>


 <details>
<summary> <ins> Lec 31:  Assertion Methods </ins></summary>
     
<p>   
<img width="1111" height="435" alt="image" src="https://github.com/user-attachments/assets/5ccc1bea-9bc9-4f7f-aad5-7ada570aa90e" />   

<ins>Lec31_Comp.tsx</ins>

```javascript
const Lec31_Comp = () => {
    return (
        <div>
            <h1>Lec30:  Assertion Methods</h1>
            <input 
                className='test-style my-custom-style' 
                id='user' type='text' 
                defaultValue='abc' 
                name='userName' 
                data-test='dummy'
                />
            
            <button disabled className="btn1" id='btn-id'>Click Me</button>
        </div>
    )
}
export default Lec31_Comp

```

<ins>Lec31_Comp.test.tsx</ins>

```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec31_Comp from './Lec31_Comp'

configure({testIdAttribute: 'element-id'})

 test('test - input textbox', () => {
    render(<Lec31_Comp />)
    const input = screen.getByRole('textbox')
    expect(input).toBeInTheDocument()
    expect(input).toHaveValue()
    expect(input).toHaveValue('abc')
    expect(input).toBeEnabled()
    expect(input).toHaveAttribute('id')
    expect(input).toHaveAttribute('data-test')
    expect(input).toHaveClass('test-style')
    expect(input).toHaveClass('my-custom-style')
 })

  test('test - negavtive cases', () => {
    render(<Lec31_Comp />)
    const btn = screen.getByRole('button')
    expect(btn).toBeInTheDocument()
    expect(btn).not.toHaveClass('btn')
    expect(btn).not.toHaveAttribute('id','abc')
    expect(btn).not.toBeEnabled()
  })
```
</p>

</details>

<hr/>

<details>
<summary> <ins> Lec 32:  TextMatch with String and Regex </ins> </summary>
<p> 
<img width="829" height="332" alt="image" src="https://github.com/user-attachments/assets/0f55dce2-4fbe-4f1c-b117-260980a5648b" />   

<ins>Lec32_Comp.tsx</ins>

```javascript
const Lec32_Comp = () => {
    return (
        <div>
            <h1>Lec32: TextMatch with String and Regex</h1>
            <div>Hello World</div>
         </div>
    )
}

export default Lec32_Comp
```

<ins>Lec32_Comp.test.tsx</ins>

```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec32_Comp from './Lec32_Comp'

configure({testIdAttribute: 'element-id'})

 test('text match with string', () => {
    render(<Lec32_Comp />)
    const divEle1 = screen.getByText('hello world',{exact: false})
    expect(divEle1).toBeInTheDocument()

    const divEle2 = screen.getByText('hello World',{exact: false})
    expect(divEle2).toBeInTheDocument()

    const divEle3 = screen.getByText('Hello world',{exact: false})
    expect(divEle3).toBeInTheDocument()
    
    const divEle4 = screen.getByText('hello',{exact: false})
    expect(divEle4).toBeInTheDocument()
 })

  test('text match with regex', () => {
    render(<Lec32_Comp />)
    const div1 = screen.getByText(/Hello/)
    expect(div1).toBeInTheDocument()

    const div2 = screen.getByText(/lo Wo/)
    expect(div2).toBeInTheDocument()

    const div3 = screen.getByText(/hello/i)
    expect(div3).toBeInTheDocument()


    const div4 = screen.getByText(/Hello W?orld/i)
    expect(div4).toBeInTheDocument()
  })

```
    
</p>

</details>

<hr/>

 <details>
<summary> <ins> Lec 33:  TextMatch with Function </ins> </summary>
<p>    
<img width="829" height="271" alt="image" src="https://github.com/user-attachments/assets/d73083c1-dcd2-4d87-a973-99db59e35eb7" />   

<ins>Lec33_Comp.tsx</ins>
```javascript
const Lec33_Comp = () => {
    return (
        <div>
            <h1>Lec33: TextMatch with Function</h1>
            <div>Hello World</div>
         </div>
    )
}
export default Lec33_Comp

```

<ins>Lec33_Comp.test.tsx</ins>

```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec33_Comp from './Lec33_Comp'

configure({testIdAttribute: 'element-id'})

 test('text match with string', () => {
    render(<Lec33_Comp />)
    const divEle1 = screen.getByText((content,element) => content.startsWith('Hello'))
    expect(divEle1).toBeInTheDocument()

   const divEle2 = screen.getByText((content, element) => content.endsWith('World'))
   expect(divEle2).toBeInTheDocument()    

   const divEle3 = screen.getByText((content, element) => {
      return (content?.length === 11) && content?.includes('lo Wo')
   })
   expect(divEle3).toBeInTheDocument()    

 })

```

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 34:  QueryBy and QueryAllBy | Test hidden elements </ins> </summary>
<p>   
<img width="1114" height="526" alt="image" src="https://github.com/user-attachments/assets/f6ef83e5-8580-4357-87a7-ceb16df385ce" />   
Almost all features of getBy are there in queryBy, The extra feature with queryBy is even if element is hidden in UI, then also we can test it.   

<ins>Lec34_Comp.tsx</ins>   
```javascript
const Lec34_Comp = () => {
    let isLogin= false
    return (
        <div>
            <h1>Lec34: QueryBy and QueryAllBy</h1>
            {!isLogin ? (<button>Login</button>): (<button>Logout</button>)}
         </div>
    )
}
export default Lec34_Comp
```


<ins>Lec34_Comp.test.tsx</ins>   
```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec34_Comp from './Lec34_Comp'

 test('queryBy test case', () => {
    render(<Lec34_Comp />)
    const div1 = screen.getByText('Login')
    expect(div1).toBeInTheDocument()

   
   //  const div2 = screen.getByText('Logout')
   //  expect(div2).toBeInTheDocument()
   /* This will fail because in Lec34_Comp.tsx, isLogin is false
   so Logout button will not be rendered
   To solve this we will use "queryBy" approach  */   

   const div2 = screen.queryByText('Logout')
   expect(div2).not.toBeInTheDocument()

    /* Note: if we try .not.toBeInTheDocument()
    with getBy, it will not work 
   // const div3 = screen.getByText('Logout')
   // expect(div3).not.toBeInTheDocument()
   */ 
 })
```
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 35:  findBy and findAllBy | test async elements </ins> </summary>
<p>
<img width="1114" height="526" alt="image" src="https://github.com/user-attachments/assets/6f1d2b7b-a935-4e59-8e80-34d0cb0293d4" />   

<ins>Lec35_Comp.tsx</ins>  

```javascript
import { useEffect, useState } from "react"

const Lec35_Comp = () => {
    const [data, setData]= useState(false)

    useEffect(() => {
        setTimeout(() => {
            setData(true)
        }, 3000);
    }, [])
    
    return (
        <div>
            <h1>Lec35:findBy and findAllBy | test async elements</h1>
            {data ? (<div>Data Found</div>): (<div>Data Not Found</div>)}
         </div>
    )
}

export default Lec35_Comp

```

<ins>Lec35_Comp.test.tsx</ins>   

```javascript
import {render, screen, configure} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec35_Comp from './Lec35_Comp'

 test('findBy test case', async() => {
    render(<Lec35_Comp />)
    // this will fail
    /*
    const dataFoundEle = screen.getByText('Data Found')
    expect(dataFoundEle).toBeInTheDocument()
    */

     // this will also fail
    /*
    const dataFoundEle = screen.queryByText('Data Found')
    expect(dataFoundEle).toBeInTheDocument()
    */

    const dataFoundEle = await screen.findByText('Data Found',{}, {timeout: 3000})
    expect(dataFoundEle).toBeInTheDocument()

 })

```

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 36:  Test Elements with JavaScript Query | Custom Query </ins> </summary>
<p>
Custom query is used in case we are not able to use getBy/queryBy/findBy   

<ins>Lec36_Comp.tsx</ins> 

```javascript

const Lec36_Comp = () => {
    
    return (
        <div>
            <h1>Lec36 : Test Elements with JavaScript Query | Custom Query </h1>
            <div id='test-id'>Hello World</div>
         </div>
    )
}

export default Lec36_Comp

```


<ins>Lec36_Comp.test.tsx</ins> 

```javascript
import {render} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec36_Comp from './Lec36_Comp'

 test('test case with custom query', async() => {
    render(<Lec36_Comp />)
    const ele = document.querySelector('#test-id')
    expect(ele).toBeInTheDocument()
    expect(ele).toHaveTextContent('Hello World')
 })
```

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 37: Querying Within Elements </ins> </summary>
<p>
This is used when with the parent we need to test for the child as well.   

<ins>Lec37_Comp.tsx</ins> 

```javascript
const Lec37_Comp = () => {
    
    return (
        <div>
            <h1>Lec37 : Querying Within Elements </h1>
            <div >
                Hello World
                <p>Hi</p>
                <p>bye</p>
            </div>
         </div>
    )
}

export default Lec37_Comp
```

<ins>Lec37_Comp.test.tsx</ins> 

```javascript
import {render, screen, within} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec37_Comp from './Lec37_Comp'

 test('test case with custom query', async() => {
    render(<Lec37_Comp />)
    const el = screen.getByText('Hello World')
    expect(el).toBeInTheDocument()
    const subEl = within(el).getByText('Hi')
    expect(subEl).toBeInTheDocument()
 })
```
    
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 38: Click Event with User Event Library </ins> </summary>
<p>
<img width="818" height="381" alt="image" src="https://github.com/user-attachments/assets/84418738-9007-4ce0-8128-f706b8e33c12" />   

We have earlier seen the testing of Click event. Refer: **Lec 10: Click event test case with button | event fire**       
   
- RTL is used not only with react but also with vanilla js/vue js/angular js etc.
  When we install react in our project,so generally we get this by default. But in other framework like vue/angular when we install RTL we get this user-event library. There are some event which RTL picks up 
  from User-Event library. In short, user-event lib is supporting lib for RTL.

- User-event lib is specially designed for user events like onClick,mouseover. Its simpler to use than fireEvent of RTL and covers wider-range of testcases.  

 
- if we see documentation for RTL, its recommended to use user-events lib: https://testing-library.com/docs/user-event/intro   

<img width="1197" height="955" alt="image" src="https://github.com/user-attachments/assets/cfd606fc-df68-44d0-be4b-2ce110cf6868" />


Also, see the highlighted text in red which suggest to upgrade to version 14      
In our package.json, the current version for the user-event library is:   

>  "@testing-library/user-event": "^13.5.0",   

so we will give below command to upgrade   

> yarn add @testing-library/user-event@latest   

and now we can see the user-event version is upgraded to 14   

> "@testing-library/user-event": "^14.6.1",

Now we will write some code in **Lec38_Comp.tsx** and then its testcase in **Lec38_Comp.test.tsx** using user-event library   

<ins>Lec38_Comp.tsx</ins> 

```javascript
import { useState } from "react"

const Lec38_Comp = () => {
    const [data, setData] = useState('')
    return (
        <div>
            <h1>Lec38 : Click Event with User Event Library</h1>
            <h2>{data}</h2>
            <div >
               <button onClick={() => setData('Hello')}>Click Me</button>
            </div>
         </div>
    )
}
export default Lec38_Comp
```

<ins>Lec38_Comp.test.tsx</ins> 

```javascript

import {render, screen, within} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec38_Comp from './Lec38_Comp'
import userEvent from '@testing-library/user-event'

 test('test click event with user-event library', async() => {
   userEvent.setup()
   render(<Lec38_Comp />)
   const btn = screen.getByText('Click Me')
   await userEvent.click(btn)
   expect(screen.getByText('Hello')).toBeInTheDocument()
 })

```

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 39: onChange Event Testing | Keyboard Interactions </ins> </summary>
<p>
<img width="1119" height="510" alt="image" src="https://github.com/user-attachments/assets/0f3be7f1-ef27-415d-b213-9506dd0b82ea" />

<ins>Lec39_Comp.tsx</ins> 

```javascript

import { useState } from "react"

const Lec39_Comp = () => {
    const [name, setName] = useState('')
    return (
        <div>
            <h1>Lec 39: onChange Event Testing | Keyboard Interactions</h1>
            <h2>{name}</h2>
            <div>
              <input type="text" onChange={(e) => setName(e?.target?.value)} placeholder="Enter Name" />
            </div>
         </div>
    )
}
export default Lec39_Comp

```

<ins>Lec39_Comp.test.tsx</ins> 

```javascript

import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec39_Comp from './Lec39_Comp'
import userEvent from '@testing-library/user-event'

 test('test onChange event with user-event library', async() => {
   userEvent.setup()
   render(<Lec39_Comp />)
   const ele = screen.getByRole('textbox')
   await userEvent.type(ele, 'abc')
   expect(screen.getByText('abc')).toBeInTheDocument()
 })

```
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 40: act function </ins> </summary>   

<p>
<img width="832" height="379" alt="image" src="https://github.com/user-attachments/assets/70211246-51b4-49b1-82f7-8540313e65f9" />   

While writing test cases for events like onClick and onChange, there are state update as well.   
This state update is async and can cause error. To solve this we will use **act** function.   

<ins>Lec40_Comp.tsx</ins> 

```javascript
import { useState } from "react"

const Lec40_Comp = () => {
    const [name, setName] = useState('')

    
    return (
        <div>
            <h1>Lec 40:act functions</h1>
            <h2>{name}</h2>
            <div>
              <input type="text" onChange={(e) => setName(e?.target?.value)} placeholder="Enter Name" />
            </div>
         </div>
    )
}

export default Lec40_Comp

```

<ins>Lec40_Comp.test.tsx</ins> 

```javascript

import {act, render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec40_Comp from './Lec40_Comp'
import userEvent from '@testing-library/user-event'

 test('test onChange event with act function', async() => {
   userEvent.setup()
   render(<Lec40_Comp />)
   const ele = screen.getByRole('textbox')
   await act(async() => {
    await userEvent.type(ele, 'xyz')
   }) 
   expect(screen.getByText('xyz')).toBeInTheDocument()
 })

```

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 41: Test component Props </ins> </summary>   
<p>
<img width="1121" height="520" alt="image" src="https://github.com/user-attachments/assets/64a45085-3afc-46e7-86cf-46bf889df241" />   

<ins>Lec41_User_Comp.tsx</ins> 

```javascript
const Lec41_User_Comp = (props:any) => {
  return (
    <div>
      <h1>Username is:{props?.name}</h1>
    </div>
  )
}
export default Lec41_User_Comp
```
<ins>Lec41_Comp.tsx</ins> 

```javascript
import Lec41_User_Comp from "./Lec41_User_Comp"

const Lec41_Comp = () => {
    return (
        <div>
            <h1>Lec 41: Prop Testing</h1>
            <hr />
            <Lec41_User_Comp name='abcd'/>
         </div>
    )
}
export default Lec41_Comp
```

<ins>Lec41_Comp.test.tsx</ins> 

```javascript

import {render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec41_User_Comp from './Lec41_User_Comp'

 test('Props Testing', () => {
  const name= 'swatantra'
   render(<Lec41_User_Comp name={name} />)
   const userName = screen.getByText(`Username is:${name}`)
   expect(userName).toBeInTheDocument()
 })

```
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 42: Functional Props Testing and Function Mocking </ins> </summary>   
<p>
<img width="821" height="382" alt="image" src="https://github.com/user-attachments/assets/df11433f-bb58-4615-a947-6ce1d71327ad" />   

<ins>Lec42_Comp.tsx</ins> 
```javascript
const Lec42_Comp = (props:any) => {
    return (
        <div>
            <h1>Lec 42: Functional Props Testing and Function Mocking</h1>
            <button onClick={props?.testFunc}>Click</button>
         </div>
    )
}
export default Lec42_Comp
```

<ins>Lec42_Comp.test.tsx</ins> 

```javascript
import { render, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Lec42_Comp from './Lec42_Comp'
import userEvent from '@testing-library/user-event'

 test('test onChange event with act function', async() => {
  const testFunc = jest.fn()
  userEvent.setup()
   render(<Lec42_Comp testFunc={testFunc}/>)
   const btn = screen.getByRole('button')
   await userEvent.click(btn)
   expect(testFunc).toBeCalled()
 })
```

</p>

</details>

<hr/>

<details>
<summary> <ins> Lec 43: Debugging in React testing library </ins> </summary>   
<p>
<img width="818" height="438" alt="image" src="https://github.com/user-attachments/assets/bb8dbdbc-d291-45ff-8bce-d257d7a78bc0" />   

1. Automatic debudding : Its there by default. It shows text in red where the testcase mismatches and failed.   

2. prettyDom: To print the html content in terminal we can do :

```javascript
const {container} = render(<Lec43_Comp />)
console.log(container)
```

The above will print the content of DOM but the HTML is not readable.    
For this we can use **prettyDom** method as below:   

```javascript
const {container} = render(<Lec43_Comp />)
console.log(prettyDOM(container))
```

<img width="885" height="662" alt="image" src="https://github.com/user-attachments/assets/503eab6a-8e43-4922-9f73-801cc7b832d4" />


3. debug: this will also display contents of DOM in readable format   

```javascript
const {debug} = render(<Lec43_Comp />)
debug()
```

4. DEBUG_PRINT_LIMIT: By default, the number of lines to be printed is around 7000, for debugging purpose we can increase it to 10000
We can give below command:

> DEBUG_PRINT_LIMIT=10000 npm run test 

5. logRoles: it helps in identifying elements in DOM clearly         

```javascript
const {container} = render(<Lec43_Comp />)
logRoles(container)
```
<img width="877" height="633" alt="image" src="https://github.com/user-attachments/assets/575408ba-5854-47d9-b1b9-df3855fd53d8" />   

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 44: Testing playground chrome extension </ins> </summary>   
<p>
<img width="829" height="334" alt="image" src="https://github.com/user-attachments/assets/64f4225b-a37d-4127-923b-3cf61fc126f4" />   

**Testing playground** is chrome extension. We need to first install it and to use we need to right click -> inspect  and then go to Testing Playground tab.    
We can then hover over element in DOM to see the details like roles, labelText, altText etc

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 45: What is MSW | Mock Service worker </ins> </summary>   

<p>
<img width="1112" height="499" alt="image" src="https://github.com/user-attachments/assets/529f5989-dfe3-4c4d-aad8-dd6940672d9b" />   

</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 46: API Call for Testing </ins> </summary>   
<p>
We wil do API calling in this lecture and then we will test it using MSW in next lecture   

<ins>Lec46_Comp.tsx</ins> 

```javascript

import { useEffect, useState } from "react"

type UserDataType= {
  id: number,
  name: string,
  username: string,
  email: string,
  phone: string,
}

const Lec46_Comp = () => {
    const [data, setData] = useState<UserDataType[] | null>(null)
    
    useEffect(() => {
      getData()
    }, [])

    const getData = async() => {
      const response = await fetch('https://jsonplaceholder.typicode.com/users')
      const result = await response.json() as UserDataType[]
      console.log('result : ' , result)
      if(result) {
        setData(result)
      }
    }

    
    return (
        <div>
            <h1>Lec 46: API Call for Testing</h1>
            <h2>List Of Users:</h2>
            {data && (
              <ul>
                {data?.map((user: UserDataType) => (
                  <li key={user?.id}>{user?.name}</li>
                ))}
              </ul>
            )}
            
         </div>
    )
}

export default Lec46_Comp

```
 
</p>
</details>

<hr/>

<details>
<summary> <ins> Lec 47: API test with MSW </ins> </summary>   
<p>
We did API calling in the previous lecture-46 and now in this lecture, we will test it using MSW.   

<img width="813" height="390" alt="image" src="https://github.com/user-attachments/assets/4fc5f94b-fdea-4521-aa90-0a396a009734" />

<ins>Lec47_Comp.test.tsx</ins> 

1. install MSW   

> yarn add msw --dev

2. inside **src** create a new folder **mockServices** and add two files
- server.js
- handlers.js


```javascript

```
</details>





