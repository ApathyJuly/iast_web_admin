<template>
  <div class="app-container">
    <button @click="add">add</button>
    <button @click="change">切换</button>
    <golden-layout class="hscreen" ref="vueGolden">
      <gl-row>
        <gl-stack>
          <gl-component title="component2">
            <h1>Component this two</h1>
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
      num: 4,
      config: {
        content: [
          {
            type: "column",
            content: [
              {
                type: "component",
                componentName: "componentOne",
                componentState: { text: "Component 1" },
              },
            ],
          },
        ],
      },
    };
  },
  created() {},
  methods: {
    add() {
      this.$refs.vueGolden.add(this.newItem);
      this.num++;
      this.assem.push({ id: this.num });
    },
    change() {
      this.$refs.vueGolden.changeSelectedName("component3");
    },
  },
  components: {},
  computed: {
    newItem() {
      let config = {
        type: "component",
        componentName: `Newcomponent${this.num}`,
        componentState: { key: this.num },
      };
      return config;
    },
  },
};
</script>
 
<style>
.hscreen {
  width: 100vw;
  height: 100vh;
}
</style>
