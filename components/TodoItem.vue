<template>
  <li class="list-group-item list-group-item-action todo-item">
		<span :class="{ 'completed-todo': todo.completed }">{{ todo.title }}</span>
	</li>
</template>

<script>
export default {
	name: 'TodoItem',
	props: {
		todo: {
			type: Object,
			required: true,
		}
	}
};
</script>

<style scoped>
.completed-todo {
  text-decoration: line-through !important;
}

.todo-item {
  display: flex;
}
</style>>