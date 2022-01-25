# React面向组件编程

### 模块
```
1.理解：向外提供特定功能的js程序, 一般就是一个js文件

2.为什么要拆成模块：随着业务逻辑增加，代码越来越多且复杂。

3.作用：复用js, 简化js的编写, 提高js运行效率

4.模块化:当应用的js都以模块来编写的, 这个应用就是一个模块化的应用
```

### 组件
```
1.理解：用来实现局部功能效果的代码和资源的集合(html/css/js/image等等)

2.为什么要用组件： 一个界面的功能更复杂

3.作用：复用编码, 简化项目编码, 提高运行效率

4.组件化:当应用是以多组件的方式实现, 这个应用就是一个组件化的应用
```


### class 类式组件 (一般用于复杂类型组件)
``` js
<script type="text/babel">
		//1.创建类式组件
		class MyComponent extends React.Component {
			render(){
				//render是放在哪里的？—— MyComponent的原型对象上，供实例使用。
				//render中的this是谁？—— MyComponent的实例对象 <=> MyComponent组件实例对象。
				console.log('render中的this:',this);
				return <h2>我是用类定义的组件(适用于【复杂组件】的定义)</h2>
			}
		}
		//2.渲染组件到页面
		ReactDOM.render(<MyComponent/>,document.getElementById('test'))
		/* 
			执行了ReactDOM.render(<MyComponent/>.......之后，发生了什么？
					1.React解析组件标签，找到了MyComponent组件。
					2.发现组件是使用类定义的，随后new出来该类的实例，并通过该实例调用到原型上的render方法。
					3.将render返回的虚拟DOM转为真实DOM，随后呈现在页面中。
		*/
	</script>
```

### 函数式组件 (一般用于简单类型组件)
``` js 
<script type="text/babel">
		//1.创建函数式组件
		function MyComponent(){
			console.log(this); //此处的this是undefined，因为babel编译后开启了严格模式
			return <h2>我是用函数定义的组件(适用于【简单组件】的定义)</h2>
		}
		//2.渲染组件到页面
		ReactDOM.render(<MyComponent/>,document.getElementById('test'))
		/* 
			执行了ReactDOM.render(<MyComponent/>.......之后，发生了什么？
					1.React解析组件标签，找到了MyComponent组件。
					2.发现组件是使用函数定义的，随后调用该函数，将返回的虚拟DOM转为真实DOM，随后呈现在页面中。
		*/
	</script>
```


### 组件三大核心属性1: state
```
1.state是组件对象最重要的属性, 值是对象(可以包含多个key-value的组合)

2.组件被称为"状态机", 通过更新组件的state来更新对应的页面显示(重新渲染组件)

3.不能直接修改或更新
```

### 组件三大核心属性2: props
```
1.每个组件对象都会有props(properties的简写)属性

2.组件标签的所有属性都保存在props中

3.通过标签属性从组件外向组件内传递变化的数据

4.注意: 组件内部不要修改props数据
```


### 组件三大核心属性3: refs与事件处理
``` 
```