---
description: 외부에서 만든 Window 조작 상태로 변경한다
---

# SetOtherWindowMode

public void SetOtherWindowMode\(bool isOtherWindow\);

## 설명 

상점 방 등 WindowFacade에서 관리하지 않는 Window와 호환되도록 만드는 함수이다   
이 함수를 사용하면 WindowFacade 관리 하의 Window와 외부 Window가 충돌나지 않는다   
ex\) 외부 Window인 상점창 사용 중 ESC를 누르면 상점창만 꺼지고 메뉴는 열리지 않음   
상점 방 등 외부 Window가 열리는 경우뿐만 아니라 이벤트 선택 등 캐릭터 조작 등을 막아야하는 경우도 사용 가능하다 

외부 Window에서 SetOtherWindowMode\(\)를 사용하는 방법은 아래와 같다 

```text
    // 상점을 열 경우 SetOtherWindowMode(true)로 
    public void UseNPC()
    {
        _popUp.SetActive(true);
        instance._stackPopUp.Push(_popUp);
        CGlobal.useNPC = true;
        CWindowFacade.instance.SetOtherWindowMode(true);
    }
    
    // 상점을 닫을 경우 SetOtherWindowMode(false)
    public void CanclePopUp()
    {
        if (instance._stackPopUp.Count != 0)
        {
            GameObject popUp = instance._stackPopUp.Pop();
            popUp.SetActive(false);
        }

        if (instance._stackPopUp.Count == 0)
        {
            CGlobal.useNPC = false;
            CWindowFacade.instance.SetOtherWindowMode(false);
        }
    }
```

