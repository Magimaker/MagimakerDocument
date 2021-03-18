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
* 패시브 효과 : 

## 

