<template>
    <div class="section" id="live">
        <h3>{{ title }}</h3>
        <div class="section-box">
            <div class="iframe-container">
                <iframe
                    width="1280"
                    height="720"
                    src="https://www.youtube.com/embed/-DDRgn4MAc4"
                    title="YouTube video player"
                    frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen
                ></iframe>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: '電視罷免說明會',
        }
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
</style>
