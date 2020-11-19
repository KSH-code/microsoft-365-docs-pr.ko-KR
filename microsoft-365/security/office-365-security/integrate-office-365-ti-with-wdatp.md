---
title: Microsoft defender for Office 365 with Endpoint for for 끝점 사용
f1.keywords:
- NOCSH
keywords: 통합, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft defender for Office 365와 Microsoft Defender for Endpoint를 함께 사용 하 여 장치 및 전자 메일 콘텐츠에 대 한 위협에 대 한 자세한 정보를 확인 하세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f668aa1234509789dacd2b018b94f1bfbc79e2c
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357782"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft defender for Office 365 with Endpoint for for 끝점 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft defender For Office 365 For](office-365-atp.md) [Endpoint에 대](https://docs.microsoft.com/windows/security/threat-protection)

Microsoft defender for Office 365을 끝점에 통합 하면 사용자의 장치가 위험에 처 한 경우 보안 운영 팀이 보다 신속 하 게 작업을 수행 하는 데 도움이 될 수 있습니다. 예를 들어 통합을 사용 하도록 설정 하면 보안 운영 팀이 검색 된 전자 메일 메시지의 영향을 받을 가능성이 있는 장치를 볼 수 있을 뿐만 아니라 끝점에 대 한 Microsoft Defender에서 해당 장치에 대 한 최근 경고가 발생 한 횟수를 확인할 수도 있습니다. 

다음 이미지에서는 **장치** 탭에 사용 되는 끝점 통합에 대 한 Microsoft Defender가 있는 것 처럼 보이는 결과를 보여 줍니다.
  
![끝점에 대해 Microsoft Defender를 사용 하도록 설정 하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
이 예에서는 검색 된 전자 메일 메시지의 받는 사람에 게 4 개의 장치가 있고 하나에 경고가 있음을 확인할 수 있습니다. 장치에 대 한 링크를 클릭 하면 Microsoft Defender 보안 센터 ()에서 해당 페이지가 열립니다 [https://securitycenter.windows.com](https://securitycenter.windows.com) .

> [!TIP]
> **[Microsoft Defender 보안 센터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (끝점 포털 용 microsoft defender 라고도 함)에 대해 자세히 알아보세요.
  
## <a name="requirements"></a>요구 사항

- 조직에 Office 365 (또는 Office 365 E5) 용 Microsoft Defender가 있고 끝점에 대 한 Microsoft Defender가 있어야 합니다.
    
- 전역 관리자 이거나 보안 및 [ &amp; 준수 센터](https://protection.office.com)에서 보안 관리자 역할 (예: 보안 관리자)을 할당 해야 합니다. ( [보안 및 &amp; 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)참조)
    
- 보안 & 준수 센터 및 Microsoft Defender 보안 센터에서 두 [탐색기 (또는 실시간 검색)](threat-explorer.md) 에 액세스할 수 있어야 합니다.
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft defender for Office 365을 사용 하 여 끝점을 Microsoft에 통합 하려면

보안 & 준수 센터와 Microsoft Defender 보안 센터를 모두 사용 하 여 Office 365 용 microsoft defender (Microsoft Defender for Endpoint)를 통합 합니다.
  
1. 전역 관리자 또는 보안 관리자로 이동 하 여 [https://protection.office.com](https://protection.office.com) 로그인 합니다. (이 경우 Office 365 보안 & 준수 센터가로 이동 합니다.)
    
2. 탐색 창에서 **위협 관리**  >  **탐색기** 를 선택 합니다.<br>![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 화면의 오른쪽 위 모서리에서 **끝점 설정에 대해 Defender** 를 선택 합니다.
    
4. Microsoft Defender for 끝점 연결 대화 상자에서 **끝점에 대 한 Microsoft defender에 연결** 을 설정 합니다.<br>![끝점 연결용 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Microsoft Defender 보안 센터 ()로 이동 [https://securitycenter.windows.com](https://securitycenter.windows.com) 합니다.

6. 탐색 모음에서 **설정을** 선택 합니다. 그런 다음 **일반** 에서 **고급 기능** 을 선택 합니다.

7. 아래로 스크롤하여 **Office 365 위협 인텔리전스 연결** 을 설정 하 고 연결을 켭니다.<br/>![Office 365 위협 인텔리전스 연결](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>관련 문서

[Office 365의 위협 조사 및 응답 기능](office-365-ti.md)
  
[Office 365용 Microsoft Defender](office-365-atp.md)
  
[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)
