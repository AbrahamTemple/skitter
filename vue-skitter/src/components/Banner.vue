<template>
     <div class="box_skitter box_skitter_large" ref="skitters">
            <ul>
                <li v-for="(img,$index) in banner" :key="$index">
                    <a :href="img.link" target="_blank"><img :src="img.url" :class="img.mode"/></a>
                    <div class="label_text">
                        <p><strong><font :color="img.color">{{img.title}}</font></strong></p>
                    </div>
                </li>
            </ul>
      </div>
</template>

<script>
    import $ from 'jquery';
    import '@/assets/js/jquery.easing.1.3';
    import 'skitter-slider';
    export default {
        name: "Banner",
        data(){
            return{
                banner: [
                    {
                        url: require('@/assets/img/001.jpg'),
                        mode: 'circlesRotate',
                        link: '#list/41',
                        title: '繁华落幕的城市',
                        color: '#ffffff'
                    },
                    {
                        url: require('@/assets/img/002.jpg'),
                        mode: 'cubeRandom',
                        link: '#list/19',
                        title: '孤舟独进的邮轮',
                        color: '#FF00FF'
                    },
                    {
                        url: require('@/assets/img/003.jpg'),
                        mode: 'horizontal',
                        link: '#list/48',
                        title: '照亮黑夜的极光',
                        color: '#FFFF00'
                    }
                ]
            }
        },
        mounted() {
            $('.box_skitter_large').skitter({
                    label: true,
                    dots : false,
                    // numbers: true,
                    interval:3500,
                    show_randomly: true,
                    hideTools: true,
                    theme: 'minimalist'
            });
        },
    }
</script>

<style scoped>
    @import "../assets/css/skitter.css";
</style>
