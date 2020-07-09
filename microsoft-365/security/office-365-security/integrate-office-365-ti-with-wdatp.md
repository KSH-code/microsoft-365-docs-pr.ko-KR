---
title: Office 365 ATP와 Microsoft Defender ATP를 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Microsoft Defender Advanced Threat Protection과 Office 365 Advanced Threat Protection을 통합 하 여 보다 자세한 위협 관리 정보를 확인 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086711"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection을 사용 하 여 Office 365 Advanced Threat Protection 통합

Microsoft defender [Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection) (MICROSOFT defender atp)에서 작동 하도록 [Office 365 Advanced threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (office 365 atp)을 구성할 수 있습니다.

Office 365 ATP를 Microsoft Defender ATP와 통합 하면 사용자의 장치가 위험에 처 한 경우 보안 운영 팀이 보다 신속 하 게 조치를 취할 수 있습니다. 예를 들어 통합이 설정 되 면 보안 운영 팀이 검색 된 전자 메일 메시지의 영향을 받을 가능성이 있는 장치를 볼 수 있을 뿐 아니라 해당 장치에 Microsoft Defender ATP가 갖고 있는 최근 알림을 몇 개 표시할 수도 있습니다. 

다음 그림에서는 Microsoft Defender ATP 통합을 사용 하도록 설정한 **장치** 탭의 모양을 보여 줍니다.
  
![Microsoft Defender ATP를 사용 하도록 설정 하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
이 예에서는 검색 된 전자 메일 메시지의 받는 사람에 게 4 개의 장치가 있고 하나에 경고가 있음을 확인할 수 있습니다. 장치에 대 한 링크를 클릭 하면 Microsoft Defender 보안 센터 ()에서 해당 페이지가 열립니다 [https://securitycenter.windows.com](https://securitycenter.windows.com) .

> [!TIP]
> **[Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (MICROSOFT defender ATP 포털이 라고도 함)에 대해 자세히 알아보세요.
  
## <a name="requirements"></a>요구 사항

- 조직에 Office 365 ATP 계획 2 (또는 Office 365 E5)와 Microsoft Defender ATP가 있어야 합니다.
    
- 전역 관리자 이거나 보안 및 [ &amp; 준수 센터](https://protection.office.com)에서 보안 관리자 역할 (예: 보안 관리자)을 할당 해야 합니다. ( [보안 및 &amp; 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)참조)
    
- 보안 & 준수 센터 및 Microsoft Defender 보안 센터에서 두 [탐색기 (또는 실시간 검색)](threat-explorer.md) 에 액세스할 수 있어야 합니다.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Office 365 ATP를 Microsoft Defender ATP와 통합 하려면

Microsoft Defender ATP와 Office 365 ATP를 통합 하는 기능은 보안 & 준수 센터와 Microsoft Defender 보안 센터를 모두 사용 하 여 설정 됩니다.
  
1. 전역 관리자 또는 보안 관리자로 이동 하 여 [https://protection.office.com](https://protection.office.com) 로그인 합니다. (이 경우 Office 365 보안 & 준수 센터가로 이동 합니다.)
    
2. 탐색 창에서 **위협 관리**  >  **탐색기**를 선택 합니다.<br>![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 화면의 오른쪽 위 모서리에서 **Wdatp 설정을**선택 합니다.
    
4. Microsoft Defender ATP 연결 대화 상자에서 **WINDOWS ATP에 연결**을 설정 합니다.<br>![Microsoft Defender ATP 연결](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Microsoft Defender 보안 센터 ()로 이동 [https://securitycenter.windows.com](https://securitycenter.windows.com) 합니다.

6. 탐색 모음에서 **설정을**선택 합니다. 그런 다음 **일반**에서 **고급 기능**을 선택 합니다.

7. 아래로 스크롤하여 **Office 365 위협 인텔리전스 연결**을 설정 하 고 연결을 켭니다.<br/>![Office 365 위협 인텔리전스 연결](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>관련 문서

[Office 365의 위협 조사 및 응답 기능](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
