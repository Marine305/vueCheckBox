<template>
  <div class="check-list">
    <checkbox v-for="item of list" v-bind:item="item" />
  </div>
</template>

<script>
import Checkbox from "@/components/Checkbox";

export default {
  props: ["list"],
  components: {
    Checkbox,
  },
};
</script>

<style lang="scss">
.check-list {
  display: flex;
  flex-direction: column;
  max-width: 300px;
  margin: 0 auto;
  align-items: start;
}
</style>
