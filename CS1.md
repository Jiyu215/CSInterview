### 🎯브라우저에서 사용자가 URL을 입력하고 엔터를 누른 후, 화면이 렌더링되기까지의 과정을 설명해 주세요. 

#### 키워드
DNS
, TCP handshake
, HTTP 요청/응답
, DOM
, CSSOM
, Render Tree
, Layout (Reflow)
, Paint
, JavaScript의 역할

#### 📢대답
사용자가 URL을 입력하면 DNS를 통해서 도메인을 IP 주소로 변환합니다.

다음으로 TCP 3-way-handshake과정을 통해서 서버와 연결을 맺고, HTTP 요청을 서버에 보내면 서버는 HTML, CSS, JavaScript 파일을 응답합니다.

브라우저는 HTML을 파싱해서 DOM을 생성하고, CSS를 파싱해서 CSSOM을 생성하고, 이 두개를 결합해서 Render Tree를 생성하는데,
이 트리는 실제 화면에 보이는(표시되는) 요소만을 포함합니다.

이후 Layout과정을 통해 각 요소의 크기와 위치를 계산하고,
Paint과정을 통해서 화면에 픽셀 단위로 렌더링합니다.

여기서 JavaScript는 실행되면서 DOM을 동적으로 변경할 수 있으며,
이 과정에서 Layout과 Paint과정이 다시 발생할 수 있습니다.
또한 JavaScript 실행은 HTML 파싱을 중단시킬 수도 있습니다.
