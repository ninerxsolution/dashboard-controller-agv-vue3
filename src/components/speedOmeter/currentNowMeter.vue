<template>
    <div class="semicircle">
        <div ref="progressBar" class="square-rotate"></div>
        <div class="semicircle-in-semicircle">
            <div ref="meter" class="needle"></div>
            <div class="middle-dot"></div>
            <span class="value-1">0</span>
            <span class="value-2">20</span>
            <span class="value-3">40</span>
            <span class="value-4">60</span>
            <span class="value-5">80</span>
            <span class="value-6">100</span>
            <span class="value-7">120</span>
        </div>
    </div>
    <!-- <span>{{ speedCurrent }}</span> -->
</template>

<script>
export default{
    name:'electricalVal',
    props:['getCurrentNow'],
    data(){
        return{
            speedCurrent:50,
            progressVal:"rotate(0.25turn)",
            meterVal:"rotate(90deg)",
        }
    },
    created(){
        setInterval(()=>{
            this.speedCurrent = this.getCurrentNow * (0.83);
            this.progressVal = "rotate("+(this.speedCurrent * 0.005).toFixed(2).toString()+"turn)";
            this.meterVal = "rotate("+Math.round(this.speedCurrent * 1.8).toString()+"deg)";
            this.setSpeedCurrent()
        },1000)
    },
    methods:{
        setSpeedCurrent(){
            this.$refs['progressBar'].style.transform = this.progressVal;
            this.$refs['meter'].style.transform = this.meterVal;

        }
    }
}
</script>

<style scoped>
.semicircle{
    /* border:solid aliceblue 1px; */
    position: relative;
    background-color: #3f4044;
    width: 187px;
    height: 94px;
    border-radius: 94px 94px 0px 0px;
    margin: 2px;
    display: flex;
    align-items: end;
    justify-content: center;
    overflow: hidden;
    /* transition: all 0.5s ease-in-out; */
}
.semicircle-in-semicircle{
    /* border:solid aliceblue 1px; */
    position: absolute;
    background-color: #31373b;
    width: 157px;
    height: 78px;
    border-radius: 78px 78px 0px 0px;
    bottom: 0.2%;
}
.square-rotate{
    position: absolute;
    top: 99%;
    width: inherit;
    /* left: 0; */
    height: 100%;
    background: #5d99cd;
    transform-origin:center top;
    transform: rotate(0.25turn);
    transition: all 0.5s ease-in-out;
}

.needle{
    position: absolute;
    top: 50%;
    /* bottom: 7%; */
    width: 50%;
    height: 100%;
    background-color: #e6e6e6;
    clip-path: polygon(0 50%,0 50%,100% 52%,100% 40%);
    transform: rotate(90deg);
    transform-origin: right center;
    transition: all 0.5s ease-in-out;
    z-index: 300;
}
.middle-dot{
    width: 15%;
    height: 30%;
    background-color: #e6e6e6;
    position: absolute;
    top: 85%;
    left: 44%;
    border-radius: 50%;
    border: solid 3px #f3f3ed;
}

span{
    color: #fff;
}

.value-1{
    position: absolute;
    top: 80%;
    left: 7%;
}
.value-2{
    position: absolute;
    top: 50%;
    left: 13%;
}
.value-3{
    position: absolute;
    top: 21%;
    left:26% ;
}
.value-4{
    position: absolute;
    top: 8%;
    left: 46%;
}
.value-5{
    position: absolute;
    top: 23%;
    left: 66%;
}
.value-6{
    position: absolute;
    top: 50%;
    left: 73%;
}
.value-7{
    position: absolute;
    left: 78%;
    top: 80%;
}
</style>