---
description: 몬스터 패턴 및 적용 예시
---

# Monster

## Monster 기본 행동 패턴

* [Idle](basepattern.md#idle)
* [Chase](basepattern.md#chase)
* [Attack](basepattern.md#attack)
* [Skill](basepattern.md#skill)
* [Hit](basepattern.md#hit)
* [Dead](basepattern.md#dead)

해당 상태는 Animator의 Transition의 조건을 만족하는 경우 자동으로 전환됨.

![&#xBAAC;&#xC2A4;&#xD130; Animator&#xC758; &#xAE30;&#xBCF8; &#xAD6C;&#xC131; \(&#xC608;&#xC2DC;\)](../../.gitbook/assets/.png%20%281%29.png)

Animator 복잡한 상태를 직관적으로 표현하기 위해 Sub-State machine으로 하위구조로 만듦. Animator.StringToHash를 이용해 접근하기 위해선, hierarchies를 정확하게 기입해야 함.

```text
_idleState = Animator.StringToHash("Base Layer.Idle");
_standState = Animator.StringToHash("Base Layer.MovingSub.Stand");
_walkState = Animator.StringToHash("Base Layer.MovingSub.Walk");
_runState = Animator.StringToHash("Base Layer.MovingSub.Run");
_attackState1 = Animator.StringToHash("Base Layer.AttackSub.Attack1");
_waitState = Animator.StringToHash("Base Layer.AttackSub.AttackWait");
_attackState2 = Animator.StringToHash("Base Layer.AttackSub.Attack2");
_skillState1 = Animator.StringToHash("Base Layer.AnySub.Skill1");
_skillState2 = Animator.StringToHash("Base Layer.AnySub.Skill2");
_skillState2 = Animator.StringToHash("Base Layer.AnySub.Skill3");
_skillWaitState1 = Animator.StringToHash("Base Layer.AnySub.SkillWait1");
_skillWaitState1 = Animator.StringToHash("Base Layer.AnySub.SkillWait2");
_skillWaitState1 = Animator.StringToHash("Base Layer.AnySub.SkillWait3");
_gethitState = Animator.StringToHash("Base Layer.AnySub.GetHit");
_deadState = Animator.StringToHash("Base Layer.AnySub.Dead");
```



## Monster 프리팹의 기본 구성

몬스터 프리팹이 인식되어 게임에 제대로 추가되기 위해선 아래 조건들을 충족해야합니다

1. CRespawn이 포함된 오브젝트에 해당 몬스터 프리팹을 넣어야함.
2. 몬스터 프리팹에 CEnemyPara의 스탯 값을 저장해야 함.



