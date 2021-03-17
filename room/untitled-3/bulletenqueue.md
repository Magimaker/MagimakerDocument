---
description: public bool BulletEnqueue(GameObject bullet);
---

# BulletEnqueue

## 설명

오브젝트를 생성하고, 큐에 삽, Bullet오브젝트의 자식으로 배정, Active상태를 False로 바꾼다.

## Returns

| 조건. | 반환값. |
| :--- | :--- |
| 성공. | true |
| 실패. | false |

```text
void Start()
    {
        for (int i = 0; i < 70; i++)
        {
            GameObject bullet = Resources.Load("Object/EventBullet") as GameObject;
            CBulletQueue.instance.BulletEnqueue(bullet);
        }
    }
```



