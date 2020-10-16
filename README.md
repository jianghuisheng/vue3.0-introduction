# vue3-project

## Project setup

```
yarn install
```

### Compiles and hot-reloads for development

```
yarn serve
```

### Compiles and minifies for production

```
yarn build
```

### Lints and fixes files

```
yarn lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

### 函数式

setup()启动 二个函数
setup(props,context)
setup(props,{root}){}
setup 无法用 this

var a1 = [1,2,3]
var a2 = [4,5]
var a3 = [...a1,...a2]

var o1 = {id:1}
var o2 = {name:'abc'}
var o3 = {...o1,...o2} // {id:1,name:'abc'}
var o4 = {...01,o2}
