Lambda 本质上是一种匿名方法，没有方法名，没有访问修饰符，没有返回值类型

1. 使用前配置 app/build.gradle

```js
	android {
		defaultConfig{
			...
			jackOptions.enabled = true
		}
		compileOptions {
        	sourceCompatibility JavaVersion.VERSION_1_8
        	targetCompatibility JavaVersion.VERSION_1_8
    	}
	}


```

2. 使用方法

当某个接口仅有一个待实现方法，都可使用 lambda 代替创建传统的匿名内部类方法

例1 ：

```java

new Thread(new Runnable(){
	public void run(){

	}
});
```

用Lambda表达式就可以写成

```java
new Thread(()->{
	// run方法内部的实现
});

```
可以看出  ()->{...}  实现了创建匿名内部类，以及方法的重写


例2：

```java
Runnable runable = new Runnable(){
	@Override
	public void run(){

	}
}


用Lambda 代替：

Runnable runnable = ()->{

}
```

例3： 含参数的Lambda表达式


```java

button.setOnClickListener(new View.OnClickListener(){
	@Override
	public void onClick(View v){
		...
	}
});


用Lambda 表达式
button.setOnClickListener((String v)->{

});

或者省略类型声明：
button.setOnClickListener((v)->{

});

当只有一个参数时，可以省略括号：
button.setOnClickListener( v ->{

});

```
