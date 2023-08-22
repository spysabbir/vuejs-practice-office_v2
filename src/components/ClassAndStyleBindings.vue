<script>
export default {
  data() {
    return {
      isActive: true,
      activeColor: "blue",
      fontSize: 24,
      baseStyles: "color: green",
      overridingStyles: "font-size: 30px",
      activeClass: 'activeClass',
      errorClass: 'errorClass',
    };
  },
  methods: {
    
  }
};
</script>

<template>
  <h4>Binding HTML Classes</h4>
  <div :class="{ active: isActive}">Binding to Objects</div>
  <div :class="[activeClass, errorClass]">Binding to Arrays</div>

  <hr>
  <h4>Binding Inline Styles</h4>
  <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">Binding to Objects</div>
  <div :style="[baseStyles, overridingStyles]">Binding to Arrays</div>

  <div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }">
    <div style="background-color: blue; width: 100px; height: 100px;"></div>
    <div style="background-color: red; width: 100px; height: 100px;"></div>
    <div style="background-color: green; width: 100px; height: 100px;"></div>
  </div>

</template>

<style scoped>
.active{
  color: red;
}
.activeClass{
  background-color: aquamarine;
}
.errorClass{
  color: black;
}
</style>
