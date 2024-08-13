<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
	<section class="intro-section">
        <h1>Welcome to The Calculator App</h1>
        <p>My calculator app is designed to help you perform a variety of calculations easily and efficiently. Whether you're doing basic arithmetic or more complex operations, our user-friendly interface makes it simple.</p>
        <RouterLink to="/calculator" class="btn-primary">Go to Calculator</RouterLink>
	</section>
</template>