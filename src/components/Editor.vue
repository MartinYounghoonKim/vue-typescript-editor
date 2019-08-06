<template>
    <div>
        <div class="editor" id="codex-editor">
        </div>
        <button type="button" @click="onSaveHandler">저장</button>
    </div>

</template>

<script lang="ts">
    import {Component, Prop, Vue} from 'vue-property-decorator';
    import EditorJS from '@editorjs/editorjs';
    import List from '@editorjs/list';
    import Header from '@editorjs/header';
    import ImageTool from '@editorjs/image';
    import Embed from '@editorjs/embed';

    @Component({
        name: 'Editor',
    })
    export default class Editor extends Vue {
        test: EditorJS;
        constructor () {
            super();
            this.test = null;
        }
        created () {
            this.test = new EditorJS({
                holderId: 'codex-editor',
                tools: {
                    header: Header,
                    embed: {
                        class: Embed,
                        inlineToolbar: false,
                        config: {
                            services: {
                                youtube: true,
                            }
                        }
                    },
                    list: {
                        class: List,
                        inlineToolbar: true,
                    },
                    image: {
                        class: ImageTool
                    }
                },
            });
        }
        @Prop() private msg!: string;
        onSaveHandler (): void {
            console.log(123);
            this.test.save()
                .then(res => {
                    console.log(res);
                })
        }
    }
</script>

<style scoped lang="scss">
    .editor {
        text-align: left;
        border: 1px solid gray;
        height: 1000px;
        textarea {
            width: 100%;
            height: 100%;
        }
    }
</style>
