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

* Time : 효과 지속 시간\(초 단위\) 
* ID : 효과 ID - 각 효과들 구분하는 용도  효과 ID가 같은 효과끼리는 중복 적용 불가, 덮어씌우는 구조  스택형 버프의 경우 효과 ID가 같으면 스택 추가 
* Tick Effect : 일정 주기마다 체력 변화 효과를 줌   
  Tick Hp Change, Tick Period 2개로 구성됨 

  * Tick Hp Change : Tick Period마다 적용되는 [체력 변화 효과](undefined.md) 
  * Tick Period : 효과 적용 주기 

  ex\) 6초 동안 1초마다 데미지를 주는 효과의 경우 Time = 6, Tick Period = 1, \(Tick Hp Change는 생략\)

* Change Abilities : 능력치 버프 / 디버프 설정

  ![](../../.gitbook/assets/image%20%2814%29.png)

  * \(1\) : 버프 종류 선택 
  * \(2\) : 버프인지 디버프인지 선택
  * \(3\) : 초기 버프랑 선택 
  * \(4\) : 스택에 따른 추가 버프량 선택 

  ex\) 5스택짜리 30%+스택 당 10% 추가되는 공격 버프의 경우  
  \(1\) = Attack, \(2\) = True, \(3\) = 30, \(4\) = 10  

* Increase Stack : 효과 적용 시 추가되는 스택량  ex\) 저주 3스택 추가의 경우 Increase Stack = 3 
* Max Stack : 스택 최대치  ex\) 5스택까지 가능한 버프의 경우 Max Stack = 5 

{% hint style="warning" %}
Persist Effect의 경우 Time, ID, Increase Stack, Max Stack이 설정이 완료되지 않으면 작동하지 않습니다   
작동을 위해선 다음 조건들을 만족해야 합니다

Time : 0보다 큼   
ID : 0이 아님   
Increase Stack : 1 이상   
Max Stack : 1 이상 
{% endhint %}

  


#### Conditional Effect

특정 효과가 걸려있을 때 발동하는 효과\(ex\) 첨습이 걸려있을 때 추가효과 발동\)

* Conditional Effect Id : 발동 조건\(효과\) id  \(ex\) 첨습이 걸려있을 때 추가효과 발동이면 Conditional Effect Id = 첨습 효과 id\)
* Is Relation Stack : 발동 조건\(효과\) 스택에 따라 강화되는지
* Stack Bonus Rate : 스택에 따른 강화비율\(%가 기준, 현재는 즉발 효과만 됨\)
* Effect : 발동 조건\(효과\)을 충족했을 때 발동하는 효과

### 지정된 효과\(첨습, 저주 등\) 추가하기 



## 원하는 클래스에 사용 효과 추가하기  

ex\) 이벤트 수행 시 기존에 만들어둔 사용효과\(CUseEffect\)를 이용해서 효과를 주는 경우 





## 원하는 사용효과 만들기 

ex\) 아이템 등 사용효과 포맷을 써야하는데 기존 효과로 표현할 수 없는 경우 

효과와 상관없이 CUseEffectHandle을 상속받고 원하는 효과를 TakeUseEffect\(\)에 구현하면 됩니다   
예를 들어, 랜덤 발동 효과의 경우 아래와 같이 구현되어 있습니다  

```csharp
public class CRandomUseEffect : CUseEffectHandle
{
    public override void TakeUseEffect(CharacterPara cPara)
    {
        int selectEffect = SelectRandomEffect();
        if (selectEffect == -1)
        {
            return;
        }
        cPara.TakeUseEffect(effects[selectEffect].effect);
    }
}
```

만약 사용자의 스탯에 영향을 받고 싶게 만들고 싶다면 EnhanceEffectByStat\(\)도 구현해야 합니다 

