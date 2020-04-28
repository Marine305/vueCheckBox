<template>
  <div id="app">
    <checklist :list="list" />
  </div>
</template>

<script>
import Checklist from "@/components/CheckList";

export default {
  name: "App",
  data() {
    return {
      list: [
        {
          id: 1,
          title: "disabled & checked",
          option1: "disabled",
          option2: "checked",
        },
        { id: 2, title: "disabled", option1: "disabled", option2: "" },
        { id: 3, title: "click 1", option1: "", option2: "" },
        { id: 4, title: "click 2", option1: "", option2: "" },
      ],
    };
  },
  components: {
    Checklist,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
html,
body,
div,
span,
iframe,
a,
form,
label {
  margin: 0;
  padding: 0;
  border: 0;
  vertical-align: baseline;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0) !important;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}

html {
  box-sizing: border-box;
  width: 100%;
  -webkit-text-size-adjust: none;
  -webkit-overflow-scrolling: touch;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -ms-text-size-adjust: 100%;
}

body {
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  color: #fff;
  line-height: 1.2;
  letter-spacing: 0;
  width: 100%;
  height: 100%;
  min-width: 320px;
  display: flex;
  flex-flow: column nowrap;
  overflow-x: hidden;
  position: relative;
}
</style>
