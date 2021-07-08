<template>
  <div class="container">
    <columnList :list="list"></columnList>
  </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue';
import "bootstrap/dist/css/bootstrap.css"
import ColumnList, {ColumnProps} from "./components/ColumnList.vue";

const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1专栏',
    description: 'test1专栏',
    avatar: 'https://v3.cn.vuejs.org/logo.png'
  },
  {
    id: 2,
    title: 'test2专栏',
    description: 'test2专栏',
    // avatar: 'https://v3.cn.vuejs.org/logo.png'
  },
  {
    id: 3,
    title: 'test2专栏',
    description: 'test2专栏',
    avatar: 'https://v3.cn.vuejs.org/logo.png'
  },
  {
    id: 4,
    title: 'test2专栏',
    description: 'test2专栏',
    avatar: 'https://v3.cn.vuejs.org/logo.png'
  }
]
export default defineComponent({
  name: 'App',
  components: {
    ColumnList
  },
  setup() {
    return {
      list: testData
    }
  }
});
</script>

<style>

</style>
