<template>
    <div class="section" id="recall">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <p>{{ content }}</p>
            <ul>
                <li v-for="item in list" :key="item.id">
                    {{ item }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '罷免門檻',
            content: `依照《公職人員選舉罷免法》第九十條第一項，
罷免投票的通過門檻必須同時符合以下兩條件 ：`,
            list: [
                `（一）有效同意票數多於不同意票。`,
                `（二）同意票數達原選舉區選舉人總數四分之一以上。`,
                `中選會預計1月5日前公布罷免案可投票人數，若以2020年立委選舉台北市第五選區可投票人數24萬4748人估算，罷免案通過門檻為「6萬1187票」。`,
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
