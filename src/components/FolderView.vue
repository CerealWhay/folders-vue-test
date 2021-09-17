<template>
  <div class="folder">
    <div class="folder-name-wrapper" @click="openOrCloseFolder">
      <span class="folder-name" :class=folderName>{{name}}</span>
      <span class="folder-info">
        {{folders.length}} folders, {{files.length}} files
      </span>
    </div>
    <div class="content-wrapper" :style="{'display':display}">
      <div  v-for="folder in folders" >
        <FolderView :name="folder.name" :folders="folder.folders" :files="folder.files"/>
      </div>
      <div v-for="file in files">
        <FileView :name="file.name"/>
      </div>
    </div>
  </div>
</template>

<script>
import FileView from "./FileView";
export default {
  name: 'FolderView',
  components: {FileView},
  props: {
    name: String,
    folders:Array,
    files:Array,
  },
  data(){
    return {
      display: 'none',
      folderName: '',
    }
  },
  methods: {
    openOrCloseFolder() {
      this.display === 'none' ? this.display = 'block': this.display = 'none';
      this.folderName === '' ? this.folderName = 'folder-name-active': this.folderName = '';
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.folder {
  background-color: white;
  .folder-name-wrapper {
    border-radius: 5px;
    padding: 10px;
    .folder-name {
      color: #333;
      &::before {
        display: inline-block;
        vertical-align: top;
        content: ">";
        font-weight: 100;
        font-size: 16px;
        color: #467bff;
        margin-right: 15px;
        transition: 0.2s;
      }
      &-active {
        &::before {
          transform: rotate(90deg);
        }
      }
    }
    .folder-info {
      margin-left: 30px;
      color: #ccc;
      font-size: 14px;
    }
    &:hover {
      .folder-name {
        color: #467bff;
      }
      cursor: pointer;
      background-color: #e9f0fe;
    }
  }
  .content-wrapper{
    margin-left: 10px;
  }
}
</style>
