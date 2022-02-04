<template>
  <div class="overflow-hidden">
    <v-app-bar
      absolute
      light
      color="white"
      elevation="0"
    >
      <v-app-bar-title>Name Surname</v-app-bar-title>

      <v-spacer />
      <v-btn icon href="/login">
        <v-icon>mdi-logout</v-icon>
      </v-btn>
    </v-app-bar>
    <v-sheet>
      <br><br>
      <v-alert class="ma-2 text3" color="indigo" dark>
        <v-row>
          <v-col>
            บันทึกกิจกรรมโฮมรูม
          </v-col>
        </v-row>
      </v-alert>
    </v-sheet>

    <!-- tabs -->
    <template>
      <v-tabs v-model="tabs" fixed-tabs class="tab1">
        <v-tab v-for="n in 4" :key="n">
          {{ n }} Item
        </v-tab>
      </v-tabs>
    </template>
    <v-tabs-items v-model="tabs">
      <v-tab-item>
        <!-- sheet -->
        <v-sheet class="overflow-y-auto pb-16" max-height="420">
          <v-simple-table>
            <template #default>
              <thead>
                <tr>
                  <th class="text-left">
                    เลขที่
                  </th>
                  <th class="text-left">
                    ชื่อ-สกุล
                  </th>
                  <th class="text-left">
                    สถานะ
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in desserts" :key="item.name">
                  <td>{{ item.id }}</td>
                  <td>{{ item.name }}</td>
                  <td class="ww">
                    <v-select :items="items" label="เลือก" />
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-sheet>
        <!-- sheet -->
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-title class="text-h5">
            An awesome title
          </v-card-title>
          <v-card-text>
            <p>
              Duis lobortis massa imperdiet quam
            </p>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-title class="text-h5">
            An even better title
          </v-card-title>
          <v-card-text>
            <p>
              Maecenas ullamcorper
            </p>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-title class="text-h5">
            An even better title
          </v-card-title>
          <v-card-text>
            <p>
              Eaecenas ullamcorper
            </p>
          </v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>

    <!-- menu -->
    <v-bottom-navigation
      color="indigo"
      absolute
    >
      <v-btn href="/home">
        <span>หน้าแรก</span>
        <v-icon>mdi-home</v-icon>
      </v-btn>

      <v-btn>
        <span>บันทึก</span>
        <v-icon>mdi-content-save</v-icon>
      </v-btn>

      <v-btn>
        <span>รับรอง</span>
        <v-icon>mdi-text-box-check</v-icon>
      </v-btn>

      <v-btn>
        <span>รายงาน</span>
        <v-icon>mdi-text-box</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tabs: null,
      text: '...',
      desserts: [
        { id: '01', name: 'Name Surname' },
        { id: '02', name: 'Name Surname' },
        { id: '03', name: 'Name Surname' },
        { id: '04', name: 'Name Surname' },
        { id: '05', name: 'Name Surname' },
        { id: '06', name: 'Name Surname' },
        { id: '07', name: 'Name Surname' },
        { id: '08', name: 'Name Surname' },
        { id: '09', name: 'Name Surname' }
      ],
      items: ['มา', 'สาย', 'ขาด', 'ลา']
    }
  }
}
</script>

<style>
.tab1{
  width: max-content;
}
.ww{
  width: 100px;
}
</style>
