<script>
export default {
  data() {
    return {
        count: '0',
        inputValue: '',
        inputResult: '',
        inputResult: '',
        selfCount: '0',
        keyupInputValue: '',
        keyupInputResult: '',
    };
  },
  methods: {
    say(name) {
        alert(name)
    },
    sayEvent(name, event) {
        event.preventDefault();
        alert(name)
        console.log(event.type)
    },
    doThis(){
        alert('Event Modifiers')
    },
    onSubmit(){
        this.inputResult = this.inputValue
    },
    doThatBox(){
        this.selfCount++
    },
    submit(){
        this.keyupInputResult = this.keyupInputValue
    }
  }
};
</script>

<template>

<h4>Inline Handlers</h4>
<button @click="count++">+</button>
<span>Count is: {{ count }}</span>
<button @click="count--">-</button>

<hr>

<h4>Method Handlers</h4>
<button @click="say('Sabbir')">Say hello</button>
<button @click="sayEvent('Sabbir', $event)">Say hello</button>

<hr>

<h4>Event Modifiers</h4>
<a @click.stop="doThis">Event Modifiers</a>
<form @submit.prevent="onSubmit">
    <input type="text"  v-model="inputValue">
    <button type="submit">Input</button>
    <span>{{ inputResult }}</span>
</form>

<hr>

<div class="box" @click.self="doThatBox">
    Click Main Div
    <div class="child-box">
        {{ selfCount }}
    </div>
</div>


<hr>
<h4>Key Modifiers</h4>
<input type="text" @keyup.enter="submit" v-model="keyupInputValue">
<span>{{ keyupInputResult }}</span>

<hr>
<h4>Mouse Button Modifiers</h4>
<div class="box" @click.right="doThatBox">
    Right Click {{ selfCount }}
</div>

</template>

<style scoped>
.box{
    width: 100px;
    height: 100px;
    background-color: aqua;
    color: black;
}
.child-box{
    width: 80px;
    height: 80px;
    background-color: rgb(0, 255, 34);
    color: black;
}
</style>
