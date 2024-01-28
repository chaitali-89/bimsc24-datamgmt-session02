<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()

//this is my first line in javascript
// console.log("Hello World")

// let name = "Chaitali"
console.log(name)

const doc = document.documentElement;
// console.log(doc)

//change style of the doc from js
doc.style.background = "grey"
doc.style.fontFamily = "monospace"

//access particular elemnts
const nav = document.querySelector('title')
console.log(nav)
nav.innerHTML = "My first Webpageo"
nav.style.fontSize = "12px"


const sidebar = document.getElementById('sidebar')
console.log(sidebar)

//create a form element in the sidebar
let input = document.createElement("input")
input.style.width = "90%"
input.style.fontSize = "20px"
sidebar.appendChild(input)

let submitButton = document.createElement("button")
sidebar.appendChild(submitButton)
submitButton.innerHTML = "Submit"
submitButton.style.fontSize = "6px"


//add elemnts from js
let resetButton = document.createElement("button")
sidebar.appendChild(resetButton)
resetButton.innerHTML = "Reset Button"
resetButton.style.fontSize = "6px"

//create an event when you click the button
submitButton.addEventListener('click', displaytext)
resetButton.addEventListener('click', Refresh)

const main = document.querySelector("main")

function displaytext() {

    let inputText = input.createElement(p)

    main.innerHTML += inputText



}


function Refresh() {
    let inputText = input.value
    main.innerHTML = ""

    // get rid of all the pagragraphs

}

m
</script>



<!-- the template is where the html code goes -->
<template>
    <div id="navbar" class="container">
        <div id="title">David's bootcamp website website</div>
        <div id="logo">



        </div>


    </div>

    <div id="flex">

        <div id="sidebar" class="container"> Sidebar </div>

        <div id="main" class="container">
            <p> input </p>
            <p> </p>


        </div>
    </div>
</template>



<!-- style is where the css code goes -->
<style scoped>
html {

    background-color: rgb(219, 210, 210);
    color: white;
}

body {

    margin: 0;
}

div {

    /* put the borders in the inside of container */
    box-sizing: border-box;
}

img {

    height: 100%;
    width: auto;

}

#navbar {

    height: 50px;
    border-color: red;
    text-decoration-color: aqua;
}

#flex {

    display: flex;

    height: calc(100vh - 50px);
}

#sidebar {

    width: 30%;
    border-color: blue;

}

#main {
    width: 70%;
    border-color: green;

}

#title {
    width: 70%;
    float: left;
}

#logo {
    width: 30%;
    height: 100%;
    float: right;
    text-align: right;

}

.container {

    border-style: dotted;
    border-width: 1px;

}
</style>