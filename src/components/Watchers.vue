<script>
export default {
  data() {
    return {
        answer: '',
        x: '',
        y: '',
        sum: '',
        
    };
  },
  methods: {
    calculateSum(newX, newY) {
      const sum = Number(newX) + Number(newY);
      this.sum = sum
    },
  },
  watch: {
    answer(newAnswer, oldAnswer){
        if(newAnswer === 'Yes'){
            alert('Right Answer')
        }
    },
    x(newX, oldX) {
      this.calculateSum(newX, this.y);
    },
    y(newY, oldY) {
      this.calculateSum(this.x, newY);
    },
  }
};
</script>

<template>
    <h4>Basic Example</h4>
    <div>
      <label>Questions usually contain a question mark?</label>
      <input type="text" v-model="answer">
    </div>

    <hr>
    <h4>Watch Source Types</h4>
    <input type="text" v-model="x"> + <input type="text" v-model="y">
    <span>Sum: {{ sum }}</span>

</template>

<style scoped>

</style>
