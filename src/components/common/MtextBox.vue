// 通用组件 - 多行文本输入框
<template lang="pug">
.MtextBox
    textarea(
        v-model="message"
        v-bind:maxLength="setMtextBoxObj.maxLength"
        v-bind:placeholder="setMtextBoxObj.placeholder"
    )
    p {{ message.length }} / {{ setMtextBoxObj.maxLength }}
</template>

<script>
export default {
    name: 'MtextBox',
    props: {
        // 多行文本 - 基本配置
        setMtextBoxObj: {
            type: Object,
            default: function() {
                return {
                    maxLength: 200,
                    placeholder: '提示文本'
                }
            }
        }
    },
    methods: {
        test() {
            console.log( 'test' )
        }
    },
    data() {
        return {
            message: ''
        }
    }
}   
</script>

<style lang="sass">
@import "../../sass/main"

.MtextBox
    +REL
    textarea
        padding: 5%
        width: 90%
        +REM( height, $F-text*11 )
        border: none
        +REM-fontStyle( $F-text, $C-assist,2 )
    >p
        +ABS
        bottom: $D-autoPadding
        right: $D-autoPadding
        +REM-fontStyle( $F-assist, $C-assist )
</style>