<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User name: {{ switchName() }}</p>
        <p>User age: {{ userAge }}</p>
        <button @click="resetName">Reset name</button>
        <button @click="resetFn()">Reset name</button>
    </div>
</template>

<script>
    export default {
    	props: ['name', 'resetFn', 'userAge'],
        methods: {
    		switchName() {
    			return this.name.split('').reverse().join('')
            },
            resetName() {
    			this.name = 'Max';
    			this.$emit('nameWasReset',this.name)
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
