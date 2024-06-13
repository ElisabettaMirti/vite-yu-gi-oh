<script>
// import 

export default {
    data(){
        return{

        }
    },
    components: {
        
    },
    props: {
        
    }
}
</script>

<template>
<div class="flip1">
    <img src="http://vignette2.wikia.nocookie.net/myyugiohdeck/images/d/da/Dark_Magician.jpg/revision/latest?cb=20110610035254" width="240" height="290" />
</div>
<div class="flip2">
    <img src="http://vignette3.wikia.nocookie.net/yugioh/images/9/94/Back-Anime-2.png/revision/20090601084536" width="240" height="290" />
</div>
</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

body{
    background-color: #d48f38;
}

div {
    -webkit-animation-duration: 3s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function:linear;
    -webkit-backface-visibility: hidden;
    color: blue;
    font-family: Helvetica,Arial,sans-serif;
    font-weight: bold;
    padding: 20px;
    position: absolute;
    top: 50%;
    left: 40%;
    transform: translate(-50%, -50%);
}

@-webkit-keyframes flip1 {
    from { -webkit-transform: rotateY(0deg); }
    to { -webkit-transform: rotateY(360deg); }
}

div.flip1 {
    -webkit-animation-name: flip1;
}

@-webkit-keyframes flip2 {
    from { -webkit-transform: rotateY(-180deg); }
    to { -webkit-transform: rotateY(180deg); }
}

div.flip2 {
    -webkit-animation-name: flip2;
}
</style>
