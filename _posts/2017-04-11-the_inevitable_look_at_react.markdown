---
layout: post
title:  "The inevitable look at REACT."
date:   2017-04-11 12:29:53 +0000
---


https://2old2code.wordpress.com/

The inevitable look at REACT.
As I start to scratch the surface with REACT,  I sketched out a few points for myself that I would like to either review or thought would be worth noting for reference.

Using JSX and the need for an single outermost element
Sandbox testing behavior of rendering elements with functions and props
Noting REACTS use of the Virtual DOM and updating nodes in the DOM only when they change.
JSX REQUIRES A SINGLE OUTERMOST ELEMENT

React is a very powerful framework. One of the main syntax challenges to get use to is the use of JSX over html.

On several occasions while working with content and building up an JSX expressions I would have several level of tags. However, it requires only one outermost element.

Although this like valid HTML it will throw an error in REACT

var sentences = (

<p>Some stuff to say.</p>

<p>More stuff to say</p> );
IN order to create an single outermost element adding

when there are several unique elements is a key rule to remember. Code corrected to make above compliant.

 

var sentences = (

<div id=“outermost-element-id”>

<p>Some stuff to say.</p>

<p>More stuff to say.</p>

</div> );
 

Building out and messing around with React components.

const numbers = [1, 2, 3, 4, 5];

const PlainNumber = (props) => {
return (

{props.numbers.map((number) => (
{number}
))}
</div>
)
}

const DoubleNumber = (props) => {
return (

{props.numbers.map((number) => (
{number * 2}
))}
</div>
)
}

const App = () => {
return (

Plain

Double

)
}

ReactDOM.render(
<App />,
document.getElementById(‘root’)
);

Renders the following results:

Plain

1
2
3
4
5
Double

2
4
6
8
10
This was a small lesson on seeing how breaking components into pieces can simplify data. The original array is the source data and manipulating as a double is a second action to be handled separately.
VIRTUAL DOM and DOM

Document Object Model

REACT use of Virtual DOM to updates the DOM elements on a need basis(only when an element changes) is one of the main advantages in it speed and efficiencies.

The HTML DOM Tree of Objects

DOM HTML tree https://www.w3schools.com/js/js_htmldom.asp
 

In summary, here’s what happens when you try to update the DOM in React:

The entire virtual DOM gets updated.
The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
The changed objects, and the changed objects only, get updated on the real DOM.
Changes on the real DOM cause the screen to change.
https://www.codecademy.com/articles/react-virtual-dom
