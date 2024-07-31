<template>
    Hello, World!
</template>

<script setup lang="ts">
import { useMessage } from "naive-ui";
import { onMounted } from "vue";

const message = useMessage();
const notify = async (title: string, body: string) => {
    if (!("Notification" in window)) {
        message.warning("浏览器不支持通知");
        return;
    }

    if (Notification.permission !== "granted") {
        const permission = await Notification.requestPermission();
        if (permission !== "granted") {
            message.warning("请允许通知");
            return;
        }
    }

    const notification = new Notification(title, { body });
    notification.onclick = (event) => {
        console.log(event);
        notification.close();
    }
}

onMounted(() => {
    notify("Hello", "World");
})
</script>