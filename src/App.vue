<template>
  <div id="my-strictly-unique-vue-upload-multiple-image" style="display: flex; justify-content: center;">
    <vue-upload-multiple-image
      @upload-success="uploadImageSuccess"
      @before-remove="beforeRemove"
      @edit-image="editImage"
      @data-change="dataChange"
      @limit-exceeded="limitExceeded"
      ></vue-upload-multiple-image>
  </div>
</template>

<script>
import VueUploadMultipleImage from './components/VueUploadMultipleImage'
import axios from 'axios'
export default {
  name: 'app',
  data () {
    return {
    }
  },
  components: {
    VueUploadMultipleImage
  },
  methods: {
    uploadImageSuccess(formData, index, fileList) {
      console.log('data', formData, index, fileList)
      // Upload image api
      // axios.post('http://gostore.gostore-api.test/api/items/upload', formData).then(response => {
      //   console.log(response)
      // })
    },
    beforeRemove (index, done, fileList) {
      console.log('index', index, fileList)
      var r = confirm("remove image")
      if (r == true) {
        done()
      } else {
      }
    },
    editImage (formData, index, fileList) {
      console.log('edit data', formData, index, fileList)
    },
    dataChange (data) {
      console.log(data)
    },
    limitExceeded(amount){
      console.log(amount)
    }
  }
}
</script>
