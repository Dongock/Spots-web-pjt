# :eight_pointed_black_star: 프로젝트 이름 : SPOTs



## :busts_in_silhouette: 팀원소개

##### :man: 정진권(팀장/Frontend) : Front 디자인, 모임 대기방, 팀 정보, 결제시스템, 팀 프로필, 팀 참여 팝업, 로그인, 회원가입 담당

##### :man: 이동옥(Frontend) : Front 디자인, 메인 페이지, 매니저 평가 페이지, 개인 프로필, 랭킹 페이지, 경기장 정보 페이지, 모임 참여 팝업 담당

##### :man: 오정엽(backend) : 데이터베이스, 팀 정보, 모임 대기방, 결제 시스템 담당

##### :man: 최현민(backend) : 메인페이지, 개인 정보, 서버배포 담당

##### :man: 서민규(backend) : 평가 페이지, 랭킹 페이지 담당 



## :book: 프로젝트 소개​

- 축구는 11명이서 하는 게임인데 나는 나 혼자일 때....

- 더 이상 피파, 위닝이 아니라 몸으로 축구 뛰고 싶다!

- 축구는 단체게임이지만 할 사람이 적거나 혼자인 사람들을 위한 페이지

- SPOTs를 통해 정해진 날짜와 장소에서 축구 모임 만들거나 가입해서

  축구도 하고 랭킹도 올리자!

- 마음 맞는 사람들이 있다면 팀을 만들수도 있는 시스템!
- 카카오 페이 qr코드 결제 시스템을 이용해 쉽게 결제하고 모임 참여하자!\
- 경기 후 매니저 평가를 통해 MVP도 선정되어 랭킹도 오르고 문제 있는 사람은 블랙리스트로 신고!

- 팀에 들어가고 싶다면 팀 정보를 확인하여 팀에 참가하거나 지인의 팀 참여!
- 개인 랭킹 뿐만 아니라 팀 랭킹도 구성되어 있어 소속감도 얻을 수 있다!



## 💻 스택

