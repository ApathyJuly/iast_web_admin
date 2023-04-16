<template>
  <div id="layoutContainer"></div>
</template>

<script>
import GoldenLayout from "golden-layout";
import $ from "jquery";

export default {
  name: "VueGoldenLayout",
  // 传入数据配置数据
  props: {
    config: {
      required: false,
    },
  },
  data() {
    return {
      layout: null,
      arrCom: [],
      savedState: null,
      myLayout: "",
      itemContainer: [],
      layoutA: "",
      layoutB: "",
      nodeBody: "",
      closeStackText: "",
      closeTabText: "",
      selectedName: "",
    };
  },
  mounted() {
    arrConfig(config)
    this.createLayout()
  },
  methods: {
    //创建布局：
    createLayout() {
      let layout = new GoldenLayout(this.config, $("#layoutContainer"));
      for (let ele of arrCom) {
        layout.registerComponent(ele, (container, state) => {
          container.getElement().html("<h2>" + state.text + "</h2>");
        });
      }
      myLayout.init();
    },
  },
  arrConfig(config) {
    let minify = (this.minify = GoldenLayout.minifyConfig(config));
    let arrCom = new Array();
    minify.g[0].g.forEach((e) => {
      if (e.l == "5") {
        arrCom.push(e.h);
      } else {
        e.g.forEach((com) => {
          arrCom.push(com.h);
        });
      }
    });
    this.arrCom = arrCom;
    return arrCom;
  },
};
</script>
<style></style>