<template>
    <n-config-provider :theme="theme">
        <n-layout>
            <div class="container">
                <Profile />
                <Menu />
            </div>
        </n-layout>
    </n-config-provider>
</template>

<script>
import Profile from "./components/Profile.vue";
import Menu from "./components/Menu.vue";
import {
    NConfigProvider,
    NLayout,
    darkTheme,
} from "naive-ui";

var SunCalc = require('suncalc');

export default {
    name: "App",
    components: {
        Profile,
        Menu,
        NConfigProvider,
        NLayout,
    },
    data() {
        return {
            isDarktheme: true,
        }
    },
    computed: {
        theme() {
            return this.isDarktheme ? darkTheme : {};
        },
    },
    provide() {
        return {
            changeTheme: () => {
                console.log("changeTheme");
                this.isDarktheme = !this.isDarktheme;
            }
        }
    },
    mounted() {
        navigator.geolocation.getCurrentPosition((position => {
            let times = SunCalc.getTimes(new Date(), position.coords.latitude, position.coords.longitude);
            //return whether the current time is daytime
            this.isDarktheme = !(new Date() > times.sunrise && new Date() < times.sunset);
        }))
    }
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
}

body {
    min-height: 100vh;
    height: 100vh;
    font-family: v-mono, v-sans, system-ui, -apple-system, BlinkMacSystemFont,
        "Segoe UI", sans-serif, "Apple Color Emoji", "Segoe UI Emoji",
        "Segoe UI Symbol";
}

.container {
    height: 80vh;
    width: 100vw;
    padding: 10vh 10vw;
    display: flex;
    align-items: center;
    justify-content: center;
}

.column {
    flex: auto;
    width: 30vw;
}

.menu {
    align-items: flex-start;
}

@media screen and (max-width: 768px) {
    .container {
        min-height: 100vh;
        flex-direction: column;
        align-items: flex-start;
        height: 90vh;
        padding: 1vh 5vw;
        box-sizing: border-box;
    }

    .column {
        width: 90vw;
    }

    .menu {
        width: 60vw;
        margin-left: 20vw;
        margin-right: 20vw;
        box-sizing: border-box;
    }

    .menu .title {
        margin-left: 10vw;
    }

    .menu .btn {
        font-size: 30px;
    }

    .btn:nth-child(3) {
        margin-bottom: 0;
    }
}

/* @media screen and (max-width: 768px) {
    body {
        margin: 0;
        display: inline;
        max-width: 100%;
    }

    html {
        overflow-y: hidden;
    }

    #container {
        margin: 0;
        display: inline;
    }

    .column {
        margin: 2.5%;
        min-width: 90%;
        width: 90%;
    }

    img {
        margin-left: 5%;
    }

    button {
        min-width: 90%;
        margin-left: 10%;
    }
} */
</style>
