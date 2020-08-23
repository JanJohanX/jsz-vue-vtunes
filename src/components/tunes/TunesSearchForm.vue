<template>
	<form action="#" @submit.prevent="getMusic()" class="jsz-tunes-search-form">
		<input v-model="query" ref="searchInput" type="text" @keyup="search()" placeholder="Search for music" autofocus />
	</form>
</template>

<script>
	import axios from 'axios';
	import { debounce } from 'lodash-es';

	export default {
		data() {
			return {
				query: '',
			}
		},
		methods: {
			search: debounce(function() {
				this.getMusic(this.query)
			}, 500),
			getMusic() {
				axios.get(
					`
					https://itunes.apple.com/search
						?term=${encodeURI(this.query)}
						&entity=song
						&limit=15
					`
				)
					.then((res) => {
						let vTunesSongs = res.data.results;
						this.$emit('add-new-songs', vTunesSongs);
					})

			},
		},
		mounted() {
			this.$refs.searchInput.focus();
		},
	}
</script>