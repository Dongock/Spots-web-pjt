<template>
  <div>
    <!-- 축구 모임 지원 사이트에서 경기 후 매니저가 선수평가를 내리는 페이지 -->
    <!-- 제목 부분 -->
   <base-header class="pb-5 pt-md-8 mb-4">
      <div class="row d-flex flex-row justify-content-between">
        <div class="col-7">
          <card title="Room information" class="mb-4 mb-xl-0">
            <h2 class="mb-0">{{ RoomData.title }}</h2>
            <!-- 방의 이름을 불러옴 -->
          </card>
          <h3 class="text-white mt-2">담당 매니저 : {{Manager.nickname}}  </h3>4
          <!-- 매니저 이름 불러오기 -->
        </div>
      </div>
    </base-header>

<!-- 매니저 평가를 위한 선수 창 -->
    <div class="row d-flex flex-row" :class="type === 'dark' ? 'bg-default' : ''">
      <div class="table-responsive col m-2">
        <div class="text-center p-2 mb-2 bg-danger rounded-top">
          <h2>Red Team</h2>
          <!-- 좌측의 레드팀 -->
        </div>
        <base-table
          class="table align-items-center table-flush border-solid table-danger rounded-bottom text-center"
          :class="type === 'dark' ? 'table-dark' : ''"
          :thead-classes="type === 'dark' ? 'thead-dark' : 'thead-light'"
          tbody-classes="list"
          :data="RedtableDatas"
        >
        <!-- 레드팀의 데이터를 불러와서 표를 채움 -->
          <template slot="columns">
            <th>유저 명</th>
            <th>기록 및 평가</th>
          </template>

         <template slot-scope="{ row }">
            <th scope="row">
              <span class="name mb-0 text-sm text-default">{{ row.name }}</span>
            </th>
            <td class="row justify-content-between ml-4 mr-4">
              <button class="btn-secondary ml-3 btn-lg" > 득점 : {{ row.goal }} <base-dropdown>
                  <a class="dropdown-item" v-for="(sc,i) in score" 
                  v-bind:key="i" @click="inputgoal(sc, row) ">{{sc}}</a>
              </base-dropdown></button>
            <!-- 매니저가 직접 골을 입력하는 방식 -->
              <button class="btn-secondary btn-lg">도움 : {{ row.assist }}<base-dropdown>
              <a class="dropdown-item" v-for="(sc,i) in score" 
              v-bind:key="i" @click="inputassist(sc, row)">{{sc}}</a></base-dropdown></button>
              
              <base-button block type="secondary" size="lg" class="col-4 mr-3"  @click="modal1 = true, black(row)" >신고
              </base-button>
              <!-- 매니저가 도움을 입력하는 방식 -->
              <modal :show.sync="modal1" body-classes="p-0" modal-classes="modal-dialog modal-md">
                <!-- 블랙리스트를 선정하는 모달 창 -->
                <card
                  type="secondary"
                  shadow
                  header-classes="bg-white pb-5"
                  body-classes="px-lg-5 py-lg-5"
                  class="border-0"
                >
                <template >
                  <div class="text-muted text-center mb-3">
                    <h4>유저 {{rowlist.name}} 블랙리스트 신고하기</h4>
                  </div>
                </template>
                <template>
                  <div class="text-center text-muted mb-4">
                    <h6>신고 사유를 선택해주세요</h6>
                  </div>
                  <form role="form">
                    <base-button class="btn-secondary mr-0 btn-lg" style="z-index:9999;">신고사유 : {{wbl}}<base-dropdown>
                  <a class="dropdown-item" v-for="(bl,i) in blacklist" 
                  v-bind:key="i" @click="inputblack(bl)">{{bl}}</a></base-dropdown></base-button>
                    <div class="text-center">
                      <base-button class="mt-3" type="warning" @click="modal1 = false, blackpoint(wbl)" >제출</base-button>
                      <base-button class="mt-3" type="secondary" @click="modal1 = false">닫기</base-button>
                    </div>
                  </form>
                </template>
              </card>
            </modal>
            </td>
          </template>
        </base-table>
      </div>
      <!-- 위와 마찬가지로 블루팀 -->
      <div class="table-responsive col m-2">
        <div class="text-center p-2 mb-2 bg-primary rounded-top">
          <h2 class="text-white">Blue Team</h2>
        </div>
        <base-table
          class="table align-items-center table-flush border-solid table-primary rounded-bottom text-center"
          :class="type === 'dark' ? 'table-dark' : ''"
          :thead-classes="type === 'dark' ? 'thead-dark' : 'thead-light'"
          tbody-classes="list"
          :data="BluetableDatas"

        >
          <template slot="columns">
            <th>유저 명</th>
            <th>기록 및 평가</th>
          </template>

          <template slot-scope="{ row }">
            <th scope="row">
              <span class="name mb-0 text-sm text-default">{{ row.name }}</span>
            </th>
            <td class="row justify-content-between ml-4 mr-4">
              <button class="btn-secondary ml-3 btn-lg" > 득점 : {{ row.goal }} <base-dropdown>
                  <a class="dropdown-item" v-for="(sc,i) in score" 
                  v-bind:key="i" @click="inputgoal(sc, row) ">{{sc}}</a>
              </base-dropdown></button>

              <button class="btn-secondary btn-lg">도움 : {{ row.assist }}<base-dropdown>
              <a class="dropdown-item" v-for="(sc,i) in score" 
              v-bind:key="i" @click="inputassist(sc, row)">{{sc}}</a></base-dropdown></button>
              
              <base-button block type="secondary" size="lg" class="col-4 mr-3" @click="modal1 = true, black(row)" >신고
              </base-button>
              <modal :show.sync="modal1" body-classes="p-0" modal-classes="modal-dialog modal-md">
                <card
                  type="secondary"
                  shadow
                  header-classes="bg-white pb-5"
                  body-classes="px-lg-5 py-lg-5"
                  class="border-0"
                >
                  <template >
                    <div class="text-muted text-center mb-3">
                      <h4>유저 {{rowlist.name}} 블랙리스트 신고하기</h4>
                    </div>
                  </template>
                  <template>
                    <div class="text-center text-muted mb-4">
                      <h6>신고 사유를 선택해주세요</h6>
                    </div>
                    <form role="form">
                      <base-button class="btn-secondary mr-0 btn-lg" style="z-index:9999;">신고사유 : {{wbl}}<base-dropdown>
                    <a class="dropdown-item" v-for="(bl,i) in blacklist" 
                    v-bind:key="i" @click="inputblack(bl)">{{bl}}</a></base-dropdown></base-button>
                      <div class="text-center">
                        <base-button class="mt-3" type="warning" @click="modal1 = false, blackpoint(wbl)" >제출</base-button>
                        <base-button class="mt-3" type="secondary" @click="modal1 = false">닫기</base-button>
                      </div>
                    </form>
                  </template>
                </card>
              </modal>
            </td>
          </template>
        </base-table>
      </div>
    </div>
    <div class=" d-flex justify-content-between" style="height:40px;">
      <!-- mvp 선정을 위한 버튼 -->
      <base-button type="success"  class="ml-4" @click="modal2 = true, pickmvp(RedtableDatas, BluetableDatas)">오늘의 MVP 선정</base-button>
      <modal :show.sync="modal2" body-classes="p-0" modal-classes="modal-dialog modal-md">
          <card
            type="secondary"
            shadow
            header-classes="bg-white pb-5"
            body-classes="px-lg-5 py-lg-5"
            class="border-0"
          >
            <template>
              <div class="text-muted text-center mb-3">
                <h4>오늘의 MVP 선정</h4>
              </div>
            </template>
            <template>
              <div class="text-center text-muted mb-4">
                <h6>MVP를 골라주세요!</h6>
              </div>
              <div class="text-center">
              <form role="form">
                <base-button class="btn-secondary mr-0 btn-lg " style="z-index:9999;">오늘의 MVP : {{mvp}}<base-dropdown>
              <a class="dropdown-item" v-for="(un,i) in rowlist" 
              v-bind:key="i" @click="choicemvp(un, un.name)">{{un.name}}</a></base-dropdown></base-button>
                <div class="text-center">
                  <base-button class="mt-3" type="warning" @click="modal2 = false, mvppoint()" >제출</base-button>
                  <base-button class="mt-3" type="secondary" @click="modal2 = false">닫기</base-button>
                </div>
              </form>
              </div>
            </template>
          </card>
        </modal>
        <!-- 매니저가 입력한 값을 통해 스코어를 보여주는 버튼 -->
     <base-button type="secondary" >{{this.winteam}} {{this.rgoal}} : {{this.bgoal}}</base-button>
    <base-button type="warning" class="mr-4" @click='submit'>평가 및 경기 마치기</base-button> 
    <!-- 경기를 마치고 정보를 제출하는 버튼 -->
  </div>
  <!-- 예외 상황을 대비한 모달 -->
   <modal :show.sync="dupli" gradient="danger" class="text-center">
                   <div class="py-3 text-center mb-0">
                     <h3 class="text-white mb-3">이미 투표하셨습니다.</h3>
                     <base-button size="sm" type="secondary" @click="dupli = false">닫기</base-button>
                   </div>
                </modal>
    <modal :show.sync="this.problem" gradient="danger" class="text-center">
        <div class="py-3 text-center mb-0">
          <h3 class="text-white mb-3">문제가 발생하였습니다. 메인페이지로 돌아갑니다.</h3>
          <base-button size="sm" type="secondary" @click="problem = false">닫기</base-button>
        </div>
      </modal>
      <modal :show.sync="this.vote" gradient="danger" class="text-center">
        <div class="py-3 text-center mb-0">
          <h3 class="text-white mb-3">MVP 투표 해주세요!</h3>
          <base-button size="sm" type="secondary" @click="vote = false">닫기</base-button>
        </div>
      </modal>
  </div>
