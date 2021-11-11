# WebRTC

WebRTC(Web Real-Time Communication)은 웹 어플리케이션과 사이트가 중간자 없이 브라우저 간에 오디오나 영상 미디어를 포착하고 마음대로 스트림할 뿐만 아니라 임의의 데이터도 교환할 수 있는 기술이다.

일반적으로 우리가 사용하는 인터넷 네트워크는 방화벽이 존재하며, NAT(Network Address Translation)을 사용하여 서로 다른 네트워크 상의 서버, 호스트 등이 일부 내부 네트워크를 통해 서로 매핑하여 통신하는 방식입니다.

WebRTC는 시그널링(Signaling)이라는 통신 절차를 통해 P2P(Peer to Peer)로 통신하는데, 이 때 방확벽 뒤에 숨은 네트워크에 속한 클라이언트 Private IP들 끼리는 P2P 통신이 불가한 경우가 발생한다. 이 때 STUN 또는 TURN 서버가 필요하다.

**✅ NAT(Network Address Translation)**

IP 패킷의 TCP/UDP 포트 숫자와 소스 및 목적지의 IP 주소 등을 재기록하면서 라우터를 통해 네트워크 트래픽을 주고 받는 기술이다.

이용하는 이유는 보통 사설 네트워크에 속한 여러 개의 호스트가 하나의 공인 IP주소를 사용하여 인터넷에 접속하기 위함이다.

- 인터넷의 공인 IP 주소를 절약할 수 있다.
- 인터넷이라는 공공망과 연결되는 사용자들의 고유한 사설망을 침입자들로부터 보호할 수 있다.

💡 참고 : https://jwprogramming.tistory.com/30

**✅ Signaling**

다른 곳에서 논의한 것처럼 서로 다른 네트워크에 있는 2개의 디바이스들을 서로 위치시키기 위해서는, 각 디바이스들의 위치를 발견하는 방법과 미디어 포맷 협의가 필요하다. 이러한 프로세스를 시그널링이라고 한다.

## STUN(Session Traversal Utilites for NAT)

💡 참고 : https://andonekwon.tistory.com/59

STUN 서버는 UDP 프로토콜 기반으로 동작하며, 클라이언트의 Public IP를 확인하여 시그널링을 수행할 수 있도록 한다.

Signaling Server는 Kurento 미디어 서버가 된다.

NAT환경에서는 Private IP를 별도로 가지고 있기 때문에 Peer to Peer(이하 P2P) 통신이 불가능 하다. 따라서 클라이언트는 자신의 Public IP를 확인하기 위해 STUN 서버로 요청을 보내고 서버로 부터 자신의 Public IP를 받는다. 그래서 이때부터 클라이언트는 자신이 받은 Public IP를 이용하여 시그널링을 할때 받은 그 정보를 이용해서 시그널링을 하게 한다.

다만 STUN으로 모든 걸 해결할 수는 없는데 바로 두 Client가 같은 네트워크에 존재하고 있을 때는 이것으로는 해결이 되지 않는다. 또한, NAT 환경에서는 Symmetirc NAT의 경우는 어플리케이션이 달라지면 NAT의 매핑테이블이 바뀔 수 있기 때문이다.

## TURN (Treversal Using Relays around NAT)

TURN 서버는 클라이언트들이 서로 통신할 때 Public 망에 존재하는 TURN 서버를 경유하도록 하여 미디어 스트리밍을 릴레이하도록 Peer와 Peer가 통신할 수 있도록 해준다.

STUN의 확장 개념이며, 클라이언트가 서로 다른 NAT 또는 방화벽 뒤에 있을 때, NAT 또는 방확벽을 순회하며 클라이언트가 중개 서버를 통해 데이터를 주고 받을 수 있도록 한다.

클라이언트는 자신의 Private IP가 포함된 TURN 메세지를 TURN 서버로 보낸다. 그러면 TURN 서버는 메세지에 포함된 Network Layer IP 주소와 Transport Layer의 UDP 포트 넘버와의 차이를 확인하고 클라이언트의 Public IP로 응답하게 된다. 이때 NAT는 NAT 매핑테이블에 기록되어 있는 정보에 따라서 내부 네트워크에 있는 클라이언트의 Private IP로 메세지를 전송한다.

TURN 서버는 ICE의 일부로 사용될 수 있도록 디자인 되었다.

**✅ ICE(Interactive Connectivity Establishment)**

ICE는 Client가 모든 통신 가능한 주소를 식별하는 것을 의미한다.클라이언트는 STUN 메세지를 TURN 서버로 요청 및 응답 과정에서 다음 3가지의 주소를 확인 하게 된다.

- Relayed Address : TURN 서버가 패킷 릴레이를 위해 할당하는 주소
- Server Reflexive Address : NAT 가 매핑한 클라이언트의 공인망(Public IP, Port)
- Local Address : 클라이언트의 사설주소(Private IP, Port)

따라서, STUN 서버는 Server Reflexive Address 만을 응답하지만 TURN 서버는 Relayed Address와 Server Reflexive Address를 모두 응답한다.

✅ 추가 개념 **Cadidate**

