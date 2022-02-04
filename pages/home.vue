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
    <v-sheet class="overflow-y-auto pb-16" max-height="600">
      <br><br>
      <v-alert class="ma-2 text3" color="indigo" dark>
        <v-row>
          <v-col cols="10">
            สรุปผลเข้าร่วมกิจกรรมโฮมรูม
          </v-col>
          <v-spacer />
          <v-col cols="2">
            <v-icon>mdi-circle-edit-outline</v-icon>
          </v-col>
        </v-row>
      </v-alert>
      <v-simple-table>
        <template #default>
          <thead>
            <tr>
              <th class="text-left">
                ชื่อ-สกุล
              </th>
              <th class="text-left">
                เปอร์เซ็นต์
              </th>
              <th class="text-left">
                สรุป
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in desserts" :key="item.name">
              <td>{{ item.name }}</td>
              <td>{{ item.percent }}</td>
              <td>{{ item.summarize }}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-sheet>
    <v-bottom-navigation
      color="indigo"
      absolute
    >
      <v-btn href="/home">
        <span>หน้าแรก</span>
        <v-icon>mdi-home</v-icon>
      </v-btn>

      <v-btn href="/note">
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
      desserts: [
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' },
        { name: 'Name Surname', percent: 100, summarize: 'ผ่าน' }
      ]
    }
  }
}
</script>
