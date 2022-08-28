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
yarn dev
```  
# 1.1 To get Functional Component with Typescript snippet  
```
tsrsfc  
```  

```
// home.tsx  
import * as React from "react";

interface IAppProps {
  
}
const App: React.FunctionComponent<IAppProps> =(props)=>{
  return;
};
export default App;

```  

# 2. Type of parameters of an Arrow function(void) that return nothing  
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
# 7. Type of an Arrow function(void) that return nothing  

```
let myFunc:Function;

myFunc=(a:number,b:number):void=>{

   consol.log(a+b);

}

myFunc(10,5);

```  

# 8. Type of Arrow function that return a string  

```
let myFunc:Function;
myFunc =(a:number,b:number):string =>{

   consol.log(a+b);

 return `a is ${a} and b is ${b}`;

}

myFunc(10,5);
```  
# 9.0 Type of Functional Component in NEXT.JS-WITH-TYPESCRIPT:-    

# Type of Functional Components:-  
## IPost.tsx  

```
export interface IPost {

notes: {
  id: number

  title: string

  body: string

}
}
```  
# Or  

```
export type IPost = {

notes: {
  id: number

  title: string

  body: string

}
}
```  

# AddPost.tsx  
```
import * aa React from 'react';  
impoet IPost from '../types
// const AddPost: React.FunctionComponent<type of Props of FC> = (props) => {
const AddPost: React.FC<IPost> = ({ notes }) => {

  const [formData, setFormData] = React.useState<IPost>()

  const handleFormInputFiled = (e: React.FormEvent<HTMLInputElement>): void => {
    setFormData({...formData,[e.currentTarget.id]: e.currentTarget.value})
  }
    return (
      <div>
         <input type='text'
               name='title'
               value ={formData}
               onChange ={handleFormInputField}
               placeholdee ='Enter your title'
               required
               minlength={4}
               maxlength={50}
               
             
             
         />
      <div/>
    
    );
  }

export defoult AddPost;
```  
# 9.1 Type of Functional Component in NEXT.JS-WITH-TYPESCRIPT:-  
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
    setFormData({...formData,[e.currentTarget.id]: e.currentTarget.value,})
  }

export defoult AddPost;
```  

# 9.2 Functional Components:-  
## IPost.tsx
```
interface IPost {

  id: number

  title: string

  body: string

}
```  

## AddPost.tsx  

```

import * as React from 'react';  
import React, {useState,FormEvent,FC} from 'react';

import { IPost } from '../types';

type Props = {

  savePost: (e: FormEvent, formData: IPost) => void

}

const AddPost: React.FunctionComponent<Props> = ({ savePost }) => {

  const [formData, setFormData] = useState<IPost>()

  const handleFormInputFiled = (e: FormEvent<HTMLInputElement>): void => {

    setFormData({

      ...formData,

      [e.target.name]: e.target.value,

    })

  }

export defoult AddPost;

```  


# 9.3 Functional Components:-  

## IPost.tsx

```

interface IPost {

  id: number

  title: string

  body: string

}

```  

## AddPost.tsx  

```

import * as React from 'react';  
import React, {useState,FormEvent,FC} from 'react';

import { IPost } from '../types';

type Props = {

  savePost: (e: FormEvent, formData: IPost) => void

}

const AddPost: React.FC<Props> = ({ savePost }) => {

  const [formData, setFormData] = useState<IPost>()

  const handleFormInputFiled = (e: FormEvent<HTMLInputElement>): void => {

    setFormData({

      ...formData,

      [e.target.name]: e.target.value,

    })

  }

export defoult AddPost;

```  
# 10. Type of variables & constants  
## index.tsx  
```
import React, {useState} from "react";
const Home =()=>{
   const [note,setNote]=useState<{
      id:string,
      title: string,
      text: string, 
      color: string,
      date: string,
   }[]>([{
           id: (new Date).toString(),
           title:"This is Title",
           text:"Lorem100",
           coror:"#09re54",
           date: (new Date).toString(),
       )}]);
   
   return (
      <div>
         <h1> {note.id}</h1>
         <h1> {note.title}</h1>
         <h1> {note.text}</h1>
         <h1> {note.color}</h1>
         <h1> {note.date}</h1>
      </div>
   
   );

};
export default Home;


```  

# OR  

