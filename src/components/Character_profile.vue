<template>
    <div class="section" id="profile">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <div class="grid">
                <figure>
                    <img src="../assets/profile.jpg" alt="林昶佐" />
                    <figcaption class="name">{{ name }}</figcaption>
                </figure>
                <article>
                    <p style="margin-left: 1rem; margin-bottom:0; font-weight:bolder;">學歷：</p>
                    <ul>
                        <li style="margin-bottom: 2rem;">{{ detail.edu }}</li>
                    </ul>
                    <p style="margin-left: 1rem; margin-bottom:0; font-weight:bolder;">經歷：</p>
                    <ul>
                        <li v-for="(item, index) of detail.exp" :key="index">{{ detail.exp[index] }}</li>
                    </ul>
                </article>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '被罷免人背景',
            name: '林昶佐',
            detail: {
                edu: '‧ 國立台北大學企業管理學系學士',
                exp: [
                    '時代力量創黨工程隊總隊長',
                    '時代力量主席團成員',
                    '國際知名閃靈樂團主唱',
                    '國際特赦組織台灣分會理事長',
                    '行政院二二八基金會董事',
                    '獨立音樂協會理事長',
                    '曾獲金曲獎 、 總統文化獎',
                    '現任台北市中正萬華區立委',
                ],
            },
        }
    },
}
</script>

<style scoped>
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
}

@media screen and (max-width: 768px) {
    .grid {
        grid-template-columns: 1fr;
    }
}

p {
    text-align: left;
    font-size: 1.2rem;
}

ul li {
    font-size: 1.2rem;
    margin: 1rem 0 1rem 2rem;
}

@media screen and (max-width: 768px) {
    p,
    ul li {
        font-size: 1rem;
    }
}

img {
    width: 100%;
}
</style>
