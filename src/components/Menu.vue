<template>
    <div class="column menu">
        <n-button class="btn" size="large" text tag="a" href="https://github.com/qzmlgfj">
            <div class="btn-content">
                <n-icon size="30px">
                    <github />
                </n-icon>
                <span class="title">Github</span>
            </div>
        </n-button>
        <n-button class="btn" text tag="a" href="https://blog.antrol.xyz/">
            <div class="btn-content">
                <n-icon size="30px">
                    <home />
                </n-icon>
                <span class="title">Blog</span>
            </div>
        </n-button>
        <n-button class="btn" text tag="a" href="mailto:qzmlgfj@gmail.com">
            <div class="btn-content">
                <n-icon size="30px">
                    <email />
                </n-icon>
                <span class="title">E-Mail</span>
            </div>
        </n-button>
    </div>
</template>

<script>
import { NButton, NIcon } from "naive-ui";
import { Github } from "@vicons/fa";
import { Home,Email } from "@vicons/carbon";

export default {
    name: "Menu",
    components: {
        NButton,
        NIcon,
        Github,
        Home,
        Email,
    },
};
</script>

<style scoped>
a {
    text-decoration: none;
}

.menu {
    display: flex;
    flex-direction: column;
}

.btn {
    font-size: 36px;
    margin-bottom: 5vh;
}

.btn-content {
    display: flex;
    align-items: center;
}

.title {
    margin-left: 2vw;
}
</style>