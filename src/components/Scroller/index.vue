<template>
    <div class="wrapper" ref="wrapper">
        <slot></slot>
    </div>
</template>

<script>
//滚动组件封装
//引入better-scroll
import BScroll from 'better-scroll' 

export default {
    name: 'Scroller',
    props: { //父子组件通信
        handleToScroll: {
            type : Function,
            default : function(){}
        },
        handleToTouchEnd: {
            type : Function,
            default : function(){}
        }
    },
    mounted(){
        var scroll = new BScroll(this.$refs.wrapper,{
            tap: true,
            probeType: 1
        });

        this.scroll = scroll;

        scroll.on('scroll',(pos)=>{
            this.handleToScroll(pos);
        });

        scroll.on('touchEnd',(pos)=>{
            this.handleToTouchEnd(pos);
        });
    },
    methods: {
        toScrollTop(y){
            this.scroll.scrollTo(0,y);
        }
    }
}
</script>

<style scoped>
    .wrapper{height: 100%;}
</style>