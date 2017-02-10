# vue-text-editor

   <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/s.png" width="350">
 
       一个vue的文本编辑器组件


## 样式需求库
    1. Bootstrap css
    2. Font awesome css
    
## 使用方法:

1. 导入vue-text-editor-component并在vue组件中加入并使用

   <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/1.png" width="300">

2. 在父组件创建一个初始化对象preLoad并通过v-on父子组件传输的方式传入vue-text-editor

   <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/2.png" width="300">

## preLoad初始化对象:

### article: 包含(title,content,category) 默认为空, 可传入已有内容进行编辑
    
  * title: 标题
        
  * content: 内容
        
  * category: 选择分类(如hasCategory为false则不显示)

<br /><br />
### hasCategory: 是否显示文章分类(默认为false)

<br /><br />
### categoryList: 可供选择的文章分类列表 (默认为空)

<br /><br />
### submit: 提交函数, 可传入一个用作保存的函数, 当点击提交时将会使用这个函数

##### 将会传回两个函数, (1. 返回的数据 2. 一个用于调用自身结果显示的函数) 第二个不是必要, 所以需要提供至少一个参数作为返回的数据

* 参数1: 将会返回编辑后的标题(title), 编辑后的内容(content), 如果hasCategory为true则将会返回编辑后的分类(category)
* 参数2: 一个回调函数, 可以用来触发编辑器自身的结果显示功能

         onResult("结果内容","error") 显示错误信息
         
         onResult("结果内容","success") 显示成功信息


  <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/4.png" width="400">
  
  

#### 一个submit的例子


  <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/5.png" width="300">


      data为返回的数据, 通过Object.assign()与原本组件的数据进行合并并提交.
      
      onResult为显示结果的回调函数, 通过将返回的result传回editor进行显示. 
      
<br /><br />
### cancel: 取消函数, 可传入一个用作取消的函数, 当点击取消时将会使用这个函数
   

## 在vue-text-editor中加入自定义内容

    vue-text-editor在标题与文本样式按钮栏之中提供了一个slot (也可以自己添加/修改)
    
    通过这个slot可以在两者之间添加任何自定义的内容, 但是submit并不会返回这些内容的数据, 所以需要在父组件中自行绑定这些内容
    
    
#### 一个包含checkbox自定义内容的vue-text-editor
    <br />
    <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/s.png" width="350">
    <br />
    <img src="https://github.com/yyss8/vue-text-editor-component/blob/master/screenshots/6.png" width="400">
