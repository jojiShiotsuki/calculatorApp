<script setup>
import { ref } from 'vue'

const total = ref(0)
const num = ref('')
const getNum = (event) => {
	const number = event.target.getAttribute('data-number');
	num.value = number
	total.value = total.value * 10 + parseInt(number)
	console.log(total.value)
}
const addition = (event) => {
	
}

</script>

<template>
	<section class="calculatorContainer">
		<div class="calculator">
			<div class="display" id="display">{{ total }}</div>
			<div class="buttons">
				<button class="btn operator" data-operator="C">C</button>
				<button class="btn operator" data-operator="/">/</button>
				<button class="btn operator" data-operator="*">*</button>
				<button class="btn operator" data-operator="-">-</button>
				<button @click="getNum" class="btn" data-number="7">7</button>
				<button @click="getNum" class="btn" data-number="8">8</button>
				<button @click="getNum" class="btn" data-number="9">9</button>
				<button @click="addition" class="btn operator" data-operator="+">+</button>
				<button @click="getNum" class="btn" data-number="4">4</button>
				<button @click="getNum" class="btn" data-number="5">5</button>
				<button @click="getNum" class="btn" data-number="6">6</button>
				<button class="btn operator" data-operator="=">=</button>
				<button @click="getNum" class="btn" data-number="1">1</button>
				<button @click="getNum" class="btn" data-number="2">2</button>
				<button @click="getNum" class="btn" data-number="3">3</button>
				<button @click="getNum" class="btn" data-number="0">0</button>
				<button class="btn operator" data-operator=".">.</button>
			</div>
    	</div>
	</section>
</template>