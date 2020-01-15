<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{ switchName() }}</p>
        <p>User Age: {{ userAge }}</p>
        <button @click="resetNameChild">Reset name</button>
        <button @click="resetName">Reset name callback</button>
    </div>
</template>

<script>
    import { eventBus } from '../main';

    export default {
        props: {
            name: {
                type: String,
                required: true,
                default: 'Leo'
            },
            resetName: Function,
            userAge: Number,
        },
        methods: {
            switchName() {
                return this.name.split('').reverse().join('')
            },
            resetNameChild() {
                this.name = 'Leo';
                this.$emit('nameResetted', this.name);
            }
        },
        created() {
            eventBus.$on('ageEditted', (newAge) => {
                this.userAge = newAge
            })
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
