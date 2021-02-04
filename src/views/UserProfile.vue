<template>
        <div>
        <v-row class="text-left">
            <v-col cols="10">
                <h1 class="green--text text--darken-2">
                    <v-icon large color="green darken-2">mdi-account-outline</v-icon>
                    Иван Иванов
                </h1>
            </v-col>
        </v-row>
        <v-row class="text-left">
            <v-col cols="2">
                <img src="https://randomuser.me/api/portraits/men/7.jpg" style="max-width: 100%">
            </v-col>
            <v-col cols="10" class="text-left">
                <p>
                    Веб-сайт: <a :href="'http://' + userData.website" target="_blank">{{userData.website}}</a>
                </p>
                <p>
                    E-mail: <a :href="'mailto:' + userData.email">{{userData.email}}</a>
                </p>
                <p>
                    Город: ...
                </p>
                <p>
                    Место работы: ...
                </p>
            </v-col>
        </v-row>

        {{userData}}
    </div>
</template>

<script>
export default {
    name: 'UserProfile',
    data(){
        return  {
            userData: ''
        }
    },
    methods: {
        getUserData(){
            this.axios.get(`http://jsonplaceholder.typicode.com/users/${this.$route.params.id}`)
                .then( (response)=>{
                    this.userData = response.data;
                } )
        }
    },
    mounted(){
        this.getUserData();
    },
    watch: {
        $route(){
            this.getUserData();
        }
    }
}
</script>