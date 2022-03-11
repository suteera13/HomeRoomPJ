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
              <v-img src="../storage/profiles/246.jpg" />
            </v-avatar>
          </v-btn>
        </template>

        <v-card class="padd text-center" width="200px" height="280px">
          <br>
          <v-avatar>
            <v-img src="../storage/profiles/246.jpg" />
          </v-avatar>
          <p class="text4">
            <strong>name</strong>
          </p>
          <p class="text2">
            admin@gmail.com
          </p>
          <br>
          <v-card class="menu text-left" href="/profile" color="transparent" elevation="0">
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
        อนุมัติการบันทึกข้อมูลกิจกรรมโฮมรูม
      </v-alert>
    </v-sheet>
    <!-- table -->
    <v-sheet class="overflow-y-auto pb-16" max-height="460">
      <v-simple-table>
        <template #default>
          <thead>
            <tr>
              <th class="text-left">
                สัปดาห์
              </th>
              <th class="text-left">
                กลุ่ม
              </th>
              <th class="text-left">
                สถานะ
              </th>
              <th class="text-left">
                รับรอง
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="st in students" :key="st.id">
              <td>{{ st.week }}</td>
              <td>{{ st.group }}</td>
              <td><v-btn depressed rounded>{{ st.group_id }}</v-btn></td>
              <td><v-btn depressed rounded>{{ st.major_id }}</v-btn></td>
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
    id: '',
    students: [
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' },
      { week: '1', group: 'e1', group_id: 'รอบันทึก', major_id: 'ยังไม่อ่าน' }
    ]
  }),
  created () {
    this.ShowStd()
  },
  methods: {
    async ShowStd () {
      console.log('show student')
      this.id = this.$route.query.id
      const res = await fetch('http://localhost:7000/list_tch?id=' + this.id)
      const data = await res.json()
      // this.group_id = data.datas[0].group_id
      console.log('data2=', data.datas)
    },
    NextPf () {
      console.log('next profile')
      this.$router.push('/profile?id=' + this.id)
    }
  }
}
</script>
