<template>
    <div>
        <div v-if="kk==1">
            <Goodlist :goodId="1"></Goodlist>
        </div>
        <div v-else-if="kk==2">
            <Goodlist :goodId="2"></Goodlist>
        </div>
        <div v-else-if="kk==3">
            3333333333
        </div>
        <div v-else-if="kk==4">
            4444444444
        </div>
        <div v-else-if="kk==5">
            5555555
        </div>
        <div v-else-if="kk==6">
            6666666
        </div>
        <div v-else-if="kk==7">
            777777777777
        </div>
        <div v-else-if="kk==8">
            88888888
        </div>
        <div v-else-if="kk==9">
            999999999999
        </div>
        <div v-else-if="kk==10">
            10
        </div>
        <div v-else-if="kk==11">
            11
        </div>
        <div v-else>
            <Goodlist :goodId="0"></Goodlist>
        </div>
    </div>
</template>

<script>
import Msg from './Msg.js'
import Goodlist from './Goodlist.vue'
export default {
    data(){
        return {
            kk:0
        }
    },
    mounted:function(){
        var _this = this
        Msg.$on('val',function(m){
            _this.kk = m;
        })
    },
    components:{
        Goodlist
    }
}
</script>

<style>

</style>