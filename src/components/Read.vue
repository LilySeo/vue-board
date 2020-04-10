<template>
  <div>
    <table>
      <thead>
        <tr>
          <th>번호</th>
          <th>제목</th>
          <th>내용</th>
          <th>글쓴이</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(data, index) in datas" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ data.title }}</td>
          <td>{{ data.content }} </td>
          <td>{{ data.writer }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import data from "@/data"

export default {
  name: 'Read',
  data() {
    return {
      datas: data
    }
  }
}
</script>

<style>
table td {
  border: 1px solid #ddd;
}
</style>