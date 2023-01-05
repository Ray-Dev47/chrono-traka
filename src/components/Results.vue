<template>
<div>
    <p v-if="showresults = true">Reaction time: {{score}} ms</p>
    <div class="rank" v-if="score">{{rank}}!</div>
</div>
  
</template>

<script>
export default {
    props: {
    // showresults: {
    //   type: [String, Boolean, Number]
    // },
    score: {
      type: [String, Boolean, Number]
    }
  },
  data(){
    return {
        rank: null
    }
  },
  mounted(){
     if(this.score < 150){
        this.rank = 'Ninja Fingers'
     } else if( this.score < 300 ){
        this.rank = 'Rapid Reflexes'
     } else {
        this.rank = '...Small Pace'
     }
    //  console.log(this.reactionTime)
  }

}
</script>

<style>
.rank{
    font-size: 1.4em;
    color: #0fa787;
    font-weight: bold;
}

</style>