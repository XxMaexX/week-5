<template>
    <div>
        <form @submit.prevent="addTodo" >
            <input type="text" v-model="newTodo" >
        </form>
        <slot name="desc" > </slot>
        <br/>
        <slot> </slot>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodo:" "
        };
    },
    methods: {
        addTodo() {
            if (this.newTodo.length) {
                this.$emit("newTodo", this.newTodo);
                this.newTodo = "";
            }
        }
    }
};
</script>

