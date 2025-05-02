<script setup lang="ts">
import { ref } from 'vue'
import {
  SelectContent,
  SelectItem,
  SelectItemText,
  SelectPortal,
  SelectRoot,
  SelectTrigger,
  SelectValue,
} from 'reka-ui'

const value = ref<('a' | 'b' | 'c')[]>([])
</script>

<template>
  <form @submit.prevent="console.log(value)">
    <SelectRoot v-model="value" multiple required>
      <SelectTrigger>
        <SelectValue placeholder="Select" />
      </SelectTrigger>

      <SelectPortal>
        <SelectContent class="border-gray-300 border rounded-md shadow-md">
          <SelectItem value="a">
            <SelectItemText> Item A </SelectItemText>
          </SelectItem>

          <SelectItem value="b">
            <SelectItemText> Item B </SelectItemText>
          </SelectItem>

          <SelectItem value="c">
            <SelectItemText> Item C </SelectItemText>
          </SelectItem>
        </SelectContent>
      </SelectPortal>
    </SelectRoot>

    <button type="submit" class="shadow-sm ml-10 bg-indigo-600 text-white px-3 py-2">submit</button>
  </form>

  <kbd>Value is : {{ value }}</kbd>
</template>
