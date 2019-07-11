<template>
    <v-tabs
      vertical
      v-model="tab"
      background-color="aliceblue"
    >
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
        v-for="{ code, name, email, deadline } in countries"
        :key="code + '-item'"
      >
        <v-card>
          <v-card-title style="background-color: aliceblue">
            <span class="flag-icon" :class="'flag-icon-' + code"></span>
            {{ name }}
            <v-spacer />
            <v-chip
              v-if="deadline"
            >
              Local Submission Deadline: {{ deadline }}
            </v-chip>
          </v-card-title>
          <v-divider />
          <v-flex xs12>
            <v-layout fill-height row wrap>
              <v-flex>
                <v-card>
                  <v-card-title
                    class="text-xs-center"
                  >FOR ANY INQUIRY PLEASE CONTACT</v-card-title>
                  <v-divider />
                  <v-card-actions>
                    <v-btn
                      block
                      color="primary"
                      dark
                      :href="'mailto:' + countries[tab].email"
                    >
                      <v-icon>email</v-icon>
                      {{ countries[tab].email }}
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-flex>
              <v-flex>
                <v-card>
                  <v-card-title>
                    CLICK HERE TO DOWNLOAD THE SUBMISSION FORM
                  </v-card-title>
                  <v-divider />
                  <v-card-actions>
                    <v-btn
                      block
                      color="primary"
                      dark
                      href="/dc6_21st_EntryForm.pdf"
                    >
                      <v-icon>picture_as_pdf</v-icon>
                      Entry Form
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-flex>
            </v-layout>
            <v-alert
              color="error"
              dark
              elevation="2"
              class="mb-0"
            >
              FOR ALL THE CREATORS WHO ARE SUBMITTING THERE WORK, <br v-if="code === 'id'">PLEASE DOWNLOAD SUBMISSION APPLICATION AND FILL IN AND EMAIL TO
              <v-chip
                :href="'mailto:' + countries[tab].email"
                label
                color="primary"
                text-color="white"
              >
                <v-icon>email</v-icon>
                {{ countries[tab].email.toUpperCase() }}
              </v-chip>
              <span v-if="code === 'id'">
                OR
              </span>
              <v-chip
                v-if="code === 'id'"
                :href="'mailto:' + 'budaya@jpf.or.id'"
                label
                color="primary"
                text-color="white"
              >
                <v-icon>email</v-icon>
                BUDAYA@JPF.OR.ID
              </v-chip>
              <br>
              PLEASE DON'T FORGET TO PROVIDE US THE <strong>LINK TO DOWNLOAD YOUR VIDEO</strong>
            </v-alert>
          </v-flex>
          <v-flex xs12>
            <v-layout justify-center row>
              <v-flex
                lg5
                xl4
              >
                <v-card class="my-2">
                  <v-img
                    alt="poster"
                    src="/digicon-id.jpg"
                  >
                    <v-card
                      flat
                      class="text-xs-center deadline"
                      color="#FDFFDE"
                    >
                      SUBMISSION<br>
                      DEADLINE<br>
                      <span v-if="deadline">
                      {{ deadline }}
                    </span>
                      <span v-else>
                      TBD
                    </span>
                    </v-card>
                  </v-img>
                </v-card>
              </v-flex>
              <v-flex
                lg7
                xl8
              >
                <v-card class="my-2">
                  <v-card-title>
                    2019 Digicon6 Asia Award Prizes
                  </v-card-title>
                  <v-divider />
                  <v-list>
                    <template v-for="(prize, index) in prizes">
                      <v-divider v-if="index !== 0" />
                      <v-list-item :key="index">
                        <v-list-item-content>
                          <v-list-item-title v-text="prize.name"></v-list-item-title>
                        </v-list-item-content>
                        <v-list-item-action>
                          {{ prize.prize }} yen
                        </v-list-item-action>
                      </v-list-item>
                    </template>
                  </v-list>
                </v-card>
                <v-card
                  v-if="code === 'th' || code === 'id'"
                >
                  <v-card-title>
                    LOCAL SUPPORTING ORGANIZER AND PARTNER
                  </v-card-title>
                  <v-divider />
                  <v-card-text>
                    <v-img src="/Logomark_A.jpg" max-width="200" class="justify-center text-xs-center mx-auto" />
                  </v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-flex>
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
          "email": "info-hk@tbs-digicon.asia",
          "deadline": "2019/8/8"
        },
        {
          "name": "India",
          "code": "in",
          "email": "info-india@tbs-digicon.asia",
          "deadline": "2019/8/30"
        },
        {
          "name": "Indonesia",
          "code": "id",
          "email": "info-indonesia@tbs-digicon.asia",
          "deadline": "2019/7/31"
        },
        {
          "name": "Japan",
          "code": "jp",
          "email": "info-japan@tbs-digicon.asia"
        },
        {
          "name": "Malaysia",
          "code": "my",
          "email": "info-malaysia@tbs-digicon.asia",
          "deadline": "2019/8/1"
        },
        {
          "name": "Singapore",
          "code": "sg",
          "email": "info-singapore@tbs-digicon.asia",
          "deadline": "2019/8/15"
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
          "email": "info-taiwan@tbs-digicon.asia",
          "deadline": "2019/7/31"
        },
        {
          "name": "Thailand",
          "code": "th",
          "email": "info-thailand@tbs-digicon.asia"
        },
        {
          "name": "Uzbekistan",
          "code": "uz",
          "email": "info-uzbekistan@tbs-digicon.asia",
          "deadline": "2019/9/1"
        },
        {
          "name": "Vietnam",
          "code": "vn",
          "email": "info-vietnam@tbs-digicon.asia",
          "deadline": "2019/9/1"
        }
      ],
      prizes: [
        { name: 'DigiCon6 ASIA Grand Prize', prize: '500,000' },
        { name: 'DigiCon6 ASIA Gold', prize: '300,000' },
        { name: 'Asian Silver Asian Perspective', prize: '100,000' },
        { name: 'Asian Silver Splendid Technique', prize: '100,000' },
        { name: 'Asian Silver Innovative Art', prize: '100,000' },
        { name: 'Asia NEXT GENERATION', prize: '100,000' },
        { name: 'That’s Entertainment!', prize: '100,000' },
      ]
    }
  },
}
</script>

<style scoped>
  .deadline {
    color: rgb(240,126,41) !important;
    font-weight: bold;
    font-size: 24px;
    width: 38.2%;
    height: 12.8%;
    position: absolute;
    right: 2%;
    top: 26.45%
  }
</style>
