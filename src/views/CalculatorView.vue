<script setup>
import { ref } from 'vue'

const display = ref(0)
const currentNum = ref('')
const previousNum = ref('')
const operator = ref('')

const getNum = (event) => {
	const number = event.target.getAttribute('data-number');
	currentNum.value += number
	display.value = currentNum.value
}

const setOperator = (op) => {
	if(currentNum.value){
		previousNum.value = currentNum.value;
		currentNum.value = '';
	}
	operator.value = op;
}

const calculate = () => {
	let result = 0;
	if(operator.value === '+'){
		result = parseFloat(previousNum.value) + parseFloat(currentNum.value)
	}else if(operator.value === '-'){
		result = parseFloat(previousNum.value) - parseFloat(currentNum.value)
	}else if(operator.value === '*'){
		result = parseFloat(previousNum.value) * parseFloat(currentNum.value)
	}else {
		result = parseFloat(previousNum.value) / parseFloat(currentNum.value)
	}
	display.value = result;
	currentNum.value = result.toString(); // Store the result as the current number for further calculations
  	previousNum.value = ''; // Reset previous number
 	operator.value = ''; // Reset operator
}

const clear = () => {
	currentNum.value = '';
 	previousNum.value = '';
  	operator.value = '';
  	display.value = 0; // Reset the display
}

</script>

<template>
	<section class="calculatorContainer">
		<div class="calculator">
			<div class="display" id="display">{{ display }}</div>
			<div class="buttons">
				<button @click="clear" class="btn operator" data-operator="C">C</button>
				<button @click="setOperator('/')" class="btn operator" data-operator="/">/</button>
				<button @click="setOperator('*')" class="btn operator" data-operator="*">*</button>
				<button @click="setOperator('-')" class="btn operator" data-operator="-">-</button>
				<button @click="getNum" class="btn" data-number="7">7</button>
				<button @click="getNum" class="btn" data-number="8">8</button>
				<button @click="getNum" class="btn" data-number="9">9</button>
				<button @click="setOperator('+')" class="btn operator" data-operator="+">+</button>
				<button @click="getNum" class="btn" data-number="4">4</button>
				<button @click="getNum" class="btn" data-number="5">5</button>
				<button @click="getNum" class="btn" data-number="6">6</button>
				<button @click="calculate" class="btn operator" data-operator="=">=</button>
				<button @click="getNum" class="btn" data-number="1">1</button>
				<button @click="getNum" class="btn" data-number="2">2</button>
				<button @click="getNum" class="btn" data-number="3">3</button>
				<button @click="getNum" class="btn" data-number="0">0</button>
			</div>
    	</div>
	</section>
</template>