<template>
	<transition-group class="list-group" name="todo-list" tag="ul">
		<todo-item v-for="todo in todos" :key="todo.id" :todo="todo" />
	</transition-group>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
	name: "TodoList",
	props: {
		todos: {
			type: Array,
			required: true,
		},
	},
	components: {
		TodoItem,
	},
};
</script>

<style scoped>
.todo-list-enter-active,
.todo-list-leave-active {
	transition: all 0.5s;
}
.todo-list-enter,
.todo-list-leave-to {
	opacity: 0;
	transform: scaleY(0);
}
</style>