<template>
  <div>
    <input v-model="title" type="text" placeholder="제목" />
    <textarea v-model="content" name="" id="" cols="30" rows="10" placeholder="내용"></textarea>
    <input v-model="writer" type="text" placeholder="글쓴이" />

    <button @click="index !== undefined ? update() : write()">{{ index !== undefined ? '수정' : '저장'}}</button>
    <button @click="clear">취소</button>
  </div>
</template>

<script>
import data from '@/data'

export default {
  name: 'Create',
  data() {
    const index = this.$route.params.contentId
    return {
      datas: data,
      index: index,
      title: index !== undefined ? data[index].title : "",
      content: index !== undefined ? data[index].content : "",
      writer: index !== undefined ? data[index].writer : "",
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
    update() {
      data[this.index].title = this.title
      data[this.index].content = this.content
      data[this.index].writer = this.writer
    
      this.$router.push({
        path: '/'
      })
    },
    clear() {
      this.$router.push({
        path: '/'
      })
    }
  
  }

}
</script>