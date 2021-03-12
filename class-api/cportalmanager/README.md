---
description: 포탈의 작동을 관리하는 싱글톤 클래스
---

# CPortalManager

## 설명 

포탈을 사용하여 다음 방으로 넘어가는 일련의 과정을 관리하는 싱글톤 클래스다. 

## Properties

| 변수명. | 설명. |
| :--- | :--- |
| instance | 싱글톤 패턴을 이용하기 위한 변수. |

## Public Method

| 함수명. | 설명. |
| :--- | :--- |
| [MoveToNextRoom](movetonextroom.md) | 다음 방으로 건너갈 때 사용. CFadeInOut을 호출하여 화면을 바꾸고, RefreshWorld\(\)를 호출하여 새로운 방을 만들고 플레이어를 위치시킨다. |