</template>
<script>
export default {
  name: "freematchroom",
  components: {},
  props: {
    type: {type:String},
  },
  data() {
    return {
      RoomData: Object,
      Manager : Object,
      rgoal:0,
      bgoal:0,
      mvp:"",
      homewin:1,
      RedtableDatas: [],
      BluetableDatas: [],
      persondata:[],
      wbl:"",
      dupoint : [],
      dumvp : [],
      myTeam: "RED",
      myPosUid: 0,
      erowlist:[],
      rowlist:[],
      mvplist:[],
      manageruid:0,
      winteam: "무승부",
      blacklist: ["공격적인 태도", "무단불참", "지속적인 거친 반칙", "폭언 및 욕설", "이기적인 태도"],
      teamList: [{ name: "RED" }, { name: "BLUE" }],
      posRedList: [],
      posBlueList: [],
      pastuid : [],
      ismvp : false,
      posNameList: [
        "defender1_uid",
        "defender2_uid",
        "defender3_uid",
        "defender4_uid",
        "goalkeeper_uid",
        "midfielder1_uid",
        "midfielder2_uid",
        "midfielder3_uid",
        "midfielder4_uid",
        "striker1_uid",
        "striker2_uid",
        "striker3_uid",
        "striker4_uid",
      ],
      score:[0,1,2,3,4,5,6,7,8,9,10],
      modal1:false,
      modal2:false,
      dupli:false,
      problem : false,
      vote : false,
     };
  },

  methods: {
    inputgoal(sc, row) {
      // 골을 입력했을 때
       row.goal = sc;
       for (var a=0; a<this.RedtableDatas.length; a++) {
         if (this.RedtableDatas[a].uid == (row.uid)) {
           this.RedtableDatas[a].goal = sc;
           this.rgoal = 0;
           this.bgoal = 0;
         }
         else if (this.BluetableDatas[a].uid == (row.uid)){
           this.BluetableDatas[a].goal = sc;
           this.bgoal = 0;
           this.rgoal = 0;
         }
       }
       this.goalcheck();
    },
    black(row){
      this.rowlist = row;
    },
    pickmvp(row1,row2){
      this.rowlist = row1.concat(row2);
    },
    choicemvp(un, choice) {
      // mvp 선정
      this.mvp = choice
      this.mvplist = un
    },
    inputassist(sc, row) {
      // 어시스트 삽입
     row.assist = sc;
    },
    inputblack(bl) {
      this.wbl = bl
      // 블랙리스트 신고를 위해 삽입
    },
    blackpoint(wbl) {
      // 블랙리스트로 선정하여 제출하기 전에 정보 갱신
      if (this.dupoint.includes(this.rowlist.uid)) {
        this.wbl="";
        this.dupli = true;
      }
      else {
        if (wbl != "") {
          if (this.rowlist.blacklist == null){
          this.rowlist.blacklist = 0;
          }
          this.rowlist.blacklist += 1;
          this.dupoint.push(this.rowlist.uid);
          this.wbl="";
         }
       for (var a=0; a<this.RedtableDatas.length; a++) {
         if (this.RedtableDatas[a].uid == (this.rowlist.uid)) {
           this.RedtableDatas[a].blacklist += 1;
         }
         else if (this.BluetableDatas[a].uid == (this.rowlist.uid)){
           this.BluetableDatas[a].blacklist += 1;
         }  
      }
      }
    },
    mvppoint() {
      // mvp를 선정해서 제출하기 전에 정보 갱신
        if (this.dumvp.includes(this.mvplist.uid)) {
        this.dupli = true
        }
        else {
          this.mvplist.mvp = 0;
          this.mvplist.mvp += 1;
          if (this.dumvp.length != 0){
            this.pastuid.push(this.dumvp[0].uid)
            this.dumvp.pop(0)
          }
          this.dumvp.push(this.mvplist.uid); 
        }
        for (var a=0; a<this.RedtableDatas.length; a++){
          if (this.pastuid.length != 0){
            if (this.RedtableDatas[a].uid == this.pastuid.uid) {
              this.RedtableDatas[a].mvp -= 1
              this.pastuid.pop(0)
            }
          }
            if (this.RedtableDatas[a].uid == this.mvplist.uid) {
              this.RedtableDatas[a].mvp += 1
            }
        }
          for (a=0; a<this.BluetableDatas.length; a++){
          if (this.pastuid.length != 0){
            if (this.BluetableDatas[a].uid == this.pastuid.uid) {
              this.BluetableDatas[a].mvp -= 1
              this.pastuid.pop(0)
            }
          }
            if (this.BluetableDatas[a].uid == this.mvplist.uid) {
              this.BluetableDatas[a].mvp += 1
            }
         
        } 
        this.ismvp = true;
    },
    RedTeamList() {
      // 레드팀을 불러오기
      const Team_entry_uid = new FormData();
      Team_entry_uid.append(
        "team_entry_uid",
        this.RoomData.home_matching_entry_uid
      );
      // 비동기 요청을 통해 레드팀 리스트를 불러옴
      this.$axios
        .post(this.$SERVER_URL + "FreeMatchRoom/entrylist/", Team_entry_uid)
        .then((res) => {
         
          this.posRedList.push(res.data.defender1_uid);
          this.posRedList.push(res.data.defender2_uid);
          this.posRedList.push(res.data.defender3_uid);
          this.posRedList.push(res.data.defender4_uid);
          this.posRedList.push(res.data.goalkeeper_uid);
          this.posRedList.push(res.data.midfielder1_uid);
          this.posRedList.push(res.data.midfielder2_uid);
          this.posRedList.push(res.data.midfielder3_uid);
          this.posRedList.push(res.data.midfielder4_uid);
          this.posRedList.push(res.data.striker1_uid);
          this.posRedList.push(res.data.striker2_uid);
          this.posRedList.push(res.data.striker3_uid);
          this.posRedList.push(res.data.striker4_uid);
          this.RedpostionList = [];
          var Redsub = new Object
          Redsub.name = "랜덤"
          this.RedpostionList.push(Redsub)
          for(var i=0; i < this.posRedList.length; i++) { 
              
            if (this.posRedList[i] != 0) {
              this.RedTeamUser(this.posRedList[i], this.posNameList[i])
            } 
          }
        })
      
    },
    RedTeamUser(uid) {
      // 레드팀 유저 정보를 갱신
      const usid = new FormData()
      usid.append('uid', uid)
      this.$axios.post(this.$SERVER_URL + 'user/detail2/', usid)
        .then(res => {
          var Redsub = new Object
          Redsub.uid = res.data.uid
          Redsub.goal = 0
          Redsub.assist = 0
          Redsub.mvp = res.data.mvp
          Redsub.blacklist = res.data.blacklist
          Redsub.name = res.data.nickname
          this.RedtableDatas.push(Redsub)
        })
      
    },
    
    BlueTeamList() {
      // 마찬가지로 블루팀 정보를 위해
      const Team_entry_uid = new FormData();
      Team_entry_uid.append(
        "team_entry_uid",
        this.RoomData.away_matching_entry_uid
      );
      this.$axios
        .post(this.$SERVER_URL + "FreeMatchRoom/entrylist/", Team_entry_uid)
        .then((res) => {
       
          this.posBlueList.push(res.data.defender1_uid);
          this.posBlueList.push(res.data.defender2_uid);
          this.posBlueList.push(res.data.defender3_uid);
          this.posBlueList.push(res.data.defender4_uid);
          this.posBlueList.push(res.data.goalkeeper_uid);
          this.posBlueList.push(res.data.midfielder1_uid);
          this.posBlueList.push(res.data.midfielder2_uid);
          this.posBlueList.push(res.data.midfielder3_uid);
          this.posBlueList.push(res.data.midfielder4_uid);
          this.posBlueList.push(res.data.striker1_uid);
          this.posBlueList.push(res.data.striker2_uid);
          this.posBlueList.push(res.data.striker3_uid);
          this.posBlueList.push(res.data.striker4_uid);
          this.BluepostionList = [];
          var Bluesub = new Object
          Bluesub.name = "랜덤"
          this.BluepostionList.push(Bluesub)
          for(var i=0; i < this.posBlueList.length; i++) { 
  
            if (this.posBlueList[i] != 0) {
              this.BlueTeamUser(this.posBlueList[i], this.posNameList[i])
            } 
          }
        })
   
    },
    BlueTeamUser(uid) {
  //  블루팀 정보를 갱신
      const usid = new FormData()
      usid.append('uid', uid)
      this.$axios.post(this.$SERVER_URL + 'user/detail2/', usid)
        .then(res => {
          var Bluesub = new Object
          Bluesub.uid = res.data.uid
          Bluesub.goal = 0
          Bluesub.assist = 0
          Bluesub.mvp = res.data.mvp
          Bluesub.blacklist = res.data.blacklist
          Bluesub.name = res.data.nickname
          this.BluetableDatas.push(Bluesub)
          if (res.data.nickname == this.isMine) {
            this.isEnter = true
          }
        })
    
    },
    goalcheck() {
      // 넣은 골확인
      for (var a=0; a<this.RedtableDatas.length; a++){
        this.rgoal += this.RedtableDatas[a].goal
        this.bgoal += this.BluetableDatas[a].goal
        this.wincheck(this.rgoal, this.bgoal)
      }
    },
    wincheck(r,b) {
      // 승리팀 확인
      if (r > b) {
        this.winteam = "레드팀 승리"
        this.homewin = 3;
      }
      else if (r < b) {
        this.winteam = "블루팀 승리"
        this.homewin = 0;
      }
      else {
        this.winteam = "무승부"
        this.homewin = 1;
      }
    },
    submit() {
      // 여태까지 갱신한 정보를 모두 백엔드로 보내기 위한 작업
      if (this.ismvp == true){
      const FreeRoomData = new FormData();
      FreeRoomData.append("uid", this.$route.params.uid);
      this.$axios
      .post(this.$SERVER_URL + "FreeMatchRoom/", FreeRoomData)
      .then((res) => {
       const MatchRoomData = new FormData();
       MatchRoomData.append("uid", res.data[0].uid);
       MatchRoomData.append("head_uid", res.data[0].head_uid);
       MatchRoomData.append("home_matching_entry_uid", res.data[0].home_matching_entry_uid);
       MatchRoomData.append("away_matching_entry_uid", res.data[0].away_matching_entry_uid); 
       MatchRoomData.append("create_date", res.data[0].create_date);
       MatchRoomData.append("matching_date", res.data[0].matching_date);
       MatchRoomData.append("home_score", res.data[0].home_score);
       MatchRoomData.append("away_score", res.data[0].away_score);
       MatchRoomData.append("ready_num", res.data[0].ready_num);
       MatchRoomData.append("place_uid", res.data[0].place_uid);
       MatchRoomData.append("price", res.data[0].price);
       MatchRoomData.append("head_price", res.data[0].head_price);
       MatchRoomData.append("dong_code", res.data[0].dong_code);
       MatchRoomData.append("title", res.data[0].title);
       MatchRoomData.append("mvp", res.data[0].mvp);
      // 승점을 데이터베이스에 넣기 위한 작업
        if (this.homewin == 3){
          this.$axios.post(this.$SERVER_URL + "FreeMatch/win", MatchRoomData)
         
        }
        else if (this.homewin == 1){
          this.$axios.post(this.$SERVER_URL + "FreeMatch/draw", MatchRoomData)
         
        }
        else {
          this.$axios.post(this.$SERVER_URL + "FreeMatch/lose", MatchRoomData)
          
        }
        this.$router.push({ name: "SPOTs" });
      })
     
      }
      else {
        this.vote = true
      }
      // MVP 포인트를 넣기 위한 작업
      const MVPdata = new FormData();
      MVPdata.append("uid", this.$route.params.uid);
      MVPdata.append('mvp',1);
      this.$axios.post(this.$SERVER_URL + 'matchEnd/', MVPdata)
        // 레드팈 블루팀 모두 데이터 저장을 위해
       for (var a=0; a<this.RedtableDatas.length; a++) {
        const MatchData = new FormData();
        MatchData.append('uid', this.RedtableDatas[a].uid)
        MatchData.append('goal', this.RedtableDatas[a].goal)
        MatchData.append('assist', this.RedtableDatas[a].assist)
        MatchData.append('mvp', this.RedtableDatas[a].mvp)
        MatchData.append('blacklist', this.RedtableDatas[a].blacklist)
         this.$axios.post(this.$SERVER_URL + "FreeMatchRoom/updateuser", MatchData)
        }
        for (a=0; a<this.BluetableDatas.length; a++) {
        const MatchData = new FormData();  
        MatchData.append('uid', this.BluetableDatas[a].uid)
        MatchData.append('goal', this.BluetableDatas[a].goal)
        MatchData.append('assist', this.BluetableDatas[a].assist)
        MatchData.append('mvp', this.BluetableDatas[a].mvp)
        MatchData.append('blacklist', this.BluetableDatas[a].blacklist)
         this.$axios.post(this.$SERVER_URL + "FreeMatchRoom/updateuser", MatchData)
        }
       
    },
  },
  created() {
    const FreeRoomData = new FormData();
    FreeRoomData.append("uid", this.$route.params.uid);
    this.$axios
      .post(this.$SERVER_URL + "FreeMatchRoom/", FreeRoomData)
      .then((res) => {
        this.manageruid = res.data[0].manager_uid
        // 문제 있을시 메인페이지로
        if (res.data == "") {
          this.problem = true;
          this.$router.push({ name: "SPOTs" });
        } else {
          // 메니저 불러오기
          this.RoomData = res.data[0];
           var managerform = new FormData()
            managerform.append('uid', res.data[0].manager_uid)
            this.$axios.post(this.$SERVER_URL + "user/detail2/", managerform)
              .then(res => {
                this.Manager = res.data
                if (res.data.uid == this.$cookies.get('UserInfo').uid) {
                  this.isManager = true
                }
              })
              
          var kuid = this.$cookies.get("UserInfo").uid
          if (res.data[0].head_uid == kuid) {
            this.isHeader = true
          }
      
          this.RedtableDatas = [];
          this.RedTeamList();
       
          this.BluetableDatas = [];
          this.BlueTeamList();

        }
        // 쿠키를 통해 정보를 확인
      if (this.$cookies.isKey("UserInfo")) {
        this.isLogined = true;
        this.isMine = this.$cookies.get("UserInfo").nickname;
        
    } 
      })
      .catch(() => {
        this.problem = true
        this.$router.push({ name: "SPOTs" });
      });

  },
};
</script>
<style>

</style>