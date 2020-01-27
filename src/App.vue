<template>
  <div id="app">
			<div class="container">
				<h2 class="counter-text">{{ count }}</h2>
				<!--If we want to directly listen to events emitted from Vue components, we have to use the "native" modifier. -->
				<counter-button @click.native="incrementCount" title="Increment count"/>
				<counter-button @click.native="decrementCount" title="Decrement count"/>
				<counter-button @click.native="resetCount" title="Reset count"/>
			</div>
  </div>
</template>

<script>
import CounterButton from './components/CounterButton.vue'

export default {
  name: 'app',
  components: {
		CounterButton
	},
	data() {
		return {
			count: 0
		}
	},
	methods: {
		incrementCount() {
			this.count = this.count + 1;
		},
		decrementCount() {
			this.count = this.count - 1;
		},
		resetCount() {
			this.count = 0;
		},
	}
}
</script>

<style>
/*
This is where we'll put our general styling rules.
They'll serve as a base for all our components.
For example: the line-height we set here, will 'filter' through to the Button component.
*/

body, html {
	margin: 0;
	padding: 0;
	color: #212529;
	font-family: 'Courier New', Courier, monospace;
	line-height: 1.5;
	background-color: #faeee7;
}

* {
	box-sizing: border-box;
}

#app {
	text-align: center;
	display: flex;
	align-items: center;
	justify-content: center;
	height: 100vh;
}

.counter-text {
	font-weight: normal;
	font-size: 3rem;
	margin-top: 0;
	margin-bottom: 1.5rem;
}

.container {
	width: 100%;
	max-width: 800px;
	padding: 1rem 15px;
	margin: 0 auto;
	background-color: #f8f9fa;
	border: 1px solid rgba(184, 141, 152, 0.38);
	border-radius: 0.25rem;
}
</style>
