---
title: 끝점용 Microsoft Defender와 함께 Office 365용 Microsoft Defender 사용
f1.keywords:
- NOCSH
keywords: 통합, Microsoft Defender, 끝점용 Microsoft Defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 끝점용 Microsoft Defender와 함께 Office 365용 Microsoft Defender를 사용하여 장치 및 전자 메일 콘텐츠에 대한 위협에 대한 자세한 정보를 얻을 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6ad81102a9702a725f40fcdb5421a2b19b0086d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934036"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender와 함께 Office 365용 Microsoft Defender 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365용 Microsoft Defender는](defender-for-office-365.md) [끝점용 Microsoft Defender와 함께 작동하도록 구성할 수 있습니다.](/windows/security/threat-protection)

Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합하면 보안 운영 팀이 사용자의 장치가 위험에 노출될 경우 신속하게 조치를 취할 수 있습니다. 예를 들어 통합이 사용하도록 설정되면 보안 운영 팀은 감지된 전자 메일 메시지의 영향을 받을 수 있는 장치와 끝점용 Microsoft Defender에서 해당 장치에 대해 생성된 최근 알림 수를 볼 수 있습니다.

다음 이미지는 끝점용 Microsoft Defender 통합을 사용하도록 설정한 경우 장치 탭의 모양을 나타났습니다. 

![끝점용 Microsoft Defender를 사용하도록 설정하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

이 예에서는 감지된 전자 메일 메시지의 받는 사람에게 4개의 장치가 있으며, 다른 하나는 경고를 표시하는지 볼 수 있습니다. 장치에 대한 링크를 클릭하면 Microsoft Defender 보안 센터( )에서 해당 페이지가 <https://securitycenter.windows.com> 열립니다.

> [!TIP]
> **[Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use)** 보안 센터(끝점 포털용 Microsoft Defender라고도 합니다.)

## <a name="requirements"></a>요구 사항

- 조직에는 Office 365용 Microsoft Defender(또는 Office 365 E5) 및 끝점용 Microsoft Defender가 있어야 합니다.

- 보안 및 준수 센터 에서 전역 관리자 또는 보안 관리자 [역할(예: 보안 관리자)이 & 합니다.](https://protection.office.com) (보안 [및 준수 센터의 & 참조)](permissions-in-the-security-and-compliance-center.md)

- 보안 및 준수 [](threat-explorer.md) 센터와 Microsoft Defender 보안 센터에서 탐색기(& 검색)에 모두 액세스할 수 있어야 합니다.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합

Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합하는 것은 보안 및 준수 센터와 Microsoft Defender & 사용하여 설정됩니다.

1. 전역 관리자 또는 보안 관리자로 이동하여 <https://protection.office.com> 로그인합니다. 이 경우 Office 365 보안 및 준수 & 수 있습니다.

2. 탐색 창에서 위협 관리 **탐색기를** \> **선택 합니다.**

   ![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)

3. 화면의 오른쪽 위 모서리에서 끝점 설정(MDE 설정)에 대한 **Defender를 선택합니다.**

4. 끝점 연결용 Microsoft Defender 대화 상자에서 **끝점용 Microsoft Defender에 연결을 켜야 합니다.**

   ![끝점 연결용 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)

5. Microsoft Defender 보안 센터()로 <https://securitycenter.windows.com> 이동하십시오.

6. 탐색 모음에서 설정을 **선택합니다.** 그런 다음 **일반에서** 고급 기능을 **선택 합니다.**

7. 아래로 스크롤하여 **Office 365 위협** 인텔리전스 연결로 이동한 다음 연결을 켜야 합니다.

   ![Office 365 위협 인텔리전스 연결](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>관련 문서

[Office 365의 위협 조사 및 응답 기능](office-365-ti.md)

[Office 365용 Microsoft Defender](defender-for-office-365.md)

[엔드포인트용 Microsoft Defender](/windows/security/threat-protection)