---
description: 방과 포탈을 생성하고 관리하는 싱글톤 클래스
---

# CCreateMap

## 설명 

다음 방을 랜덤으로 만들어내는 클래스. 어떤 방이 나올지 따로 설정이 가능하다. 포탈을 생성하고 관리한다.

## Properties

| 변수명 | 설 |
| :--- | :--- |
| [\_explicitRoomList](_explicitroomlist.md) | 디버그용으로 제작된 방 설정용 변수 |
| instance | 싱글톤 패턴을 이용하기 위한 변수  |

## Public Method

| 함수 | 설 |
| :--- | :--- |
| NotifyPortal | 옵저버 패턴을 위한 방송용 함수 |

