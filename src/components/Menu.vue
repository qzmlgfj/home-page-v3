<template>
    <div class="column">
        <a href="https://github.com/qzmlgfj">
            <button @mouseover="gitMouseOver" @mouseleave="gitMouseLeave">
                <n-icon size="64">
                    <BrandGithub />
                </n-icon>
                <span
                    id="github"
                    :style="{ visibility: gitVisible }"
                    class="animate__animated"
                    :class="{ animate__slideInRight: gitFlag }"
                    >Github</span
                >
            </button>
        </a>
        <a href="https://qzmlgfj.ml/blog/">
            <button @mouseover="blogMouseOver" @mouseleave="blogMouseLeave">
                <svg
                    width="64px"
                    height="64px"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                >
                    <path
                        d="M10.5495 2.53189C11.3874 1.82531 12.6126 1.82531 13.4505 2.5319L20.2005 8.224C20.7074 8.65152 21 9.2809 21 9.94406V19.7468C21 20.7133 20.2165 21.4968 19.25 21.4968H15.75C14.7835 21.4968 14 20.7133 14 19.7468V14.2468C14 14.1088 13.8881 13.9968 13.75 13.9968H10.25C10.1119 13.9968 9.99999 14.1088 9.99999 14.2468V19.7468C9.99999 20.7133 9.2165 21.4968 8.25 21.4968H4.75C3.7835 21.4968 3 20.7133 3 19.7468V9.94406C3 9.2809 3.29255 8.65152 3.79952 8.224L10.5495 2.53189ZM12.4835 3.6786C12.2042 3.44307 11.7958 3.44307 11.5165 3.6786L4.76651 9.37071C4.59752 9.51321 4.5 9.72301 4.5 9.94406V19.7468C4.5 19.8849 4.61193 19.9968 4.75 19.9968H8.25C8.38807 19.9968 8.49999 19.8849 8.49999 19.7468V14.2468C8.49999 13.2803 9.2835 12.4968 10.25 12.4968H13.75C14.7165 12.4968 15.5 13.2803 15.5 14.2468V19.7468C15.5 19.8849 15.6119 19.9968 15.75 19.9968H19.25C19.3881 19.9968 19.5 19.8849 19.5 19.7468V9.94406C19.5 9.72301 19.4025 9.51321 19.2335 9.37071L12.4835 3.6786Z"
                        fill="currentColor"
                    ></path>
                </svg>
                <span
                    id="blog"
                    :style="{ visibility: blogVisible }"
                    class="animate__animated"
                    :class="{ animate__slideInRight: blogFlag }"
                    >Blog</span
                >
            </button>
        </a>
        <a href="mailto:qzmlgfj@gmail.com">
            <button @mouseover="mailMouseOver" @mouseleave="mailMouseLeave">
                <svg
                    width="64px"
                    height="64px"
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 24 24"
                >
                    <path d="M0 0h24v24H0z" fill="none"></path>
                    <path
                        d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10h5v-2h-5c-4.34 0-8-3.66-8-8s3.66-8 8-8 8 3.66 8 8v1.43c0 .79-.71 1.57-1.5 1.57s-1.5-.78-1.5-1.57V12c0-2.76-2.24-5-5-5s-5 2.24-5 5 2.24 5 5 5c1.38 0 2.64-.56 3.54-1.47.65.89 1.77 1.47 2.96 1.47 1.97 0 3.5-1.6 3.5-3.57V12c0-5.52-4.48-10-10-10zm0 13c-1.66 0-3-1.34-3-3s1.34-3 3-3 3 1.34 3 3-1.34 3-3 3z"
                    ></path>
                </svg>
                <span
                    id="mail"
                    :style="{ visibility: mailVisible }"
                    class="animate__animated"
                    :class="{ animate__slideInRight: mailFlag }"
                    >E-mail</span
                >
            </button>
        </a>
    </div>
</template>

<script>
import { BrandGithub } from "@vicons/carbon";
import { NIcon } from "naive-ui";

export default {
    name: "Menu",
    components: {
        BrandGithub,
        NIcon,
    },
    data: function () {
        return {
            gitFlag: false,
            blogFlag: false,
            mailFlag: false,
        };
    },
    methods: {
        gitMouseOver: function () {
            if (this.mobileFlag) {
                this.gitFlag = false;
            } else {
                this.gitFlag = true;
            }
        },
        blogMouseOver: function () {
            if (this.mobileFlag) {
                this.blogFlag = false;
            } else {
                this.blogFlag = true;
            }
        },
        mailMouseOver: function () {
            if (this.mobileFlag) {
                this.mailFlag = false;
            } else {
                this.mailFlag = true;
            }
        },
        gitMouseLeave: function () {
            this.gitFlag = false;
        },
        blogMouseLeave: function () {
            this.blogFlag = false;
        },
        mailMouseLeave: function () {
            this.mailFlag = false;
        },
    },
    computed: {
        gitVisible: function () {
            if (this.mobileFlag) {
                return "visible";
            } else {
                return this.gitFlag ? "visible" : "hidden";
            }
        },
        blogVisible: function () {
            if (this.mobileFlag) {
                return "visible";
            } else {
                return this.blogFlag ? "visible" : "hidden";
            }
        },
        mailVisible: function () {
            if (this.mobileFlag) {
                return "visible";
            } else {
                return this.mailFlag ? "visible" : "hidden";
            }
        },
        mobileFlag: function () {
            return window.matchMedia("(max-width: 768px)").matches
                ? true
                : false;
        },
    },
};
</script>

<style scoped>
.column span{
  font-family: Fira Code;
}
</style>