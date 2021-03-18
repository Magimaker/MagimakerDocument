---
description: 메시지 프로토콜 종류에 따라 필요한 메시지의 내용을 구현
---

# MakePacket

## 설명

PacketProc 파일에서 메시지를 처리할 때 담을 메시지의 내용을 구현하는 파일입니다.  
다음과 같은 메시지에 내용을 담아 제공합니다.

1. 헤더 메시지\(헤더에 메시지 프로토콜만 담음\)  
2. 로그인 단계 메시지 \(로그인\)  
3. 대기실 단계 메시지 \(방 생‌성 , 방 목록 불러오기, 방 접속\)  
4. 방 단계 메시지 \(게임 시작, 유저 입장/퇴장\)  
5. 게임 단계 메시지 \(케릭터 정보,  위치, ..\)

## Header & Login Message Functions

| 함수명 | 설명 |
| :--- | :--- |
| MakePacketProtocolMessage | 프로토콜 헤더만 필요한 메시지를 처리 |
| MakePacketLoginSuccess | 로그인 성공시 사용자 정보를 패킷에 추가 |



## Lobby Message Functions

| 함수명 | 설명 |
| :--- | :--- |
| MakePacketRoomCreateSuccess | 생성된 방 번호를 패킷에 추가 |
| MakePacketRoomEnterSuccess | 방 입장시 자신의 슬롯과 내부 유저의 정보를 패킷에 추가 |
| MakePacketRoomList | 방 목록에 대한 정보를을 패킷에 추가 |

## Room Message Functions

| 함수명 | 설명 |
| :--- | :--- |
| MakePacketGameStart | 시작한 방에 있는 유저의 수를 패킷에 추가 |
| MakePacketRoomExitNotice | 퇴장한 유저의 슬롯을 패킷에 추가 |
| MakePacketRoomBroadcast | 방 입장에 성공한 유저의 정보를 패킷에 추가 |

## Game Functions

| 함수명 | 설명 |
| :--- | :--- |
| MakePacketCharacterInfo | 방에 참가한 유저들의 정보와 참가한 인원 수를 패킷에 추가 |
| MakePacketMoveStart | 유저가 이동할 정보를 패킷에 추가 |
| MakePacketMoveStop | 유저가 멈춘 위치를 패킷에 추가 |

