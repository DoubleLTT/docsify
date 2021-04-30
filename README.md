# travel travel yunNan
go go go
- 5.1 7:35-15:30 CD East(6:20 - 7:00)->DaLi->hotel   
yueManXiLou、xiZhouGuZhen、daLi ancient city(night)
- 5.2 ErHai Lake
- 5.3 DaLi->KunMing
- 5.4 7:25-9:00 Kunming->CD

<!-- ![alt dali](dali.png) -->

| title | title | title |
| ----  | ----  | ----  |
| grid  | grid  | grid  |   

>git语句  
- 查看远程仓库地址 git remote -v
- 更改commit信息 git commit --amend -m "reset commits"
- 上次commit撤回 git reset HEAD~1       

>闭包：是一种私有变量保护机制。目的：保护函数中私有变量不受外界干扰。实现原理：形成一个不销毁栈环境。 

Promise &&  await
> Promise是ES6提供的类，可以更加优雅编写复杂的异步任务，是一种更好的编程风格，并不是把异步转换成同步
```javascript
new Promise(function(resolve, reject){
    console.log(1);
    resolve(2);
}).then(function(val) {
    console.log(val);
    return 3
})
console.log('end');
//打印顺序：1 'end' 2
//若promise内函数为异步，则打印'end' 1 2
```
> await指令在异步函数async function中使用，await指令后必须跟一个Promise。
```javascript
async function fun(){
    await new Promise(function(resolve, reject){
        resolve('value')
    })
    console.log('end')
}
```
> ES模块是一种JavaScript代码重用机制。  
其他模块化方式有：AMD、UMD、CommonJS（nodeJS采用） 
      
早期通过script标签引入js文件，当项目越来越庞大时，这种方式就会出现问题：
- js文件作用域都是顶层，会造成变量污染
- js文件引入有顺序问题，引入顺序出错则代码会报错  

ES模块化的出现就是为了解决以上问题
- 解决变量污染：每个文件都是独立作用域，不存在变量污染
- 解决文件依赖：一个文件里面可以清楚看到依赖了哪些其他文件  

CommonJS和ES Module的区别   
- commonJS可以动态加载语句，代码发生在运行时     
  ES是静态的，不可动态加载语句（如下），只能声明在该文件顶部，代码发生在编译时
  ```javascript
  //if(true){
     //import {name} from 'xxx';报错
  //}
  ```   
- commonJS导出值是拷贝，可以修改导出的值（缺点：代码出错时不好排查引起变量污染）   
  ES导出是引用值，是可读的但不能修改
> WebSocket：是Html5提供的一种在单个TCP连接上进行双工通讯的协议   
   
  使客户端和服务器之间数据交换变得更简单，允许服务端<font color="orange" size=4>主动</font>向客户端推送数据    

> VUE2 && VUE3  
- 脚手架名称 
 vue2: npm install -g vue-cli   
 vue3: npm install -g @vue/cli
- 创建项目
 vue2: npm init  hello-vue2  
 vue3: vue create hello-vue3    
- 运行    
 npm run serve
- 实例化区别       
```javascript
new Vue({          //VUE2
 //选项
});

Vue.createApp({     //VUE3
 //选项
})
```
- 挂载区别
```javascript
new Vue({          //VUE2
 el:'#id'
});

Vue.createApp({     //VUE3
 //选项
}).mount('#id')
``` 
- v-if和v-show区别 
 相同点：控制元素显示隐藏   
 不同点：   
 （1）实现方法不同  
    v-show 通过控制css样式display:none,控制隐藏   
    v-if   动态向DOM树内添加或删除DOM元素   
 （2）性能比较
    v-show 只编译一次，性能更好   
    v-if 不停销毁创建
 （3）适用场景
    v-show 适用需要频繁切换的节点，无论true或false初始都会渲染，因此初始开销大，但切换时开销小   
    v-if 适用于不需要频繁切换的节点，初始为false不会渲染（懒加载），因此初始开销小，切换是开销大
>JS
- 判断数据类型    
  ①typeof 引用数据类型（array、object)和基础数据类型(null)会被判断为<font color="red">object</font> 
  ②instanceof 只能正确判断引用数据类型，而不能判断基本数据类型   
```javascript
typeof [];  //object
typeof {};  //object
typeof null;  //object

console.log([] instanceof Array); //true
console.log({} instanceof Object); //true
console.log(true instanceof Boolean); //false
```    
> 正则表达式 
    
1、匹配字符或字符串在某个位置出现   
```javascript
/a/.test('javascript'); //true
/script/.test('javascript'); //true
``` 
2、匹配以字符串开头，开始位置标识：<font color="orange">^</font>
```javascript
/^a/.test('javascript'); //false
/^java/.test('javascript'); //true
```
3、匹配以字符串结尾，结束位置标识：<font color="orange">$</font>
```javascript
/a$/.test('javascript'); //false
/script$/.test('javascript'); //true
```
4、匹配字符：<font color="orange">[ ]</font> 只要包含某一字符就匹配
```javascript
/[ab]/.test('ace'); //true 包含a或b就匹配
```
5、匹配字符串：<font color="orange">|</font> 只要包含某一字符串就匹配
```javascript
/abc|xyz/.test('aabbxyz'); //true 包含字符串xyz
```
6、不含字符：<font color="orange">[^a]</font> 只要字符串中有不是这个<font color="red">集合</font>里面的字符
```javascript
//①含非a的字符
/[^a]/.test('aaa'); //false 
/[^a]/.test('abc'); //true  
/[^abc]/.test('abcabc');//含非abc的字符? => false
//②以非a字符开始
/^[^a]/.test('javascript'); //true 
/^[^a]/.test('abc'); //false
//③以非a字符结尾
/[^a]$/.test('javascript');  //true
/[^a]$/.test('cba'); //false
```
7、前瞻：匹配字符串中前面部分，<font color="orange">exp1(?=exp2)</font>
```javascript
/java(?=script)/.test('javascript'); //true 匹配script前面部分是java
/java(?=script)/.test('java123script'); //false 
//和直接匹配字符串的区别：括号内可替换表达式
/script(?=[\d+])/.test('123script123java'); //true 匹配数字前面的script字符  '\d':匹配数字； '/d+':匹配一个或多个数字
```
8、后顾：匹配字符串后面部分，<font color="orange">(?<=exp2)exp1</font>
```javascript
/(?<=java)script/i.test('12javascript345') //true 匹配java后面部分是script并不论大小写
```
9、负前瞻：匹配<font color="red">一个</font>位置，这个位置后面不是某字符串，<font color="orange">exp1(?!exp2)</font>
```javascript
/java(?!script)/.test('javascript javaee typescript') //true
```
10、负后顾：匹配<font color="red">一个</font>位置，这个位置前面不是某字符串，<font color="orange">(?<!exp2)exp1</font>
```javascript
/(?<!java)script/.test('javascript javaee typescript') //true
```
