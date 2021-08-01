<template>
    <div id="container">
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
    }
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

body {
    margin: 0;
    min-height: 100vh;
    min-width: 100vw;
    align-items: center;
    display: flex;
    justify-content: center;
}

#app {
    width: 100vw;
    max-height: 100vh;
}

#container {
    height: 100vh;
    width: 75%;
    align-items: center;
    display: flex;
    justify-content: center;
    margin-left: 19%;
}

.column {
    float: left;
    width: 45%;
    margin: 3%;
}

@media screen and (max-width: 768px) {
    body {
        margin: 0;
        display: inline;
    }

    #container {
        margin: 0;
        display: inline;
    }

    .column {
        margin-left: 5%;
        max-width: 85%;
        width: 85%;
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
