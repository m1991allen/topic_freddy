<template>
    <div class="section" id="porcess">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <div>
                <h4>2021年</h4>
                <ul>
                    <li v-for="(item, index) of list21" :key="index">
                        <span>{{ list21[index].date }}</span>
                        <p>{{ list21[index].project }}</p>
                    </li>
                </ul>
                <h4>2022年</h4>
                <ul>
                    <li v-for="(item, index) of list22" :key="index">
                        <span>{{ list22[index].date }}</span>
                        <p>{{ list22[index].project }}</p>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '罷免程序',
            list21: [
                {
                    date: '12月3日',
                    project: '罷免案成立之宣告',
                },
                {
                    date: '12月13日',
                    project: '被罷免人提出答辯書',
                },
                {
                    date: '12月16日',
                    project: '發布罷免公告',
                },
                {
                    date: '12月20日',
                    project: '投票人名冊編造完成',
                },
                {
                    date: '12月30日至1月8日',
                    project: '辦理公辦電視罷免說明會',
                },
            ],

            list22: [
                {
                    date: '1月5日前',
                    project: '公告罷免投票人人數',
                },
                {
                    date: '1月9日',
                    project: '投票、開票',
                },
                {
                    date: '1月14日前',
                    project: '審定罷免投票結果',
                },
                {
                    date: '1月14日',
                    project: '公告罷免投票結果',
                },
            ],
        }
    },
}
</script>

<style scoped>
.section-box div {
    padding: 1rem;
    text-align: center;
}

ul {
    display: inline-block;
    max-width: 390px;
    width: 100%;
}

ul li {
    width: 100%;
    margin-bottom: 2rem;
    text-align: center;
    padding: 1rem;
    position: relative;
    background-color: #ededed;
    border-radius: 10px;
}

ul li::after {
    content: '|';
    position: absolute;
    bottom: -25px;
}

ul li:nth-last-child(1)::after {
    content: '';
}

ul li span {
    display: inline-flex;
    text-align: center;
    margin: 0 0.3rem;
    display: block;
}

ul li p {
    text-align: center;
    margin: 0;
}

h4 {
    text-align: center;
    font-size: 1.6rem;
}
</style>
