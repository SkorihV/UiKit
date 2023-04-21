<script setup>
  import Checkbox from "@/components/checkbox/Checkbox.vue";
  import {ref} from "vue";

  const emits = defineEmits(['update:value'])
  const props = defineProps({
    value: {
      type: Array,
      default: () => []
    },
    name: {
      type: String,
      required: true
    },
    options: {
      type: Array,
      default: () => [],
      required: true,
      validator(value) {
        const hasName = value.every((option) => Object.keys(option).includes('name'));
        const hasId = value.every((option) => Object.keys(option).includes('id'));
        return hasName && hasId;
      }
    }
  })

  const check = (params) => {
    let updateValue = [...props.value];
    if (params.checked) {
      updateValue.push(params.optionId)
    } else {
      updateValue.splice(updateValue.indexOf(params.optionId), 1);
    }

    emits('update:value', updateValue);
  }

</script>

<template>
  <div v-for="option in options" :key="option.id">
      <Checkbox
        :label="option.name"
        :name="name"
        :id="option.id"
        :value="option.name"
        :checked="value.includes(option.id)"
        group
        @updateCheckboxGroup="check"
      ></Checkbox>
  </div>
</template>

<style scoped>

</style>
