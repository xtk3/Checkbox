<script>
export default {
  props: {
    label: {String,default: "Выключить"},
    checked: {type: Boolean,default: false},
    active:{type: Boolean,default: true},
    disabled:{type: Boolean,default: false},
  },
};
</script>
<template>
  <div>
    <input
        @input="(event) => $emit('update:checked', event.target.checked)"
        type="checkbox"
        :checked="checked"
        :disabled="disabled"
        class="mr-2 hidden"
        :id="fieldId"/>
    <label v-if="active" :for="id">
      {{label}}
    </label>
  </div>
</template>
<style>
input[type="checkbox"]:checked + label:after,
input[type="checkbox"]:not(:checked) + label:after {
  left: 3px;
  top: 4px;
  width: 10px;
  height: 5px;
  border-radius: 1px;
  border-left: 4px solid #d03535;
  border-bottom: 4px solid #d03535;
  -webkit-transform: rotate(-45deg);
  -moz-transform: rotate(-45deg);
  -o-transform: rotate(-45deg);
  -ms-transform: rotate(-45deg);
  transform: rotate(-45deg);
}
</style>
