<template>
  <div class="card shadow" :class="type === 'dark' ? 'bg-default' : ''">
    <div class="card-header border-0" :class="type === 'dark' ? 'bg-transparent' : ''">
      <div class="row align-items-center">
        <div class="col">
          <h3 class="mb-0" :class="type === 'dark' ? 'text-white' : ''">{{ tabletitle }}</h3>
        </div>
      </div>
    </div>

    <div class="table-responsive">
      <base-table
        class="table align-items-center table-flush"
        :class="type === 'dark' ? 'table-dark' : ''"
        :thead-classes="type === 'dark' ? 'thead-dark' : 'thead-light'"
        tbody-classes="list"
        :data="TeamTable"
      >
        <template slot="columns">
          <th>제목</th>
          <th>날짜</th>
          <th>주소</th>
          <th>참여 팀</th>
          <th>대기 상태</th>
          <th></th>
        </template>

        <template slot-scope="{ row }">
          <th scope="row">
            <div class="media align-items-center">
              <div class="media-body">
                <router-link
                  :to="{
                    name: '팀 SPOT',
                    params: { uid: row.uid },
                  }"
                >
                 <span class="name mb-0 text-sm" style="color:azure;" @click="move(row.uid)">{{ row.title }}</span>
                </router-link>
              </div>
            </div>
          </th>
          <td class="time">{{ row.matching_date }}</td>
          <td>
            <span class="status">{{ getSpotName(row.place_uid) }}</span>
          </td>
          <td>{{ row.ready_num + " / 2" }}</td>

          <td>
            <div class="d-flex align-items-center">
              <span class="completion mr-2" :class="row.wait == '신청종료' ? 'text-danger':''">{{ row.wait }}</span>
            </div>
          </td>

          <td class="text-right">
            <router-link
              :to="{
                name: '팀 SPOT',
                params: { uid: row.uid },
              }"
              v-if="isLogined"
            >
              <base-button outline type="secondary">입장하기</base-button>
            </router-link>
            <base-button outline type="secondary" v-if="!isLogined" @click="notEnter = true">입장하기</base-button>
          </td>
        </template>
      </base-table>
    </div>
    <div
      class="card-footer d-flex justify-content-between"
      :class="type === 'dark' ? 'bg-transparent' : ''"
    >
      <div class="col-md-4">
        <base-button type="secondary" :disabled="!isEnterMatch || !isFullteam || !isHeader" @click="modals = true">팀SPOT 만들기</base-button>

        <modal :show.sync="modals" body-classes="p-0" modal-classes="modal-dialog modal-md">
          <card
            type="secondary"
            shadow
            header-classes="bg-white pb-5"
            body-classes="px-lg-5 py-lg-5"
            class="border-0"
          >
            <template>
              <div class="text-muted text-center mb-3">
                <h4>팀 SPOT 만들기</h4>
              </div>
            </template>
            <template>
              <div class="text-center text-muted mb-4">
                <h6>정보를 입력해주세요</h6>
              </div>
              <form role="form">
                <base-input alternative class="mb-3" v-model="title" placeholder="제목을 적어주세요"></base-input>
                <base-input addon-left-icon="ni ni-calendar-grid-58">
                  <flat-picker
                    slot-scope="{ focus, blur }"
                    @on-open="focus"
                    @on-close="blur"
                    :config="dates.config"
                    class="form-control datepicker"
                    v-model="dates.simple"
                  ></flat-picker>
                </base-input>
                <base-dropdown class="mr-3">
                  <base-button
                    slot="title"
                    type="secondary"
                    class="dropdown-toggle"
                  >{{ this.stadiumN }}</base-button>
                  <a
                    class="dropdown-item"
                    v-for="(stadiumData,i) in stadiumDatas"
                    v-bind:key="i"
                    @click="choice1(stadiumData)"
                  >{{ stadiumData.place_name }}({{ stadiumData.address }})</a>
                </base-dropdown>
                <div class="text-center">
                  <base-button type="success" @click="getTSpot" class="my-4 mr-4">팀 대결하기</base-button>
                  <modal :show.sync="this.choice" gradient="danger" class="text-center">
                   <div class="py-3 text-center mb-0">
                     <h3 class="text-white mb-3">방 이름과 경기장 모두를 선택해 주세요!</h3>
                     <base-button size="sm" type="secondary" @click="choice = false">닫기</base-button>
                   </div>
                </modal>
                <modal :show.sync="this.needlogin" gradient="danger" class="text-center">
                   <div class="py-3 text-center mb-0">
                     <h3 class="text-white mb-3">로그인이 필요합니다! 로그인 해주세요.!</h3>
                     <base-button size="sm" type="secondary" @click="needlogin = false">닫기</base-button>
                   </div>
                </modal>
                  <base-button type="secondary" @click="modals = false">닫기</base-button>
                </div>
              </form>
            </template>
          </card>
        </modal>

        <modal
          :show.sync="isCredit"
          body-classes="p-0"
          modal-classes="modal-dialog modal-md"
        >
          <card
            type="secondary"
            shadow
            header-classes="bg-white pb-5"
            body-classes="px-lg-5 py-lg-5"
            class="border-0"
          >
            <template>
              <div class="text-muted text-center mb-3">
                <h4>입장 준비</h4>
              </div>
            </template>
            <template>
              <div class="text-center text-muted mb-4">
                <h6>진영을 선택해주세요.</h6>
              </div>
              <form role="form">
                <div class="d-flex justify-content-center">
                  <base-dropdown class="mr-3">
                    <base-button slot="title" type="secondary" class="dropdown-toggle">{{ myTeam }}</base-button>
                    <a
                      class="dropdown-item"
                      v-for="(teamitem,i) in teamList"
                      :key="i"
                      @click="TeamChange(teamitem.name)"
                    >{{ teamitem.name }}</a>
                  </base-dropdown>
                </div>
                <div class="text-center text-muted mb-4">
                  <small>
                    진영을 선택하였으면 결제를 해주세요.
                    <br />결제 금액은
                    <big style="font-size:30px;" class="text-warning">
                      <b>{{ roomprice }}원</b>
                    </big> 입니다.
                  </small>
                </div>
                <div class="text-center">
                  <base-button type="success" class="my-4 mr-4" @click="CreditGo">결제하기</base-button>
                  <base-button type="secondary" @click="isCredit = false">닫기</base-button>
                </div>
              </form>
            </template>
          </card>
        </modal>

        <modal
          :show.sync="notEnter"
          gradient="danger"
          modal-classes="modal-danger modal-dialog-centered"
        >
          <div class="py-3 text-center">
            <i class="ni ni-bell-55 ni-3x"></i>
            <h4 class="heading mt-4">로그인을 하셔야 이용할 수 있습니다.</h4>
            <p>로그인 페이지로 이동하셔서 로그인을 먼저 진행해주세요.</p>
          </div>

          <template slot="footer">
            <router-link to="/login">
              <base-button type="white">로그인하기</base-button>
            </router-link>
            <base-button
              type="link"
              text-color="white"
              class="ml-auto"
              @click="notEnter = false"
            >닫기</base-button>
          </template>
        </modal>
      </div>
      <div>
        <base-pagination :page-count="Math.ceil(TeamtableData.length / 5)" v-model="pagination"></base-pagination>
      </div>
    </div>
  </div>
