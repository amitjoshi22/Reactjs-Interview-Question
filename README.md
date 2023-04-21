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

return(
  <div className="App">
      <h1>React Coding Questions 1</h1>
      {search.map((item)=>(
         <div key={item.id}>
         <p>{item.name}</p>
         <p>{item.category}</p>
         </div>
      ))}
  </div>
);
}

export default App;


```
