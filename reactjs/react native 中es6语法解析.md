#react native 中es6语法解析

解构赋值

>var {
  StyleSheet,
  Text,
  View
} = React;

这句代码是ES6 中新增的解构(Destructuring)赋值语句。准许你获取对象的多个属性并且使用一条语句将它们赋给多个变量。

上面的代码等价于：

var StyleSheet = React.StyleSheet;
var Text = React.Text;
var View = React.View

再看几个例子，以前，为变量赋值，只能直接指定值:

var a = 1;
var b = 2;
var c = 3;

而ES6 允许这样写：

var [a, b, c] = [1, 2, 3];

更详细的内容可参看： 变量的解构赋值
箭头函数

React Native 里面经常会出现类似的代码:

ES6中新增的箭头操作符 => 简化了函数的书写。操作符左边为输入的参数，而右边则是进行的操作以及返回的值 Inputs=>outputs

举几个栗子感受下：

var array = [1, 2, 3];
//传统写法
array.forEach(function(v, i, a) {
    console.log(v);
});
//ES6
array.forEach(v = > console.log(v));

var sum = (num1, num2) => { return num1 + num2; }
//等同于：
var sum = function(num1, num2) {
    return num1 + num2;
 };

更多详细内容请自行Google，或查看： https://www.imququ.com/post/arrow-function-in-es6.html
延展操作符(Spread operator)

这个 … 操作符（也被叫做延展操作符 － spread operator）已经被 ES6 数组 支持。它允许传递数组或者类数组直接做为函数的参数而不用通过apply。

var people=['Wayou','John','Sherlock'];
//sayHello函数本来接收三个单独的参数人妖，人二和人三
function sayHello(people1,people2,people3){
  console.log(`Hello ${people1},${people2},${people3}`);
}
//但是我们将一个数组以拓展参数的形式传递，它能很好地映射到每个单独的参数
sayHello(...people);//输出：Hello Wayou,John,Sherlock 
//而在以前，如果需要传递数组当参数，我们需要使用函数的apply方法
sayHello.apply(null,people);//输出：Hello Wayou,John,Sherlock

而在 React 中，延展操作符一般用于属性的批量赋值上。在JSX中，可以使用…运算符，表示将一个对象的键值对与ReactElement的props属性合并。

var props = {};
  props.foo = x;
  props.bar = y;
  var component = <Component {...props} />;
  
//等价于
var props = {};
  props.foo = x;
  props.bar = y;
  var component = <Component foo={x} bar={y} />;

它也可以和普通的XML属性混合使用，需要同名属性，后者将覆盖前者：

var props = { foo: 'default' };
var component = <Component {...props} foo={'override'} />;
console.log(component.props.foo); // 'override'

更多详细信息： https://facebook.github.io/react/docs/jsx-spread.html
class

ES6中添加了对类的支持，引入了class关键字（其实class在JavaScript中一直是保留字，目的就是考虑到可能在以后的新版本中会用到，现在终于派上用场了）。JS本身就是面向对象的，ES6中提供的类实际上只是JS原型模式的包装。现在提供原生的class支持后，对象的创建，继承更加直观了，并且父类方法的调用，实例化，静态方法和构造函数等概念都更加形象化。

class PropertyView extends Component {
  render() {
    return (
      <View></View>
    )
  }
}
//等价于
var PropertyView = React.createClass({
  render() {
    return (
      <View></View>
    )
  }
})

方法定义(method definition)

ECMAScript 6中,引入了一种名叫方法定义(method definition)的新语法糖,相对于以前的完整写法,这种简写形式可以让你少写一个function键字.

React.createClass({
  render() {
    return (
      <View></View>
    )
  }
})
//等价于
React.createClass({
  render : function() {
    return (
      <View></View>
    )
  }
})

