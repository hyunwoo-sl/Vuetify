<template>
  <v-layout row justify-center>
    <v-dialog v-model="dialog" persistent max-width="800px">
      <v-card>
        <v-card-title>
          <span class="headline">Spray</span>
        </v-card-title>
        <v-card-text>
          <v-container grid-list-md>
            <v-layout column wrap justify-center>
              <base-map
                class="pa-1"
                style="width: 100%">
              </base-map>
              <v-flex py3>
                <v-divider></v-divider>
              </v-flex>
              <v-spacer></v-spacer>
              <p>살포 설정</p>
              <v-text-field
                v-model="fertilizer"
                label="비료"
                disabled
              ></v-text-field>
              <v-text-field
                v-model="fertilizerSection"
                label="비료 구분"
                disabled
              ></v-text-field>
            </v-layout>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" flat @click="closePopup()">닫기</v-btn>
          <v-btn color="blue darken-1" flat @click="closePopup()">저장</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-layout>
</template>

<script>
  import BaseMap from '@/components/map/BaseMap'

  export default {
    name: "SprayDialog",
    components: {
      BaseMap
    },
    data: () => ({
      dialog: false,

      fertilizer: "",
      fertilizerSection: ""
    }),
    created() {
      this.dialog = true
    },
    methods: {
      closePopup() {
        this.dialog = false
        this.$emit('close')
      }
    }
  }
</script>

<style scoped>

</style>
