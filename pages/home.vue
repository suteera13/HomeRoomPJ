<template>
  <div class="overflow-hidden">
    <v-app-bar
      absolute
      light
      color="white"
      elevation="0"
    >
      <v-app-bar-title>HOMEROOM</v-app-bar-title>

      <v-spacer />
      <v-menu
        left
        bottom
      >
        <template #activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-avatar size="26px">
              <v-img src="../img/ava2.jpg" />
            </v-avatar>
          </v-btn>
        </template>

        <v-card class="padd text-center" width="200px" height="280px">
          <br>
          <v-avatar>
            <v-img src="../img/ava2.jpg" />
          </v-avatar>
          <p class="text4">
            <strong>{{ ufirstname }}</strong>
          </p>
          <p class="text2">
            {{ email }}
          </p>
          <br>
          <v-card class="menu text-left" color="transparent" elevation="0" @click="NextPf">
            <p>
              <v-icon>mdi-pencil</v-icon>
              แก้ไขโปรไฟล์
            </p>
          </v-card>
          <v-divider class="up2" />
          <v-card class="menu text-left" href="/" color="transparent" elevation="0">
            <p class="drop2">
              <v-icon>mdi-logout</v-icon>
              ออกจากระบบ
            </p>
          </v-card>
        </v-card>
      </v-menu>
    </v-app-bar>
    <v-sheet>
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
    </v-sheet>
    <!-- table -->
    <v-sheet class="overflow-y-auto pb-16" max-height="460">
      <v-simple-table>
        <template #default>
          <thead>
            <tr>
              <th class="text-left">
                ชื่อ
              </th>
              <th class="text-left">
                สกุล
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
            <tr v-for="std in students" :key="std.id">
              <td>{{ std.firstname }}</td>
              <td>{{ std.lastname }}</td>
              <td>{{ std.group_id }}</td>
              <td>{{ std.major_id }}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-sheet>
  </div>
</template>

<script>
export default {
  data: () => ({
    techer: '',
    firstname: '',
    lastname: '',
    group_id: '',
    major_id: '',
    students: [
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' },
      { firstname: 'Name', lastname: 'Surname', group_id: 100, major_id: 'ผ่าน' }
    ],
    id: '',
    email: '',
    ufirstname: '',
    ulastname: ''
  }),
  created () {
    this.ShowStd()
    this.ShowPf()
  },
  methods: {
    async ShowStd () {
      console.log('show student')
      this.id = this.$route.query.id
      const res = await fetch('http://localhost:7000/list_std?id=' + this.id)
      const data = await res.json()
      this.students = data.datas
      console.log('data2=', data.datas)
    },
    async ShowPf () {
      console.log('show techer')
      this.id = this.$route.query.id
      const res = await fetch('http://localhost:7000/list_tch?id=' + this.id)
      const data = await res.json()
      console.log('techer=', data.datas[0])
      this.ulastname = data.datas[0].lastname
      this.ufirstname = data.datas[0].firstname
      this.email = data.datas[0].email
    },
    NextPf () {
      console.log('next profile')
      this.$router.push('/profile?id=' + this.id)
    }
  }
}
</script>2+
