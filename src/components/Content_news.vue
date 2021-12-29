<template>
    <div class="section" id="news">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <div class="news" v-for="(item, index) of newsInfo" :key="index">
                <a :href="'https://www.ftvnews.com.tw/news/detail/' + item.ID" target="blank">
                    <div>
                        <img :src="item.Image" alt="新聞封面照" />
                    </div>
                    <div>
                        <h2 class="title">{{ item.Title }}</h2>
                    </div>
                    <div>
                        <p class="date">{{ item.CreateDate }}</p>
                    </div>
                </a>
            </div>
        </div>
        <div class="btn_more">
            <a href="https://www.ftvnews.com.tw/tag/林昶佐/" target="blank">更多 「 林昶佐罷免案 」 新聞</a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '最新新聞',
            newsInfo: [],
        }
    },
    methods: {
        getData_ftvNews() {
            // eslint-disable-next-line no-undef
            axios
                .get('https://ftvnews-api2.azurewebsites.net/API/FtvGetNewsWeb.aspx?Cate=林昶佐&Page=1&sp=3')
                .then((response) => {
                    // console.log(response)
                    let data = response.data.ITEM
                    data.forEach((item) => {
                        this.newsInfo.push(item)
                    })
                    // console.log(this.newsInfo)
                })
                .catch((error) => {
                    console.log('error' + error)
                })
        },
    },
    mounted() {
        this.getData_ftvNews()
    },
}
</script>

<style scoped>
.section-box {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-column-gap: 1rem;
}
@media screen and (max-width: 768px) {
    .section-box {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-column-gap: 1rem;
    }
}

@media screen and (max-width: 500px) {
    .section-box {
        display: grid;
        grid-template-columns: 1fr;
        grid-column-gap: 1rem;
    }
}

.news {
    background-color: #9b9b9b;
    transition: 0.3s;
    margin-bottom: 1rem;
    color: white;
}

@media screen and (max-width: 500px) {
    .news {
        margin-right: 0;
    }
}

.news:hover {
    background-color: #e18a59;
}

.news p {
    text-align: left;
    font-size: 0.9rem;
    font-weight: lighter;
    padding: 1rem;
    margin: 0;
    color: white;
}

.news img {
    width: 100%;
}

.news a div:nth-child(1) {
    overflow: hidden;
}

.title {
    display: -webkit-box;
    overflow: hidden;
    text-overflow: ellipsis;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    /* 解決firefox不支援-webkit-line-clamp的問題 */
    line-height: 30px;
    max-height: 70px;
    text-align: left;
    font-size: 1.2rem;
    font-weight: normal;
    padding: 1rem;
    color: white;
}
@media screen and (max-width: 768px) {
    .title {
        font-size: 1rem;
    }
}

.btn_more {
    max-width: 300px;
    margin: 3rem auto;
    background-color: #4d4d4d;
    padding: 0.6rem;
    display: block;
    font-weight: bolder;
    cursor: pointer;
}

.btn_more a {
    color: white;
}

@media screen and (max-width: 700px) {
    .flex {
        display: block;
    }
}
</style>
