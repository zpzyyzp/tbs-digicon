<template>
  <v-tabs
    vertical
    v-model="tab"
    background-color="aliceblue"
  >
    <v-list dark class="elevation-1">
      <v-list-item>
          <span class="title">For Any Inquiry Please Contact<br>
          <a :href="'mailto:' + countries[tab].email" class="font-weight-bold" style="text-shadow:0 0 1px #5cd983; color: #00bcd4;">{{ countries[tab].email }}</a>
          </span>
      </v-list-item>
    </v-list>
    <v-btn
      color="primary"
      href="/dc6_21st_EntryForm.pdf"
      class="my-1"
    >
      <v-icon>picture_as_pdf</v-icon>
      Entry Form
    </v-btn>
    <v-tab
      dark
      v-for="{ code, name } in countries"
      :key="code"
    >
      <div class="mr-auto">
        <span class="flag-icon" :class="'flag-icon-' + code"></span>
        {{ name }}
      </div>
    </v-tab>
    <v-tab-item
      v-for="{ code, name, email } in countries"
      :key="code + '-item'"
    >
      <v-card>
        <v-card-title style="background-color: aliceblue">
          <span class="flag-icon" :class="'flag-icon-' + code"></span>
          {{ name }}
          <v-spacer />
          <v-chip
            v-if="code === 'sg'"
          >
            Local Submission Deadline: 8/15
          </v-chip>
        </v-card-title>
        <v-divider />
        <v-card-text class="text-xs-center">
          <img
            alt="poster"
            src="/pic.jpg"
          />
        </v-card-text>
      </v-card>
    </v-tab-item>
  </v-tabs>
</template>

<script>

export default {
  data () {
    return {
      tab: 0,
      countries: [
        {
          "name": "Cambodia",
          "code": "kh",
          "email": "info-cambodia@tbs-digicon.asia"
        },
        {
          "name": "China",
          "code": "cn",
          "email": "info-china@tbs-digicon.asia"
        },
        {
          "name": "Hong Kong",
          "code": "hk",
          "email": "info-hk@tbs-digicon.asia"
        },
        {
          "name": "India",
          "code": "in",
          "email": "info-india@tbs-digicon.asia"
        },
        {
          "name": "Indonesia",
          "code": "id",
          "email": "info-indonesia@tbs-digicon.asia"
        },
        {
          "name": "Japan",
          "code": "jp",
          "email": "info-japan@tbs-digicon.asia"
        },
        {
          "name": "Malaysia",
          "code": "my",
          "email": "info-malaysia@tbs-digicon.asia"
        },
        {
          "name": "Singapore",
          "code": "sg",
          "email": "info-singapore@tbs-digicon.asia"
        },
        {
          "name": "South Korea",
          "code": "kr",
          "email": "info-korea@tbs-digicon.asia"
        },
        {
          "name": "Sri Lanka",
          "code": "lk",
          "email": "info-srilanka@tbs-digicon.asia"
        },
        {
          "name": "Taiwan",
          "code": "tw",
          "email": "info-taiwan@tbs-digicon.asia"
        },
        {
          "name": "Thailand",
          "code": "th",
          "email": "info-thailand@tbs-digicon.asia"
        },
        {
          "name": "Uzbekistan",
          "code": "uz",
          "email": "info-uzbekistan@tbs-digicon.asia"
        },
        {
          "name": "Vietnam",
          "code": "vn",
          "email": "info-vietnam@tbs-digicon.asia"
        }
      ]
    }
  },
}
</script>

<style scoped>
</style>
