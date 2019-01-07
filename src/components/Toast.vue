<template>
    <div>
        <div v-if="flag">Thanks for searching!</div>
    </div>
</template>

<script>
export default {
    props: ['val'],
    data: () => ({
        flag: undefined,
        lastValue: ''
    }),
    watch: {
        val (val) {
            if (val) {
                this.flag = false
                this.lastValue = val
                this.sendMessage(val)
            }
        }
    },
    methods: {
        sendMessage (val) {
            setTimeout(() => {
                if (val === this.lastValue) {
                    this.flag = true
                    this.hideMessage()
                }
            }, 3000)
        },
        hideMessage () {
            setTimeout(() => {
                this.flag = false
            }, 2000)
        }
    }
}
</script>

<style>

</style>
