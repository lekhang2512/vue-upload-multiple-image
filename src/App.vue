<template>
  <div id="my-strictly-unique-vue-upload-multiple-image" style="display: flex; justify-content: center;">
    <vue-upload-multiple-image @upload-success="uploadImageSuccess" @before-remove="beforeRemove" @edit-image="editImage"
      @data-change="dataChange" @limit-exceeded="limitExceeded"></vue-upload-multiple-image>
  </div>
</template>

<script>
import VueUploadMultipleImage from './components/VueUploadMultipleImage'
export default {
  name: 'app',
  components: {
    VueUploadMultipleImage
  },
  methods: {

    beforeRemove(index, done, fileList) {
      var r = confirm("remove image")
      if (r == true) {
        done()
      }
    },

  }
}
</script>
