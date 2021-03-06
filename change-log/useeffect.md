# UseEffect

#### 클래스 설명



## History

### CUseEffect 생성 이전

### 200923

#### 클래스 제작의 필요성

### 210121

#### 현 구조의 문제점

**Unity의 object composition cycle로 인한 Serialize 제한**

Unity는 serialize 단계를 7단계로 제한함

하위 효과에 UseEffect를 직접 넣으면 단계 제한에 따라 일부 효과가 Serialize 되지 않음

또 Serialize 단계가 높아짐에 따라 단계 구분을 위한 들여쓰기가 많아져 변수 이름이 짤리는 불편함 존재

**스택 누적 효과 및 조건부 효과 지정에 제한이 있음**

**효과 재사용성 문제**

UseEffect를 아이템에 직접 넣다보니 똑같은 효과를 재사용하기 힘들었음

따로 재사용 구분용 변수 등을 만들어 이를 해결해도 구조가 복잡해지는 등의 문제 발생

#### 새로운 UseEffect 구조 설계

**1. GameObject로 UseEffect 따로 담기**

먼저 UseEffect는 Component로 바꿈

기존 UseEffect를 담는 부분을 UseEffect를 넣은 GameObject로 담게 만듦

GameObject를 통해 간접적으로 UseEffect를 담음으로써 기존 문제들을 해결

**기존 구조의 문제점을 해결하는가?**

1. Unity의 object composition cycle로 인한 Serialization 제한

 - 하위 효과를 GameObject를 통해 담을 것이므로

2. 스택 누적 효과 및 조건부 효과 지정에 제한이 있음

 - GameObject로 효과를 넣으므로 효과 지정에 제한이 없음

3. 효과 재사용성 문제

 - 만들어둔 GameObject를 재사용할 수 있음

**이 구조의 문제점**

\(1\) 효과 제작이 번거로움 : UseEffect 제작을 위해서 GameObject를 만들고 Component를 추가해 값 설정 후 아이템에 효과를 넣어줘야 함

\(2\) 일회적으로 제작한 효과\(해당 아이템, 스킬에만 있는 효과\)도 저장하게 됨

\(3\) 효과 누락 : 효과는 만들어놓고 아이템에 효과를 넣지 않아서 누락될 수 있음

**2. 아이템 GameObject에 UseEffect Component 직접 담기**

아이템 GameObject 자체 혹은 자식 GameObject에 UseEffect Component를 직접 담음

**기존 구조의 문제점을 해결하는가?**

1. Unity의 object composition cycle로 인한 Serialization 제한

 - 하위 효과는 UseEffect Component를 추가하여 넣으므로 Serialization 문제를 피할 수 있음

2. 스택 누적 효과 및 조건부 효과 지정에 제한이 있음

 - Component로 효과를 넣으므로 효과 지정에 제한이 없음

3. 효과 재사용성 문제

 - 정의된 효과용 GameObject를 만들어 재사용할 수 있음

**이 구조의 문제점**

\(1\) 효과 누락 : 효과는 만들어놓고 아이템에 효과를 넣지 않아서 누락될 수 있음

- 문제 해결이 불가능하진 않음

\(2\) 효과 네이밍 문제 : Component 포인터를 보고는 넣어둔 효과가 무엇인지 확인이 어려움

- 이 문제가 아이템\(혹은 스킬 등\) 제작에 있어 큰 문제가 되는가 확인 필요

**효과 재사용성을 높이기 위한 1번 방법과의 결합**

UseEffect를 Component로 담는 건 동일하지만 정의된 효과의 경우 Resource/UseEffect 폴더에 GameObject\(프리팹\)로 저장해 관리함

#### 다양한 효과를 넣을 수 있는 UseEffect

UseEffect\(클래스 구조\)를 크게 변경하지 않으면서 다양한 효과를 구현할 수 있는 구조가 필요

**다양한 효과의 종류**

**투사체 발사**

시전자를 기준으로 GameObject를 생성하는 효과

**랜덤 효과**

여러 효과 중 하나를 랜덤으로 골라서 사용하는 효과

**자유 효과**

UseEffect로 설정할 수 없는 특수한 효과

