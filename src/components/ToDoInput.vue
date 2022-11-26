<template>
	<div class="absolute flex flex-row w-full justify-center items-center mt-28 ml-80">
		<div class="relative w-full justify-center items-center">
			<form action="#" class="font-normal">				
				<input
					class="w-full p-3 rounded-md shadow-lg text-sm"
					id="name"
					name="name"
					type="text"
					required=""
					placeholder="Create a new todo..."
					aria-label="Name"
				/>							
			</form>
	</div>
	</div>
</template>

<script>
	export default {
		name: "ToDoInput",
		data() {
			return {
				text: ""
			}
		},
		methods: {
			/**
			 * Event: add new task
			 */
			onAddNewTask(e) {
				e.preventDefault()
				const taskName = this.text

				this.$emit("eventAddNewTask", taskName)

				// reset the textbox
				this.text = ""
			}
		}
	}
</script>

