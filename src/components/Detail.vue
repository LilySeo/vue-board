<template>
  <div>
    <div>{{ datas.title }}</div>
    <div>{{ datas.content }}</div>
    <div>{{ datas.writer }}</div>
    <button @click="dataUpdate">수정</button>
    <button @click="dataDelete">삭제</button>
  </div>
</template>

<script>
import data from "@/data"

export default {
  name: 'Detail',
  data() {
    const index = this.$route.params.contentId
    return {
      datas: data[index],
      index: index
    }
  },
  methods: {
    dataUpdate() {
      this.$router.push({
        name: 'Create',
        params: {
          contentId: this.index
        }
      })
    },
    dataDelete() {
      data.splice(this.index, 1)
      this.$router.push({
        path: '/'
      })
    }
  }
}
</script>