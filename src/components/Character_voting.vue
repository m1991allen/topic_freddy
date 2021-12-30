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
            <!-- <div class="vote">
                <div class="votebox"><span id="agree_bar"></span></div>
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
            </div> -->
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '直播專區',
            title_agree: '同意（門檻：6萬1187票）: ',
            title_disagree: '不同意： ',
            vote_total: 200000,
            vote_agree: 0,
            vote_disagree: 0,
        }
    },

    methods: {
        vote(vote_total) {
            // eslint-disable-next-line no-undef
            axios
                .get('https://ftvnews.com.tw/topics/freddy/poll220109_freddy.json')
                .then(function(res) {
                    let vote_agree = res.data.Data[0].AgreeTickets
                    let vote_disagree = res.data.Data[0].RejectTickets
                    let bar_agree = Math.floor((vote_agree / vote_total) * 100)
                    let bar_disagree = Math.floor((vote_disagree / vote_total) * 100)

                    document.getElementById('agree_vote').innerText =
                        vote_agree.toString().replace(/\B(?=(\d{4})+(?!\d))/g, '萬') + ' 票'
                    document.getElementById('disagree_vote').innerText =
                        vote_disagree.toString().replace(/\B(?=(\d{4})+(?!\d))/g, '萬') + ' 票'

                    document.getElementById('agree_bar').style.width = bar_agree + '%'
                    document.getElementById('disagree_bar').style.width = bar_disagree + '%'
                })
                .catch(function(err) {
                    // Error happened
                    console.log(err)
                })
        },

        keepVoting() {
            setInterval(() => {
                this.vote()
            }, 15000)
        },
    },

    mounted() {
        this.vote(this.vote_total)
        this.keepVoting()
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
</style>
