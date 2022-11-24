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
	<div class="relative flow-root h-32 bg-cover bg-center">
		<div class="absolute float-left  z-30 flex w-full h-full">
			<div class="relative z-30 w-full px-6 py-8 text-white md:py-10 md:w-1/2">
				<h2 class="text-center text-5xl tracking-widest font-bold mt-9">T O D O</h2>				
			</div>
		</div>		
		<div class="absolute z-30 top-0 right-0 flex w-full h-full">
      <div class="w-2/3 h-full"></div>
      <div class="relative w-1/3 mt-12">
        <theme-switcher
					:theme="theme"
					@themeChanged="updateTheme"
					class="ml-8 bg-primary-light text-center dark:bg-ternary-dark px-3 py-2 shadow-sm rounded-xl cursor-pointer"
				/>
      </div>
    </div>	
		<div class="absolute block w-full h-full">
			<img
				v-if="theme === 'light'"
				src="@/assets/images/bg-desktop-light.jpg"
				class="w-full"
				alt="Dark Logo"
			/>
			<img
				v-else
				src="@/assets/images/bg-desktop-dark.jpg"
				class="w-full"
				alt="Light Logo"
			/>
		</div>
	</div>  
</template>

