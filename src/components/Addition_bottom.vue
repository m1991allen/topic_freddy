<template>
    <div class="bottom">
        <!-- <a href="https://lihi1.cc/lwxZF"><i class="fas fa-user"></i> 罷免理由</a> -->
        <a href="https://lihi1.cc/x4AHh"><i class="fad fa-vote-nay"></i> 即時開票</a>
        <a href="https://lihi1.cc/JlE12"><i class="fad fa-chart-pie"></i> 罷免門檻</a>
        <a href="https://lihi1.cc/bebPW"><i class="fad fa-rss"></i> 最新新聞</a>
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
    z-index: 999;
}
.bottom a {
    width: 33.3%;
    padding: 1rem;
    color: white;
}

.bottom a:nth-child(1) {
    background-color: #4d4d4d;
}
.bottom a:nth-child(2) {
    background-color: #606060;
}
.bottom a:nth-child(3) {
    background-color: #747474;
}
</style>
