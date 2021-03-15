---
description: 기존 게임 로직과 네트워크를 어떻게 분리하는지에 대해 적은 문서입니다
---

# 네트워크와 게임 로직 분리

이 게임은 싱글플레이와 멀티플레이를 지원하지만 이 때문에 모든 게임 파트에서 싱글플레이와 멀티플레이를 구분하여 구현하는 것은 매우 비효율적입니다 

클라이언트 작업 특성 상 싱글플레이로 보고 제작하는 것이 매우 효율적이므로 네트워크 관련 파트를 제외한 모든 파트에서는 싱글플레이로 보고 제작합니다   
다만 이 게임은 멀티플레이도 가능해야하므로 싱글플레이와 멀티플레이가 다른 몇 가지 부분은 구조 상 타협이 필요합니다



![&#xCE90;&#xB9AD;&#xD130; &#xC774;&#xB3D9;&#xC758; &#xACBD;&#xC6B0; &#xC2F1;&#xAE00; &#xD50C;&#xB808;&#xC774;&#xB97C; &#xAE30;&#xC900;&#xC73C;&#xB85C; &#xB9CC;&#xB4E4;&#xC5B4;&#xB3C4; &#xBA40;&#xD2F0;&#xD50C;&#xB808;&#xC774;&#xC5D0; &#xB9DE;&#xAC8C; &#xB85C;&#xC9C1; &#xCD94;&#xAC00;&#xAC00; &#xC27D;&#xB2E4; ](../../.gitbook/assets/image%20%281%29.png)



![&#xBAAC;&#xC2A4;&#xD130; &#xCC98;&#xCE58;&#xC758; &#xACBD;&#xC6B0; &#xC2F1;&#xAE00; &#xD50C;&#xB808;&#xC774;&#xB97C; &#xAE30;&#xC900;&#xC73C;&#xB85C; &#xB9CC;&#xB4E4;&#xBA74; &#xBA40;&#xD2F0;&#xD50C;&#xB808;&#xC774;&#xC5B4; &#xB9DE;&#xCD94;&#xAE30; &#xD798;&#xB4E4;&#xB2E4; ](../../.gitbook/assets/image%20%282%29.png)



![](../../.gitbook/assets/image.png)



