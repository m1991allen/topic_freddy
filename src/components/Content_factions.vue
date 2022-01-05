<template>
    <div class="section" id="factions">
        <h3>{{ title }}</h3>
        <div class="section-box flex">
            <div class="part1">
                <h4>反對罷免</h4>
                <div v-for="(person, index) of talk_a" :key="index">
                    <figure class="flex">
                        <img :src="person.img" :alt="person.name" />
                        <figcaption>{{ person.name }}</figcaption>
                    </figure>
                    <div class="speech">
                        <span></span>
                        <p>{{ person.speech }}</p>
                    </div>
                </div>
            </div>

            <div class="part2">
                <h4>贊成罷免</h4>
                <div v-for="(person, index) of talk_b" :key="index">
                    <figure class="flex">
                        <img :src="person.img" :alt="person.name" />
                        <figcaption>{{ person.name }}</figcaption>
                    </figure>
                    <div class="speech">
                        <span></span>
                        <p>{{ person.speech }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '各方說法',
            // 反對
            talk_a: [
                {
                    name: '副總統 賴清德',
                    speech: `林昶佐不只關心內政與地方建設，更關心國防、外交，是國際級的立法委員，拜託大家一定要投下「不同意」罷免，用手中神聖的選票，終止惡質的罷免文化。`,
                    img: require('../assets/賴清德.png'),
                },
                {
                    name: '中二選區立委候選人 林靜儀',
                    speech: `林昶佐委員在立法院推動開放國會、民主外交；在中正萬華致力疫後振興、經濟復甦，優秀的立委如今卻要面臨報復性罷免。我相信為了下一代、為守護台灣未來發展而努力的人們，一定會贏過只想拖垮台灣的人。Freddy加油，我們全力以赴，守護民主！`,
                    img: require('../assets/林靜儀.png'),
                },
                {
                    name: '民進黨立委 賴品妤',
                    speech: `昶佐委員對台灣、對人權、對中正萬華區的努力付出，不僅獲得公督盟評鑑6次優秀立委的殊榮，亦受到地方民代、鄉親的肯定，更受邀參加美國總統拜登舉辦的「民主峰會」場邊會，是唯一亞洲代表！呼籲大家團結起來，終結報復性罷免，拒絕傷害台灣民主，投下反對票。`,
                    img: require('../assets/賴品妤.png'),
                },
            ],
            // 贊成
            talk_b: [
                {
                    name: '台北市議員 鍾小平',
                    speech: `罷免萬華叛徒林昶佐，是許多萬華人的心聲，許多在地民眾反應林昶佐不跑基層、沒有服務，反對公開3+11會議記錄，不讓萬華人看到疫情破口的真相，都重重傷了萬華人的心。希望大家能夠團結，完成罷免的最終目標，讓萬華人再次驕傲。`,
                    img: require('../assets/鍾小平.png'),
                },
                {
                    name: '前台北市議員 童仲彥',
                    speech: `林昶佐的錯罄竹難書，包括「讓學生吃萊豬」、「火燒萬華炒死人」、「滿滿標案不住選區」、「 假台獨意識型態誤國」、「 利用疫情圖謀政治不軌」。無論是政治老前輩林郁方委員，或者是擺攤做法律服務的徐立信議員，甚至是藍綠各黨各派的議員、政治人物或後起之秀，讓我們團結起來，為中正萬華討公道。`,
                    img: require('../assets/童仲彥.png'),
                },
            ],
        }
    },
}
</script>

<style scoped>
h4 {
    text-align: right;
    font-size: 1.2rem;
    font-weight: 900;
    background-color: rgb(158, 158, 158);
    padding: 10px;
    color: white;
    border-radius: 0 10px 0px 0;
}

figure {
    text-align: left;
    margin-top: 2rem;
}
figure img {
    max-width: 100px;
    text-align: left;
}
figure figcaption {
    font-size: 1.3rem;
    font-weight: bolder;
    margin: 0 0 1rem 1rem;
}

.speech p {
    text-align: left;
    line-height: 1.8rem;
    background-color: #ffffff;
    padding: 1rem;
    margin: 0;
    border-radius: 10px;
}

.speech span {
    display: block;
    width: 0;
    height: 0;
    border-style: solid;
    border-width: 30px 0 0 30px;
    border-color: transparent transparent transparent #ffffff;
    transform: translateX(60px);
}

.section-box {
    max-width: 500px;
}

.section-box .part1 {
    background-color: #ededed;
    padding: 1rem;
    border-radius: 10px;
    margin-bottom: 2rem;
}

.section-box .part2 {
    background-color: #ededed;
    padding: 1rem;
    border-radius: 10px;
    margin-top: 2rem;
}

#factions .flex {
    display: flex;
    align-items: center;
    max-width: 100%;
}

.part1,
.part2 {
    width: 50%;
    margin: 1rem;
}

@media screen and (max-width: 768px) {
    #factions .flex {
        display: block !important;
    }

    .part1,
    .part2 {
        width: 100%;
        margin: 0px;
    }
}
</style>
