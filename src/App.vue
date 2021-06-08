<template>
  <div id="app" >
    <div class="image-edit-container">
        <div class="image-editor"> 
          <image-editor
              :include-ui="true"
              :options="options"
            >
          </image-editor>
        </div>
    </div>
  </div>
</template>

<script>

// Load Style Code
import "tui-color-picker/dist/tui-color-picker.css";
import "tui-image-editor/dist/tui-image-editor.css";
import {ImageEditor} from '@toast-ui/vue-image-editor';

export default {
  name: 'App',
  components: {
    ImageEditor
  },
  data() {
    return {
        options: {
          includeUI: {
            loadImage: {
              path: "/assets/SampleWhite.png",
              name: "EditImage"
            },
            initMenu: "draw"
          },
          usageStatistics: false,
          cssMaxWidth: 1000,
          cssMaxHeight: 2000
        }
    }
  },
  methods:{
     async done() {
      let imageData = this.$refs.tuiImageEditor.editorInstance.toDataURL();
      console.log(imageData)
    },
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 98vh;
}
.image-edit-container {
  width: 100%;
  height: 100%;
}
.image-editor {
  height: 100%;
  position: relative;
}
.tui-image-editor-header-logo {
  display: none;
}
</style>
