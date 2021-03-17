---
description: public void ActivateFountain()
---

# ActivateFountain

## 설명 

템 분수 이벤트를 실행하려면 분수npc에 CActivateFountain 스크립트를 할당하고 ActivateFountain 함수를 호출하면 된다.

```text
public void Start()
    {
        GameObject _fountain = GameObject.Find("Fountain");
        _fountain.GetComponent<CActivateFountain>().SendMessage("ActivateFountain");
    }
```

