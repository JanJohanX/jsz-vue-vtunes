<template>
	<ul class="jsz-tunes-list">
		<li>
			<tunes-song v-for="song in newSongs" :key="song.id" :song="song" />
		</li>
	</ul>
</template>

<script>
	import TunesSong from '@/components/tunes/TunesSong.vue';

	export default {
		components: {
			TunesSong
		},
		props: [
			'new-songs'
		]
	}
</script>