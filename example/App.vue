<template>
  <ele-upload-video
    :fileSize="20"
    :responseFn="handleResponse"
    @error="handleUploadError"
    action="https://jsonplaceholder.typicode.com/posts/"
    name="video"
    style="margin: 50px"
    v-model="video"
  />
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      video: null
    }
  },
  methods: {
    handleUploadError (error) {
      this.$notify.error({
        title: '上传提示',
        message: '测试环境无法上传文件'
      })
      // eslint-disable-next-line no-console
      console.log('error', error)
    },
    handleResponse({ id }) {
      return 'https://s3.pstatp.com/aweme/resource/web/static/image/index/tvc-v2_30097df.mp4?id=' + id
    }
  }
}
</script>

