<template>
	<div class="km">
		<h1>Отправка маркировок</h1>
		<input class="input_km" type="text" v-model="km" @change=sendKm(km) />
	</div>
</template>

<script>
import axios from 'axios'

export default {
	name: 'HomeView',
	data() {
		return {
			km: ''
		}
	},
	methods: {
		async sendKm(km) {
			await axios.post('https://vorstack.ru:8087/km', {
				km: km
			})
			this.km = ''
		}
	}
}
</script>

<style>
.km {
	padding: 40px;
}
.input_km {
	width: 100%;
	margin: 20px 0 0 0;
	padding: 10px 20px;
	border: 2px solid rgb(247, 218, 0);
	border-radius: 7px;
	outline: none;
}
.input_km:focus {
	border: 2px solid rgb(247, 0, 0);
}
</style>