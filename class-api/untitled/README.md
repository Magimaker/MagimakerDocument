---
description: 플레이어 캐릭터를 원격으로 조작하는 클래스
---

# CPlayerCommand

예시 - 이 API는 Unity Script API 스타일입니다  
Unity Script API 스타일은 클래스 이름으로 된 문서는 멤버 변수/함수의 간략한 설명만 담고, 멤버 변수/함수 세부적인 내용\(이름, 설명, 예시 등\)은 하위 문서로 담습니다 

## 설명 

플레이어가 조작하는 캐릭터\(최대 4개\)에게 명령을 내리는 싱글톤 클래스  
Teleport를 제외한 모든 명령은 해당 클리어언트가 직접 조작 중인 캐릭터에게는 적용되지 않는다  
\(예를 들어, 해당 클라이언트가 3번 캐릭터를 조작하고 있다면 2번 캐릭터에게는 명령을 할 수 있지만 3번 캐릭터에게는 명령할 수 없음\)

## Properties

| [players](players.md) | 게임에 존재하는 캐릭터 목록 |
| :--- | :--- |
| ControlCharacterID | 해당 클라이언트가 조작 중인 캐릭터의 ID |

## Public Methods

| [Move](move.md) | charID에 해당하는 캐릭터를 movePos로 이동시킨다 |
| :--- | :--- |
|  |  |



