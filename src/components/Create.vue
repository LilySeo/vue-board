<template>
  <div>
    <input v-model="title" type="text" placeholder="제목" />
    <textarea v-model="content" name="" id="" cols="30" rows="10" placeholder="내용"></textarea>
    <input v-model="writer" type="text" placeholder="글쓴이" />

    <button @click="write">저장</button>
    <button @click="clear">취소</button>
  </div>
</template>

<script>
import data from '@/data'

export default {
  name: 'Create',
  data() {
    return {
      datas: data,
      title: "",
      content: "",
      writer: "",
    }
  },
  methods: {
    write() {
      this.datas.push({
        title: this.title,
        content: this.content,
        writer: this.writer
      })
      this.$router.push({
        path: '/'
      })
    },
    clear() {
    }
  
  }

}
</script>