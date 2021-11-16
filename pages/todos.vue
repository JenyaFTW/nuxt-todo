<template>
	<div id="todos">
		<h2 class="text-center">
			Todos page
			<transition name="slide">
				<span v-if="loading" class="loading-spinner ml-3">
					<span class="spinner-border"></span>
				</span>
			</transition>
		</h2>

		<alert v-if="error">{{ error }}</alert>
		
		<section>
			<todo-list :todos="todos" />
		</section>
	</div>
</template>

<script>
import TodoList from '../components/TodoList.vue';

export default {
	name: 'TodosPage',
	components: {
		TodoList
	},
	data() {
		return {
			todos: [],
			loading: false,
			error: null,
		};
	},
	created() {
		this.fetchTodos();
	},
	methods: {
		async fetchTodos() {
			this.loading = true;

			try {
				const res = await this.$axios.get('https://jsonplaceholder.typicode.com/todos');
				this.todos = res.data;
			} catch (err) {
				this.error = err;
			}

			this.loading = false;
		}
	}
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