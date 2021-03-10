---
description: 아이템 Prefab을 만드는 방법
---

# 아이템 설정 가이드

## 아이템 프리팹의 기본 구성

아이템 프리팹이 인식되어 게임에 제대로 추가되기 위해선 아래 조건들을 충족해야합니다

1. Prefab이 `Resource/Item`에 위치해야 합니다
2. Tag = ITEM, Layer = Item이어야 합니다
3. `CEquipComponent` 혹은 `CConsumableComponent`를 가지고, 

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

## 아이템에 사용 효과를 추가하는 방법

아래 그림처럼 

![](https://lh4.googleusercontent.com/UdY3QmC2sBJsWSwycNYMBy-uCx2I1M7eF7sh-d3nE-lZUwIShgN-l50tnuSawXd9ReFbonsMCION-CC_M_9veXjcJ8Z0bGeO8wWpYChe0IQoiCrFUhnxG7uUBpj5GSt1o19OH_Sk)

