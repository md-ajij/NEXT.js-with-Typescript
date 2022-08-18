# NEXT.js-with-Typescript  
---  
# 1. To create NEXT app with Typescript:-  
---  

```
npx create-next-app my-project --typescript
```  

# or  
```
npx create-next-app my-project --ts
```  

# or  
```
yarn create next-app my-project --typescript  
```  
# To run the app. Enter the following comand in terminal:-  
```
npm run dev
```  
## or  
```
yearn dev
```  


# 2. Type of parameters of a Arrow function(void) that return nothing  
```
const myFunc=(a:number,b:number):void=>{
   consol.log(a+b);
}

myFunc(10,5);
```  
# 3. Type of parameters of a Arrow function that return a sting  

```

const myFunc=(a:number,b:number):string =>{

   consol.log(a+b);
 return `a is ${a} and b is ${b}`;
}

myFunc(10,5);
```  

# 4. Optional Type of a variable:- 

```

const myFunc =(a:number,b:number,c?:number=500):string =>{

   consol.log(a+b);

 return `a is ${a} and b is ${b}`;

}

myFunc(10,5);

```  



# 5. Normal function(void) that return nothing  

```

function myFunc(a:number,b:number):void {

   consol.log(a+b);

}

myFunc(10,5);

```  
# 6. Normal function(sting) that return a sting  

```

function myFunc(a:number,b:number):string {

   consol.log(a+b);

 return `a is ${a} and b is ${b}`;

}

myFunc(10,5);

```  
# 7. Type of  Arrow function(void) that return nothing  

```
let myFunc:Function;

myFunc=(a:number,b:number):void=>{

   consol.log(a+b);

}

myFunc(10,5);

```  

# 8. Type of Arrow function(sting) that return a sting  

```
let myFunc:Function;
myFunc =(a:number,b:number):string =>{

   consol.log(a+b);

 return `a is ${a} and b is ${b}`;

}

myFunc(10,5);
```  
# 9. Functional Component in NEXT.JS-WITH-TYPESCRIPT:-  
## IPost.ts  
```
export interface IPost {

  id: number

  title: string

  body: string

}
```  
# Functional Components:-  
// AddPost.tsx  
```

import * as React from 'react';
import { IPost } from '../types';

type Props = {
  savePost: (e: React.FormEvent, formData: IPost) => void
}

const AddPost: React.FC<Props> = ({ savePost }) => {
  const [formData, setFormData] = React.useState<IPost>()

  const handleFormInputFiled = (e: React.FormEvent<HTMLInputElement>): void => {
    setFormData({
      ...formData,
      [e.currentTarget.id]: e.currentTarget.value,
    })
  }

export defoult AddPost;
```  


# Functional Components:-  

// AddPost.tsx  

```

import * as React from 'react';  
import React, {useState,FormEvent,FC} from 'react';

import { IPost } from '../types';

type Props = {

  savePost: (e: FormEvent, formData: IPost) => void

}

const AddPost: FC<Props> = ({ savePost }) => {

  const [formData, setFormData] = useState<IPost>()

  const handleFormInputFiled = (e: FormEvent<HTMLInputElement>): void => {

    setFormData({

      ...formData,

      [e.target.name]: e.target.value,

    })

  }

export defoult AddPost;

```  
# 10. Typing event props:-

  <!-- click event: event: React.MouseEvent<HTMLButtonElement>

  type ButtonProps = {

 handleClick: (event: React.MouseEvent<HTMLButtonElement>) => void;

 handleChange: (event: React.ChangeEvent<HTMLInputElement>) => void

 };
-->

  # Ajij.tsx

  ```
  import React, { useState } from "react";

  type NewUserProps = {

    name: string;

    email: string;

  };

  const NewUser = () => {

    const [user, setUser] = useState<NewUserProps>({ name: "", email: "" });

    const handleInputFieldChange = (event: React.ChangeEvent<HTMLInputElement>) => {

      const fieldName = event.target.name;

      setUser({ ...user, [fieldName]: event.target.value });

    };

    const handleSubmit = (event: React.FormEvent<HTMLFormElement>) => {

      event.preventDefault();

      console.log(user);

    };

    return (

      <div>

        <h2>Create User</h2>

        <form onSubmit={handleSubmit}>

          <div>

            <label htmlFor="name">

              Name

              <input

                type="text"

                id="name"

                name="name"

                value={user.name}

                onChange={handleInputFieldChange}

                required

              />

            </label>

          </div>

          <div>

            <label htmlFor="email">

              Email

              <input

                type="email"

                id="email"

                name="email"

                value={user.email}

                onChange={handleInputFieldChange}

                required

              />

            </label>

          </div>

          <button type="submit">Create User</button>

        </form>

      </div>

      );

    };

    export default NewUser;
    ```  
    
    
  # or  
  
  ```
  
  import React, { useState, ChangeEvent,FormEvent } from "react";

  type NewUserProps = {
    name: string;
    email: string;
  };
  const NewUser = () => {
    const [user, setUser] = useState<NewUserProps>({ name: "", email: "" });

    const handleInputFieldChange = (e: ChangeEvent<HTMLInputElement>) => {
      const fieldName = e.target.name;
      setUser({ ...user, [fieldName]: e.target.value });
    };

    const handleSubmit = (e: FormEvent<HTMLFormElement>) => {
      e.preventDefault();
      console.log(user);
    };
    return (
      <div>
        <h2>Create User</h2>
        <form onSubmit={handleSubmit}>
          <div>
            <label htmlFor="name">
              Name
              <input
                type="text"
                id="name"
                name="name"
                value={user.name}
                onChange={handleInputFieldChange}
                required
              />
            </label>
          </div>
          <div>
            <label htmlFor="email">
              Email
              <input
                type="email"
                id="email"
                name="email"
                value={user.email}
                onChange={handleInputFieldChange}
                required
              />
            </label>
          </div>
          <button type="submit">Create User</button>
        </form>
      </div>
      );
    };

    export default NewUser;
```  



