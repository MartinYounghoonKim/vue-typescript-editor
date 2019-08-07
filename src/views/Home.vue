<template>
  <div class="home">
    <editor />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Editor from '@/components/Editor.vue';

@Component({
  components: {
    Editor
  }
})
export default class Home extends Vue {}
</script>
