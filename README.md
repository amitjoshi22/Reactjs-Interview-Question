# Reactjs-Interview-Question

### 1) Create a React component that renders a list of items from an array of data, and allows the user to filter the list by a search term.

 <b>Solution ➡️</b>
 
 ``` js
//App.js

import React, { useState } from "react";

function App(){
const items = [
    {
      id: 1,
      name: "item1",
      category: "category1",
    },
    {
      id: 2,
      name: "item2",
      category: "category2",
    },
    {
      id: 3,
      name: "item3",
      category: "category1",
    },
    {
      id: 4,
      name: "item4",
      category: "category3",
    },
    {
      id: 5,
      name: "item5",
      category: "category2",
    },
  ];
  
const [search, setSearch] = useState(items);
const [find,setFind] = useState("");

function handleSearch() {
 if (find === "") {
   setSearch(items);
 } else {
   setSearch(
     items.filter(
       (item) => item.name.includes(find) || item.category.includes(find),
     ),
   );
 }
}

function handleClear() {
 setFind("");
 setSearch(items);
}

return(
  <div className="App">
      <h1>React Coding Questions 1</h1>
      <input
       type="text"
       placeholder="Enter search term"
       value={find}
       onChange={(e) => setFind(e.target.value)}
     />
     <button onClick={handleSearch}>Search</button>
     <button onClick={handleClear}>Clear</button>
      {search.map((item)=>(
         <div key={item.id}>
         <p>Name: {item.name}</p>
         <p>Category: {item.category}</p>
         </div>
      ))}
  </div>
);
}

export default App;


```

### 2) Create a React component that renders a form with two input fields (username and password) and a submit button. The form should validate the input fields and display error messages if the input is not valid. The form should also handle the form submission and display a success message if the input is valid.

 <b>Solution ➡️</b>
 
  ``` js
//App.js

import { useState } from 'react';

function App() {

const [username, setUsername] = useState('');
const [password, setPassword] = useState('');

const handleSubmit =(e)=>{
    e.preventDefault()
    if(!username && !password){
      alert('Username and password Required');
    }else if(username=='Amit' && password=='123'){
      alert('Form Submitted');
    }else alert("Form is not submitted!");
    setUsername('')
    setPassword('')
  }

return(
 <div className="App">
 <h1>React Coding Second Questions</h1>
  <div>
     <form onSubmit={handleSubmit} >
      <p><input type='text' placeholder='Enter username' onChange={(e)=>setUsername(e.target.value)} /></p>
      <p><input type='text' placeholder='Enter Password' onChange={(e)=>setPassword(e.target.value)} /></p>
      <button type='submit'>Submit</button>
      </form>
  </div>
 </div>
)

 export default App;


```