IP와 포트의 조합으로 표시된 주소이다.

3가지 연결을 지원한다.

- Direct Connection : Host 같의 직접적인 미디어 송수신
- Server Reflexive Connection : Server Reflexive Candidate를 이용한 미디어 송수신
- TURN Relay Connection : Relay Candidate를 이용한 미디어 송수신

이렇게 확보된 3개의 주소들의 우선순위를 정하여 SDP내에 포함시켜 전송한다.

Connection을 체크한 후 Connection이 완료되면 RTP 및 RTCP 패킷을 전송하여 통화가 가능하게 된다.

**✅ RTP**

실시간 전송 프로토콜(Real-time Transport Protocol, RTP)은 IP 네트워크 상에서 오디오와 비디오를 전달하기 위한 통신 프로토콜이다.

## STUN 서버와 TURN 서버의 차이점

TURN서버는 STUN서버의 개념을 포함하고 있는 Super Set이며 STUN서버 처럼 단순히 라우팅 테이블을 통해서 private ip와 public ip를 연결하는데에서 그치지 않는다.

WebRTC를 예로 들면 미디어 데이터를 1:1로 보내준다고 했을 때 그 모든 데이터는 TURN 서버를 Relay 서버로 하여 데이터를 원하는 Peer에게 전달해주게 된다.

## Kurento 미디어 서버

WebRTC의 사양이 모두 구현된 WebRTC 미디어 서버와 클라이언트 API를 제공하는 패키지로 WebRTC 화상 어플리케이션의 개발을 가능하게 하는 오픈 소스이다.

<br>

### RTSP

**Real Time Streaming Protocol** : 실시간 멀티미디어 스트림을 제어하기 위한 프로토콜

### VLC

미디어 플레이어

### WSL

**Windows Subsystem for Linux** : Linux용 Windows 하위 시스템

개발자가 기존 가상 머신의 오버헤드 또는 듀얼 부팅 설정 없이 대부분의 명령줄 도구, 유틸리티 및 애플리케이션을 비롯한 GNU/Linux 환경을 수정하지 않고 Windows에서 직접 실행할 수 있다.

<br>

# OpenVidu 연결

공식 문서 : https://docs.openvidu.io/en/2.20.0/deployment/ce/on-premises/

공식 문서를 참고하여 설치 + SSL 인증서 발급(https://certbot.eff.org/)

### 채팅 구현

**joinSession()**

```javascript
// 메세지를 받는 부분(채팅)
      this.session.on('signal:chat', (event) => {
        const eventData = JSON.parse(event.data)
        this.messages.push(eventData)
        console.log('메세지 내용 출력', this.messages)
        if (!this.chatOpen) {
          this.message = 0
          this.messageLength++
        }
        // 스크롤이 자동으로 맞춰서 내려가게 한다
        setTimeout(() => {
          const chatDiv = document.getElementById('chat-div')
          chatDiv.scrollTo({
            top: chatDiv.scrollHeight,
            behavior: 'smooth'
          })
        }, 50)
      })
```

**함수 추가**

```javascript
// 메세지 보내는 함수(채팅)
    sendMessage () {
      const messageData = {
        content: this.message,
        from: this.myUserName
      }
      this.message = ''
      this.session.signal({
        data: JSON.stringify(messageData), // Any string (optional)
        to: [], // Array of Connection objects (optional. Broadcast to everyone if empty)
        type: 'chat' // The type of message (optional)
      })
    },
		// 메세지 알림(숫자)
    CountMessage () {
      this.chatOpen = !this.chatOpen
      if (this.chatOpen === true) {
        this.messageLength = '0'
      }
      console.log(this.chatOpen)
    },
```

**Template**

```html
<div id="chat-div" style="height:300px; overflow:scroll;">
          <v-expansion-panels>
          <v-expansion-panel>
            <v-expansion-panel-header class="font-weight-bold" style="font-size: 20px; height: 60px" @click="CountMessage">
              채팅
              <template v-slot:actions>
                <v-badge
                  color="green"
                  :content="messageLength"
                >
                  <v-icon color="#FFB4B4">
                    fas fa-comment
                  </v-icon>
                </v-badge>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content v-for="(message, i) in messages" :key="i">
              <div v-if="message.from == myUserName" class="my-massage">
                <v-avatar color="brown" size="32">
                  <span class="white--text text-h5">KG</span>
                </v-avatar>
                <span class="font-weight-bold" style="margin: 0px 3px">{{ message.from }}</span>
                <span>{{ message.content }}</span>
              </div>
              <div v-else class="your-massage">
                <v-avatar color="pink" size="32">
                  <span class="white--text text-h5">WH</span>
                </v-avatar>
                <span class="font-weight-bold" style="margin: 0px 3px">{{ message.from }}</span>
                <span>{{ message.content }}</span>
              </div>
            </v-expansion-panel-content>
            <v-expansion-panel-content>
              <div>
                <input style="width: 528px" v-model="message" type="text" placeholder="내용을 입력해주세요.." @keydown.enter="sendMessage">
                <v-icon style="width: 24px">fas fa-location-arrow</v-icon>
              </div>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
        </div>
```

