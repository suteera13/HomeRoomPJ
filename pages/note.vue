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
        บันทึกกิจกรรมโฮมรูม
      </v-alert>
    </v-sheet>

    <!-- tabs -->
    <template>
      <v-tabs v-model="tabs" fixed-tabs class="tab1">
        <v-tab v-for="n in 4" :key="n">
          Step {{ n }}
        </v-tab>
      </v-tabs>
    </template>
    <v-tabs-items v-model="tabs">
      <!-- item tap 1 -->
      <v-tab-item>
        <!-- sheet -->
        <form>
          <v-sheet class="overflow-y-auto pb-16 padd" max-height="450">
            <v-simple-table>
              <template #top>
                <p class="sp">
                  <strong>เช็คชื่อโฮมรูม</strong>
                </p>
                <v-divider />
              </template>
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
                      สถานะ
                    </th>
                  </tr>
                </thead>
                <!-- เช็คชื่อ -->
                <tbody>
                  <tr v-for="item in desserts" :key="item.id">
                    <td>{{ item.firstname }}</td>
                    <td>{{ item.lastname }}</td>
                    <td class="ww">
                      <v-select :items="tus" label="มา" />
                    </td>
                  </tr>
                </tbody>
              <!-- เช็คชื่อ -->
              </template>
            </v-simple-table>
            <div class="text-right">
              <v-btn class="top drop" color="indigo" dark @click="SaveCheck">
                Save
              </v-btn>
            </div>
          </v-sheet>
        </form>
        <!-- sheet -->
      </v-tab-item>
      <!-- item tap -->
      <v-tab-item>
        <v-sheet class="overflow-y-auto pb-16 padd" max-height="450">
          <p class="sp">
            <strong>บันทึกรายงานการปฏิบัติงานของครูที่ปรึกษา</strong>
          </p>
          <v-textarea
            label="เรื่องที่ให้คำแนะนำ นักเรียน นักศึกษา"
            auto-grow
            outlined
            rows="3"
            row-height="40"
            shaped
          />
          <p class="sp">
            <strong>สถิติการตอบแบบสอบถามการประเมินตนเอง</strong>
          </p>
          <v-row class="padd">
            <v-col cols="7">
              จำนวนผู้ตอบแบบสอบถาม
            </v-col>
            <v-col cols="3">
              <v-text-field label="จำนวน" class="topup" />
            </v-col>
            <v-col cols="2">
              คน
            </v-col>
          </v-row>
          <p class="text-center">
            จำนวนนักเรียนทั้งหมด {{ num }} คน
          </p>
          <p class="sp">
            <strong>รูปภาพขณะให้คำแนะนำ</strong>
          </p>
          <v-file-input label="Image1" filled prepend-icon="mdi-camera" />
          <v-file-input label="Image2" filled prepend-icon="mdi-camera" />
          <div class="text-left">
            <v-btn class="top drop" light>
              cancel
            </v-btn>
            <v-btn class="top drop" color="indigo" dark>
              Save
            </v-btn>
          </div>
        </v-sheet>
      </v-tab-item>
      <v-tab-item>
        <!-- sheet -->
        <v-sheet class="overflow-y-auto pb-16 padd" max-height="440">
          <v-simple-table>
            <template #top>
              <p class="sp">
                <strong>ประเมินความเสี่ยง</strong>
              </p>
              <v-divider />
            </template>
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
                    สถานะ
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in desserts" :key="item.id">
                  <td>{{ item.firstname }}</td>
                  <td>{{ item.lastname }}</td>
                  <td class="ww">
                    <v-select :items="check" label="ไม่เสี่ยง" />
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
          <div class="text-left">
            <v-btn class="top drop" light>
              cancel
            </v-btn>
            <v-btn class="top drop" color="indigo" dark>
              Save
            </v-btn>
          </div>
        </v-sheet>
        <!-- sheet -->
      </v-tab-item>
      <v-tab-item>
        <!-- sheet -->
        <v-sheet class="overflow-y-auto pb-16 padd" max-height="450">
          <v-simple-table>
            <template #top>
              <p class="sp">
                <strong>ยืนยันการบันทึกข้อมูล</strong>
              </p>
              <v-divider />
            </template>
            <template #default>
              <thead>
                <tr>
                  <th class="text-left">
                    สกุล
                  </th>
                  <th class="text-left">
                    สกุล
                  </th>
                  <th class="text-left">
                    เช็คชื่อ
                  </th>
                  <th class="text-left">
                    ความเสี่ยง
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in desserts" :key="item.id">
                  <td>{{ item.firstname }}</td>
                  <td>{{ item.lastname }}</td>
                  <td>{{ item.chn }}</td>
                  <td>{{ item.chs }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
          <div class="text-left">
            <v-btn class="top drop" light>
              cancel
            </v-btn>
            <v-btn class="top drop" color="indigo" dark>
              Save
            </v-btn>
          </div>
        </v-sheet>
        <!-- sheet -->
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>

<script>
export default {
  data: () => ({
    room: '',
    t_id: '',
    std_id: '',
    tabs: null,
    tus: ['มา', 'ขาด', 'ลา', 'สาย'],
    check: ['เสี่ยง', 'ไม่เสี่ยง'],
    num: '0',
    desserts: [
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' },
      { room: 'a', firstname: 'firstname', lastname: 'lastname' }
    ]
  }),
  created () {
    this.ShowStd()
  },
  methods: {
    async ShowStd () {
      console.log('show student')
      this.id = this.$route.query.id
      this.std_id = this.$route.query.std_id
      const res = await fetch('http://localhost:7000/group_name?id=' + this.id)
      const data = await res.json()
      this.desserts = data.datas
      console.log('data=', data.datas)
    },
    clr () {
      this.std_id = ''
      this.t_id = ''
      this.cstatus = ''
    },
    async SaveCheck () {
      const detail = {
        std_id: this.id,
        t_id: this.id,
        cstatus: this.cstatus
      }
      console.log('detail:', detail)
      const res = await fetch('http://localhost:7000/save_check?id=' + this.detail)
      const data = await res.json()
      console.log('data2=', data.datas)
    },
    NextPf () {
      console.log('next profile')
      this.$router.push('/profile?id=' + this.id)
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
.topup{
  margin-top: -16px;
}
.sp{
  margin-left: 10px;
}
</style>
