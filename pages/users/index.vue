<template>
    <div>
        <h1 class="text-center">List Users</h1>

        <b-form-group
            label="User Id"
            label-for="userId"
        >
            <b-form-input
            id="userId"
            type="number"
            v-model="form.id"
            placeholder="User Id"
            min="0"
            required
            ></b-form-input>
        </b-form-group>

        <b-button
            @click="loadUser"
            variant="primary"
            block
        >Find</b-button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            form: {
                id: ''
            }
        }
    },

    methods: {
        loadUser() {
            this.$router.push(`/users/${this.form.id}`)
        }
    }
}
</script>
