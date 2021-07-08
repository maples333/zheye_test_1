<template>
  <div class="row">
    <div class="col-4 mb-4" v-for="column in columnList" :key="column.id">
      <div class="card h-100 shadow-sm" style="width: 18rem;">
        <div class="card-body text-center">
          <img class="rounded-circle border border-light w-25 my-3" :src="column.avatar" alt="column.title">
          <h5 class="card-title">{{ column.title }}</h5>
          <p class="card-text text-left">{{ column.description }}</p>
          <a href="#" class="btn btn-outline-primary">进入专栏</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent, PropType ,computed} from 'vue';

// import "bootstrap/dist/css/bootstrap.min.css"

export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string
}

export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      // 只能用PropType来添加断言
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup(props) {
    const columnList = computed(()=>{
      // map() 方法按照原始数组元素顺序依次处理元素。
      return props.list.map(column =>{
        if(!column.avatar){
          // 处理没有设置图片的情况，设置一张默认的图片上去
          column.avatar = require('@/assets/zhihu_default.png')
        }
        return column
      })
    })
    return {
      columnList
    }
  }
});
</script>
