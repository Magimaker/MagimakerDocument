---
description: 포탈의 기능을 정의하는 클래스.
---

# CPortal

## 설명 

방을 클리어하고 다음 방으로 넘어가는 포탈의 기능을 정의하는 인터페이스 클래스다. 상속을 받아 OpenNclosePortal\(\)을 구현하고 사용하면 된다.

see also: [CBossRoomPortal](cbossroomportal.md), [CEventRoomPortal](ceventroomportal.md), [CItemEliteRoomPortal](citemeliteroomportal.md), [CNormalRoomPortal](cnormalroomportal.md)

## Properties

| 변수명  | 설명  |
| :--- | :--- |
| PortalAcceptParent | 포탈에 접촉했을  나오는 팝업 |
| FadeController | 포탈을 사용했을 때 나오는 페이드아웃,인 연출을 위한 캔버스 |

## Abstract Method

| 함수명  | 설명  |
| :--- | :--- |
| OpenNClosePortal | 상황에 따라 포탈을 열었다 닫았다 할 수 있는 함수  |

