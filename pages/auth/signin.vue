<template>
    <div class="d-flex justify-center align-center" style="height: 100vh;">
        <v-card max-width="500" class="pa-7"  >
            <h1>Login  Page</h1>
            <v-form>
                <v-text-field 
                label="Email"
                type="Email"
                ></v-text-field>

                <v-text-field 
                label="Password"
                type="Passowrd"
                ></v-text-field>

                <v-btn 
                color="primary"
                type="submit"
                class="mt-4"
                block>Login
                ></v-btn>
            </v-form>
        </v-card>
    </div>
</template>
<script>
export default {
    layout: "auth"
}
</script>