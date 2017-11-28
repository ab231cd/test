# ES6学习笔记
> ECMAScript 6 对js提出了新的规范和标准，多了一些特性和新的语法，早就想学习了，一直找工作理由，今天就从这儿开始。别学别写点文档帮助记忆，难免
有失误不当之处，以后再回头修改完善。

##  Arrows （箭头函数）
 >按我的理解，箭头函数主要是对语法的精简，是代码看起来更简洁,直接demo:
 
~~~
var my = {
	_name: "yh",
	_friends: ["A","B","C"],
	printFriends(){
		this._friends.forEach(
			(f) =>{
				console.log(this._name + " knows " + f);
				console.log(f);
			}
		);
	}
}
my.printFriends();
~~~
## Classes 对象
>es6对对象是完全增强了，增加了析构函数，继承、set，get
~~~
//Classes
class  Book {
	constructor(isbn){
		this.isbn = isbn;
		this.bookName = isbn + '_test';
	}
	get BookName(){
		return this._bookName;
	}
	set BookName(name){
		this._bookName = name;
	}
	showIsbn(){
		console.log(this.isbn);
	}
	//静态变量
	if{
	    
	}
}
//继承
class myBook extends Book{
	constructor(isbn,author){
		super(isbn);
		this.author = author;
	}
	get author(){
		return this._author;
	}
	set author(value){
		this._author = value;
	}
	showBook(){
		console.log(
			this.author,
			this.isbn
		);
	}
}

var book1 = new Book('123456');
console.log(book1);
book1.BookName = '人与自然';
console.log(book1);
console.log(book1.BookName);
console.log('================');

var book2 = new myBook('123456','yh');

book2.showBook();
book2.author = 'yh1';
book2.showIsbn();
book2.showBook();
~~~
## import export 导入导出模块
>node和最新版chrome 暂时都还没有支持（截止2017-11-28），react中已经使用
，通过babel转换
~~~
//output.js
export function output() {
    console.log("OUT: ", arguments);
}
export function output1() {
    console.log("OUT: ", arguments);
}
//in.js
import { out } from 'output.js';
 
out("I'm using output!");

import * as Output from 'output'; // 你也可以忽略 `.js` 后缀
 
Output.out("I'm using output!");
~~~
