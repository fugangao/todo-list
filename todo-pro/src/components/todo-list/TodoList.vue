<template>
    <ul class="list-group mt-3">
        <li class="list-group-item d-flex justify-content-between align-items-center" v-for="(item, index) in list"
            :key="item.id">
            <div class="form-check">
                <input class="form-check-input" type="checkbox" value="" id="defaultCheck1" v-model="item.done">
                <label class="form-check-label" for="defaultCheck1">
                    {{item.task}}
                </label>
            </div>
            <span class="badge badge-success badge-pill" v-if="item.done">已完成</span>
            <span class="badge badge-danger badge-pill" v-else>未完成</span>
        </li>

    </ul>
</template>

<script>
export default {
    name: 'TodoList',
    props: {
        list: {
            type: Array,
            required: true,
            default: [],
        }
    }
}
</script>

<style lang="css" scoped>

</style>