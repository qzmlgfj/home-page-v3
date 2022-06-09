<template>
    <n-grid y-gap="48" :cols="1" id="Menu">
        <n-gi>
            <n-button
                text
                style="font-size: 32px"
                tag="a"
                href="https://github.com/qzmlgfj"
            >
                Github
            </n-button>
        </n-gi>
        <n-gi>
            <n-button
                text
                style="font-size: 32px"
                tag="a"
                href="https://blog.qzmlgfj.ml/"
            >
                Blog
            </n-button>
        </n-gi>
        <n-gi>
            <n-button
                text
                style="font-size: 32px"
                tag="a"
                href="mailto:qzmlgfj@gmail.com"
            >
                E-Mail
            </n-button>
        </n-gi>
    </n-grid>
</template>

<script>
import { NButton, NGrid, NGi } from "naive-ui";

export default {
    name: "Menu",
    components: {
        NButton,
        NGrid,
        NGi,
    },
};
</script>

<style scoped>
a {
    text-decoration: none;
    display: inline-block;
}

#Menu {
    margin-top: 20%;
    margin-left: 30%;
}
</style>