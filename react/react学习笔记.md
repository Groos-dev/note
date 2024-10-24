# react 学习笔记

## 创建组件

``` jsx
function Component() {
    return <>
    // html 标签
    </>
}
```

## hook 函数使用

1. useState
作用：定义数据，当定义的数据改变后会刷新组件
使用：

    ``` js
    import {useState} from "react";
    const [data, setData] = useState(1);

    // 直接被改变数据的值不会改变刷新ui
    data = data + 1;

    // 使用hook返回的函数可以改变数值后能回刷新ui
    setData(data + 1);
    ```

2. useRef
   作用:

   1.  当需要在组件中维护有状态数据，且数据会随着组件初始化而初始化，为了组件刷新时不重新初始化数据，就可以使用useRef
   
    ```jsx
    import {useRef, useState} from "react";
    function Component(){
        const [time, setTime] = useState(new Date().getTime()); 
        let timer = useRef(null);
        // 保证每次组件刷新使用都是同一个timer实例
        function clickHandler(){
           clearInterval(timer.current) 
        }
        timer.current = setInterval(function() {
            setTime(new Date().getTime());
        }, 1000)
        return <>
        <div>{time}</div>
        <button onClick{clickHandler}/>
        </>
    }
    ```
   
   2. Ref 可以和dom元素或组件绑定，直接通过绑定的值操作dom对象
   
   ```jsx
   import {useRef} from "react"
   
   function Demo(){
     return <>
       	<input></input>
       </>
   }
   ```
   
   

## 使用context

场景：嵌套组件或者多组件共享数据

### 创建

```js

    import {createContext} from "react"
    const dataContext = createContext(defaultValue)
    
    export default dataContext;
```

### 使用

```jsx
import {useContext} from "react"
import dataContext from "xxx.js"

function Component() {
    return <>
    <dataContext.Provider value = {defaultValue}>
        <SubComponent/> 
    <dataContext.Provider>
    </>
}

function OtherComponent() {
    const context = useContext(dataContext); 

    return <>

    </>
}

```
