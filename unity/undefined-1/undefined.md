---
description: 힐이나 데미지를 설정하는 방법
---

# 체력 변화 세팅



체력 변화 효과는 아래와 같이 구성됩니다 

* IsHeal : 힐인지 데미지인지 \(기본은 데미지\)
* IsTrueDamage : 데미지일 경우 방어 무시 데미지인지 \(기본은 방어 무시 X\) 
* Fixed Amount : 사용자의 스탯 영향을 받지 않고 고정된 수치 적용  ex\) 플레이어의 스탯과 상관없이 50의 데미지  
* Enhance Percent : 사용자의 스탯에 따라 강화되는 수치\(퍼센트\)  ex\) Enhance Percent = 50인 경우 사용자 공격력이 200이면 100의 데미지가 적용됨  
* Ratio Type : 현재 체력 / 최대 체력 / 잃은 체력 비례 효과를 설정 
* Ratio Percent : Ratio Type에 따른 적용 수치\(퍼센트\)  ex\) Ratio Type = Current, Ratio Percent = 10인 경우 현재 체력의 10%만큼 데미지를 줌 

