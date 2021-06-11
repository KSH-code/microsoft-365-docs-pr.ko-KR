---
title: 끝점용 Microsoft Defender와 함께 Office 365 Microsoft Defender 사용
f1.keywords:
- NOCSH
keywords: 통합, Microsoft Defender, 끝점용 Microsoft Defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft Defender를 Office 365 Microsoft Defender for Endpoint를 사용하여 장치 및 전자 메일 콘텐츠에 대한 위협에 대한 자세한 정보를 얻을 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904083"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender와 함께 Office 365 Microsoft Defender 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md) [Microsoft Defender for Endpoint에서 작동하도록 구성할 수 있습니다.](/windows/security/threat-protection)

Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합하면 보안 운영 팀이 사용자의 장치가 위험에 노출될 경우 신속하게 조치를 취할 수 있습니다. 예를 들어 통합이 사용하도록 설정되면 보안 운영 팀은 감지된 전자 메일 메시지의 영향을 받을 수 있는 장치와 끝점용 Microsoft Defender에서 해당 장치에 대해 생성된 최근 알림 수를 볼 수 있습니다.

다음 이미지는 끝점용 Microsoft Defender 통합을 사용하도록 설정한 경우 장치 탭의 모양을 나타났습니다. 

![끝점용 Microsoft Defender를 사용하도록 설정하면 경고가 있는 장치 목록을 볼 수 있습니다.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

이 예에서는 감지된 전자 메일 메시지의 받는 사람에게 4개의 장치가 있으며, 다른 하나는 경고를 표시하는지 볼 수 있습니다. 디바이스에 대한 링크를 클릭하면 Microsoft 365 [Defender(이전의](../defender-endpoint/microsoft-defender-security-center.md) Microsoft Defender 보안 센터) 페이지가 열립니다.

> [!TIP]
> Microsoft 365 Defender 포털은 Microsoft Defender 보안 센터. [Defender의 끝점에 대한 Microsoft Defender를 Microsoft 365 참조합니다.](../defender/microsoft-365-security-center-mde.md)

## <a name="requirements"></a>요구 사항

- 조직에 Microsoft Defender for Office 365(또는 E5용)Office 365 Microsoft Defender가 있어야 합니다.

- 전역 관리자 또는 보안 관리자 역할(예: 보안 관리자)이 Microsoft 365. (보안 [및 준수 센터의 & 참조)](permissions-in-the-security-and-compliance-center.md)

- 탐색기(또는 실시간 [검색)에 액세스할 수 있어야 합니다.](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합

Microsoft Defender for Office 365 끝점용 Microsoft Defender와 통합은 Endpoint용 Defender 및 365용 Defender에서 Office 365.

1. 전역 관리자 또는 보안 관리자로 이동하여 [https://protection.office.com](https://protection.office.com) 로그인합니다. (이 경우 Office 365 보안 & 센터로 진행됩니다.)

2. 탐색 창에서 위협 관리 **탐색기를** \> **선택 합니다.**

   ![위협 관리 메뉴의 탐색기](../../media/ThreatMgmt-Explorer-nav.png)

3. In the upper right corner of the screen, choose **Defender for Endpoint 설정 (MDE 설정)**.

4. 끝점 연결용 Microsoft Defender 대화 상자에서 **끝점용 Microsoft Defender에 커넥트 를 으로 전환합니다.**

   ![끝점 연결용 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)

5. Defender Microsoft 365(로 [https://security.microsoft.com](https://security.microsoft.com) 이동).

6. 탐색 모음에서 를 **설정.** 그런 다음 **일반에서** 고급 기능을 **선택 합니다.**

7. 아래로 스크롤하여 **Office 365 위협 인텔리전스** 연결을 으로 전환합니다.

   ![Office 365 인텔리전스 연결](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>관련 문서

[보안 위협 조사 및 대응 Office 365](office-365-ti.md)

[Office 365용 Microsoft Defender](defender-for-office-365.md)

[엔드포인트용 Microsoft Defender](/windows/security/threat-protection)
