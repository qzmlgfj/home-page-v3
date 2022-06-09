<template>
    <div class="column">
        <n-h1 @click="changeTheme">
            Qzmlgfj
        </n-h1>

        <n-h2>Who's this guy</n-h2>
        A lazy dog from a second-rate university, an undergraduate student.

        <n-h2>Interests</n-h2>
        <n-ul>
            <n-li>
                Enjoy creating new projects and repositories, but never finish
                them.
            </n-li>
            <n-li>Front-end development, just a beginner.</n-li>
            <n-li>Making gadgets.</n-li>
        </n-ul>

        <n-h2>Recent plans</n-h2>
        <n-ul>
            <n-li>Find something interests me.</n-li>
            <n-li
                >Write some introductory articles about Computer Science.</n-li
            >
        </n-ul>
    </div>
</template>

<script>
import {inject} from "vue";
import { NH1, NH2, NUl, NLi } from "naive-ui";

export default {
    name: "Profile",
    components: {
        NH1,
        NH2,
        NUl,
        NLi,
    },
    data: function () {
        return {
            IDIsShaking: true,
            shakingTimes: 0,
        };
    },
    setup() {
        return {
            changeTheme: inject("changeTheme"),
        }
    }
};
</script>