![Generic badge](https://img.shields.io/badge/platform-Web-brightgreen.svg) ![Generic badge](https://img.shields.io/badge/library-vue-blue.svg) ![Generic badge](https://img.shields.io/badge/framework-spring-green.svg)
![Generic badge](https://img.shields.io/badge/database-MySQL-yellow.svg) ![Generic badge](https://img.shields.io/badge/server-AWS-9cf.svg) ![Generic badge](https://img.shields.io/badge/language-Java,JavaScript-important.svg)



## :game_die: 이용 방법

### IDE

```
VScode
STS
```

### Clone

```
git clone https://github.com/Dongock/Spots-web-pjt.git
```

### Frontend

```
$yarn install
$yarn serve --port 3000
```



## :1st_place_medal: 기획

#### 와이어 프레임

<http://github.com/Dongock/Spots-web-pjt/blob/master/wireframe.pdf>



## :closed_book: 페이지 별 서비스 설명

#### 1. 메인 페이지(대기방 확인)

- 검색 기능 (도, 시, 동과 제목을 입력하여 검색)
- 페이지네이션(5개별로 페이지 나눔)
- 비동기 요청으로 방이 가득차면 바로 반영
- 경기가 끝난 방의 경우 자동으로 반영되어 사라짐

#### 2. 매칭 대기 룸(개인, 팀)

- 카카오페이 QR코드 결제 시스템
- 팀, 포지션 변경

#### 3. 평가 페이지

- MVP 선정 및 블랙리스트 신고 가능
- 평가 완료 시 결과 바로 반영

#### 4. 매칭 만들기

- 주소 및 날짜 선택하여 방 만들기

#### 5. 팀 만들기

- 현재 팀 없을시 기본 정보 값 입력하여 팀 만들기

#### 6. 팀 가입하기

- 팀 정보 확인 후 가입한 팀이 없다면 가입 가능(팀장에게 신청)

#### 7. 경기장 및 랭킹 페이지

- 사용 가능한 경기장 목록 확인 및 나의 개인 랭킹과 팀 랭킹 확인 가능

#### 8. 개인 및 팀 프로필

- 개인 프로필 확인 가능 / 팀 프로필 확인 가능
- 비밀번호 변경 가능
- 개인 스탯 확인 가능
- 팀장의 경우 팀원 신청 받기 가능

#### 9. 회원가입/로그인

- 회원가입 시 이메일 인증을 통해 회원가입 가능



## :file_folder: 폴더구조

### FrontEnd

```
📦frontend
 ┣ 📂.github
 ┃ ┗ 📂workflows
 ┃ ┃ ┗ 📜main.yml
 ┣ 📂node_modules
 ┃ ┣ 📂.bin
 ┃ ┃ ┣ 📜acorn
 ┃ ┃ ┣ 📜acorn.cmd
 ┃ ┃ ┣ 📜ansi-html
 ┃ ┃ ┣ 📜ansi-html.cmd
 ┃ ┃ ┣ 📜atob
 ┃ ┃ ┣ 📜atob.cmd
 ┃ ┃ ┣ 📜autoprefixer
 ┃ ┃ ┣ 📜autoprefixer.cmd
 ┃ ┃ ┣ 📜babylon
 ┃ ┃ ┣ 📜babylon.cmd
 ┃ ┃ ┣ 📜browserslist
 ┃ ┃ ┣ 📜browserslist.cmd
 ┃ ┃ ┣ 📜cssesc
 ┃ ┃ ┣ 📜cssesc.cmd
 ┃ ┃ ┣ 📜errno
 ┃ ┃ ┣ 📜errno.cmd
 ┃ ┃ ┣ 📜eslint
 ┃ ┃ ┣ 📜eslint.cmd
 ┃ ┃ ┣ 📜esparse
 ┃ ┃ ┣ 📜esparse.cmd
 ┃ ┃ ┣ 📜esvalidate
 ┃ ┃ ┣ 📜esvalidate.cmd
 ┃ ┃ ┣ 📜he
 ┃ ┃ ┣ 📜he.cmd
 ┃ ┃ ┣ 📜highlight
 ┃ ┃ ┣ 📜highlight.cmd
 ┃ ┃ ┣ 📜html-minifier
 ┃ ┃ ┣ 📜html-minifier.cmd
 ┃ ┃ ┣ 📜import-local-fixture
 ┃ ┃ ┣ 📜import-local-fixture.cmd
 ┃ ┃ ┣ 📜in-install
 ┃ ┃ ┣ 📜in-install.cmd
 ┃ ┃ ┣ 📜in-publish
 ┃ ┃ ┣ 📜in-publish.cmd
 ┃ ┃ ┣ 📜is-ci
 ┃ ┃ ┣ 📜is-ci.cmd
 ┃ ┃ ┣ 📜js-yaml
 ┃ ┃ ┣ 📜js-yaml.cmd
 ┃ ┃ ┣ 📜jsesc
 ┃ ┃ ┣ 📜jsesc.cmd
 ┃ ┃ ┣ 📜json5
 ┃ ┃ ┣ 📜json5.cmd
 ┃ ┃ ┣ 📜loose-envify
 ┃ ┃ ┣ 📜loose-envify.cmd
 ┃ ┃ ┣ 📜miller-rabin
 ┃ ┃ ┣ 📜miller-rabin.cmd
 ┃ ┃ ┣ 📜mime
 ┃ ┃ ┣ 📜mime.cmd
 ┃ ┃ ┣ 📜mkdirp
 ┃ ┃ ┣ 📜mkdirp.cmd
 ┃ ┃ ┣ 📜multicast-dns
 ┃ ┃ ┣ 📜multicast-dns.cmd
 ┃ ┃ ┣ 📜node-gyp
 ┃ ┃ ┣ 📜node-gyp.cmd
 ┃ ┃ ┣ 📜node-sass
 ┃ ┃ ┣ 📜node-sass.cmd
 ┃ ┃ ┣ 📜node-which
 ┃ ┃ ┣ 📜node-which.cmd
 ┃ ┃ ┣ 📜nopt
 ┃ ┃ ┣ 📜nopt.cmd
 ┃ ┃ ┣ 📜not-in-install
 ┃ ┃ ┣ 📜not-in-install.cmd
 ┃ ┃ ┣ 📜not-in-publish
 ┃ ┃ ┣ 📜not-in-publish.cmd
 ┃ ┃ ┣ 📜opencollective
 ┃ ┃ ┣ 📜opencollective.cmd
 ┃ ┃ ┣ 📜opener
 ┃ ┃ ┣ 📜opener.cmd
 ┃ ┃ ┣ 📜parser
 ┃ ┃ ┣ 📜parser.cmd
 ┃ ┃ ┣ 📜prettier
 ┃ ┃ ┣ 📜prettier.cmd
 ┃ ┃ ┣ 📜regjsparser
 ┃ ┃ ┣ 📜regjsparser.cmd
 ┃ ┃ ┣ 📜rimraf
 ┃ ┃ ┣ 📜rimraf.cmd
 ┃ ┃ ┣ 📜sassgraph
 ┃ ┃ ┣ 📜sassgraph.cmd
 ┃ ┃ ┣ 📜semver
 ┃ ┃ ┣ 📜semver.cmd
 ┃ ┃ ┣ 📜sha.js
 ┃ ┃ ┣ 📜sha.js.cmd
 ┃ ┃ ┣ 📜sshpk-conv
 ┃ ┃ ┣ 📜sshpk-conv.cmd
 ┃ ┃ ┣ 📜sshpk-sign
 ┃ ┃ ┣ 📜sshpk-sign.cmd
 ┃ ┃ ┣ 📜sshpk-verify
 ┃ ┃ ┣ 📜sshpk-verify.cmd
 ┃ ┃ ┣ 📜strip-indent
 ┃ ┃ ┣ 📜strip-indent.cmd
 ┃ ┃ ┣ 📜svgo
 ┃ ┃ ┣ 📜svgo.cmd
 ┃ ┃ ┣ 📜terser
 ┃ ┃ ┣ 📜terser.cmd
 ┃ ┃ ┣ 📜uglifyjs
 ┃ ┃ ┣ 📜uglifyjs.cmd
 ┃ ┃ ┣ 📜uuid
 ┃ ┃ ┣ 📜uuid.cmd
 ┃ ┃ ┣ 📜vue-cli-service
 ┃ ┃ ┣ 📜vue-cli-service.cmd
 ┃ ┃ ┣ 📜webpack
 ┃ ┃ ┣ 📜webpack-bundle-analyzer
 ┃ ┃ ┣ 📜webpack-bundle-analyzer.cmd
 ┃ ┃ ┣ 📜webpack-dev-server
 ┃ ┃ ┣ 📜webpack-dev-server.cmd
 ┃ ┃ ┗ 📜webpack.cmd
 ┃ ┃ ┃
 ┃ ┣ 📂@babel
 ┃ ┃ ┣ 📂code-frame
 ┃ ┃ ┃ ┣ 📂lib
 ┃ ┃ ┃ ┃ ┗ 📜index.js
 ┃ ┃ ┃ ┣ 📜LICENSE
 ┃ ┃ ┃ ┣ 📜package.json
 ┃ ┃ ┃ ┗ 📜README.md
 ┃ ┃ ┗ 📂compat-data
 ┃ ┃ ┃ ┣ 📂data
 ┃ ┃ ┃ ┃ ┣ 📜corejs2-built-ins.json
 ┃ ┃ ┃ ┃ ┣ 📜corejs3-shipped-proposals.json
 ┃ ┃ ┃ ┃ ┣ 📜native-modules.json
 ┃ ┃ ┃ ┃ ┣ 📜overlapping-plugins.json
 ┃ ┃ ┃ ┃ ┣ 📜plugin-bugfixes.json
 ┃ ┃ ┃ ┃ ┗ 📜plugins.json
 ┃ ┃ ┃ ┣ 📂node_modules
 ┃ ┃ ┃ ┃ ┣ 📂.bin
 ┃ ┃ ┃ ┃ ┃ ┣ 📜browserslist
 ┃ ┃ ┃ ┃ ┃ ┣ 📜browserslist.cmd
 ┃ ┃ ┃ ┃ ┃ ┣ 📜semver
 ┃ ┃ ┃ ┃ ┃ ┗ 📜semver.cmd
 ┃ ┃ ┃ ┃ ┣ 📂browserslist
 ┃ ┃ ┃ ┃ ┃ ┣ 📜browser.js
 ┃ ┃ ┃ ┃ ┃ ┣ 📜CHANGELOG.md
 ┃ ┃ ┃ ┃ ┃ ┣ 📜cli.js
 ┃ ┃ ┃ ┃ ┃ ┣ 📜error.js
 ┃ ┃ ┃ ┃ ┃ ┣ 📜index.js
 ┃ ┃ ┃ ┃ ┃ ┣ 📜LICENSE
 ┃ ┃ ┃ ┃ ┃ ┣ 📜node.js
 ┃ ┃ ┃ ┃ ┃ ┣ 📜package.json
 ┃ ┃ ┃ ┃ ┃ ┣ 📜README.md
 ┃ ┃ ┃ ┃ ┃ ┗ 📜update-db.js
 ┃ ┃ ┃ ┃ ┗ 📂caniuse-lite
 ┃ ┃ ┃ ┃ ┃ ┣ 📂data
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📂features
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜aac.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜abortcontroller.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜ac3-ec3.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜accelerometer.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜addeventlistener.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜alternate-stylesheet.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜ambient-light.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜apng.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜array-find-index.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜array-find.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜array-flat.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜array-includes.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜arrow-functions.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜asmjs.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜async-clipboard.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜async-functions.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜async-iterations-and-generators.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜atob-btoa.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜audio-api.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜audio.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜audiotracks.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜autofocus.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜aux-click.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜auxclick.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜av1.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜avif.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜background-attachment.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜background-clip-text.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜background-img-opts.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜background-position-x-y.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜background-repeat-round-space.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜background-sync.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜battery-status.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜beacon.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜beforeafterprint.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜bigint.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜blobbuilder.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜bloburls.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜border-image.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜border-radius.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜broadcastchannel.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜brotli.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜calc.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜canvas-blending.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜canvas-text.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜canvas.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜ch-unit.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜chacha20-poly1305.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜channel-messaging.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜childnode-remove.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜classlist.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜clear-site-data-header.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜client-hints-dpr-width-viewport.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜clipboard.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜comparedocumentposition.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜console-basic.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜console-time.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜agents.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜browsers.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜browserVersions.js
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜features.js
 ┃ ┃ ┃ ┃ ┃ ┣ 📜CHANGELOG.md
 ┃ ┃ ┃ ┃ ┃ ┣ 📜LICENSE
 ┃ ┃ ┃ ┃ ┃ ┣ 📜package.json
 ┃ ┃ ┃ ┃ ┃ ┗ 📜README.md
 ┃ ┃ ┃ ┣ 📜corejs2-built-ins.js
 ┃ ┃ ┃ ┣ 📜corejs3-shipped-proposals.js
 ┃ ┃ ┃ ┣ 📜LICENSE
 ┃ ┃ ┃ ┣ 📜native-modules.js
 ┃ ┃ ┃ ┣ 📜overlapping-plugins.js
 ┃ ┃ ┃ ┣ 📜package.json
 ┃ ┃ ┃ ┣ 📜plugin-bugfixes.js
 ┃ ┃ ┃ ┗ 📜plugins.js
 ┃ ┗ 📜.yarn-integrity
 ┣ 📂public
 ┃ ┣ 📂img
 ┃ ┃ ┣ 📂background
 ┃ ┃ ┃ ┗ 📜goal.jpg
 ┃ ┃ ┣ 📂brand
 ┃ ┃ ┃ ┣ 📂SPOTs
 ┃ ┃ ┃ ┃ ┣ 📜SPOTs_dark.jpg
 ┃ ┃ ┃ ┃ ┣ 📜SPOTs_dark_log.jpg
 ┃ ┃ ┃ ┃ ┣ 📜SPOTs_white.jpg
 ┃ ┃ ┃ ┃ ┗ 📜SPOTs_white.png
 ┃ ┃ ┃ ┣ 📜favicon.png
 ┃ ┃ ┃ ┣ 📜green.png
 ┃ ┃ ┃ ┗ 📜white.png
 ┃ ┃ ┣ 📂font
 ┃ ┃ ┃ ┣ 📜DoHyeon-Regular.ttf
 ┃ ┃ ┃ ┗ 📜Jua-Regular.ttf
 ┃ ┃ ┣ 📂icons
 ┃ ┃ ┃ ┣ 📂common
 ┃ ┃ ┃ ┃ ┣ 📜github.svg
 ┃ ┃ ┃ ┃ ┣ 📜google.svg
 ┃ ┃ ┃ ┃ ┣ 📜kakao.svg
 ┃ ┃ ┃ ┃ ┗ 📜kakao_login_medium.png
 ┃ ┃ ┃ ┣ 📜android-chrome-192x192.png
 ┃ ┃ ┃ ┣ 📜android-chrome-512x512.png
 ┃ ┃ ┃ ┣ 📜android-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜android-icon-192x192.png
 ┃ ┃ ┃ ┣ 📜android-icon-36x36.png
 ┃ ┃ ┃ ┣ 📜android-icon-48x48.png
 ┃ ┃ ┃ ┣ 📜android-icon-72x72.png
 ┃ ┃ ┃ ┣ 📜android-icon-96x96.png
 ┃ ┃ ┃ ┣ 📜apple-icon-114x114.png
 ┃ ┃ ┃ ┣ 📜apple-icon-120x120.png
 ┃ ┃ ┃ ┣ 📜apple-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜apple-icon-152x152.png
 ┃ ┃ ┃ ┣ 📜apple-icon-180x180.png
 ┃ ┃ ┃ ┣ 📜apple-icon-57x57.png
 ┃ ┃ ┃ ┣ 📜apple-icon-60x60.png
 ┃ ┃ ┃ ┣ 📜apple-icon-72x72.png
 ┃ ┃ ┃ ┣ 📜apple-icon-76x76.png
 ┃ ┃ ┃ ┣ 📜apple-icon-precomposed.png
 ┃ ┃ ┃ ┣ 📜apple-icon.png
 ┃ ┃ ┃ ┣ 📜apple-touch-icon-120x120.png
 ┃ ┃ ┃ ┣ 📜apple-touch-icon-152x152.png
 ┃ ┃ ┃ ┣ 📜apple-touch-icon-180x180.png
 ┃ ┃ ┃ ┣ 📜apple-touch-icon-60x60.png
 ┃ ┃ ┃ ┣ 📜apple-touch-icon-76x76.png
 ┃ ┃ ┃ ┣ 📜apple-touch-icon.png
 ┃ ┃ ┃ ┣ 📜browserconfig.xml
 ┃ ┃ ┃ ┣ 📜favicon-16x16.png
 ┃ ┃ ┃ ┣ 📜favicon-32x32.png
 ┃ ┃ ┃ ┣ 📜favicon-96x96.png
 ┃ ┃ ┃ ┣ 📜manifest.json
 ┃ ┃ ┃ ┣ 📜ms-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜ms-icon-150x150.png
 ┃ ┃ ┃ ┣ 📜ms-icon-310x310.png
 ┃ ┃ ┃ ┣ 📜ms-icon-70x70.png
 ┃ ┃ ┃ ┣ 📜msapplication-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜mstile-150x150.png
 ┃ ┃ ┃ ┣ 📜safari-pinned-tab.svg
 ┃ ┃ ┃ ┗ 📜SPOTs_Logo.png
 ┃ ┃ ┣ 📂img
 ┃ ┃ ┃ ┣ 📜계남근린공원 인조잔디 축구장.jpg
 ┃ ┃ ┃ ┣ 📜고척근린공원 운동장.jpg
 ┃ ┃ ┃ ┣ 📜고척스카이돔 야외 축구장.jpg
 ┃ ┃ ┃ ┣ 📜광나루축구장.jpg
 ┃ ┃ ┃ ┣ 📜광나루한강공원 축구장.jpg
 ┃ ┃ ┃ ┣ 📜노들나루공원 인조잔디구장.jpg
 ┃ ┃ ┃ ┣ 📜대림운동장 인조잔디구장.jpg
 ┃ ┃ ┃ ┣ 📜독산동 잔디축구장.jpg
 ┃ ┃ ┃ ┣ 📜동명근린공원 인조잔디축구장.jpg
 ┃ ┃ ┃ ┣ 📜반포한강공원.jpg
 ┃ ┃ ┃ ┣ 📜보라매공원.jpg
 ┃ ┃ ┃ ┣ 📜서울시인재개발원 축구장.jpg
 ┃ ┃ ┃ ┣ 📜성보고등학교.jpg
 ┃ ┃ ┃ ┣ 📜송파구 여성축구장.jpg
 ┃ ┃ ┃ ┣ 📜송파구시각장애인축구장.jpg
 ┃ ┃ ┃ ┣ 📜안양천체육생태공원.jpg
 ┃ ┃ ┃ ┣ 📜양재근린공원 축구장.jpg
 ┃ ┃ ┃ ┣ 📜양화한강공원.jpg
 ┃ ┃ ┃ ┣ 📜영롱이억새구장, 갈대구장.jpg
 ┃ ┃ ┃ ┣ 📜잠원한강공원.jpg
 ┃ ┃ ┃ ┣ 📜천마공원 축구장.jpg
 ┃ ┃ ┃ ┗ 📜탄천물재생센터축구장.jpg
 ┃ ┃ ┣ 📂SPOTs
 ┃ ┃ ┃ ┣ 📜android-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜android-icon-192x192.png
 ┃ ┃ ┃ ┣ 📜android-icon-36x36.png
 ┃ ┃ ┃ ┣ 📜android-icon-48x48.png
 ┃ ┃ ┃ ┣ 📜android-icon-72x72.png
 ┃ ┃ ┃ ┣ 📜android-icon-96x96.png
 ┃ ┃ ┃ ┣ 📜apple-icon-114x114.png
 ┃ ┃ ┃ ┣ 📜apple-icon-120x120.png
 ┃ ┃ ┃ ┣ 📜apple-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜apple-icon-152x152.png
 ┃ ┃ ┃ ┣ 📜apple-icon-180x180.png
 ┃ ┃ ┃ ┣ 📜apple-icon-57x57.png
 ┃ ┃ ┃ ┣ 📜apple-icon-60x60.png
 ┃ ┃ ┃ ┣ 📜apple-icon-72x72.png
 ┃ ┃ ┃ ┣ 📜apple-icon-76x76.png
 ┃ ┃ ┃ ┣ 📜apple-icon-precomposed.png
 ┃ ┃ ┃ ┣ 📜apple-icon.png
 ┃ ┃ ┃ ┣ 📜browserconfig.xml
 ┃ ┃ ┃ ┣ 📜favicon-16x16.png
 ┃ ┃ ┃ ┣ 📜favicon-32x32.png
 ┃ ┃ ┃ ┣ 📜favicon-96x96.png
 ┃ ┃ ┃ ┣ 📜favicon.ico
 ┃ ┃ ┃ ┣ 📜manifest.json
 ┃ ┃ ┃ ┣ 📜ms-icon-144x144.png
 ┃ ┃ ┃ ┣ 📜ms-icon-150x150.png
 ┃ ┃ ┃ ┣ 📜ms-icon-310x310.png
 ┃ ┃ ┃ ┗ 📜ms-icon-70x70.png
 ┃ ┃ ┣ 📂stadium
 ┃ ┃ ┃ ┣ 📜계남근린공원 인조잔디 축구장.jpg
 ┃ ┃ ┃ ┣ 📜고척근린공원 운동장.jpg
 ┃ ┃ ┃ ┣ 📜고척스카이돔 야외 축구장.jpg
 ┃ ┃ ┃ ┣ 📜광나루축구장.jpg
 ┃ ┃ ┃ ┣ 📜광나루한강공원 축구장.jpg
 ┃ ┃ ┃ ┣ 📜노들나루공원 인조잔디구장.jpg
 ┃ ┃ ┃ ┣ 📜대림운동장 인조잔디구장.jpg
 ┃ ┃ ┃ ┣ 📜독산동 잔디축구장.jpg
 ┃ ┃ ┃ ┣ 📜동명근린공원 인조잔디축구장.jpg
 ┃ ┃ ┃ ┣ 📜반포한강공원.jpg
 ┃ ┃ ┃ ┣ 📜보라매공원.jpg
 ┃ ┃ ┃ ┣ 📜서울시인재개발원 축구장.jpg
 ┃ ┃ ┃ ┣ 📜성보고등학교.jpg
 ┃ ┃ ┃ ┣ 📜송파구 여성축구장.jpg
 ┃ ┃ ┃ ┣ 📜송파구시각장애인축구장.jpg
 ┃ ┃ ┃ ┣ 📜안양천체육생태공원1.jpg
 ┃ ┃ ┃ ┣ 📜안양천체육생태공원2.jpg
 ┃ ┃ ┃ ┣ 📜양재근린공원 축구장.jpg
 ┃ ┃ ┃ ┣ 📜양화한강공원.jpg
 ┃ ┃ ┃ ┣ 📜영롱이억새구장, 갈대구장.jpg
 ┃ ┃ ┃ ┣ 📜잠원한강공원.jpg
 ┃ ┃ ┃ ┣ 📜천마공원 축구장.jpg
 ┃ ┃ ┃ ┗ 📜탄천물재생센터축구장.jpg
 ┃ ┃ ┣ 📂teamLogo
 ┃ ┃ ┃ ┣ 📜club_logo (1).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (10).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (11).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (12).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (13).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (14).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (15).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (16).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (17).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (18).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (19).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (2).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (20).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (21).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (22).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (23).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (24).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (25).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (26).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (27).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (28).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (29).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (3).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (30).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (31).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (32).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (33).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (34).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (35).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (36).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (37).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (38).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (39).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (4).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (40).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (5).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (52).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (53).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (54).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (55).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (56).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (57).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (58).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (59).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (6).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (60).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (61).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (62).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (63).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (64).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (65).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (66).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (67).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (68).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (69).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (7).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (70).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (71).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (72).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (73).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (74).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (75).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (76).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (77).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (78).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (79).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (8).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (80).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (81).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (82).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (83).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (84).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (85).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (86).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (87).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (88).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (89).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (9).jpg
 ┃ ┃ ┃ ┣ 📜club_logo (90).jpg
 ┃ ┃ ┃ ┗ 📜club_logo (91).jpg
 ┃ ┃ ┣ 📂theme
 ┃ ┃ ┃ ┣ 📜angular.jpg
 ┃ ┃ ┃ ┣ 📜bootstrap.jpg
 ┃ ┃ ┃ ┣ 📜loading.gif
 ┃ ┃ ┃ ┣ 📜profile-cover.jpg
 ┃ ┃ ┃ ┣ 📜profile.jpg
 ┃ ┃ ┃ ┣ 📜react.jpg
 ┃ ┃ ┃ ┣ 📜sketch.jpg
 ┃ ┃ ┃ ┣ 📜team-1-800x800.jpg
 ┃ ┃ ┃ ┣ 📜team-2-800x800.jpg
 ┃ ┃ ┃ ┣ 📜team-3-800x800.jpg
 ┃ ┃ ┃ ┣ 📜team-4-800x800.jpg
 ┃ ┃ ┃ ┗ 📜vue.jpg
 ┃ ┃ ┗ 📂userLogo
 ┃ ┃ ┃ ┣ 📜1.png
 ┃ ┃ ┃ ┣ 📜10.png
 ┃ ┃ ┃ ┣ 📜11.png
 ┃ ┃ ┃ ┣ 📜12.png
 ┃ ┃ ┃ ┣ 📜13.png
 ┃ ┃ ┃ ┣ 📜14.png
 ┃ ┃ ┃ ┣ 📜15.png
 ┃ ┃ ┃ ┣ 📜16.png
 ┃ ┃ ┃ ┣ 📜17.png
 ┃ ┃ ┃ ┣ 📜18.png
 ┃ ┃ ┃ ┣ 📜19.png
 ┃ ┃ ┃ ┣ 📜2.png
 ┃ ┃ ┃ ┣ 📜20.png
 ┃ ┃ ┃ ┣ 📜21.png
 ┃ ┃ ┃ ┣ 📜22.png
 ┃ ┃ ┃ ┣ 📜23.png
 ┃ ┃ ┃ ┣ 📜24.png
 ┃ ┃ ┃ ┣ 📜3.png
 ┃ ┃ ┃ ┣ 📜4.png
 ┃ ┃ ┃ ┣ 📜5.png
 ┃ ┃ ┃ ┣ 📜6.png
 ┃ ┃ ┃ ┣ 📜7.png
 ┃ ┃ ┃ ┣ 📜8.png
 ┃ ┃ ┃ ┗ 📜9.png
 ┃ ┣ 📜favicon.ico
 ┃ ┣ 📜index.html
 ┃ ┣ 📜manifest.json
 ┃ ┗ 📜robots.txt
 ┣ 📂src
 ┃ ┣ 📂assets
 ┃ ┃ ┣ 📂scss
 ┃ ┃ ┃ ┣ 📂core
 ┃ ┃ ┃ ┃ ┣ 📂alerts
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_alert-dismissible.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_alert.scss
 ┃ ┃ ┃ ┃ ┣ 📂avatars
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_avatar-group.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_avatar.scss
 ┃ ┃ ┃ ┃ ┣ 📂badges
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_badge-circle.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_badge-dot.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_badge.scss
 ┃ ┃ ┃ ┃ ┣ 📂buttons
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_button-brand.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_button-icon.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_button.scss
 ┃ ┃ ┃ ┃ ┣ 📂cards
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_card-animations.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_card-blockquote.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_card-profile.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_card-stats.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_card.scss
 ┃ ┃ ┃ ┃ ┣ 📂charts
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_chart.scss
 ┃ ┃ ┃ ┃ ┣ 📂close
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_close.scss
 ┃ ┃ ┃ ┃ ┣ 📂custom-forms
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_custom-checkbox.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_custom-control.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_custom-form.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_custom-radio.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_custom-toggle.scss
 ┃ ┃ ┃ ┃ ┣ 📂dropdowns
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_dropdown.scss
 ┃ ┃ ┃ ┃ ┣ 📂footers
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_footer.scss
 ┃ ┃ ┃ ┃ ┣ 📂forms
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_form-validation.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_form.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_input-group.scss
 ┃ ┃ ┃ ┃ ┣ 📂headers
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_header.scss
 ┃ ┃ ┃ ┃ ┣ 📂icons
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_icon-shape.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_icon.scss
 ┃ ┃ ┃ ┃ ┣ 📂list-groups
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_list-group.scss
 ┃ ┃ ┃ ┃ ┣ 📂maps
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_map.scss
 ┃ ┃ ┃ ┃ ┣ 📂masks
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_mask.scss
 ┃ ┃ ┃ ┃ ┣ 📂mixins
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_alert.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_background-variant.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_badge.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_buttons.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_forms.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_icon.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_modals.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_popover.scss
 ┃ ┃ ┃ ┃ ┣ 📂modals
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_modal.scss
 ┃ ┃ ┃ ┃ ┣ 📂navbars
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_navbar-collapse.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_navbar-dropdown.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_navbar-search.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_navbar-vertical.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_navbar.scss
 ┃ ┃ ┃ ┃ ┣ 📂navs
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_nav-pills.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_nav.scss
 ┃ ┃ ┃ ┃ ┣ 📂paginations
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_pagination.scss
 ┃ ┃ ┃ ┃ ┣ 📂popovers
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_popover.scss
 ┃ ┃ ┃ ┃ ┣ 📂progresses
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_progress.scss
 ┃ ┃ ┃ ┃ ┣ 📂separators
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_separator.scss
 ┃ ┃ ┃ ┃ ┣ 📂tables
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_table.scss
 ┃ ┃ ┃ ┃ ┣ 📂type
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_article.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_display.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_heading.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_type.scss
 ┃ ┃ ┃ ┃ ┣ 📂utilities
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_backgrounds.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_blurable.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_floating.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_helper.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_image.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_opacity.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_overflow.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_position.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_shadows.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_sizing.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_spacing.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_text.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_transform.scss
 ┃ ┃ ┃ ┃ ┗ 📂vendors
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_flatpickr.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_headroom.scss
 ┃ ┃ ┃ ┃ ┃ ┣ 📜_nouislider.scss
 ┃ ┃ ┃ ┃ ┃ ┗ 📜_scrollbar.scss
 ┃ ┃ ┃ ┣ 📂custom
 ┃ ┃ ┃ ┃ ┣ 📜_alert.scss
 ┃ ┃ ┃ ┃ ┣ 📜_avatar.scss
 ┃ ┃ ┃ ┃ ┣ 📜_badge.scss
 ┃ ┃ ┃ ┃ ┣ 📜_buttons.scss
 ┃ ┃ ┃ ┃ ┣ 📜_card.scss
 ┃ ┃ ┃ ┃ ┣ 📜_chart.scss
 ┃ ┃ ┃ ┃ ┣ 📜_close.scss
 ┃ ┃ ┃ ┃ ┣ 📜_components.scss
 ┃ ┃ ┃ ┃ ┣ 📜_content.scss
 ┃ ┃ ┃ ┃ ┣ 📜_custom-forms.scss
 ┃ ┃ ┃ ┃ ┣ 📜_dropdown.scss
 ┃ ┃ ┃ ┃ ┣ 📜_footer.scss
 ┃ ┃ ┃ ┃ ┣ 📜_forms.scss
 ┃ ┃ ┃ ┃ ┣ 📜_functions.scss
 ┃ ┃ ┃ ┃ ┣ 📜_header.scss
 ┃ ┃ ┃ ┃ ┣ 📜_icons.scss
 ┃ ┃ ┃ ┃ ┣ 📜_input-group.scss
 ┃ ┃ ┃ ┃ ┣ 📜_list-group.scss
 ┃ ┃ ┃ ┃ ┣ 📜_map.scss
 ┃ ┃ ┃ ┃ ┣ 📜_mask.scss
 ┃ ┃ ┃ ┃ ┣ 📜_mixins.scss
 ┃ ┃ ┃ ┃ ┣ 📜_modal.scss
 ┃ ┃ ┃ ┃ ┣ 📜_nav.scss
 ┃ ┃ ┃ ┃ ┣ 📜_navbar.scss
 ┃ ┃ ┃ ┃ ┣ 📜_pagination.scss
 ┃ ┃ ┃ ┃ ┣ 📜_popover.scss
 ┃ ┃ ┃ ┃ ┣ 📜_progress.scss
 ┃ ┃ ┃ ┃ ┣ 📜_reboot.scss
 ┃ ┃ ┃ ┃ ┣ 📜_section.scss
 ┃ ┃ ┃ ┃ ┣ 📜_separator.scss
 ┃ ┃ ┃ ┃ ┣ 📜_tables.scss
 ┃ ┃ ┃ ┃ ┣ 📜_type.scss
 ┃ ┃ ┃ ┃ ┣ 📜_utilities.scss
 ┃ ┃ ┃ ┃ ┣ 📜_variables.scss
 ┃ ┃ ┃ ┃ ┗ 📜_vendors.scss
 ┃ ┃ ┃ ┗ 📜argon.scss
 ┃ ┃ ┣ 📂vendor
 ┃ ┃ ┃ ┗ 📂nucleo
 ┃ ┃ ┃ ┃ ┣ 📂css
 ┃ ┃ ┃ ┃ ┃ ┣ 📜nucleo-svg.css
 ┃ ┃ ┃ ┃ ┃ ┗ 📜nucleo.css
 ┃ ┃ ┃ ┃ ┗ 📂fonts
 ┃ ┃ ┃ ┃ ┃ ┣ 📜nucleo-icons.eot
 ┃ ┃ ┃ ┃ ┃ ┣ 📜nucleo-icons.svg
 ┃ ┃ ┃ ┃ ┃ ┣ 📜nucleo-icons.ttf
 ┃ ┃ ┃ ┃ ┃ ┣ 📜nucleo-icons.woff
 ┃ ┃ ┃ ┃ ┃ ┗ 📜nucleo-icons.woff2
 ┃ ┃ ┗ 📜logo.png
 ┃ ┣ 📂components
 ┃ ┃ ┣ 📂Charts
 ┃ ┃ ┃ ┣ 📜BarChart.js
 ┃ ┃ ┃ ┣ 📜config.js
 ┃ ┃ ┃ ┣ 📜DoughnutChart.js
 ┃ ┃ ┃ ┣ 📜globalOptionsMixin.js
 ┃ ┃ ┃ ┣ 📜LineChart.js
 ┃ ┃ ┃ ┣ 📜optionHelpers.js
 ┃ ┃ ┃ ┗ 📜PieChart.js
 ┃ ┃ ┣ 📂NotificationPlugin
 ┃ ┃ ┃ ┣ 📜index.js
 ┃ ┃ ┃ ┣ 📜Notification.vue
 ┃ ┃ ┃ ┗ 📜Notifications.vue
 ┃ ┃ ┣ 📂SidebarPlugin
 ┃ ┃ ┃ ┣ 📜index.js
 ┃ ┃ ┃ ┣ 📜SideBar.vue
 ┃ ┃ ┃ ┗ 📜SidebarItem.vue
 ┃ ┃ ┣ 📂Tabs
 ┃ ┃ ┃ ┣ 📜PillsLayout.vue
 ┃ ┃ ┃ ┣ 📜Tab.vue
 ┃ ┃ ┃ ┣ 📜TabPane.vue
 ┃ ┃ ┃ ┣ 📜Tabs.vue
 ┃ ┃ ┃ ┗ 📜TabsLayout.vue
 ┃ ┃ ┣ 📜Badge.vue
 ┃ ┃ ┣ 📜BaseAlert.vue
 ┃ ┃ ┣ 📜BaseButton.vue
 ┃ ┃ ┣ 📜BaseCheckbox.vue
 ┃ ┃ ┣ 📜BaseDropdown.vue
 ┃ ┃ ┣ 📜BaseHeader.vue
 ┃ ┃ ┣ 📜BaseInput.vue
 ┃ ┃ ┣ 📜BaseNav.vue
 ┃ ┃ ┣ 📜BasePagination.vue
 ┃ ┃ ┣ 📜BaseProgress.vue
 ┃ ┃ ┣ 📜BaseRadio.vue
 ┃ ┃ ┣ 📜BaseSlider.vue
 ┃ ┃ ┣ 📜BaseSwitch.vue
 ┃ ┃ ┣ 📜BaseTable.vue
 ┃ ┃ ┣ 📜Card.vue
 ┃ ┃ ┣ 📜CloseButton.vue
 ┃ ┃ ┣ 📜Modal.vue
 ┃ ┃ ┣ 📜NavbarToggleButton.vue
 ┃ ┃ ┣ 📜StatsCard.vue
 ┃ ┃ ┗ 📜stringUtils.js
 ┃ ┣ 📂directives
 ┃ ┃ ┗ 📜click-ouside.js
 ┃ ┣ 📂img
 ┃ ┃ ┣ 📜계남근린공원 인조잔디 축구장.jpg
 ┃ ┃ ┣ 📜고척근린공원 운동장.jpg
 ┃ ┃ ┣ 📜고척스카이돔 야외 축구장.jpg
 ┃ ┃ ┣ 📜광나루축구장.jpg
 ┃ ┃ ┣ 📜광나루한강공원 축구장.jpg
 ┃ ┃ ┣ 📜노들나루공원 인조잔디구장.jpg
 ┃ ┃ ┣ 📜대림운동장 인조잔디구장.jpg
 ┃ ┃ ┣ 📜독산동 잔디축구장.jpg
 ┃ ┃ ┣ 📜동명근린공원 인조잔디축구장.jpg
 ┃ ┃ ┣ 📜반포한강공원.jpg
 ┃ ┃ ┣ 📜보라매공원.jpg
 ┃ ┃ ┣ 📜서울시인재개발원 축구장.jpg
 ┃ ┃ ┣ 📜성보고등학교.jpg
 ┃ ┃ ┣ 📜송파구 여성축구장.jpg
 ┃ ┃ ┣ 📜송파구시각장애인축구장.jpg
 ┃ ┃ ┣ 📜안양천체육생태공원.jpg
 ┃ ┃ ┣ 📜양재근린공원 축구장.jpg
 ┃ ┃ ┣ 📜양화한강공원.jpg
 ┃ ┃ ┣ 📜영롱이억새구장, 갈대구장.jpg
 ┃ ┃ ┣ 📜잠원한강공원.jpg
 ┃ ┃ ┣ 📜천마공원 축구장.jpg
 ┃ ┃ ┗ 📜탄천물재생센터축구장.jpg
 ┃ ┣ 📂layout
 ┃ ┃ ┣ 📜AuthLayout.vue
 ┃ ┃ ┣ 📜Content.vue
 ┃ ┃ ┣ 📜ContentFooter.vue
 ┃ ┃ ┣ 📜CreditLayout.vue
 ┃ ┃ ┣ 📜DashboardLayout.vue
 ┃ ┃ ┗ 📜DashboardNavbar.vue
 ┃ ┣ 📂plugins
 ┃ ┃ ┣ 📜argon-dashboard.js
 ┃ ┃ ┣ 📜globalComponents.js
 ┃ ┃ ┗ 📜globalDirectives.js
 ┃ ┣ 📂views
 ┃ ┃ ┣ 📂Dashboard
 ┃ ┃ ┃ ┣ 📜FreeMatchRoom.vue
 ┃ ┃ ┃ ┣ 📜ManagerPage.vue
 ┃ ┃ ┃ ┣ 📜PageVisitsTable.vue
 ┃ ┃ ┃ ┣ 📜SocialTrafficTable.vue
 ┃ ┃ ┃ ┗ 📜TeamMatchRoom.vue
 ┃ ┃ ┣ 📂Tables
 ┃ ┃ ┃ ┣ 📜freeRanking.vue
 ┃ ┃ ┃ ┣ 📜ProjectsTable.vue
 ┃ ┃ ┃ ┣ 📜teamListTable.vue
 ┃ ┃ ┃ ┣ 📜teamRanking.vue
 ┃ ┃ ┃ ┗ 📜TeamTable.vue
 ┃ ┃ ┣ 📜CreditComplete.vue
 ┃ ┃ ┣ 📜Dashboard.vue
 ┃ ┃ ┣ 📜Date.vue
 ┃ ┃ ┣ 📜Login.vue
 ┃ ┃ ┣ 📜Maps.vue
 ┃ ┃ ┣ 📜Register.vue
 ┃ ┃ ┣ 📜Tables.vue
 ┃ ┃ ┣ 📜TeamList.vue
 ┃ ┃ ┣ 📜TeamProfile.vue
 ┃ ┃ ┗ 📜UserProfile.vue
 ┃ ┣ 📜App.vue
 ┃ ┣ 📜main.js
 ┃ ┣ 📜registerServiceWorker.js
 ┃ ┗ 📜router.js
 ┣ 📜.gitignore
 ┣ 📜babel.config.js
 ┣ 📜CHANGELOG.md
 ┣ 📜ISSUES_TEMPLATE.md
 ┣ 📜LICENSE.md
 ┣ 📜package-lock.json
 ┣ 📜package.json
 ┣ 📜README.md
 ┣ 📜vue.config.js
 ┗ 📜yarn.lock
```

### Backend

```
📦backend
 ┣ 📂.settings
 ┃ ┗ 📜org.eclipse.wst.common.project.facet.core.xml
 ┣ 📂gradle
 ┃ ┗ 📂wrapper
 ┃ ┃ ┣ 📜gradle-wrapper.jar
 ┃ ┃ ┗ 📜gradle-wrapper.properties
 ┣ 📂src
 ┃ ┣ 📂main
 ┃ ┃ ┣ 📂java
 ┃ ┃ ┃ ┗ 📂com
 ┃ ┃ ┃ ┃ ┗ 📂spots
 ┃ ┃ ┃ ┃ ┃ ┣ 📂controller
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EntryController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜KakaoPayController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜LoginController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜MatchController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜placeController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜RankController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜sidoController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜teamController.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜userController.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📂dto
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜ApplyTeamInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜DataInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EntryInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜FMatchInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜KakaoPayReadyVO.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜PlaceInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜SidoInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TMatchInfo.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜UserInfo.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📂mapper
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EntryMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜MatchMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜PlaceMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜RankMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜SidoMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamInfoMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamMapper.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜UserMapper.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📂properties
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜Config.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📂service
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EmailService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EmailServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EntryService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜EntryServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜FreeMatchService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜FreeMatchServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜LoginService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜LoginServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜PlaceInfoService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜PlaceInfoServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜RankService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜RankServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜SidoInfoService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜SidoInfoServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamInfoService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamInfoServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamMatchService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜TeamMatchServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┣ 📜UserInfoService.java
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜UserInfoServiceImpl.java
 ┃ ┃ ┃ ┃ ┃ ┣ 📜BackendApplication.java
 ┃ ┃ ┃ ┃ ┃ ┗ 📜ServletInitializer.java
 ┃ ┃ ┗ 📂resources
 ┃ ┃ ┃ ┣ 📂config
 ┃ ┃ ┃ ┃ ┗ 📜mybatis_config.xml
 ┃ ┃ ┃ ┣ 📂mapper
 ┃ ┃ ┃ ┃ ┣ 📜entry_query.xml
 ┃ ┃ ┃ ┃ ┣ 📜Match_query.xml
 ┃ ┃ ┃ ┃ ┣ 📜place_query.xml
 ┃ ┃ ┃ ┃ ┣ 📜rank_query.xml
 ┃ ┃ ┃ ┃ ┣ 📜sido_query.xml
 ┃ ┃ ┃ ┃ ┣ 📜TeamInfo_query.xml
 ┃ ┃ ┃ ┃ ┣ 📜team_query.xml
 ┃ ┃ ┃ ┃ ┗ 📜user_query.xml
 ┃ ┃ ┃ ┣ 📜application.properties
 ┃ ┃ ┃ ┗ 📜mail.properties
 ┃ ┗ 📂test
 ┃ ┃ ┗ 📂java
 ┃ ┃ ┃ ┗ 📂com
 ┃ ┃ ┃ ┃ ┗ 📂spots
 ┃ ┃ ┃ ┃ ┃ ┗ 📜BackendApplicationTests.java
 ┣ 📜.classpath
 ┣ 📜.gitignore
 ┣ 📜.project
 ┣ 📜build.gradle
 ┣ 📜gradlew
 ┣ 📜gradlew.bat
 ┗ 📜settings.gradle
```



## :calendar: 개발일정

<https://github.com/Dongock/Spots-web-pjt/blob/master/image-20200907162444693.png>