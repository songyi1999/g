<template>
    <div>
        <label for=""> 输入</label>
        <textarea name="" id="" cols="30" rows="10" v-model="instr"></textarea>
        <button @click="dochange">提交</button>
        <textarea name="" id="" cols="30" rows="10" v-model="outstr"></textarea>

    </div>
</template>
<script>
import translate from 'google-translate-open-api'
export default {
  data () {
    return {
      instr: '',
      outstr: ''
    }
  },
  methods: {
    async     dochange () {
      const result = await translate(this.instr, {
        tld: 'cn',
        to: 'zh-CN',
        browers: true
      })
      const data = result.data[0]
      this.outstr = data
    }
  }
}
</script>
