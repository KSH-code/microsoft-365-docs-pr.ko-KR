---
title: Microsoft Cloud App Security 통합 구성
ms.reviewer: ''
description: Microsoft Cloud App Security와 끝점에 Microsoft Defender를 통합할 수 있도록 설정을 설정하는 방법을 학습합니다.
keywords: 클라우드, 앱, 보안, 설정, 통합, 검색, 보고서
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f5e2919ae3fcbbb443f6d160c68633ee3427ae5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187532"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 Microsoft Cloud App Security 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Endpoint 클라우드 앱 검색 신호에 대한 Microsoft Defender의 이점을 활용하기 위해 Microsoft Cloud App Security 통합을 켜야 합니다.

>[!NOTE]
>이 기능은 Windows 10 버전 1709(OS 빌드 16299.1085 및 [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10을 실행하는 장치에서 [Enterprise Mobility + Security에](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) 대한 E5 라이선스로 사용할 수 있습니다. 버전 1803(OS 빌드 17134.704 [및 KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, 버전 1809(OS 빌드 17763.379( [KB4489899)](https://support.microsoft.com/help/4489899)이상 Windows 10 버전.

> [끝점용 Microsoft Defender와 Microsoft Cloud App Security의](https://docs.microsoft.com/cloud-app-security/mde-integration) 자세한 통합은 Microsoft Cloud App Security와의 끝점용 Microsoft Defender 통합을 참조하세요. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>끝점에 대해 Microsoft Defender에서 Microsoft Cloud App Security 사용

1. 탐색 창에서 기본 **설정** 고급 기능  >  **을 선택합니다.**
2. **Microsoft Cloud App Security를 선택하고** 토글을 켜기 로 **전환합니다.**
3. 기본 **설정 저장을 클릭합니다.**

활성화되면 끝점용 Microsoft Defender는 즉시 검색 신호를 Cloud App Security에 전달하기 시작합니다.

## <a name="view-the-data-collected"></a>수집된 데이터 보기

Microsoft Cloud Apps Security에서 끝점용 Microsoft Defender 데이터를 보고 액세스하는 경우 [Cloud App Security에서 장치 조사를 참조하세요.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)


클라우드 검색에 대한 자세한 내용은 검색된 앱 [작업을 참조하세요.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

Microsoft Cloud App Security를 사용해 보시고자 하는 경우 [Microsoft Cloud App Security Trial 을 참조하세요.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)

## <a name="related-topic"></a>관련 항목
- [Microsoft Cloud App Security 통합](microsoft-cloud-app-security-integration.md)
