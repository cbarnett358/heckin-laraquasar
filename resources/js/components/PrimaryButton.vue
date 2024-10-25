<template>
        <q-btn color="primary" label="Primary" />
</template>

<script>
    import { ref } from 'vue'

    export default {
        setup () {
            return {
                slide: ref('first')
            }
        }
    }
</script>
