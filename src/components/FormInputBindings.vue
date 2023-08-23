<script>
export default {
  data() {
    return {
        text : '',
        message: '',
        multilineText: '',
        checkbox: true,
        checkedNames: [],
        picked: '',
        selected: '',
        multipleSelected: [],
        options: [
            { text: 'One', value: 'A' },
            { text: 'Two', value: 'B' },
            { text: 'Three', value: 'C' }
        ],
        dynamicallySelected: '',
        toggle: '',
        dynamicTrueValue: 'Checked',
        dynamicFalseValue: 'Notchecked',
        dynamictoggle: '',
        age: '',
    };
  },
  methods: {

  }
};
</script>

<template>

    <h4>Basic Usage</h4>
    <input :value="text" @input="event => text = event.target.value" placeholder="edit me">
    <span>{{ text }}</span>
    <hr>
    <input v-model="message" placeholder="edit me" />
    <span>{{ message }}</span>

    <hr>
    <h4>Multiline text</h4>
    <textarea v-model="multilineText"></textarea>
    <p style="white-space: pre-line;">{{ multilineText }}</p>

    <hr>
    <h4>Checkbox</h4>
    <input type="checkbox" v-model="checkbox">
    <span></span>
    {{ checkbox }}

    <hr>
    <div>Checked names: {{ checkedNames }}</div>
    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
    <label for="jack">Jack</label>

    <input type="checkbox" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>

    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label>

    <hr>
    <h4>Radio</h4>
    <div>Picked: {{ picked }}</div>

    <input type="radio" id="one" value="One" v-model="picked" />
    <label for="one">One</label>

    <input type="radio" id="two" value="Two" v-model="picked" />
    <label for="two">Two</label>

    <hr>
    <h4>Select</h4>
    <div> Selected: {{ selected }}</div>
    <select v-model="selected">
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>

    <div> Selected: {{ multipleSelected }}</div>
    <select v-model="multipleSelected" multiple>
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>

    <div>Dynamically Selected: {{ dynamicallySelected }}</div>
    <select v-model="dynamicallySelected">
        <option disabled value="">Please select one</option>
        <option v-for="option in options" :value="option.value" :key="option.value">{{ option.text }}</option>
    </select>

    <hr>
    <h4>Value Bindings</h4>
    <input type="checkbox" v-model="toggle" true-value="yes" false-value="no" />
    <span>{{ toggle }}</span>
    <hr>
    <input type="checkbox" v-model="dynamictoggle" :true-value="dynamicTrueValue" :false-value="dynamicFalseValue" />
    <span>{{ dynamictoggle }}</span>

    <hr>
    <h4>Modifiers</h4>
    <input v-model.number="age" />
    <span>{{ age }}</span>





</template>

<style scoped>

</style>
