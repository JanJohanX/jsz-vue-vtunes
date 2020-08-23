<template>
	<div>
		<h2>vTunes</h2>

		<tunes-search-form @add-new-songs="songs = $event" />
		<tunes-list :new-songs="songs" />
		
	</div>
</template>

<script>
	import TunesSearchForm from '@/components/tunes/TunesSearchForm.vue';
	import TunesList from '@/components/tunes/TunesList.vue';
	
	export default {
		components: {
			TunesSearchForm,
			TunesList
		},
		data() {
			return {
				songs: []
			}
		},
		
	}
</script>

<style lang="scss" scoped>
	ul {
		padding-left: 0;
		margin-top: 2em;
	}
</style>