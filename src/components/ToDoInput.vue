<template>
	<div class="absolute item-center mt-5 w-full md:w-1/2">
		<form action="#" class="font-normal">
				
					<input
						class="w-full h-16 item-center border dark:border-primary-dark border-opacity-50 text-primary-dark dark:text-secondary-light bg-ternary-light dark:bg-ternary-dark rounded-md shadow-sm text-md"
						id="name"
						name="name"
						type="text"
						required=""
						placeholder="Create a new todo..."
						aria-label="Name"
					/>
							
			</form>
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