```
import React, {useState} from "react";
interface Note {
  
      id:string,
      title: string,
      text: string, 
      color: string,
      date: string,

}
const Home =()=>{
   const [note,setNote]=useState<Note[]>([{
           id: (new Date).toString(),
           title:"This is Title",
           text:"Lorem100",
           coror:"#09re54",
           date: (new Date).toString(),
       )}]);
   
   return (
      <div>
         <h1> {note.id}</h1>
         <h1> {note.title}</h1>
         <h1> {note.text}</h1>
         <h1> {note.color}</h1>
         <h1> {note.date}</h1>
      </div>
   
   );

};
export default Home;
```  

# Or 
## Note.tsx  

```
export interface Note {
  
      id:string,
      title: string,
      text: string, 
      color: string,
      date: string,

}

```  

```
import React, {useState} from "react";
import Note from "./components/Note";

const Home =()=>{
   const [note,setNote]=useState<Note[]>([{
           id: (new Date).toString(),
           title:"This is Title",
           text:"Lorem100",
           coror:"#09re54",
           date: (new Date).toString(),
       )}]);
   
   return (
      <div>
         <h1> {note.id}</h1>
         <h1> {note.title}</h1>
         <h1> {note.text}</h1>
         <h1> {note.color}</h1>
         <h1> {note.date}</h1>
      </div>
   
   );

};
export default Home;
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
// import React from "react";  

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
# 15. Style Type Props:-

## App.tsx  
```

// import "./App.css";

import Button from "./components/Button";

function App() {
  return (
    <div className="App">
      <Button
        styles={{ backgroundColor: "green", padding: "1rem", color: "white" }}
      />
    </div>
  );
}

export default App;
```  
# Button.tsx  

```

// props for styles -> React.CSSProperties
import React from "react";

type ButtonProps = {
  styles: React.CSSProperties;
};

const Button = (props: ButtonProps) => {
  return (
      <button style={props.styles}>
            click me
      </button>;
  );
};

export default Button;
```  

# 16. Hook type:-  

## 16.1 useState Hooks's Type:-  
## App.tsx  

```
import React, { useState } from "react";
import "./App.css";

const App =()=>{
  const [count,setCount] = useState(0);

  const handleIncrement = (): void => {
    setCount((count) => count + 1);
  };

  const handleDecrement = (): void => {
    setCount((count) => count - 1);
  };

  return (
    <div className="App">
      <h1>Count : {count}</h1>
      <button onClick={handleIncrement}>+</button>
      <button onClick={handleDecrement}>-</button>
    </div>
  );
};
export default App;
```  

## 16.2 Dealing with future values in useState Hook  
## App.tsx  

```
import React, { useState } from "react";
import "./App.css";

type User = {
  id: number;
  name: string;
};

const App = () => {
  // const [data, setData] = useState<null | string>(null);
  const [data, setData] = useState<null | User>(null);

  const handleSetData = () => {
    // setData("Md Naj");
    setData({ id: 1, name: "Md Naj" });
    console.log(data);
  };

  return (
    <div className="App">
      <h1>UseState Future value</h1>
      <button onClick={handleSetData}>set data</button>
      {/* {data && <p>{data}</p>} */}
    <!-- <p>{data?.id}</p> -->
    <!-- <p>{data?.name}</p> -->
    </div>
  );
};

export default App;
```  

## 16.3  Type asertion - without optional chaining operator
## App.tsx  

```
import React, { useState } from "react";
import "./App.css";

type User = {
  id: number;
  name: string;
};

const App = () => {
  // const [data, setData] = useState<null | string>(null);
  const [data, setData] = useState<User>({} as User);

  const handleSetData = () => {
    // setData("Md Naj");
    setData({ id: 1, name: "Md Naj" });
    console.log(data);
  };

  return (
    <div className="App">
      <h1>UseState Future value</h1>
      <button onClick={handleSetData}>set data</button>
      {/* {data && <p>{data}</p>} */}
      <p>{data.id}</p>
      <p>{data.name}</p>
    </div>
  );
};

export default App;
```  

# 16.4. useRef Hook (to collect input value by clicking a button):-  

## App.tsx  

```
import React, { useRef } from "react";
import "./App.css";

