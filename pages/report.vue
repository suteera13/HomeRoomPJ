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
        รายงาน การปฏิบัติงานของครูที่ปรึกษา(คป 06)
      </v-alert>
    </v-sheet>
    <!-- table -->
    <v-sheet class="overflow-y-auto pb-16 text-center" max-height="460">
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
                ครูที่ปรึกษา
              </th>
              <th class="text-left">
                หัวหน้าแผนก
              </th>
              <th class="text-left">
                หัวหน้างานครูที่ปรึกษา
              </th>
              <th class="text-left">
                รองผู้อำนวยการ
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="week in weeks" :key="week.name">
              <td>{{ week.week }}</td>
              <td>{{ week.group }}</td>
              <td><v-icon>{{ week.techer }}</v-icon></td>
              <td><v-icon>{{ week.boss }}</v-icon></td>
              <td><v-icon>{{ week.bosstch }}</v-icon></td>
              <td><v-icon>{{ week.po }}</v-icon></td>
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
    weeks: [
      { week: '1', group: 'e1', techer: 'mdi-close', boss: 'mdi-close', bosstch: 'mdi-close', po: 'mdi-close' },
      { week: '2', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '3', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '4', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '5', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '6', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '7', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '8', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' },
      { week: '9', group: 'e1', techer: 'mdi-check', boss: 'mdi-check', bosstch: 'mdi-check', po: 'mdi-check' }
    ]
  }),
  methods: {
    NextPf () {
      console.log('next profile')
      this.id = this.$route.query.id
      this.$router.push('/profile?id=' + this.id)
    }
  }
}
</script>
