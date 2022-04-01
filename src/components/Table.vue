<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
            <th v-for="header in headers" :key="header.key" :class="header.class">
                {{header.name}}
            </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in itens"
          :key="item.id"
        >
          <td>{{ item.id }}</td>
          <td>{{ item.firstName }}</td>
          <td>{{ item.lastName }}</td>
          <td class="text-center">{{ formatPercent(item.participation) }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
  export default {
      props:{
          headers:{
              default:null,
              type:Array
          },
          itens:{
              default:null,
              type:Array
          }
      },
      methods:{
          formatPercent(value){
              return Number(value/100).toLocaleString('pt-BR',{style: 'percent', minimumFractionDigits:2});
          }
      }
  }
</script>