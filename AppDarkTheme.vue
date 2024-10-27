<template>
    <div id="app">
        <h1>欢迎来到我的网站</h1>
        <p>这是一个黑夜和白天主题切换的示例。</p>
        <ThemeToggle />
    </div>
</template>

<script>
import ThemeToggle from "@/components/ThemeToggle.vue";

export default {
    components: {
        ThemeToggle,
    },
};
</script>

<style>
/* 在这里定义白天和黑夜的全局样式 */
body.light {
    background-color: #ffffff;
    color: #000000;
}

body.dark {
    background-color: #000000;
    color: #ffffff;
}

#app {
    text-align: center;
    padding: 50px;
    transition: background-color 0.3s ease, color 0.3s ease;
}
</style>
