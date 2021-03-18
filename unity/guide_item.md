---
description: 아이템 Prefab을 만드는 방법
---

# 아이템 설정 가이드

## 아이템 프리팹 만들기 

아이템 프리팹이 인식되어 게임에 제대로 추가되기 위해선 아래 조건들을 충족해야합니다

1. Prefab이 `Resource/Item`에 위치해야 합니다
2. Tag = ITEM, Layer = Item이어야 합니다

그 외에도 장비 / 소비 아이템은 아래 설명에 따라 만들길 바랍니다 

{% hint style="info" %}
Resource/Item에 미리 만들어 둔 프리팹을 복사\(Ctrl+D\)해서 설정을 가져와도 됩니다 
{% endhint %}

{% hint style="danger" %}
만들어둔 아이템끼리 Item Code가 같으면 Error납니다. 코드가 중복되지 않게 확인해주세요
{% endhint %}

{% hint style="warning" %}
Use Effect List의 원소 갯수만큼 UseEffect를 설정하지 않으면 Error 납니다   
\(Debug용 에러\)
{% endhint %}

### 소비 아이템 만들기 

소비 아이템은 CConsumableComponent를 사용합니다 

{% hint style="warning" %}
소비 아이템은 100의 자리가 0 입니다.   
다른 번호를 넣으면 아이템 드랍 목록에 오류가 생길 수 있으니 주의해주세요  
{% endhint %}

![](https://lh4.googleusercontent.com/UdY3QmC2sBJsWSwycNYMBy-uCx2I1M7eF7sh-d3nE-lZUwIShgN-l50tnuSawXd9ReFbonsMCION-CC_M_9veXjcJ8Z0bGeO8wWpYChe0IQoiCrFUhnxG7uUBpj5GSt1o19OH_Sk)

* Use Effect : 소비 아이템 사용 효과 \(아이템 사용자가 얻는 효과\) 

### 장비 아이템 만들기 

장비 아이템은 CEquipComponent를 사용합니다 

{% hint style="info" %}
소비 아이템은 100의 자리가 1 입니다.   
다른 번호를 넣으면 아이템 드랍 목록에 오류가 생길 수 있으니 주의해주세요
{% endhint %}

![](../.gitbook/assets/image%20%2817%29.png)

* 장비 능력치 : 장비 착용 시 얻는 스탯\(공격력 등\) 상승 
  * \(1\) : 능력치 종류 - 공격력, 방어력, HP 등 
  * \(2\) : 증가량. 기본적으로 고정 수치 
* 패시브 효과 : 조건을 만족하면 자동 사용하는 효과  ex\) 스킬 3회 사용, 피해 200 이상 등
  * \(3\) : 효과 사용 조건1. 최우선 조건  ex\) **피해** 200 이상 **입으면** -&gt; '피해 입으면'에 해당 
  * \(4\) : 효과 사용 조건2.  조건으로 누적/이상/이하 선택 가능  \(3\)에 따라 적용 안 될 수도 있음  ex\) 피해 200 **이상** 입으면 -&gt; '이상'에 해당  ex2\) 스킬 3회 사용 -&gt; 스킬은 무조건 1회씩 사용하므로 이 경우 '누적'에 해당 
  * \(5\) : 효과 사용 조건 수치  ex\) 피해 **200** 이상 입으면 -&gt; '200'에 해당 
  * \(6\) : \(3\), \(4\), \(5\) 충족 시 발동되는 효과  효과 설정 방법은 [사용 효과 세팅 가이드](guide_use_effect/) 참고
* 성장 능력치 : 특정 조건을 충족하면 얻는 스탯 상승. 무조건 누적식  ex\) 방 진입 15회 이상 
  * \(7\) : 성장 조건  ex\) **방 진입** 15회 이상 - '방 진입'에 해당 
  * \(8\) : 성장 조건 수치  ex\) 방 진입 **15**회 이상 - '15'에 해당 
  * \(9\) : 스탯 상승치. 위의 장비 능력치 설정 방식과 동일 

## 