const App = () => {
  const inputRef =useRef<null | HTMLInputElement>(null);
  const [datas, setData] = useState<string[]>([]);

  const addData = () => {
    const todo =inputRef.current?.value;
    setData([...datas,todo])
  };
  
  /***
     const addData = () => {
     
          if(inputRef.current){
             const todo =inputRef.current.value;
             setData({...datas,todo})
          };
    };
  
  
  
  ***/

  return (
    <div className="App">
      <input 
          ref={inputRef}
          type='text'
          placeholder='Enter your name'
      
      />
      
      <button onClick={addData}>Add Data</button>
      <ul>
         {
            datas.map((data)=>{
                return(
                   <li key={data}>{data}</li>
                )
            });
         
         
         }
      
      </ul>
      
    </div>
  );
};

export default App;
```  



# 17. onClick Event Type:-  
## App.tsx  

```
  //import React from "react";

  const NewUser = () => {
       const handleClick =(e: React.MouseEvent<HTMLButtonElement>)=>{
           console.log("Hello Click");
        };
    
    return (
      <div>
        <form >
          <div>
            <label htmlFor="name">
              Name
              <input
                type="text"
                id="name"
                name="name"
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
                required
              />
            </label>
          </div>
          <button type="submit" onClick ={handleClick}>Create User</button>
        </form>
      </div>
      );
    };

export default NewUser;
```  
# OR  

## App.tsx  

```
  import React,{ MouseEvent } from "react";

  const NewUser = () => {
       const handleClick =(e: MouseEvent<HTMLButtonElement>)=>{
           console.log("Hello Click");
        };
    
    return (
      <div>
        <form >
          <div>
            <label htmlFor="name">
              Name
              <input
                type="text"
                id="name"
                name="name"
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
                required
              />
            </label>
          </div>
          <button type="submit" onClick ={handleClick}>Create User</button>
        </form>
      </div>
      );
    };

export default NewUser;
```  
# 18. Input Field onChange Event  
# Ajij.tsx  

  ```
  import React, { useState } from "react";

  const NewUser = () => {
  
    const [user, setUser] = useState<{name:string;email:number}>({ name: "", email: "" });
   // const [user, setUser] = useState({ name: "", email: "" });

    const handleInputFieldChange = (e: React.ChangeEvent<HTMLInputElement>) => {

      const fieldName = e.target.name;
      const fieldValue = e.target.value;

      setUser({ ...user, [fieldName]: fieldValue });

    };
    return (

      <div>

        <h2>Create User</h2>

        <form>

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


# 19. onSubmit Event Type, Input onChange Event:-
## Ajij.tsx

  ```
  import React, { useState } from "react";

  const NewUser = () => {
      const [user, setUser] = useState<{name:string;email:number}>({ name: "", email: "" });

    //const [user, setUser] = useState({ name: "", email: "" });

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

# 20. Type of useState , onChange and onSubmit Events :-  

  # Ajij.tsx

  ```
  import React, { useState } from "react";

  type NewUserProps = {

    name: string;

    email: string;

  };

  const NewUser = () => {

    const [user, setUser] = useState<NewUserProps>({ name: "", email: "" });

    const handleInputFieldChange = (e: React.ChangeEvent<HTMLInputElement>) => {

      const fieldName = e.target.name;

      setUser({ ...user, [fieldName]: e.target.value });

    };

    const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {

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


# 21.  Form Action of a Page Ajij.tsx to another Page paySlip.tsx:-

## Ajij.tsx

```
import { useState } from "react";
import {useRouter] from "next/router";
type NewUserProps = {

    name: string;

    age: number;

  };

const Ajij = ({action = '/PaySlip'}) => {
  const router = useRouter();

  const [user, setUser] = useState<NewUserProps>({ name: "", age: "" });

  const handleInputFieldChange = (e: React.ChangeEvent<HTMLInputElement>) => {

    const fieldName = e.target.name;
    const fieldValue = e.target.value

    setUser({ ...user, [fieldName]: fieldValue });

  };  
  
// const {name,age}= user;  

  const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {

    e.preventDefault();

    router.push({
      pathname: action,
      query: {
        // name:name, age:age,
        User:user
      },
   });

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

          <label htmlFor="age">

            Age

            <input

              type="age"

              id="age"

              name="age"

              value={user.age}

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
export default Ajij;
```  

# paySlip.tsx  


```
import {useRouter} from "next/router";
const PaySlip =() =>{
  const router = useRouter();
  const {name,age} = router.query;
  return (
    <div>
      <h1>{name}</h1>
      <h1>{age}</h1>
    </div>
  );
};
export default PaySlip;
```  





