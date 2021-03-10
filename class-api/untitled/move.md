---
description: charID에 해당하는 캐릭터를 movePos로 이동시킨다
---

# Move

public void Move\(int charID, Vector3 movePos\);

## 설명 

ID에 해당하는 캐릭터에게 해당 좌표로 이동 명령을 내린다  
명령을 내린 캐릭터가 플레이어가 조종 중인 캐릭터라면 명령을 무시한다  
명령을 받은 캐릭터는 해당 좌표로 등속도 이동한다

아래 예시는 Packet을 해석해 해당 캐릭터를 좌표 지점으로 이동하게 만드는 코드이다

```text
        private void InterpretMoveStart(CPacket packet)
        {
            Int32 id;
            Vector3 now, dest;
            
            id = packet.ReadInt32();
            now.x = packet.ReadSingle();
            now.y = packet.ReadSingle();
            now.z = packet.ReadSingle();
            dest.x = packet.ReadSingle();
            dest.y = packet.ReadSingle();
            dest.z = packet.ReadSingle();

            Debug.Log("Move Start - id{0} move ({1},{2},{3}) to ({4},{5},{6})", 
                id, now.x, now.y, now.z, dest.x, dest.y, dest.z);

            //Commander
            playerCommander.Move(id, dest);
        }
```

