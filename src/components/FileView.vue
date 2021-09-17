<template>
  <div class="file">
    <a>{{name}}</a>
  </div>
</template>

<script>
export default {
  name: 'FileView',
  props: {
    name: String
  }
}
</script>

<style scoped lang="scss">
.file{
  line-height: 38px;
  margin-left: 10px;
  color: #333;
  a {
    &:hover {
      cursor: pointer;
      color: #467bff;
    }
  }
}
</style>
