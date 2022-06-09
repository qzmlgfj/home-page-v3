<template>
    <n-config-provider :theme="theme">
        <n-layout>
            <n-layout-content id="container">
                <n-grid x-gap="12" :cols="2" id="content">
                    <n-gi>
                        <Profile />
                    </n-gi>
                    <n-gi>
                        <Menu />
                    </n-gi>
                </n-grid>
            </n-layout-content>
        </n-layout>
    </n-config-provider>
</template>

<script>
import { ref, provide } from "vue";
import Profile from "./components/Profile.vue";
import Menu from "./components/Menu.vue";
import {
    NConfigProvider,
    NLayout,
    NLayoutContent,
    NGrid,
    NGi,
    darkTheme,
} from "naive-ui";

export default {
    name: "App",
    components: {
        Profile,
        Menu,
        NConfigProvider,
        NLayout,
        NLayoutContent,
        NGrid,
        NGi,
    },
    setup() {
        // Check current time is in the range of the dark theme.
        let darkThemeFlag =
            new Date().getHours() >= 19 || new Date().getHours() <= 7;
        const theme = ref(darkThemeFlag ? darkTheme : {});

        const changeTheme = ()=>{
            if (darkThemeFlag) {
                theme.value = {};
            } else {
                theme.value = darkTheme;
            }
            darkThemeFlag = !darkThemeFlag;
        }
        provide("changeTheme", changeTheme);

        return {
            theme,
        };
    },
};
</script>

<style>
* {
    box-sizing: border-box;
}

body {
    max-height: 100vh;
    margin: 0;
    font-family: v-mono, v-sans, system-ui, -apple-system, BlinkMacSystemFont,
        "Segoe UI", sans-serif, "Apple Color Emoji", "Segoe UI Emoji",
        "Segoe UI Symbol";
}

#container {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

#content {
    padding-top: 27vh;
    padding-bottom: 25vh;
}

#app {
    width: 100vw;
    max-height: 100vh;
}

@media screen and (max-width: 768px) {
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
}
</style>