</template>
<script>
import flatPicker from "vue-flatpickr-component";
import "flatpickr/dist/flatpickr.css";

export default {
  name: "projects-table",
  components: { flatPicker },
  created() {
    if (this.$cookies.isKey("UserInfo")) {
      this.isLogined = true;
      this.userInfo = this.$cookies.get("UserInfo")
    }
    this.$axios
      .get(this.$SERVER_URL + "TeamMatchAll/")
      .then((res) => {
        this.TeamtableData = res.data;
        for(var i=0; i < this.TeamtableData.length; i++) {
          if (this.TeamtableData[i].ready_num >= 2) {
            this.TeamtableData[i].wait = "신청종료"
          } else {
            this.TeamtableData[i].wait = "신청가능"
          }
        }
        this.TeamTable = this.TeamtableData.slice(0, 5);
        this.EnterMatchCheck();
      })
      
    this.$axios
      .get(this.$SERVER_URL + "place/list")
      .then((rest) => {
       
        this.stadiumDatas = rest.data;
      })
    var nowhere = new FormData()
    nowhere.append('where', "")
    this.$axios.post(this.$SERVER_URL + "team/list", nowhere)
      .then(res => {
        var myuid = this.$cookies.get('UserInfo').uid
        var teamList = res.data;
        for (var i=0; i < teamList.length; i++) {
          if (teamList[i].captain_uid == myuid) {
            this.isHeader = true;
            if (teamList[i].player_num >= 11) {
              this.isFullteam = true
            }
          }
        }
      })
     
  },
  watch: {
    sidolist: function () {
      this.sidoinfo();
    },
    pagination: function () {
      this.selectpage();
    },
  },
 props: {
    type: {
      type: String,
    },
    sidolist: {type: Array}
    },

  data() {
    return {
      dates: {
        simple: "2020-08-22 00:00:00",
        config: {
          allowInput: true,
          enableTime: true,
          dateFormat: "Y-m-d H:i:00",
        }
      },
      isEnterMatch: false,
      isLogined: false,
      isFullteam: false,
      isHeader: false,
      tabletitle: "팀 SPOT",
      TeamtableData: [],
      modals: false,
      notEnter: false,
      stadiumN: "경기장을 골라주세요",
      stadiumDatas: [],
      title: "",
      placeuid: 0,
      placeprice: 1,
      homeuid:0,
      roomprice:1,
      roomuid:0,
      placecode: 0,
      userInfo: Object,
      pagination: 1,
      TeamTable: [],
      isCredit: false,
      choice : false,
      needlogin : false,
      myTeam: 'RED',
      myPosition: "선택해주세요",
      myPosUid: 0,
      manageruid: Math.floor(Math.random()*5+1),
      teamList: [{ name: "RED" }, { name: "BLUE" }],
      postionList: [
        { name: "랜덤" },
        { name: "공격수" },
        { name: "미드필더" },
        { name: "수비수" },
        { name: "골키퍼" },
      ],
    };
  },

  methods: {
    EnterMatchCheck() {
      var CheckMatchform = new FormData()
      CheckMatchform.append('head_uid', this.$cookies.get('UserInfo').uid)
      this.$axios.post(this.$SERVER_URL + "/TRoomCheck", CheckMatchform)
        .then(res => {       
          if (res.data.length == 0) { 
            this.isEnterMatch = true
          }
        })       
    },
    choice1(stadium) {
      this.stadiumN = stadium.place_name;

      for(var a = 0; a < this.stadiumDatas.length; a++){
          if(this.stadiumN == this.stadiumDatas[a].place_name){
              this.placeuid = this.stadiumDatas[a].uid;
              break;
          }
      }

      this.placeprice = 50000;
      this.placecode = stadium.code;
    },
    getTSpot() {
      if (this.$cookies.isKey("UserInfo")) {     
        const makeData = new FormData();
        makeData.append("title", this.title);
        makeData.append('manager_uid',this.manageruid);
        makeData.append("matching_date", this.dates.simple);
        makeData.append("place_uid", this.placeuid);
        makeData.append("home_team_uid", this.$cookies.get("UserInfo").team_uid);
        makeData.append("price", this.placeprice);
        makeData.append("dong_code", this.placecode);
        makeData.append("head_uid", this.$cookies.get("UserInfo").uid);
        if (this.title != "" && this.placecode != 0) {
          this.$axios
            .post(this.$SERVER_URL + "TRoomCreate/", makeData)
            .then((res) => {
              this.modals = false
              this.isCredit = true
              this.homeuid= res.data[res.data.length-1].home_matching_entry_uid
              this.roomprice = res.data[res.data.length-1].price
              this.roomuid = res.data[res.data.length-1].uid
            })
           
        } else {
          this.choice = true;
        }
      } else {
        this.needlogin = true;
      }
    },
    sidoinfo() {
      const sidoData = new FormData();
  
      sidoData.append("doe", this.sidolist[0]);
      sidoData.append("si", this.sidolist[1]);
      sidoData.append("dong", this.sidolist[2]);
      sidoData.append("word", this.sidolist[3]);
     
      this.$axios.post(this.$SERVER_URL + "TeamMatchAll", sidoData).then((res) => {
        this.TeamtableData = res.data;
        for(var i=0; i < this.TeamtableData.length; i++) {
          if (this.TeamtableData[i].ready_num >= 2) {
            this.TeamtableData[i].wait = "신청종료"
          } else {
            this.TeamtableData[i].wait = "신청가능"
          }
        }
        this.selectpage();
        this.pagination = 1;
       
      })
    },
    selectpage() {
      this.TeamTable = [];
      this.TeamTable = this.TeamtableData.slice(
        (this.pagination - 1) * 5,
        (this.pagination - 1) * 5 + 5
      );
   
    },
    TeamChange(name) {
      this.myTeam = name;
    },
    CreditGo() {
     
      if (this.myPosition === "공격수") {
        this.myPosUid = 1;
      } else if (this.myPosition === "미드필더") {
        this.myPosUid = 5;
      } else if (this.myPosition === "수비수") {
        this.myPosUid = 9;
      } else if (this.myPosition === "골키퍼") {
        this.myPosUid = 13;
      }
      const EnterInfo = new FormData();
      const rprice = String(this.roomprice)
      EnterInfo.append("uid", this.$cookies.get("UserInfo").uid);
      EnterInfo.append("positionnum", this.myPosUid);
      EnterInfo.append("team_entry_uid", this.homeuid);
      EnterInfo.append('price', rprice)
      EnterInfo.append("room_uid", this.roomuid)
     
      this.$axios
        .post(this.$SERVER_URL + "kakaoPay/", EnterInfo)
        .then(res => {
         
          window.location.replace(res.data)
        })
   
    },

    getSpotName(uid){
      for(var a = 0; a < this.stadiumDatas.length; a++){
        if(this.stadiumDatas[a].uid == uid){
          return this.stadiumDatas[a].place_name;
        }
      }
    },
  },
};
</script>
<style></style>