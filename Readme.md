# Code Step By Step

## Introduction

This is course for learning how to write testcase using jest and RTL.

### <ins>Types of Testing</ins>
![Types of Testing](https://github.com/swatantrasinha/jest-and-RTL/blob/main/screenshots/001-type_Of_Testing.png "Testing Types")

### <ins>Our Focus Area</ins>
![Out Focus Area](https://github.com/swatantrasinha/jest-and-RTL/blob/main/screenshots/002-Our_Focus_Area.png "Focus Area")

### <ins>Write Basic Test Case</ins>
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


