<script>
import feather from 'feather-icons';
import AppHeader from './components/shared/AppHeader';

export default {
	components: {
		AppHeader,
	},
	data: () => {
		return {
			appTheme: localStorage.getItem('theme'),
		};
	},
	mounted() {
		feather.replace();
	},
	updated() {
		feather.replace();
	},
};
</script>

<template>
	<div :class="appTheme" class="">
		<!-- App header -->
		<AppHeader />

		<!-- Render active component contents with vue transition -->
		<transition name="fade" mode="out-in">
			<router-view :theme="appTheme" />
		</transition>

	</div>
</template>

<!-- <style>
#app {
	font-family: Rubik, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
}



.fade-enter-active {
	animation: coming 0.4s;
	animation-delay: 0.2s;
	opacity: 0;
}

.fade-leave-active {
	animation: going 0.4s;
}

@keyframes going {
	from {
		transform: translateX(0);
	}

	to {
		transform: translateX(-10px);
		opacity: 0;
	}
}

@keyframes coming {
	from {
		transform: translateX(-10px);
		opacity: 0;
	}

	to {
		transform: translateX(0px);
		opacity: 1;
	}
}
</style> -->
