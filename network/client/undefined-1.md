# 몬스터 패턴 동기화

싱글플레이는 자신의 방을 생성하고 그 방의 호스트가 된다고 가정  

## 이론 

  
Host - 몬스터가 개별적으로 자신의 패턴을 정함 -&gt; 패턴이 정했음을 알림\(옵저버 패턴이 좋아보임\)    
Peer - 패턴 정하지 않음. 대기    
싱글플레이면 패킷 안 거치고 호출 / 멀티플레이면 패킷을 보냄   
패킷을 받으면 해당 몬스터\(ID\)에게 패턴을 수행하게 한다 



## 구현 

몬스터 패턴 결정 전에 다음 if문을 수행   
`if(CClientInfo.IsHost) ...`  
호스트인지 판단 호스트가 아니면 패턴을 결정하지 않는다\(대기 상태\)    
why? 호스트의 몬스터 패턴을 따라가야하기 때문\(= 몬스터 패턴 동기화\) 

각 몬스터 패턴들은 패턴 결정 후 함수 Invoke   
`MonsterManager::DecideMonsterPattern(int monsterID, int playerID, int patternNumber)`  
몬스터\(monsterID\)가 플레이어\(playerID\)에게 패턴\(patternNumber\)를 하기로 결정 

`MonsterManager::CommandPattern(int monsterID, int playerID, int patternNumber)`  
몬스터\(monsterID\)가 플레이어\(playerID\)에게 패턴\(patternNumber\)을 수행 

* patternNumber는 패턴 수행 방법을 획일화하기 위한 표기방법일 뿐 

  더 좋은 방법이 있다면 바꿔도 상관없음 

### 테스트 



