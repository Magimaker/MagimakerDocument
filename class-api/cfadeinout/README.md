---
description: 페이드 인 아웃을 사용할 수 있는 싱글톤 클래스.
---

# CFadeInOut

## 설명 

페이드 인, 페이드 아웃, 인과 아웃을 합친 페이드 플로우를 사용할 수 있는 싱글톤 클래스다.

## Properties

| 변수명. | 설명. |
| :--- | :--- |
| instance | 싱글톤 패턴을 이용하기 위한 변수. |
| fadeTime | fade효과 재생시간. |
| fadeTimeInterval | fade in과 out 사이의 시간 설정. |

## Public Method

| 함수명. | 설명. |
| :--- | :--- |
| [PlayFadeIn](playfadein.md) | 페이드 인 실행. |
| [PlayFadeOut](playfadeout.md) | 페이드 아웃 실행. |
| [PlayFadeFlow](playfadeflow.md) | 페이드 아웃인 순서대로 실행. |