\(예를 들어, 스탯 영구 증가 등\)

**다양한 효과 사용 방법**

**다양한 효과를 담을 수 있는 Handle 클래스 설계**

**각 효과별 구현**

### 210205

#### 문제점 - UseEffect 클래스 재사용이 불가능

캐릭터 스킬의 데미지는 캐릭터\(플레이어 혹은 몬스터\)의 능력치를 받아서 강해질 수 있어야 함

ex\) 플레이어의 공격력이 50이고 플레이어 공격력의 80%를 받아서 공격하는 마법이 있다면 마법이 주는 데미지는 40이 되어야 함

 플레이어의 공격력이 200으로 늘어났다면 마법이 주는 데미지는 160으로 늘어나야 함

**재사용 시에도 안정적인 클래스 구조**

캐릭터 스킬 사용 등 능력치를 받을 때 값이 변경됨으로 인해 문제가 생기면 안 됨

ex\) 플레이어의 공격력이 50이고 플레이어 공격력의 80%를 받아서 공격하는 마법이 있다면

처음 사용했을 때 주는 마법의 데미지는 40\(50 \* 0.8\), 이후에 주는 마법의 데미지도 40이어야 함

**인스펙터 설정값을 변경하지 않는 새로운 구조**

기존에 설정된 인스펙터 값을 유지하기 위해 기존 변수를 변경하지 않아야 함

재사용을 위해 기존 인스펙터에서 설정한 값을 저장할 수 있어야 함

ex\)

**\(추가\) 세밀한 힐/데미지 표현**

기존 힐/데미지는 고정값만을 표기할 수 있어 잃은 체력 비례 / 전체 체력 비례 등의 설정이 불가능했음

또 데미지는 방어 무시 효과 지정 불가능했음

#### 새로운 UseEffect 구조

크게 보면 기존 UseEffect 클래스에 프로토타입 패턴을 적용했다고 볼 수 있음

**초기값 저장**

재사용을 위해 아이템/스킬 등 인스펙터를 통해 설정한 값은 따로 저장되어야 함

그래야 저장해둔 값을 통해

#### 피드백

**저장 방식의 아쉬움**

Property에 초기값을 저장하는 방식이 아닌 SerializeField\(기존 변수\)에 초기값을 저장하고 Property가 변경되는 방식이 어땠을까 생각함

구현한 방식은 위와 같지만

public InstantEffect EnhancedInstantEffect {get; private set;}

public PersistEffect EnhancedPersistEffect {get; private set;}

public ConditionalEffect EnhancedConditionalEffect {get; private set;}

이었다면 이미 구현한 방식과 비교해 2가지 이점을 얻었을 것임

1. 초기값 굳이 Awake로 복사 안 해놔도 됨

2. 인스펙터로 설정된 값이 변경되어 데미지 계수 등의 변경이 이상하게 보임을 방지

\(이건 확실하게 이점이라 보기 애매함. 이러면 Normal 인스펙터에선 플레이어 능력치에 따른 마법의 강화 내용이 안 보여서 불편할 수 있음\)

하지만 이렇게 변경하면 기존 CharacterPara의 UseEffect 내용을 다 바꿔야 함

**효율적인 초기값 저장 및 재사용을 위한 프로토타입 팩토리 적용**

각 아이템/스킬마다 설정한 UseEffect 값은 전부 다르지만 같은 스킬/아이템끼리는 초기 설정값이 동일함

ex\) 서로 다른 플레이어가 날린 ‘파이어볼’ 30개가 있다 치면 ‘파이어볼’의 스킬 계수는 전부 똑같고, 플레이어 능력치에 따라 마법이 주는 데미지는 전부 다름

그렇다면 각 스킬/아이템마다 초기 설정값을 가지고 있기 보단 초기 설정값을 모아놓은 저장소가 하나 있고 거기서 값을 가져오는게 더 효율적이지 않은가?

ex\) ‘파이어볼’ 스킬 계수는 다 똑같은데 각 ‘파이어볼’이 스킬 계수를 따로 보관하기 보단 스킬 계수 저장해놓는 곳에서 읽어들이는게 더 효율적이지 않은가?

