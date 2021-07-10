<template>
    <div id="app">
        <Profile />
        <Menu />
    </div>
</template>

<script>
import Profile from "./components/Profile.vue";
import Menu from "./components/Menu.vue";

export default {
    name: "App",
    components: {
        Profile,
        Menu,
    },
};
</script>

<style>
@import url(https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css);

@font-face {
    font-family: "Fira Code";
    src: url("https://qzmlgfj.ml/Fonts/FiraCode-Regular.woff") format("woff"),
        url("https://qzmlgfj.ml/Fonts/FiraCode-Regular.ttf") format("ttf");
}

* {
    box-sizing: border-box;
}

html {
    height: 100%;
    width: 100%;
}

body {
    margin: 0;
    min-height: 100%;
    min-width: 100%;
    align-items: center;
    display: flex;
    justify-content: center;
}

#app {
    min-width: 90%;
    align-items: center;
    display: flex;
    justify-content: center;
    margin-left: 8%;
}

.column {
    float: left;
    width: 50%;
    margin: 2.5%;
}

button {
    border: none;
    outline: none;
    width: 70%;
    height: 75px;
    transition: all 0.5s;
    cursor: pointer;
    margin-bottom: 5%;
    background-color: white;
    align-items: center;
    display: flex;
}

a {
    text-decoration: none;
}

#mail {
    font-size: 250%;
    margin-left: 24%;
    visibility: hidden;
}

#blog {
    font-size: 250%;
    margin-left: 27%;
    visibility: hidden;
}

#github {
    font-size: 250%;
    margin-left: 22%;
    visibility: hidden;
}

@media screen and (max-width: 768px) {
    body {
        margin: 0;
        min-width: 120%;
        display: inline;
    }
    #app {
        margin: 0;
        min-width: 110%;
        display: inline;
    }
    .column {
        margin-left: 5%;
        margin-right: 5%;
        min-width: 90%;
    }
    img {
        margin-left: 5%;
    }
    button {
        min-width: 90%;
        margin-left: 10%;
    }
}
</style>
