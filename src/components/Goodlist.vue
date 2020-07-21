<template>
    <div name="show">
        <ul class="goodlist">
            <li v-for="(goods,index) in list" :key="index">
                <img v-bind:src="goods.img" alt="" width="220px" height="220px">
                <p>{{goods.goodName}}</p>
            </li>
        </ul>
    </div>    
</template>

<script type="text/javascript">
export default {
    name:"show",
    data(){
        var _this = this;
        var url = "";
        if(_this.goodId==1){
            url="json/bjb.json";
        }else if(_this.goodId==2){
            url="json/sj.json";
        }else{
            url="json/bjb.json";
        }
        this.$http.get(url).then(function(res){
            _this.list = res.data;
        })
        return{
            list:[]
        }
    },
    props:{
        goodId:Number
    },
    watch:{
        goodId(){
            var _this = this;
            var url = "";
            if(_this.goodId==1){
                url="json/bjb.json";
            }else if(_this.goodId==2){
                url="json/sj.json";
            }else{
                url="json/bjb.json";
            }
            this.$http.get(url).then(function(res){
                _this.list = res.data;
            })
            return{
                list:[]
            }
        }
    }
}
</script>

<style>
    .goodlist li{
        width: 200px;
        height: 200px;
        list-style: none;
        float: left;
        font-size: 9px;
        color: red;
        margin-bottom: 30px;
    }
    .goodlist img{
        width: 180px;
        height: 180px;
    }
</style>