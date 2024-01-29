<!-- the script is where the js code goes -->
<script setup>
import { onMounted, ref } from "vue";

const myText = ref("WRITE YOUR HEART OUT");

// coloring 
const colorMain = ref("")
const colorInput = ref("");
const divNameInput = ref("")
var changecolor = null


onMounted(() => {
    changecolor = () => {
        let mySelectedDiv = document.getElementById(divNameInput.value)
        mySelectedDiv.style.background = colorInput.value
        console.log(mySelectedDiv);
        mySelectedDiv.style.width = "90%"
    };
})

onMounted(() => {
    const inputbar = document.querySelector('#textbar');

    // create a form element in the sidebar
    let input = document.createElement("input");
    input.style.width = "90%";
    input.style.fontSize = "12px";
    inputbar.appendChild(input);

    let submitButton = document.createElement("button");
    inputbar.appendChild(submitButton);
    submitButton.innerHTML = "Submit";
    submitButton.style.fontSize = "16px"; // Increased font size for better visibility

    submitButton.addEventListener('click', doSomething);

    const main = document.querySelector("#main");

    function doSomething() {
        let inputText = input.value.trim(); // Trim to remove leading and trailing spaces
        if (inputText) {
            main.innerHTML += `<p>${inputText}</p>`;
            input.value = ""; // Clear the input field after submission
        }
    }







});
</script>

<!-- the template is where the html code goes -->
<template>
    <div id="navbar">
        <p id="title">
            {{ myText }}
        </p>
    </div>

    <div id="flex">
        <div id="sidebar" class="container">
            <div id="textbar">
                <h3>INPUT TEXT</h3>
            </div>

            <div id="colorbar">
                <br />
                <h3>COLOUR </h3>




                <input class="inputbox" v-model="divNameInput" type="text" placeholder="Division: navbar/main/sidebar">
                <br />
                <input class="inputbox" v-model="colorInput" type="text" placeholder="Color">
                <br />
                <button @click="changecolor">
                    Change Color
                </button>

            </div>
        </div>

        <div id="main" class="container">
            <!-- Displaying input text as paragraphs -->
            <p>
            <h3>OUTPUT TEXT </h3>
            </p>
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
    background-color: rgb(203, 240, 239);
    text-align: center;
    text-transform: capitalize;
    box-sizing: border-box;
    border-radius: 20px;
    margin: 1%;
    box-shadow: inset;
    text-size-adjust: 80%;


}

#flex {

    display: flex;

    height: calc(100vh - 50px);
}

#sidebar {

    width: 30%;
    border-color: rgb(95, 95, 95);
    border-radius: 20px;
    text-align: center;
    margin: 0.25%;

}

#main {
    width: 70%;
    border-color: rgb(136, 137, 137);
    border-radius: 20px;
    text-align: center;
    margin: 0.25%;
}

#title {
    width: 100%;
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

.inputbox {
    width: 90%;
    text-align: left;
    margin: auto;
    align-items: center;
}
</style>