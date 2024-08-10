<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
	<section class="intro-section">
        <h1>Welcome to The Calculator App</h1>
        <p>My simple calculator App</p>
        <RouterLink to="/calculator" class="btn-primary">Go to Calculator</RouterLink>
	</section>
</template>