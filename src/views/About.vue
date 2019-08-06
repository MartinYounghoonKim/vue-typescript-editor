<template>
  <div class="about">
    <h1>This is an about page</h1>
    <editor />
  </div>
</template>
<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import Editor from "../components/Editor";
    @Component({
        components: { Editor }
    })
    export default class About extends Vue {
    }
</script>
