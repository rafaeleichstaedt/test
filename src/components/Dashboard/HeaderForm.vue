<template>
  <v-container grey lighten-3 fluid>
    <v-row align="center" justify="center">
      <v-form v-model="valid">
        <v-container>
          <v-row>
            <v-col
              cols="12"
              md="3"
            >
              <v-text-field
                v-model="firstname"
                :rules="nameRules"
                :counter="10"
                label="First name"
                required
              ></v-text-field>
            </v-col>

            <v-col
              cols="12"
              md="3"
            >
              <v-text-field
                v-model="lastname"
                :rules="nameRules"
                :counter="10"
                label="Last name"
                required
              ></v-text-field>
            </v-col>

            <v-col
              cols="12"
              md="3"
            >
              <v-text-field
                v-model="participation"
                :rules="participationRules"
                label="Participation"
                required
                type="number"
              ></v-text-field>
            </v-col>
            <v-col
              cols="12"
              md="3"
              class="mt-5"
            >
              <div class="text-center">
                <v-btn
                  rounded
                  color="grey"
                  dark
                >
                  Send
                </v-btn>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </v-row>
  </v-container>
</template>


<script>
  export default {
    name: 'Dashboard',
    data: () => ({
      valid: false,
      firstname: '',
      lastname: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 15 || 'Name must be less than 15 characters',
      ],
      participation: '',
      participationRules: [
        v => !!v || 'Participation is required',
        v => /.+@.+/.test(v) || 'Participation must be valid',
      ],
    }),
  }
</script>
