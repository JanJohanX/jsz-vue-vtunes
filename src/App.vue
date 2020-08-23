<template>
	<div id="app">
		<header>
			<the-navigation />
		</header>
		<main>
			<router-view />
		</main>
	</div>
</template>

<script>
import TheNavigation from '@/components/TheNavigation.vue';

export default {
	components: {
		TheNavigation,
	}
}
</script>

<style lang="scss">

</style>
