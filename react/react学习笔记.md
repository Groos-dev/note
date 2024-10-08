# react 学习笔记

## 创建组件

``` jsx
function Component() {
    return <>
    // html 标签
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
