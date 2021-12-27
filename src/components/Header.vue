<template>
    <div class="progress"></div>
    <div class="flex-logo">
        <i class="fad fa-2x fa-list" @click="menu">
            <nav class="nav">
                <a v-for="(item, index) of list" :key="index" :href="item.anchor">
                    <i class="fad fa-scrubber"></i> {{ item.title }}
                </a>
            </nav>
        </i>
    </div>
</template>

<script>
export default {
    data() {
        return {
            list: [
                {
                    title: '直播專區',
                    anchor: '#voting',
                },
                {
                    title: '被罷免人背景',
                    anchor: '#profile',
                },
                {
                    title: '歷屆選舉結果',
                    anchor: '#voted',
                },
                {
                    title: '罷免理由',
                    anchor: '#reason',
                },
                {
                    title: '各方說法',
                    anchor: '#factions',
                },
                {
                    title: '罷免程序',
                    anchor: '#porcess',
                },
                {
                    title: '罷免門檻',
                    anchor: '#recall',
                },
                {
                    title: '相關新聞',
                    anchor: '#news',
                },
            ],
        }
    },
    methods: {
        scroll() {
            window.addEventListener('scroll', () => {
                this.moveBar('#374674')
            })
        },

        moveBar(color = '#0984e3') {
            let bar = document.querySelector('.progress')
            let w = Math.ceil(
                (Math.round(window.pageYOffset) / (document.body.scrollHeight - window.innerHeight)) * 100
            )
            bar.style.width = w + '%'
            bar.style.background = color
        },

        menu() {},
    },
    mounted() {
        this.scroll()
        this.moveBar()
    },
}
</script>

<style scoped>
/* 漢堡選單 */
.nav {
    width: 250px;
    padding: 1rem;
    position: fixed;
    background-color: rgba(223, 223, 223, 0.822);
    z-index: 998;
    top: 3.3rem;
    right: 1rem;
    border-radius: 10px;
    display: none;
}

.fa-list {
    color: #e18a59;
    cursor: pointer;
    position: fixed;
    z-index: 999;
    top: 1rem;
    right: 1rem;
    background-color: white;
    border-radius: 10px;
    padding: 5px;
    box-shadow: 1px 2px 3px black;
}

.fa-list:hover .nav {
    display: block;
}
.nav a {
    font-size: 1rem;
    margin: 1rem;
    display: block;
    color: #a73f24;
    font-weight: bolder;
    transition: 0.3s;
}
.nav a:hover {
    color: #662616;
}

.logo {
    max-width: 100%;
    width: 300px;
}

@media screen and (max-width: 768px) {
    .logo {
        width: 200px;
    }
}

@media screen and (max-width: 450px) {
    .logo {
        width: 200px;
    }
}

/* 進度條 */
.progress {
    position: fixed;
    top: 1px;
    width: 0.5%;
    height: 10px;
    z-index: 999;
}
</style>
