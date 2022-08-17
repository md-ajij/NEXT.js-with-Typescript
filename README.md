# NEXT.js-with-Typescript  
---  
# To create NEXT app with Typescript:-  
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
# Arrow function(void) that return nothing  
```
const myFunc=(a:number,b:number):void=>{
   consol.log(a+b);
}

myFunc(10,5);
```  
# Arrow function(sting) that return a sting  

```

const myFunc=(a:number,b:number):string =>{

   consol.log(a+b);
 return `a is ${a} and b is ${b}`;
}

myFunc(10,5);
```  

# Normal function(void) that return nothing  

```

function myFunc(a:number,b:number):void {

   consol.log(a+b);

}

myFunc(10,5);

```  
# Normal function(sting) that return a sting  

```

function myFunc(a:number,b:number):string {

   consol.log(a+b);

 return `a is ${a} and b is ${b}`;

}

myFunc(10,5);

```  
# Type of  Arrow function(void) that return nothing  

```

const myFunc:Function =(a:number,b:number):void=>{

   consol.log(a+b);

}

myFunc(10,5);

```  

# Type of Arrow function(sting) that return a sting  

```

const myFunc:Function =(a:number,b:number):string =>{

   consol.log(a+b);

 return `a is ${a} and b is ${b}`;

}

myFunc(10,5);


