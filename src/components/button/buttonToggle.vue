<template>
    <div class="">
        <div></div>
        <div ref="btn" class="toggle-btn" @click="btn_click ">
            <div class="inner-circle"></div>
        </div>
        <!-- <span>{{ btn_is_clicked }}</span> -->
    </div>
</template>
<script>
export default{
    name:'buttonToggle',
    props:{
        buttValue:{
            type:Boolean
        }
    },
    data(){
        return{
            btn_is_clicked:false,
        }
    },
    methods:{
        btn_click(){
            if(this.btn_is_clicked == false){
                this.$refs.btn.className = 'toggle-btn active';
            }else{
                this.$refs.btn.className = 'toggle-btn';
            }
            this.btn_is_clicked = !this.btn_is_clicked;
        }
    },
    created(){
        setInterval(()=>{
            this.btn_is_clicked = this.buttValue;
            if(this.buttValue){
                this.$refs.btn.className = 'toggle-btn active';
            }
        },1000)
    }
}
</script>

<style>

.toggle-btn{
    width: 40px;
    height:20px;
    background: gray;
    border-radius: 30px;
    padding: 1px;
    transition: all 200ms ease-in-out;
}
.toggle-btn > .inner-circle{
    background-color: #fff;
    height: 100%;
    width:50%;
    border-radius: 50%;
    transition: all 200ms ease-in-out;
}

.toggle-btn.active{
    background: #00acee;
}
.toggle-btn.active > .inner-circle{
    margin-left: 50%;
}
</style>