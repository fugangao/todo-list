<template>
    <div class="btn-group mt-4 btn-group-lg">
        <button type="button" class="btn" :class="active === 0 ? 'btn-primary' : 'btn-secondary'"
            @click="btnClick(0)">全部</button>
        <button type="button" class="btn" :class="active === 1 ? 'btn-primary' : 'btn-secondary'" @click="btnClick(1)">
            已完成 </button>
        <button type="button" class="btn" :class="active === 2 ? 'btn-primary' : 'btn-secondary'" @click="btnClick(2)">
            未完成 </button>
    </div>
</template>
        
<script>
export default {
    name: 'TodoButton',
    props: {
        active: {
            type: Number,
            required: true,
            default: 0,
        }
    },
    emits: ['update:active'],
    methods: {
        btnClick(index) {
            if (index === this.active) return 
            this.$emit('update:active', index)
        }
    }
}
</script>
        
<style>

</style>
