<script>
import Checkbox from "./components/Chec_kbox.vue";
import { ref } from "vue";
export default {
  name: "App",
  setup() {
    const active = ref(false);
    return {
      active,
    };
  },
  components: {
    "check-box": Checkbox,
  },
};
</script>

<template>
  <div class="app">
    <checkbox
        label="Checkbox Active"
        name="active"
        disabled="disabled"
        v-model:checked="active"/>
    <check-box fieldId="volue" />
  </div>
</template>

