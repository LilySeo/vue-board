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
        <tr v-for="(data, index) in datas" :key="index" @click="detail(index)">
          <td>{{ index + 1 }}</td>
          <td>{{ data.title }}</td>
          <td>{{ data.content }} </td>
          <td>{{ data.writer }}</td>
        </tr>
      </tbody>
    </table>

    <button @click="write">글쓰기</button>
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
  },
  methods: {
    write() {
      console.log("글쓰기")
      this.$router.push({
        // object
        path: 'create'
      })
    },
    detail(index) {
      // console.log(index)
      this.$router.push({
        // 이름을 가지는 라우트
        name: 'Detail',
        params: {
          contentId: index
        }
      })
    }
  }
}
</script>

<style>
table td {
  border: 1px solid #ddd;
}

table tr {
  cursor: pointer;
}
</style>