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

1. <p> auto completion -> props  </p>
2. <p> if we pass anything other than string as name props we will get error   </p>
3. <p> component props is an object  </p>  

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
         lang={["Bengali","English","Arabic","Hindi"]};
       />
   </div>   
 )
};
export default App;
```  

# User.tsx  


```
// import React from "react";
type UserProps = {

   lang : string[];
}
const User =({lang}: UserProps) => {
   return(
      <dic>
         <p> Speaks: {lang.map((language,index)=>{
                    return <span key={index}>{language}</span> ;
              })};
         </p>     
      </div>   
   );
};
export default User;
```  



# 12.3 Array in Object  
# App.tsx  

```
// import React from "react"
import User from "./components/User";
const userDetails ={
   name:"Md Ajij",
   age: 36,
   isRegistered: true,
   lang:["Bengali","English","Arabic","Hindi"],
};

const App=() => {
 return(
   <div >
      <User 
         user = {userDetails};
       />
   </div>   
 )
};
export default App;
```  

# User.tsx  


```
// import React from "react";

type UserProps = {
   name: string;
   age:number;
   isRegistered: true,
   lang : string[];
}
const User =({user}: UserProps) => {
   return(
      <div>
         <h1>{user.name}</h1>
         <h1>{user.age}</h1>
         {user.isRegistered ? (<p> Register user</p>) : (<p> Not Registered</p>)
         }
         <p> Speaks: {user.lang.map((language,index)=>{
                    return <span key={index}>{language}</span> ;
              })};
         </p>     
      </div>   
   );
};
export default User;
```  




# 12.4 Array of Object:-  

## App.tsx  

```
// import React from "react";
// import "./App.css";

import User from "./components/User";

const users =[
  {
    id: 1,
    name: "Md Naj",
    email: "mdnaj@gmail.com",
    age: 32,
    isRegistered: true,
  },
  {
    id: 2,
    name: "Md Saju",
    email: "mdsaju@gmail.com",
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
# 12.5 Array of Object:-  
## App.tsx  

```
// import React from "react";
// import "./App.css";

import User from "./components/User";

const usersDetails =[
  {
    id: 1,
    name: "Md Naj",
    email: "mdnaj@gmail.com",
    age: 32,
    isRegistered: true,
  },
  {
    id: 2,
    name: "Md Saju",
    email: "mdsaju@gmail.com",
    age: 31,
    isRegistered: false,
  },
];

function App() {
  return (
    <div className="App">
      <h1>User Details </h1>
     
        <User users={usersDetails} />
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
  users: {
    id: number,
    name: string;
    email: string;
    age: number;
    isRegistered: boolean;
  };
};
const User = ({ users }: UserProps) => {
  return (
    <div >
      {users.map((user)=>{
         const {id,name,email,age,isRegistered} = user;
         return(
            <div key={id} style={{ border: "1px solid", margin: "1rem" }}>
                <h2>{name}</h2>
                 <p>{email}</p>
                 <p>{age} years old</p>
                 {isRegistered ? (<p>Registered Student</p) : (<p>Unregistered Student</p>);
                 };
            </div>
         );
       })};  
    </div>
  );
};
export default User;

```  


# 12.6 Object:-  

## App.tsx  

```
// import React from "react";
// import "./App.css";
import User from "./components/User";

const user1 = {
  name: "anisul islam",
  email: "anisul2010s@yahoo.co.uk",
  age: 32,
  isRegistered: true,
  lang: ['Beng','Eng'],
};
const user2 = {
  name: "Rabeya Begum",
  email: "rabu2010s@yahoo.co.uk",
  age: 31,
  isRegistered: false,
  lang: ['Arabic', 'Hindi'],
};

function App() {
  return (
    <div className="App">
      <h1>User Management App</h1>
      <User user={user1} />
      <User user={user2} />
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
    lang: string[];
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
      ) : ( <p>Unregistered Student</p>)
      }
      <p> Speaks: {user.lang.map((language,index)=>{
                    return <span key={index}>{language}</span> ;
              })};
      </p>        
    </div>
  );
};
export default User;

```  
---  
# 13. Union of Types:-  

## App.tsx  
```
import Message from "./components/Message";
function App() {
  return (
    <div className="App">
      <h1>User Management App</h1>
      <Message text ="UPDATE" />
      {/* <User users={users} /> */}
    </div>
  );
}
export default App;
```  

## Message.tsx  

```

// import React from "react";

type MessageProps = {
  text: "ADD" | "UPDATE" | "DELETE";
};

const Message = (props: MessageProps) => {
  if (props.text === "ADD") {
    return <p>User is added</p>;
  } else if (props.text === "UPDATE") {
    return <p>User is updated</p>;
  }
  return <p>User is deleted</p>;
};

export default Message;
```  
# 14. Children Props
# index.js  

```
// import React from "react";
import User from "./components/User";
const userDetails ={
   name: "Md Naj",
    email: "mdnaj@gmail.com",
    age: 36,
    isRegistered: true,
    languages: ["Beng","Eng","Arabic"],
};
const Index =()=>{

     return(
         <div>
             <User user= {userDetails} />
         </div>
     );
} 
export default Index;
```  



## User.tsx

```
// import React from "react";
import Card from "./Card";

type UserProps = {
  user: {
    name: string;
    email: string;
    age: number;
    isRegistered: boolean;
    languages: string[];
  };
};
const User = ({ user }: UserProps) => {
  return (
    <Card>
      <h2>{user.name}</h2>
      <p>{user.email}</p>
      <p>{user.age} years old</p>
      {user.isRegistered ? (
        <p>Registered Student</p>
      ) : (
        <p>Unregistered Student</p>
      )}
      <p>
        Speaks:{" "}
        {user.languages.map((language, index) => {
          return <span key={index}>{language} </span>;
        })}
      </p>
    </Card>
  );
};
export default User;
```  

# Card.tsx  

```
import React from "react";
type CardProps = {
  children: React.ReactNode;
};
const Card = ({children}: CardProps) => {
  return (
        <div className="card">
             {children}
        </div>
  );
};

export default Card;
```  
















