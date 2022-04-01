<template>
    <v-container>
        <v-row>
            <v-col
            cols="12"
            >
                <h3 class="text-center">Data</h3>
                <p class="text-center">Lorem Ipsum is simply dummy text of the printing and typesetting industry</p>
            </v-col>
        </v-row>
        <v-row>
            <v-col
                cols="12"
                md="6"
            >
                <Table :itens="tableItens" :headers="tableHeaders"/>
                
            </v-col>
            <v-col
                cols="12"
                md="6"
            >
                <PieChart :points="formatData(tableItens)" :name="'Participation'" />
            </v-col>
        </v-row>
    </v-container>
</template>

<script>

import Table from '../Table.vue'
import PieChart from '../PieChart.vue'

export default {
    components:{
        Table,
        PieChart
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
                {id:1, firstName:'Diego', lastName:'Souza', participation:12.5},
                {id:2, firstName:'Geromel', lastName:'Zagueiro', participation:25.0},
                {id:3, firstName:'Ferreira', lastName:'Ponta', participation:20.0},
                {id:4, firstName:'Campaz', lastName:'Colombia', participation:30.0},
                {id:5, firstName:'Thiago Santos', lastName:'Ruim', participation:12.5},
            ],
        }
    },
    methods:{
        formatData(tableItens){
            return tableItens.map((item) => ({
                name: item.firstName + ' ' +item.lastName,
                y:item.participation
            }))
        }
    }
    
}
</script>
