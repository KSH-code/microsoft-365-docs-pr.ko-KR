---
title: 표시기 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시, IP 주소, URL 또는 도메인에 대한 표시기를 만들 수 있습니다.
keywords: 관리, 허용, 차단, 차단, 클린, 악성, 파일 해시, ip 주소, URL, 도메인
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
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198836"
---
# <a name="create-indicators"></a>표시기 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

IoC(손상 표시기) 일치는 모든 끝점 보호 솔루션에서 필수적인 기능입니다. SecOps는 이 기능을 통해 검색 및 차단(예방 및 응답)에 대한 표시기 목록을 설정할 수 있습니다.

엔터티의 검색, 방지 및 제외를 정의하는 표시기를 만들 수 있습니다. 수행되는 작업과 작업을 적용할 기간 및 적용할 장치 그룹의 범위를 정의할 수 있습니다.

현재 지원되는 원본은 Endpoint용 Defender의 클라우드 검색 엔진, 자동화된 조사 및 수정 엔진 및 끝점 방지 엔진(Microsoft Defender 바이러스 백신)입니다.

**클라우드 검색 엔진**<br>
Endpoint용 Defender의 클라우드 검색 엔진은 정기적으로 수집된 데이터를 검색하고 설정한 지표와 일치를 합니다. 일치하는 경우 IoC에 대해 지정한 설정에 따라 작업이 수행됩니다.

**끝점 방지 엔진**<br>
동일한 표시기 목록은 방지 에이전트에 의해 존중됩니다. 즉, Microsoft Defender AV가 구성된 기본 AV인 경우 일치하는 표시기가 설정에 따라 처리됩니다. 예를 들어 작업이 "경고 및 차단"이면 Microsoft Defender AV는 파일 실행(차단 및 재구성)을 방지하고 해당 경고가 발생됩니다. 반면 동작이 "허용"으로 설정된 경우 Microsoft Defender AV는 파일을 검색하거나 실행하지 못하도록 차단하지 않습니다.

**자동화된 조사 및 수정 엔진**<BR>
자동화된 조사 및 수정은 동일하게 행동합니다. 표시기가 "허용"으로 설정된 경우 자동화된 조사 및 수정은 해당 지표에 대한 "나쁜" 판정을 무시합니다. "차단"으로 설정된 경우 자동화된 조사 및 수정은 이를 "불량"으로 취급합니다.


현재 지원되는 작업은 다음입니다.
- 허용
- 경고만
- 경고 및 차단


다음에 대한 표시기를 만들 수 있습니다.
- [파일](indicator-file.md)
- [IP 주소, URL/도메인](indicator-ip-domain.md)
- [인증서](indicator-certificates.md)


> [!NOTE]
> 테넌트당 표시기는 15,000개로 제한됩니다. 파일 및 인증서 표시기는 Microsoft Defender 바이러스 백신에 정의된 제외를 [차단하지 않습니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) Microsoft Defender 바이러스 백신에서 지원되지 않는 표시기는 수동 모드입니다. 


## <a name="related-topics"></a>관련 항목

- [상황적 IoC 만들기](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [끝점 표시기 API에 Microsoft Defender 사용](ti-indicator.md)
- [파트너 통합 솔루션 사용](partner-applications.md)
