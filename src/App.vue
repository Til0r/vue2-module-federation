<template>
  <HelloWorld msg="Vue" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import { useWindowSize } from "@vueuse/core";
import { ref, watch } from "@vue/composition-api";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
const isActive = ref(false);
console.log(`isActive ${JSON.stringify(isActive)}`);

const { width: windowWidth } = useWindowSize();
watch(windowWidth, (val) => {
  console.log(val);
});
</script>

<style></style>
