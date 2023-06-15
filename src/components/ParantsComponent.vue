<template>
  <div>
  <div className="text-center py-4 lg:px-4">
    <div class="p-2 bg-indigo-800 items-center text-indigo-100 leading-none lg:rounded-full flex lg:inline-flex" role="alert">
      <span class="flex rounded-full bg-indigo-500 uppercase px-2 py-1 text-xs font-bold mr-3">New</span>
      <span class="font-semibold mr-2 text-left flex-auto">Get the coolest UI kit for Vue.js, now with Tailwind CSS.</span>
    </div>
  </div>
    <h1>{{ title }}</h1>
    <button @click="greet">Say Hello</button>
    <!-- 使用 v-if 控制列表的顯示 -->
    <ul v-if="showList">
      <!-- 使用 v-for 渲染一個列表 -->
      <li v-for="(item, index) in list" :key="index">
        {{ item }}
      </li>
    </ul>
    <!-- 將 message 傳遞給子組件 -->
    <child-component :message="childMessage" @child-event="handleChildEvent"></child-component>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      title: 'Hello, Vue.js!',
      showList: true,
      list: ['Item 1', 'Item 2', 'Item 3'],
      childMessage: 'Message from parent'
    }
  },
  methods: {
    greet() {
      alert('Hello!');
    },
    handleChildEvent(eventValue) {
      alert(`Received value: ${eventValue} from child component.`);
    }
  }
}
</script>