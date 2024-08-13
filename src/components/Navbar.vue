<script setup>
import { RouterLink, useRoute } from 'vue-router';
</script>

<template>
	<div>
		<nav class="navbar">
			<ul>
				<li><RouterLink to="/">Home</RouterLink></li>
				<li><RouterLink to="/calculator">Calculator</RouterLink></li>
			</ul>
		</nav>
	</div>
</template>