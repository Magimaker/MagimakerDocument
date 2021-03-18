---
description: '통신에 필요한 과정을 구현 (소켓, 세션, 패킷 관련)'
---

# network

## 설명

네트워크에 필요한 주요 기능들을 담고있는 파일  
다음과 같은 주요 기능들을 제공한다.  
  
1. 초기화 과정\(주소 초기화, 소켓 연결\) 및 select 동작  
2. 연결된 클라이언트의 세션 추가  
3. 메시지 처리\(클라이언트 세션으로 부터 받은 메시지, 보낼 메시지, 완성된 메시지\)  
4. 패킷 헤더를 확인하여 메시지 분류,  패킷을 받아야 할 인원에 맞춰 보낼 수 있게 처리

## Functions

| 함수명 | 설명 |
| :--- | :--- |
| InitNetwork | 초기 소켓 연결, 넌블로킹 소켓으로 전환 |
| NetworkProcess | 연결된 소켓을 소켓셋에 넣고 select 호출 |
| CallSelect | select 동작 |
| ProcAccept | 소켓을 accept하고 해당 소켓을 세션에 추가 |
| ProcRecv | 세션에 들어간 소켓에 읽을 내용이 있는 경우 호출, 세션의 recvQ로 데이터를 옮김 |
| ProcSend | 세션에 들어간 소켓이 보낼 데이터가 있는 경우 호출, 세션의 sendQ로 데이터를 옮김 |
| CompleteRecvPacket | 완성된 패킷을 Payload에 담아 처리 |
| PacketProc |  패킷 헤더를 확인하여 메시지를 분류하고 처리 |
| SendPacketUnicast | 세션 한 개의 sendQ에 패킷을 넣음 |
| SendPacketBroadcast | 모든 세션의 sendQ에 패킷을 넣음 |
| SendPacketBroadcastInRoom | 지정된 방에 존재하는 세션의 sendQ에 패킷을 넣음 |





