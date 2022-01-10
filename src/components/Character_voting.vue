<template>
    <div class="section" id="voting">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <div class="iframe-container">
                <iframe
                    width="1280"
                    height="720"
                    src="https://www.youtube.com/embed/XGEmg3vhrzU"
                    title="YouTube video player"
                    frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen
                ></iframe>
            </div>
            <div class="vote">
                <div class="votebox"><span id="agree_bar"></span><span class="pass">未通過</span></div>

                <p>
                    {{ title_agree }}<span id="agree_vote">{{ vote_agree }}</span>
                </p>

                <div class="votebox">
                    <span id="disagree_bar"></span>
                </div>
                <p>
                    {{ title_disagree }}<span id="disagree_vote">{{ vote_disagree }}</span>
                </p>

                <h3 style="text-align:center; margin-top:5rem;">
                    開票結果
                </h3>
                <img src="../assets/result.jpg" alt="開票結果" style="width:100%" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '直播專區',
            title_agree: '同意（門檻：5萬8756票）: ',
            title_disagree: '不同意： ',
            vote_total: 70000,
            vote_agree: 0,
            vote_disagree: 0,
        }
    },

    methods: {
        vote() {
            // eslint-disable-next-line no-undef
            axios
                .get('https://www.ftvnews.com.tw/api/poll220109.json')
                .then(function(res) {
                    // 同意票
                    let vote_agree = res.data.Data[0].Candidate[0].Tickets
                    let bar_agree = Math.floor((vote_agree / 70000) * 100)

                    // 不同意票
                    let vote_disagree = res.data.Data[0].Candidate[1].Tickets
                    let bar_disagree = Math.floor((vote_disagree / 70000) * 100)

                    if (bar_agree > 100) {
                        document.getElementById('agree_bar').style.width = 100 + '%'
                    } else {
                        document.getElementById('agree_bar').style.width = bar_agree + '%'
                    }

                    if (bar_disagree > 100) {
                        document.getElementById('disagree_bar').style.width = 100 + '%'
                    } else {
                        document.getElementById('disagree_bar').style.width = bar_disagree + '%'
                    }

                    document.getElementById('agree_vote').innerText =
                        vote_agree.toString().replace(/\B(?=(\d{4})+(?!\d))/g, '萬') + ' 票'
                    document.getElementById('disagree_vote').innerText =
                        vote_disagree.toString().replace(/\B(?=(\d{4})+(?!\d))/g, '萬') + ' 票'
                })
                .catch(function(err) {
                    // Error happened
                    console.log(err)
                })
        },

        keepVoting() {
            setInterval(() => {
                this.vote()
            }, 3000)
        },
    },

    mounted() {
        this.vote(this.vote_total)
        // this.keepVoting(this.vote_total)
    },
}
</script>

<style scoped>
.iframe-container {
    overflow: hidden;
    padding-top: 56.25%;
    position: relative;
}
.iframe-container iframe {
    border: 0;
    height: 100%;
    left: 0;
    position: absolute;
    top: 0;
    width: 100%;
}

/* 4x3 縱橫比 */
.iframe-container-4x3 {
    padding-top: 75%;
}

.vote {
    margin: 2rem 0;
}

.votebox {
    background-color: #aaaaaa;
    width: 100%;
    height: 30px;
    border-radius: 10px;
    display: flex;
}

.votebox span {
    border-radius: 10px;
}

/* 票數據條 */
#agree_bar {
    width: 0%;
    background-color: #374574;
}

#disagree_bar {
    width: 0%;
    background-color: #e77434;
}

.pass {
    font-size: 1.6rem;
    transform: translateY(-28px);
    color: #7b1f06;
    transform: rotate(345deg) translateY(-2px);
    font-weight: bolder;
}

@media screen and (max-width: 400px) {
    .pass {
        font-size: 1rem;
        transform: rotate(345deg) translateY(5px);
    }
}
</style>
