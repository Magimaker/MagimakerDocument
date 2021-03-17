---
description: 사용 효과 설정 방법을 적은 문서입니다
---

# 사용 효과 세팅 가이드

## 사용 효과 설정하기 

아이템, 스킬 등 기존에 설정한 사용효과는 그림과 같은 방법으로 추가할 수 있습니다 

![](../../.gitbook/assets/image%20%2813%29.png)

여러 개의 UseEffect를 넣을 수 있으므로 필요에 따라 List 크기를 늘려 UseEffect를 추가하면 됩니다   

### CUseEffect 설정 가이드 

데미지, CC, 버프 등 일반적으로 필요한 효과는 CUseEffect에서 설정할 수 있습니다   
CUseEffect의 효과 발동 방식은 크게 3가지로 분류할 수 있습니다   
1. Instant Effect : 즉시 적용되는 효과   
2. Persist Effect : 지속 시간 동안 적용되는 효과   
3. Conditional Effect : 조건에 따라 적용되는 효과 

#### Instant Effect 

설정한 능력이 바로 적용되며, 다음과 같은 효과 지정이 가능합니다 

* [체력 변화 효과](undefined.md) 

#### Persist Effect

지속 효과로 도트 힐/데미지, 버프, \(CC - 추가 필요\)를 설정할 수 있습니다  
또한 스택형 효과 설정이 가능하며 스택에 따른 효과도 지정 가능합니다 

* Time : 
* ID : 
* Tick Effect : 일정 주기마다 체력 변화 효과를 줌   
  Tick Hp Change, Tick Period 2개로 구성됨 

  * Tick Hp Change : Tick Period마다 적용되는 [체력 변화 효과](undefined.md) 
  * Tick Period : 효과 적용 주기 

  ex\) 6초 동안 1초마다 데미지를 주는 효과의 경우 Time = 6, Tick Period = 1, \(Tick Hp Change는 생략\)

* Change Abilities : 능력치 버프 / 디버프 설정 ![](../../.gitbook/assets/image%20%2811%29.png)
  * \(1\)\(\(1ㅁㄴㅇㅁㄴㅇㅁㄴ\(177894564
  * 12312312 

#### Conditional Effect

####   

### 지정된 효과\(첨습, 저주 등\) 추가하기 



## 멤버 변수로 사용 효과 넣기 



## 원하는 사용효과 만들기 

