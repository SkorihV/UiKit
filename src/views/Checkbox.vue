<script setup>
 import Checkbox from '@/components/checkbox/Checkbox.vue'
 import CheckboxGroup from "@/components/checkbox/CheckboxGroup.vue";
 import {ref} from "vue";

 const checkboxActive = ref(true);
 const checkboxDisabled= ref(true);
 const baseStateDisabledChecked = ref(true);

 const list = ref([
   {name: 'Антон', id: 'h1'},
   {name: 'Олег', id: 'h2'},
   {name: 'Константин', id: 'h3'},
   {name: 'Пельмень', id: 'h4'},
 ]);

 const selectedCheckbox = ref(['h1', 'h3']);

</script>

<template>
  <h1 class="heading-1">Галочка</h1>

  <div class="heading-2">Checkbox active</div>
  <div class="line">
      <Checkbox
        label="Checkbox active"
        id="checkboxActive"
        name="checkboxActive"
        value="asd as"
        v-model:checked="checkboxActive"
      />
  </div>
    <div class="heading-2">Checkbox Disabled</div>
    <div class="line">
        <Checkbox
          label="Checkbox active"
          id="checkboxDisabled"
          name="checkboxDisabled"
          value="asd as"
          :disabled="checkboxDisabled"
          v-model:checked="baseStateDisabledChecked"
        />
    </div>

    <div class="heading-2">Checkbox group</div>
    <div class="line  line_block">
      <p>{{selectedCheckbox}}</p>
        <checkbox-group
           name="checkboxList"
          :options="list"
           v-model:value="selectedCheckbox"
        ></checkbox-group>
    </div>
</template>


<style scoped>

</style>
