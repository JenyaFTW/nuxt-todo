<template>
	<nav class="navbar navbar-expand-sm navbar-light bg-light">
		<a class="navbar-brand" href="#">Todos Nuxt.js Example</a>

		<ul class="navbar-nav mr-auto">
			<li class="nav-item">
				<nuxt-link class="nav-link" to="/">Main</nuxt-link>
			</li>
			<li class="nav-item">
				<nuxt-link class="nav-link" to="/todos">Todos</nuxt-link>
			</li>
		</ul>
	</nav>
</template>

<script>
export default {
	name: "NavBar",
};
</script>