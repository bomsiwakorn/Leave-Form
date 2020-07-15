<template>
  <div class="home">
    <v-container>
        <v-card max-width="800" class="mx-auto my-5">
          <v-container class="px-8">
            <form action="" @submit.prevent="submit">
              <v-img
                alt="Header"
                src="../assets/imgheader.png"
                width="180"
                class="mx-auto ma-5"
                transition="scale-transition"
              />
                <v-list-item>
                    <v-list-item-content>
                        <v-list-item-title class="headline text-center">Request For Leave</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>

                <v-col class="py-1" cols="12">
                  <v-text-field
                      v-model="allData.firstname"
                      :rules="nameRules"
                      :counter="20"
                      label="First name"
                      required
                      clearable
                      color="#f3713a"
                  ></v-text-field>
                </v-col>

                <v-col class="py-1" cols="12">
                    <v-text-field
                        v-model="allData.lastname"
                        :rules="nameRules"
                        :counter="20"
                        label="Last name"
                        required
                        clearable
                        color="#f3713a"
                    ></v-text-field>
                </v-col>

                <v-col class="py-1" cols="12">
                    <v-select
                        :items="this.leavetype"
                        v-model="allData.leavetype"
                        :rules="typeRules"
                        label="Leave Type"
                        required
                        clearable
                        color="#f3713a"
                    ></v-select>
                </v-col>
                <v-col class="py-1" cols="12">
                  <v-textarea
                    v-model="allData.reason"
                    label="Reason for Leave"
                    required
                    clearable
                    rows="2"
                    class="py-1"
                    color="#f3713a"
                  ></v-textarea>
                </v-col>

                <v-row justify="space-around">
                    <div class="group">
                        <p>Start Date</p>
                        <v-date-picker value="Start Date" elevation="7" year-icon="mdi-calendar-blank" v-model="allData.startdate" color="#f3713a"></v-date-picker>
                    </div>
                    <div class="group">
                        <p>End Date</p>
                        <v-date-picker v-model="allData.enddate" elevation="7" year-icon="mdi-calendar-blank" color="#1D2553"></v-date-picker>
                    </div>

                </v-row>

                <v-card-text class="message">
                    *โปรดกรอกข้อมูลของคุณให้ถูกต้องและครบทุกช่อง
                </v-card-text>

                <v-card-actions class="justify-end">
                    <v-btn dark color="#f3713a" type="submit" class="mr-4">
                        Submit
                    </v-btn>
                    <v-btn dark color="#1D2553" @click.prevent="reset">
                        reset
                    </v-btn>
                </v-card-actions>
            </form>
          </v-container>
      </v-card>
    </v-container>
  </div>
</template>

<script>

export default {
  name: "Home",
  data() {
        return {
            leavetype: ['ลาป่วย', 'ลากิจส่วนตัว','ลาคลอดบุตร', 'ลาพักผ่อน', 'ลาไปศึกษา ฝึกอบรม'],
            startDate: new Date().toISOString().substr(0, 10),
            endDate: new Date().toISOString().substr(0, 10),
            allData: {
                firstname: '',
                lastname: '',
                leavetype: '',
                reason: '',
                startdate: '',
                enddate: ''
            }
        }
    },
    methods: {
        submit() {
            console.log(this.allData)
        },
        reset() {
            this.allData = {
                firstname: '',
                lastname: '',
                leavetype: '',
                reason: '',
            }
        }
    },
  
};
</script>

<style scoped>
  .home {
    background: #E8EBEE;
  }
  .card-form {
    display: grid;
    align-items: center;
  }
  .group {
    margin-bottom: 1.5rem;
  }
  .message {
    color: #e73d3d;
  }
</style>
