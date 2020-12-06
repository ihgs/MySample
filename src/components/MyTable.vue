<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-simple-table>
          <template v-slot:default>
            <thead>
              <tr>
                <th>
                </th>
                <th class="">
                  code
                </th>
                <th>
                  name
                </th>
                <th>
                  date
                </th>
                <th>
                  port
                </th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item,index) in items" :key="index">
                <td>
                  <v-icon v-on:click="plus(index)">mdi-plus</v-icon>
                  <v-icon v-on:click="minus(index)">mdi-minus</v-icon>
                </td>
                <td>
                  <v-text-field v-model="item.code"></v-text-field>
                </td>
                <td>
                  <v-select v-model="item.name" :items="products"
                    item-text="label" item-value="value">
                  </v-select>
                </td>
                <td>
                  <v-text-field v-model="item.order_date" type="date"></v-text-field>
                </td>
                <td>
                  <v-text-field v-model="item.port" autocomplete="on" list="ports"></v-text-field>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
        <datalist id="ports">
          <option v-for="n in ports" :key="n">{{n}}</option>
        </datalist>

      </v-col>
    </v-row>
    <v-row>
      <v-col>{{items}}
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',

  data: () => ({
    code: '',
    ports: [
      'Kobe',
      'Yokohama',
    ],
    products: [
      {
        label: 'A', value: 'a',
      },
      {
        label: 'B', value: 'b',
      },
      {
        label: 'C', value: 'c',
      },
    ],
    items: [
      {
      },
    ],
  }),
  methods: {
    plus(index) {
      this.items.splice(index + 1, 0, {});
    },
    minus(index) {
      this.items.splice(index, 1);
      if (this.items.length === 0) {
        this.items.push({});
      }
    },
  },
};
</script>
