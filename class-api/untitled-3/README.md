---
description: object pool을 구현해둔 싱글톤 클래스.
---

# CBulletQueue

## 설명 

오브젝트 풀이 필요한 어느 곳에서도 사용할 수 있게 제작한 클래스다. 이 클래스를 사용할 경우 Bullet이라는 이름의 빈 오브젝트를 생성해두면 그 오브젝트를 부모로 삼아 object들이 소환된다.

## Properties

| 변수명. | 설명. |
| :--- | :--- |
| instance | 싱글톤 클래스를 사용하기 위한 변수. |

## Public Method

| 함수명. | 설명. |
| :--- | :--- |
| BulletEnqueue | 오브젝트를 생성, 큐에 삽, Bullet오브젝트의 자식으로 배정, Active상태를 False로 바꾼다. |
| BulletDequeue | 큐에서 오브젝트를 추출, Active 상태 true로 바꿔 리턴한다. |

