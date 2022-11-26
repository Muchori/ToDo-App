<script>
import ThemeSwitcher from '../ThemeSwitcher';

export default {
	components: {
		ThemeSwitcher,
	},
	created() {
		this.theme = localStorage.getItem('theme') || 'light';
	},
	
	methods: {
		updateTheme(theme) {
			this.theme = theme;
		},
	},	
};
</script>

<template>
	<div class="flex relative w-full">

		<div class="absolute justify-center items-center flex flex-row w-full py-4">
			<div class="relative pr-48 z-30 text-white">
				<h2 class="text-center text-2xl tracking-widest font-bold mt-10">T O D O</h2>				
			</div>

			<div class="relative z-30 mt-10 pl-24">
        <theme-switcher
					:theme="theme"
					@themeChanged="updateTheme"
					class="bg-primary-light dark:bg-ternary-dark flex shadow-sm rounded-xl cursor-pointer"
				/>
      </div>
		</div>	

			
			
		<div class="absolute h-auto w-full bg-cover bg-center">
			<img
				v-if="theme === 'light'"
				src="@/assets/images/bg-desktop-light.jpg"
				class="w-full"
				alt="Light Logo"
			/>
			<img
				v-else
				src="@/assets/images/bg-desktop-dark.jpg"
				class="w-full"
				alt="Dark Logo"
			/>
		</div>
	</div>  
</template>

