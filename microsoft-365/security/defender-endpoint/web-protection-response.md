---
title: Microsoft Defender ATP의 웹 위협에 대응
description: 악성 및 원치 않는 웹 사이트와 관련된 경고에 응답합니다. 웹 위협 방지가 최종 사용자에게 웹 브라우저 및 Windows 알림을 통해 알리는 방법 이해
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 경고, 응답, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저, 알림, 최종 사용자, Windows 알림, 차단 페이지,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 339944b94ca55c5d73fafaabfe3f7bc26dafe7bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071716"
---
# <a name="respond-to-web-threats"></a>웹 위협에 대응

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

끝점용 Microsoft Defender의 웹 보호를 사용하면 사용자 지정 표시기 목록에서 악성 웹 사이트 및 웹 사이트와 관련된 경고를 효율적으로 조사하고 대응할 수 있습니다.

## <a name="view-web-threat-alerts"></a>웹 위협 경고 보기
끝점용 Microsoft Defender는 [](manage-alerts.md) 악성 또는 의심스러운 웹 활동에 대해 다음 경고를 생성합니다.
- **네트워크 보호로** 차단된 의심스러운 연결 - 이 경고는 차단 모드에서 네트워크 보호에 의해 사용자  지정 표시기 목록의 악성 웹 사이트 또는 웹 사이트에 액세스하려는 시도가 중지될 때 *생성됩니다.*
- **네트워크 보호에서** 감지된 의심스러운 연결 - 이 경고는 감사 전용 모드에서 네트워크 보호에 의해 사용자 지정 표시기 목록의 악성 웹 사이트 또는 웹 사이트에 액세스하려고 시도할 때 *생성됩니다.*

각 경고는 다음 정보를 제공합니다. 
- 차단된 웹 사이트에 액세스하려고 시도한 장치
- 웹 요청을 보내는 데 사용되는 응용 프로그램 또는 프로그램
- 사용자 지정 표시기 목록의 악의적인 URL 또는 URL
- 응답자에 대한 권장 작업

![웹 위협 방지와 관련된 경고 이미지](images/wtp-alert.png)

>[!Note]
>경고 볼륨을 줄이기 위해 끝점용 Microsoft Defender는 매일 동일한 장치에서 동일한 도메인에 대한 웹 위협 감지를 단일 경고로 통합합니다. 하나의 경고만 생성되어 웹 보호 보고서 [에 계산됩니다.](web-protection-monitoring.md)

## <a name="inspect-website-details"></a>웹 사이트 세부 정보 검사
경고에서 웹 사이트의 URL 또는 도메인을 선택하여 더 깊이 있는 검색을 할 수 있습니다. 그러면 다음을 비롯한 다양한 정보가 있는 해당 특정 URL 또는 도메인에 대한 페이지가 열립니다.
- 웹 사이트에 액세스하려고 시도한 장치
- 웹 사이트와 관련된 인시던트 및 알림
- 조직의 이벤트에 웹 사이트가 얼마나 자주 나타날 수 있습니다.

    ![도메인 또는 URL 엔터티 세부 정보 페이지의 이미지](images/wtp-website-details.png)

[URL 또는 도메인 엔터티 페이지에 대해 자세히 알아보세요.](investigate-domain.md)

## <a name="inspect-the-device"></a>장치 검사
차단된 URL에 액세스하려고 시도한 장치를 확인할 수 있습니다. 경고 페이지에서 디바이스 이름을 선택하면 장치에 대한 포괄적인 정보가 있는 페이지가 열립니다.

[장치 엔터티 페이지에 대한 자세한 내용은](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>최종 사용자를 위한 웹 브라우저 및 Windows 알림

Endpoint용 Microsoft Defender의 웹 보호를 통해 최종 사용자는 Microsoft Edge 또는 기타 브라우저를 사용하여 악성 또는 원치 않는 웹 사이트를 방문하지 못하게 됩니다. 차단은 네트워크 보호에서 [수행하기](network-protection.md)때문에 웹 브라우저에서 일반 오류가 표시됩니다. 또한 Windows에서 알림이 표시됩니다.

![Microsoft Edge에서 403 오류 및 Windows 알림 웹 위협이 ](images/wtp-browser-blocking-page.png)
 *차단된 Microsoft Edge의 이미지*

![Chrome에서 보안 연결 경고 및 Windows 알림 웹 위협이 차단된 Chrome 웹 ](images/wtp-chrome-browser-blocking-page.png)
 *브라우저의 이미지*

## <a name="related-topics"></a>관련 항목
- [웹 보호 개요](web-protection-overview.md)
- [웹 콘텐츠 필터링](web-content-filtering.md)
- [웹 위협 방지](web-threat-protection.md)
- [웹 보안 모니터링](web-protection-monitoring.md)
