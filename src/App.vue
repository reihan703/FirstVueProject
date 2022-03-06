<template>
	<h1>{{ title }}</h1>
	<br />
	<input type="text" ref="name" />
	<button @click="handleClick">click here</button><br><br>

	<teleport to=".modals" v-if="showModal">
		<Modal theme="" @close="toggleModal">
			<template v-slot:links>
				<a href="#">btn 1</a>
				<a href="#">btn 2</a>
			</template>
			<h1>Slot</h1>
			<p>slots</p>
		</Modal>
	</teleport>

	<teleport to=".modals" v-if="showModal2">
		<Modal theme="sale" @close="toggleModal2">
			<h1>Modal 2</h1>
			<p>slots 2</p>
		</Modal>
	</teleport>

	<button @click="toggleModal">Modal</button>
	<button @click="toggleModal2">Modal2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
	name: "App",
	data() {
		return {
			title: "MyApp",
			showModal: false,
			showModal2: false,
		};
	},
	methods: {
		handleClick() {
			console.log(this.$refs.name);
			this.$refs.name.classList.add("active");
		},
		toggleModal() {
			this.showModal = !this.showModal;
		},
		toggleModal2() {
			this.showModal2 = !this.showModal2;
		},
	},
	components: {
		Modal,
	},
};
</script>

<style>
#app, .modals {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}

h1 {
	border-bottom: 1px solid gray;
	display: inline-block;
	padding-bottom: 10px;
}
button{
  background-color: #F9A300;
  border: none;
  padding: 5px 15px;
  color: #ffffff;
  font-weight: 300;
  margin-top: 10px;
  margin-right: 10px;
}
button:active {
outline: none;
border: none;
}

button:focus {outline:0;}
</style>
