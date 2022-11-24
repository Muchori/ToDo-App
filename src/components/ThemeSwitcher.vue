<script>
export default {
	props: {
		theme: {
			type: String,
			required: true,
		},
	},
	methods: {
		toggleTheme() {
			const newTheme = this.theme === 'light' ? 'dark' : 'light';
			localStorage.setItem('theme', newTheme);
			this.$emit('themeChanged', newTheme);
			this.$router.go();
		},
	},
};
</script>

<template>
	<a href="#" @click.prevent="toggleTheme" aria-label="Theme Switcher">
		<i
			v-if="theme === 'light'"
			src="../assets/images/ICON-MOON.SVG"
			data-feather="moon"
			class="text-liText-ternary-dark dark:text-liText-ternary-light dark:hover:text-liBorder-primary-light w-5"
		></i>
		<i
			v-else
			src="../assets/images/ICON-SUN.SVG"
			data-feather="sun"
			class="text-gray-200 hover:text-gray-50 w-5"
		></i>
	</a>
</template>
