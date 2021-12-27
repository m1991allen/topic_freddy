<template>
    <div class="main">
        <h1>{{ title }}</h1>
        <a href="#voting">
            <picture>
                <source srcset="../assets/banner_mobile.jpg" media="(max-width: 768px)" />
                <img src="../assets/banner_desktop.jpg" alt="林昶佐罷免案" />
            </picture>
        </a>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '林昶佐罷免案',
            date: '10/23',
            subtitle: '開票、門檻一次看',
        }
    },
}
</script>

<style scoped>
/* 背景桌機版設定 */
.main h1 {
    font-size: 5rem;
    color: white;
    left: -99999;
    position: absolute;
    z-index: -9999;
}
</style>
