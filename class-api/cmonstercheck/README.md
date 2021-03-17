---
description: 맵에 남아있는 몬스터 체크용 싱글톤 클래스.
---

# CMonsterCheck

## 설명

클리어 조건으로 남아있는 몬스터가 있는 확인이 필요할 때 사용되는 싱글톤 클래스다. 디버그용 몬스터를 강제로 죽이는 함수 ForceDeadMonster와 남아있는 몬스터가 0마리인 확인해주는 CheckMonsterCountZero가 있다.  


## Properties

| 변수명. | 설명. |
| :--- | :--- |
| instance | 싱글톤 클래스를 사용하기 위한 변수. |

## Public Method

| 함수명. | 설명. |
| :--- | :--- |
| [ForceDeadMonster](forcedeadmonster.md) | 맵에 있는 몬스터들을 확인하고 전부 강제로 죽인다. |
| [CheckMonsterCountZero](checkmonstercountzero.md) | 몬스터가 남아있나 확인하고 없으면 상황전파 종료 |



