<template>
    <div class="d-flex justify-center align-center" style="height: 100vh;">
        <v-card max-width="500" class="pa-8"  >
            <h1>Login  Page</h1>
            <v-form>
                <v-text-field 
                outlined
                label="Email"
                type="Email"
                prepend-icon="mdi-email"
                ></v-text-field>

                <v-text-field 
                label="Password"
                outlined
                type="password"
                prepend-icon="mdi-lock"
                ></v-text-field>

                <v-btn 
                color="primary"
                type="submit"
                class="mt-4"
                block>Login
                </v-btn>
            </v-form>
        </v-card>
    </div>
</template>
<script>
export default {
    layout: "auth"
}
</script>