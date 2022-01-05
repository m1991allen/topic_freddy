<template>
    <div class="section" id="recall">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <p>{{ content }}</p>
            <ul>
                <li v-for="item in list" :key="item.id" v-html="item"></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '罷免門檻',
            content: `依照《公職人員選舉罷免法》第九十條第一項， 罷免投票的通過門檻必須同時符合以下兩條件 ：`,
            list: [
                `（一）有效同意票數多於不同意票。`,
                `（二）同意票數達原選舉區選舉人總數四分之一以上。`,
                `根據台北市選委會公布罷免案投票人數，總計人數為23萬5024人，罷免門檻為<span style="font-weight:bolder;">5萬8756票</span>。`,
            ],
        }
    },
}
</script>

<style scoped>
.section-box {
    max-width: 600px;
}
</style>
