<template>
    <v-container>
        <v-row>
            <v-col
                cols="12"
                md="6"
            >
                <Table :itens="tableItens" :headers="tableHeaders"/>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>

import Table from '../Table.vue'

export default {
    components:{
        Table
    },
    data(){
        return {
            tableHeaders:[
                {key:'id', name:'', class:''},
                {key:'firstName', name:'First Name', class:'text-left'},
                {key:'lastName', name:'Last Name', class:'text-left'},
                {key:'participation', name:'Participation', class:'text-center'},
            ],
            tableItens:[
                {id:1, firstName:'Diego', lastName:'Souza', participation:0.5},
                {id:2, firstName:'Geromel', lastName:'Zagueiro', participation:25.0},
                {id:3, firstName:'Ferreira', lastName:'Ponta', participation:25.0},
                {id:4, firstName:'Campaz', lastName:'Colombia', participation:25.0},
                {id:5, firstName:'Thiago Santos', lastName:'Ruim', participation:24.5},
            ]
        }
    }
    
}
</script>
