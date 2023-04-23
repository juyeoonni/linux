---
layout : home
---
# Choi Kyeong Min Report 
# TTL

# **네트워킹에서 Time-to-Live(TTL)란?**

time to live(TTL)는 패킷이 라우터에 의해 폐기될 때까지 네트워크 내부에 존재하도록 설정된 시간 또는 "홉"의 양을 나타냅니다. TTL은 또한 CDN 캐싱과 DNS 캐싱 등 다른 컨텍스트에서도 사용됩니다.

# **TTL은 어떻게 작동할까요?**

정보 패킷이 생성되어 인터넷을 통해 전송되면 라우터에서 라우터로 무한정 전달될 위험이 있습니다. 그럴 가능성을 완화하기 위해 패킷은 Time-to-Live(TTL) 또는 홉 제한에 따라 만료되도록 설계되었습니다. 패킷 TTL은 패킷이 유포되는 기간을 결정하는 데 유용할 수 있으며, 보내는 사람은 인터넷을 통해 패킷 경로에 대한 정보를 받을 수 있습니다.

각 패킷에는 네트워크를 통해 얼마나 더 계속 이동해야 하는지를 결정하는 숫자 값을 저장하는 위치가 있습니다. 라우터는 패킷을 수신할 때마다 TTL 수에서 하나를 빼고 네트워크의 다음 위치로 전달합니다. 뺄셈을 한 후 TTL 수가 0이 되면 라우터는 패킷을 폐기하고 ICMP를 원래 호스트로 다시 보냅니다.

일반적으로 사용되는 네트워크 명령 ping 및 traceroute는 모두 TTL을 사용합니다. traceroute 명령을 사용하면 점점 더 높은 순차적 TTL을 가진 패킷 스트림이 인터넷을 통해 대상으로 전송됩니다. 연결의 각 단계는 패킷 중 하나의 종점이므로 각 위치에서는 패킷을 폐기한 후 발신자에게 ICMP 메시지를 반환합니다. 그런 다음 ICMP 메시지가 발신자에게 반환되는 데 걸리는 시간이 네트워크를 따라 각 연속 홉에 도달하는 데 걸리는 시간을 결정하는 데 사용됩니다.

## 참고 정보
### ICMP

- ICMP는 TCP/IP에서 IP 패킷을 처리할 때 발생되는 문제를 알려주는 프로토콜이다.

### CDN

- CDN(콘텐츠 전송 네트워크)은 지리적으로 분산된 여러 개의 서버입니다. 웹 콘텐츠를 사용자와 가까운 곳에서 전송함으로써 전송 속도를 높입니다.
- 전 세계 데이터센터는 파일 복사본을 임시로 저장하는 프로세스인 캐싱을 사용합니다. 따라서 사용자는 가까운 서버를 통해 웹 활성화 디바이스 또는 브라우저에서 인터넷 콘텐츠에 빠르게 접속할 수 있습니다.
- CDN은 웹 페이지, 이미지, 비디오 등의 콘텐츠를 사용자의 물리적 위치와 가까운 프록시 서버에 캐싱합니다. 이렇게 하면 콘텐츠가 로딩될 때까지 기다릴 필요 없이 영화 감상, 소프트웨어 다운로드, 은행 잔고 확인, 소셜 미디어 포스팅, 구매 등의 작업을 할 수 있습니다

### CDN 예시

- 뉴욕에 있는 사용자가 런던에 있는 업체의 웹사이트를 보고 싶어 합니다. 이 웹사이트는 영국의 서버에 호스팅되어 있습니다. 해당 사용자가 뉴욕에서 영국까지 대서양을 가로질러 요청을 보낸다면 웹사이트의 콘텐츠 로딩 시간은 길어질 것입니다. CDN은 이런 문제를 해결하기 위해 런던 웹사이트 콘텐츠를 캐싱해 전 세계 여러 곳의 ‘PoP(Points of Presence)’에 저장합니다. 이러한 PoP는 자체 캐싱 서버를 갖고 있으며 뉴욕에 있는 사용자에게 해당 콘텐츠를 전송합니다.
- 사용자의 물리적 위치와 가장 가까운 서버에서 전송되는 콘텐츠는 더 빠른 고성능 웹 경험을 제공합니다.