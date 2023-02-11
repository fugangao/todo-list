<template>

    <form class="mt-4" @submit.prevent>
        <div class="form-row align-items-center">
           
            <div class="col-auto">
                <label class="sr-only" for="inlineFormInputGroup">Username</label>
                <div class="input-group mb-2">
                    <div class="input-group-prepend">
                        <div class="input-group-text">任务</div>
                    </div>
                    <input type="text" class="form-control" placeholder="请输入任务" style="width: 500px;" v-model.trim="newTaskName" >
                </div>
            </div>
            <div class="col-auto">
                <button type="submit" class="btn btn-primary mb-2" @click="addNewTask">添加新任务</button>
            </div>
        </div>
    </form>
</template>

<script>
export default {
    name: 'TodoInput',
    props: {
        list: {
            type: Array,
            required: true,
            default: [],
        }
    },
    emits: ['add'],
    data() {
        return {
            newTaskName: '',
            nextId: 4,
        }
    },
    methods: {
        // addNewTask() {
        //     if (this.newTaskName === '') return alert('输入不能为空')
        //     this.$emit('add', this.newTaskName)
        //     this.newTaskName = ''
        // }
        addNewTask() {
            this.list.push({
                id: this.nextId, task: this.newTaskName, done: false
            })
        }
    }
}
</script>

<style lang="css" scoped>

</style>