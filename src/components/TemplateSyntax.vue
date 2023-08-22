<script>
export default {
  data() {
    return {
      message: 'This is Text Interpolation',
      number: 10,
      ok: 'Yes',
      rawHtml: '<p>Raw HTML</p>',
      seen: true,
      url: 'https://spysabbir.com/',
      doSomethingClickCount: 0,
      attributeName: "href",
      focusSomethingClickCount: 0,
    };
  },
  methods: {
    doSomething(){
      this.doSomethingClickCount++;
    },
    focusSomething(){
      this.focusSomethingClickCount++;
    },
  }
};
</script>

<template>
  <p>Text Interpolation</p>
  <span>Message: {{ message }}</span>
  <hr>

  <p>Raw HTML</p>
  <p>Using text interpolation: {{ rawHtml }}</p>
  <p>Using v-html directive: <span v-html="rawHtml"></span></p>
  <hr>

  <p>Using JavaScript Expressions</p>
  {{ number + 1 }}
  {{ ok ? 'YES' : 'NO' }}
  {{ message.split('').reverse().join('') }}
  <hr>

  <p>Directives</p>
  <p v-if="seen">Now you see me</p>

  <p>Arguments</p>
  <a v-bind:href="url"> Spy Sabbir </a>
  <!-- shorthand -->
  <a :href="url"> Spy Sabbir shorthand </a>

  <br>
  <a v-on:click="doSomething"> Click do Something {{ doSomethingClickCount }}</a>
  <!-- shorthand -->
  <a @click="doSomething"> Click do Something shorthand  {{ doSomethingClickCount }}</a>


  <p>Dynamic Arguments</p>
  <a v-bind:[attributeName]="url"> Click </a>
  <a :[attributeName]="url"> Click shorthand  </a>
  <br>
  <a v-on:click="focusSomething"> focus Something Click  {{ focusSomethingClickCount }} </a>
  <a @click="focusSomething">focus Something shorthand Click{{ focusSomethingClickCount }}</a>

  <img src="https://vuejs.org/assets/directive.69c37117.png" alt="Modifiers"  width="500" height="125" >

</template>

<style scoped>

</style>
