# 기본 패턴 설명

## Idle

몬스터가 적을 만나기 전이거나, 플레이어가 모두 사망하였거나, 어떤 행동들에 쿨타임이 가해졌을 경우 도달하는 패턴

만약 적을 만나기전이면, 스킬 쿨타임이 돌지 않게 처리해둠.

## Chase

적을 쫒는 패턴 걷거나 뛰는 Animation으로 표현 인식범위는 Animator상에서 수치 조

## Attack

몬스터의 기본 공격방식. 해당 공격은 Mesh Renderer의 OnTriggerEnter 이용하여 타격

## Skill



## Hit

피격 시 CEnemyPara에서 최대 체력의 몇 퍼센트가 넘는 데미지가 들어올 때 Animation을 재생하게 할 것인지 설정 가

## Dead

죽는 순간 해당 몬스터의 Layer와 name, tag가 변경이 되어 어떤 충돌 판정도 나지 않게 설정



 

