<template>
  <h2>Your Reaction Time is {{score}} ms</h2>
  <p :class="{
        ninja:this.score<=200,
        samurai:this.score<=300 && this.score >200,
        warrior:this.score<=400 && this.score >300,
        grasshopper:this.score>400
    }">{{rank}}</p>
</template>

<script>
export default {
    props:['score'],
    data(){
        return{
            rank: ''
        }
    },
    mounted(){
        if(this.score < 200){
            this.rank = 'You are a ninja!'
        }else if(this.score < 300){
            this.rank = 'You are a samurai!'
        }else if(this.score < 400){
            this.rank = 'You are a warrior!'
        }else{
            this.rank = 'You are a grasshopper!'
        }
    }
}
</script>

<style>
.ninja{
    color: red;
    font-size: 1.8rem;
    font-weight: bold;
}
.samurai{
    color: blue;
    font-size: 1.8rem;
    font-weight: bold;
}
.warrior{
    color: green;
    font-size: 1.8rem;
    font-weight: bold;

}
.grasshopper{
    color: yellow;
    font-size: 1.8rem;
    font-weight: bold;
}
</style>