<script setup lang="ts">
import { ref } from 'vue';

const data = new Date();
const current = `${data.getMonth() + 1}/${data.getDate()}`;

// 计算特定天数之前的日期
const calculateDate = (daysAgo: number) => {
  const date = new Date();
  date.setDate(date.getDate() - daysAgo);
  return `${date.getMonth() + 1}/${date.getDate()}`;
};

// 填充日期数组
const dates = ref([
  calculateDate(1),  // D1
  calculateDate(2),  // D2
  calculateDate(4),  // D4
  calculateDate(7),  // D7
  calculateDate(15), // D15
  calculateDate(30), // D30
  calculateDate(60), // D60
  calculateDate(90)  // D90
]);

</script>

<template>
  <div class="p-4">
    <div class="text-18px color-#001e1d font-500">艾宾浩斯每日单词列表</div>
    <div class="pt-1 pb-2 text-14px color-#0f3433">当前日期：{{ current }}</div>
    <table border class="border-collapse w-120 bg-white h-30 border-rd-md">
      <tr>
        <th colspan="8">Review</th>
      </tr>
      <tr>
        <th>D1</th>
        <th>D2</th>
        <th>D4</th>
        <th>D7</th>
        <th>D15</th>
        <th>D30</th>
        <th>D60</th>
        <th>D90</th>
      </tr>
      <tr class="text-center">
        <td>{{ dates[0] }}</td>
        <td>{{ dates[1] }}</td>
        <td>{{ dates[2] }}</td>
        <td>{{ dates[3] }}</td>
        <td>{{ dates[4] }}</td>
        <td>{{ dates[5] }}</td>
        <td>{{ dates[6] }}</td>
        <td>{{ dates[7] }}</td>
      </tr>
    </table>
  </div>
</template>
