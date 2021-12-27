<template>
    <div class="bottom">
        <a href="#reason"><i class="fas fa-user"></i> 罷免理由</a>
        <a href="#recall"><i class="fad fa-chart-pie"></i> 罷免門檻</a>
        <a href="#news"><i class="fad fa-rss"></i> 相關新聞</a>
        <!-- <i class="fad fa-vote-nay"></i> -->
    </div>
</template>

<script>
export default {}
</script>

<style>
.bottom {
    display: flex;
    position: fixed;
    bottom: 0;
    width: 100%;
    background-color: #4d4d4d;
    z-index: 999;
}
.bottom a {
    width: 33.3%;
    padding: 1rem;
    color: white;
}
</style>
