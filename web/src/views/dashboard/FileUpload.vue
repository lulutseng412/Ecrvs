<template>
  <div>
    <div id="app">
      <div class="container">
        <input id="customFile" type="file" class="form-control" @change="FileUpload" />
        <img :src="filePath" alt />
        {{ filePath }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      filePath: "",
      token: "",
      api: {
        uuid: process.env.VUE_APP_UUID,
        path: process.env.VUE_APP_APIPATH,
      },
    };
  },
  methods: {
    FileUpload() {
      this.token = document.cookie.replace(
        /(?:(?:^|.*;\s*)hexHomeworkToken\s*\=\s*([^;]*).*$)|^.*$/,
        "$1"
      );
      // 選取 DOM 中的檔案資訊

      // 轉成 Form Data
      const formData = new FormData();
      formData.append("file", uploadedfile);

      // 路由、驗證
      const url = `${this.api.path}/api/${this.api.uuid}/admin/storage`;
      axios.defaults.headers.common.Authorization = `Bearer ${this.token}`;
    },
  },
};
</script>

<style>
html,
body {
  height: 100vh;
  text-align: center;
}
body {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
  