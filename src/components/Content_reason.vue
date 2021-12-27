<template>
    <div class="section" id="reason">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <p>{{ reason }}</p>
            <ul>
                <li v-for="(item, index) of list" :key="index">
                    {{ list[index].title }}
                    <p>
                        {{ list[index].content }}
                    </p>
                </li>
            </ul>
            <hr />
            <p>{{ description }}</p>
            <ul>
                <li v-for="(item, index) of ans_list" :key="index">
                    {{ ans_list[index] }}
                </li>
            </ul>
            <a href="https://bit.ly/3msx5Wr" target="_blank"><i class="fas fa-file-export"></i> 完整答辯書連結</a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '罷免理由',
            reason: '提議人之領銜人楊文元先生提出之罷免理由書如下：',
            list: [
                {
                    title: '（一）無心地方服務，承諾政見一再跳票：',
                    content: '針對台中火力發電廠、台中空氣品質、於台灣各地廣設服務處等議題',
                },
                {
                    title: '（二）無心監督民意所託，背離選區民意：',
                    content: '針對萊克多巴胺美國豬肉進口、大麻、社會犯罪等議題',
                },
                {
                    title: '（三）發言荒腔走板，失格、失言新聞頻傳：',
                    content: '針對立法院質詢、臉書發文',
                },
                {
                    title: '（四）面對反對聲音，經常使用暴力及恐嚇言論：',
                    content: '針對追打立委吳怡玎、揚言提告民眾等事件',
                },
            ],

            description: `針對罷免案領銜人鄭大平提出的罷免理由書，林昶佐回覆4130字的答辯書，一一反駁罷免方指控，並向中正萬華的市民朋友，報告這幾年的地方服務以及中央問政成績。重點如下：`,
            ans_list: [
                '（一）支持釐清 3+11 真相，並未反對調查、隱匿真相',
                '（二）校園供膳一律本土豬，並未讓學生吃萊豬',
                '（三）致力追求真相，不重視受害者家屬並非事實',
                '（四）嚴格監督預算、確實把關施政，未監督預算放棄立場並非事實',
                '（五）堅決捍衛國家主權，無視國家主權非事實',
                '（六）林昶佐防疫紓困、振興萬華最積極',
                '（七）林昶佐國會問政第一，獲民間團體公民監督國會聯盟肯定，六度獲選為優秀立委，更在公民評鑑中獲得全立法院第一',
                '（八）林昶佐在地建設最用心，上任五年多來，解決無數長年未被重視的在地問題，地方服務與建設等案件累計高達 6198 件',
            ],
        }
    },
}
</script>

<style scoped>
.section-box {
    max-width: 800px;
}

.section-box > p {
    font-weight: bolder;
}

.section-box a {
    display: block;
    text-align: right;
    font-size: 1.2rem;
    padding-top: 1.2rem;
    color: #ca6932;
}

hr {
    margin: 2rem 0;
}
</style>
