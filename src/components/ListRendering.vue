<script>
export default {
  data() {
    return {
        names: ['Sabbir', 'Sovon', 'Alif', 'Shahariya'],
        persons: [
            { name: 'sabbir', email: 'sabbir@email.com' , phone: '01953321402'},
            { name: 'sovon', email: 'sovon@email.com' , phone: '01517805999'}
        ]
    };
  },
  methods: {

  }
};
</script>

<template>
<h4>v-for</h4>
<ul v-for="name in names">
    <li>{{ name }}</li>
</ul>
<hr>
<ul v-for="(name, i) in names">
    <li>{{ i+1 }} . {{ name }}</li>
</ul>

<hr>

<h4>v-for with an Object</h4>

<span v-for="person in persons">
    {{ person.name }} <br>
</span>
<hr>
<span v-for="(person, key) in persons">
    {{ key }}: {{ person }} <br>
</span>
<hr>
<span v-for="(person, key, i) in persons">
    {{ i }} . {{ key }}: {{ person }} <br>
</span>

<hr>
<h4>v-for with a Range</h4>
<span v-for="n in 10">
    {{ n }} <br>
</span>

<hr>
<ul>
  <template v-for="item in names">
    <li>{{ item }}</li>
  </template>
</ul>

<hr>
<h3>Maintaining State with key</h3>
<template v-for="person in persons" :key="person.name">
  <li>{{ person.name }}</li>
</template>

</template>

<style scoped>

</style>
