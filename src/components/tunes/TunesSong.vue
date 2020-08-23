<template>

	<article v-cloak class="jsz-tunes-song">
		<div class="jsz-row">
			<div class="jsz-tunes-song-cover">
				<img :src="song.artworkUrl100" alt="">
			</div>

			<div class="jsz-tunes-song-name">
				<p class="jsz-flex-end"><strong>{{song | songify | short}}</strong></p>
			</div>
		</div>

		<figure v-if="song.previewUrl">
			<audio
				controls
				:src="song.previewUrl">
					Your browser does not support the
					<code>audio</code> element.
			</audio>
		</figure>
	</article>
	
</template>

<script>
	import { truncate } from 'lodash-es';

	export default {
		name: 'TunesListSong',
		props: {
			song: {
				type: Object,
			},
		},
		filters: {
			songify(song) {
				return song.artistName + ' - ' + song.trackName;
			},
			short(str) {
				return truncate(str, {length: 45});
			}
		},
	}
</script>