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
# 9. Type of Functional Component in NEXT.JS-WITH-TYPESCRIPT:-  
## IPost.ts  
```
export interface IPost {

  id: number

  title: string

  body: string

}
```  
# Type of Functional Components:-  
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
# 10. Type of event :-

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

# 11. typescript for Props - built in types  
- built in types example -> string, number, boolean
- extension .ts and component extension is .tsx not .js or .jsx  

// auto completion -> props.
// if we pass anything other than string as name props we will get error
// component props is an object
# Version-1  

## User.tsx 


```
// import React from "react";


const User = (props: {name:string;email: string; age: number;isRegistered: boolean;})=>{
  return (
    <div style={{ border: "1px solid", margin: "1rem" }}>
      <h2>{props.name}</h2>
      <p>{props.email}</p>
      <p>{props.age} years old</p>
      {props.isRegistered ? (<p>Registered Student</p>) : (<p>Unregistered Student</p>
      )}
    </div>
  );
};
export default User;
```  


## App.tsx


```
// import React from "react";
// import "./App.css";

import User from "./components/User";

function App() {
  return (
    <div className="App">
      <h1>User Management App</h1>
      <User
        name="Md Naj"
        email="mdnaj@gmail.com"
        age={32}
        isRegistered={true}
      />
    </div>
  );
}

export default App;
```  
<hr />

# Version -2


## User.tsx

```

// import React from "react";

type UserProps = {
  name: string;
  email: string;
  age: number;
  isRegistered: boolean;
};
const User = (props: UserProps) => {
  return (
    <div style={{ border: "1px solid", margin: "1rem" }}>
      <h2>{props.name}</h2>
      <p>{props.email}</p>
      <p>{props.age} years old</p>
      {props.isRegistered ? (<p>Registered Student</p>) : (
        <p>Unregistered Student</p>
      )}
      
    </div>
  );
};
export default User;

```  

## App.tsx


```
// import React from "react";
// import "./App.css";

import User from "./components/User";

function App() {
  return (
    <div className="App">
      <h1>User Management App</h1>
      <User
        name="Md Naj"
        email="mdnaj@gmail.com"
        age={32}
        isRegistered={true}
      />
      <User
        name="Md Saju"
        email="mdsaju@gmail.com"
        age={31}
        isRegistered={false}
      />
    </div>
  );
}

export default App;
```  


# Version-3
 ## User.tsx  
 
 ```
//import React from "react";
type UserProps = {
  name: string;
  email: string;
  age: number;
  isRegistered: boolean;
};
const User = ({ name, email, age, isRegistered }: UserProps) => {
  return (
    <div style={{ border: "1px solid", margin: "1rem" }}>
      <h2>{name}</h2>
      <p>{email}</p>
      <p>{age} years old</p>
      {isRegistered ? <p>Registered Student</p> : <p>Unregistered Student</p>}
    </div>
  );
};
export default User;
```  

## App.tsx


```
// import React from "react";
// import "./App.css";

import User from "./components/User";

function App() {
  return (
    <div className="App">
      <h1>User Management App</h1>
      <User
        name="Md Naj"
        email="mdnaj@gmail.com"
        age={32}
        isRegistered={true}
      />
      <User
        name="Md Saju"
        email="mdsaju@gmail.com"
        age={31}
        isRegistered={false}
      />
    </div>
  );
}

export default App;
```  



# Return void by a Function 

```
const handleClick = (): void => {
  console.log("clicked");
};
```  

# 12.typescript for Props - User defined types  
---  

- Object
-  Array
-   Union, 
- enum
- tuple
- any
- custom type  

# 12.1 object props  

## App.tsx

```
//import React from "react";
// import "./App.css";

import User from "./components/User";

const userDetails = {
  name: "Md Naj",
  email: "mdnaj!@gmail.com",
  age: 34,
  isRegistered: true,
};


function App() {
  return (
    <div className="App">
      <h1>User Details</h1>
      <User user={userDetails} />
      
    </div>
  );
}

export default App;
```  

## User.tsx  

```
// import React from "react";

type UserProps = {
  user: {
    name: string;
    email: string;
    age: number;
    isRegistered: boolean;
  };
};
const User = ({ user }: UserProps) => {
  return (
    <div style={{ border: "1px solid", margin: "1rem" }}>
      <h2>{user.name}</h2>
      <p>{user.email}</p>
      <p>{user.age} years old</p>
      {user.isRegistered ? (
        <p>Registered Student</p>
      ) : (
        <p>Unregistered Student</p>
      )}
    </div>
  );
};
export default User;
```  



# 12.2 Array  
# App.tsx  

```
const App=() =>{
 return(
   <div >
      <User 
         lang={["Bengali","English","Arabic"]};
       />
   </div>   
 )
};
export default App;

# 12.3 Array of Object:-  

## App.tsx

```
// import React from "react";
// import "./App.css";

import User from "./components/User";

const users =[
  {
    id: 1,
    name: "anisul islam",
    email: "anisul2010s@yahoo.co.uk",
    age: 32,
    isRegistered: true,
  },
  {
    id: 2,
    name: "Rabeya Begum",
    email: "rabu2010s@yahoo.co.uk",
    age: 31,
    isRegistered: false,
  },
];

function App() {
  return (
    <div className="App">
      <h1>User Details </h1>
      {users.map((user) => (
        <User key={user.id} user={user} />
      ))}
    </div>
  );
}
export default App;
```  


# User.tsx

```

// import React from "react";

type UserProps = {
  user: {
    id: number,
    name: string;
    email: string;
    age: number;
    isRegistered: boolean;
  };
};
const User = ({ user }: UserProps) => {
  return (
    <div style={{ border: "1px solid", margin: "1rem" }}>
      <h2>{user.name}</h2>
      <p>{user.email}</p>
      <p>{user.age} years old</p>
      {user.isRegistered ? (
        <p>Registered Student</p>
      ) : (
        <p>Unregistered Student</p>
      )}
    </div>
  );
};
export default User;

```  

