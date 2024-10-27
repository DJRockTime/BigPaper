<template>
    <div id="app">
        <h1 :style="{ color: textColor }">欢迎来到我的网站</h1>
        <div class="avatar" :style="{ backgroundColor: avatarColor }">
            用户头像
        </div>

        <!-- 颜色选择器 -->
        <input type="color" v-model="colorInput" @input="updateColors" />

        <!-- 文本输入框 -->
        <input
            type="text"
            v-model="colorInput"
            placeholder="输入颜色值（如 #ff0000）"
            @input="updateColors"
        />

        <button @click="updateColors">更新颜色</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            colorInput: "#ff0000", // 默认颜色
            textColor: "#000000", // 主题文字颜色
            avatarColor: "#ff0000", // 头像背景颜色
        };
    },
    methods: {
        updateColors() {
            // 验证输入的颜色值是否有效
            const isValidColor = /^#([0-9A-F]{3}|[0-9A-F]{6})$/i.test(
                this.colorInput,
            );
            if (isValidColor) {
                this.avatarColor = this.colorInput; // 更新头像背景颜色
                this.textColor = this.colorInput; // 更新主题文字颜色
            } else {
                alert("请输入有效的颜色值，例如 #ff0000");
            }
        },
    },
};
</script>

<style>
#app {
    text-align: center;
    padding: 50px;
}

.avatar {
    width: 100px;
    height: 100px;
    margin: 20px auto;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #ffffff;
    border-radius: 50%;
}
</style>
