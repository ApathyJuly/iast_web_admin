<template>
    <div class="app-container">
      <golden-layout>
  <gl-row>
    <gl-component title="component1">
      <h1>Component 1</h1>
    </gl-component>
    <gl-stack>
      <gl-component title="component2">
        <h1>Component 2</h1>
      </gl-component>
      <gl-component title="component3">
        <h1>Component 3</h1>
      </gl-component>
    </gl-stack>
  </gl-row>
</golden-layout>
    </div>
  </template>

  <script>

  export default {
    data() {
      return {
      }
    },
    methods: {
    }
  }
  </script>
  