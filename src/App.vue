<template>
    <Header />
    <Banner />
    <CharacterVoting />
    <CharacterProfile />
    <CharacterVoted />
    <ContentReason />
    <ContentProcess />
    <ContentRecall />
    <ContentLive />
    <ContentFactions />
    <ContentNews />
    <Footer />
    <AdditionSocial />
    <AdditionScrolltop />
    <AdditionBottom />
    <!-- music btn -->
</template>

<script>
import Header from '@/components/Header.vue'
import Banner from '@/components/Banner.vue'
import CharacterVoting from '@/components/Character_voting.vue'
import CharacterProfile from '@/components/Character_profile.vue'
import CharacterVoted from '@/components/Character_voted.vue'
import ContentReason from '@/components/Content_reason.vue'
import ContentProcess from '@/components/Content_process.vue'
import ContentRecall from '@/components/Content_recall.vue'
import ContentLive from '@/components/Content_live.vue'
import ContentFactions from '@/components/Content_factions.vue'

import ContentNews from '@/components/Content_news.vue'
import Footer from '@/components/Footer.vue'
import AdditionSocial from '@/components/Addition_social.vue'
import AdditionScrolltop from './components/Addition_scrolltop.vue'
import AdditionBottom from './components/Addition_bottom.vue'

export default {
    name: 'App',
    components: {
        Header,
        Banner,
        CharacterVoted,
        CharacterVoting,
        CharacterProfile,
        ContentReason,
        ContentProcess,
        ContentRecall,
        ContentLive,
        ContentFactions,
        ContentNews,
        Footer,
        AdditionSocial,
        AdditionScrolltop,
        AdditionBottom,
    },
}
</script>

<style>
#music {
    display: none;
}
/* reset */
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html,
body,
div,
span,
applet,
object,
iframe,
h1,
h2,
h3,
h4,
h5,
h6,
p,
blockquote,
pre,
a,
abbr,
acronym,
address,
big,
cite,
code,
del,
dfn,
em,
img,
ins,
kbd,
q,
s,
samp,
small,
strike,
strong,
sub,
sup,
tt,
var,
b,
u,
i,
center,
dl,
dt,
dd,
ol,
ul,
li,
fieldset,
form,
label,
legend,
table,
caption,
tbody,
tfoot,
thead,
tr,
th,
td,
article,
aside,
canvas,
details,
embed,
figure,
figcaption,
footer,
header,
hgroup,
menu,
nav,
output,
ruby,
section,
summary,
time,
mark,
audio,
video {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section {
    display: block;
}
body {
    line-height: 1;
}
ol,
ul {
    list-style: none;
}
blockquote,
q {
    quotes: none;
}
blockquote:before,
blockquote:after,
q:before,
q:after {
    content: '';
    content: none;
}
table {
    border-collapse: collapse;
    border-spacing: 0;
}

* {
    box-sizing: border-box;
    scroll-behavior: smooth;
}

body {
    margin: 0;
    width: 100%;
    overflow-x: hidden;
}

#app {
    font-family: Helvetica, Arial, sans-serif, 微軟正黑體, 蘋果儷中黑;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    transition: 0.3s;
    width: 100%;
    overflow-x: hidden;
}

h1,
h2 {
    font-weight: lighter;
}

h3 {
    font-size: 1.6rem;
    font-weight: bolder;
    padding: 0.6rem 0;
    margin: 2.4rem 0;
    color: white;
    background-color: #e18a59;
}

ul li {
    text-align: left;
    margin: 1rem 0 1rem 0;
    font-size: 1.2rem;
    line-height: 2rem;
}

p {
    text-align: left;
    margin: 0.5rem 0 2rem 0;
    font-size: 1.2rem;
    line-height: 2rem;
}

@media screen and (max-width: 768px) {
    p,
    ul li {
        font-size: 1rem;
    }
}

a {
    color: black;
    text-decoration: none;
}

figure {
    margin: 0;
}

img {
    width: 100%;
}

.layout {
    max-width: 1000px;
}

.section {
    margin: 3rem auto;
    max-width: 1000px;
}

.section-box {
    margin: auto;
    padding: 0 1rem;
}

@media screen and (max-width: 768px) {
    .section {
        margin: 3rem auto;
        padding: 0 1rem;
        width: 100%;
    }
}

.flex {
    display: flex;
}

@media screen and (max-width: 350px) {
    .flex {
        display: block;
    }
}

.name {
    text-align: center;
    font-weight: bolder;
    font-size: 1.6rem;
    margin: 1rem 0;
    line-height: 2rem;
}

.section-box p:nth-child(1) {
    margin-left: 0;
}
</style>
