---
title: 지표 만들기
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
ms.openlocfilehash: c12e832fbbe1628593cbfee4d861803ac1b513b7
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2021
ms.locfileid: "58354371"
---
# <a name="create-indicators"></a>지표 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

IoC(손상 표시기) 일치는 모든 끝점 보호 솔루션에서 필수적인 기능입니다. SecOps는 이 기능을 통해 검색 및 차단(예방 및 응답)에 대한 표시기 목록을 설정할 수 있습니다.

엔터티의 검색, 방지 및 제외를 정의하는 표시기를 만들 수 있습니다. 수행되는 작업과 작업을 적용할 기간 및 적용할 장치 그룹의 범위를 정의할 수 있습니다.

현재 지원되는 원본은 Endpoint용 Defender의 클라우드 검색 엔진, 자동화된 조사 및 수정 엔진 및 끝점 방지 엔진(Microsoft Defender 바이러스 백신)입니다.

**클라우드 검색 엔진**<br>
Endpoint용 Defender의 클라우드 검색 엔진은 정기적으로 수집된 데이터를 검색하고 설정한 지표와 일치를 합니다. 일치하는 경우 IoC에 대해 지정한 설정에 따라 작업이 수행됩니다.

**끝점 방지 엔진**<br>
동일한 표시기 목록은 방지 에이전트에 의해 존중됩니다. 즉, Microsoft Defender AV가 구성된 기본 AV인 경우 일치하는 표시기가 설정에 따라 처리됩니다. 예를 들어 작업이 "경고 및 차단"이면 Microsoft Defender AV는 파일 실행(차단 및 재구성)을 방지하고 해당 경고가 발생됩니다. 반면 동작이 "허용"으로 설정된 경우 Microsoft Defender AV는 파일을 검색하거나 실행하지 못하도록 차단하지 않습니다.

**자동화된 조사 및 수정 엔진**<BR>
자동화된 조사 및 수정은 동일하게 행동합니다. 표시기가 "허용"으로 설정된 경우 자동화된 조사 및 수정은 해당 지표에 대한 "나쁜" 판정을 무시합니다. "차단"으로 설정된 경우 자동화된 조사 및 수정은 이를 "불량"으로 취급합니다.

> [!NOTE]
> EnableFileHashComputation 설정은 파일 검색 중에 인증 및 파일 IoC에 대한 파일 해시를 계산합니다. 신뢰할 수 있는 응용 프로그램에 속하는 해시 및 인증의 IoC 적용을 지원합니다. 이 설정은 파일 허용 또는 차단 설정과 함께 동시 사용 및 사용하지 않도록 설정됩니다. EnableFileHashComputation은 그룹 정책을 통해 수동으로 사용하도록 설정되어 있으며 기본적으로 사용하지 않도록 설정됩니다.


현재 지원되는 작업은 다음입니다.
- 허용
- 경고만
- 경고 및 차단
- 경고


>[!NOTE]
> 경고 모드를 사용하면 위험한 앱을 여는 경우 경고 메시지가 표시됩니다. 프롬프트는 앱을 사용하지 못하도록 차단하지 않지만 앱의 적절한 사용법을 설명하는 회사 페이지에 대한 사용자 지정 메시지와 링크를 제공할 수 있습니다. 사용자는 여전히 경고를 무시하고 필요한 경우 앱을 계속 사용할 수 있습니다. 자세한 내용은 [Endpoint용 Microsoft Defender에서](/cloud-app-security/mde-govern)검색한 앱 관리 를 참조하세요.


다음에 대한 표시기를 만들 수 있습니다.
- [파일](indicator-file.md)
- [IP 주소, URL/도메인](indicator-ip-domain.md)
- [인증서](indicator-certificates.md)


> [!NOTE]
> 테넌트당 표시기는 15,000개로 제한됩니다. 파일 및 인증서 표시기는 에 정의된 제외를 [차단하지 Microsoft Defender 바이러스 백신.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) 수동 모드에서는 Microsoft Defender 바이러스 백신 지원되지 않습니다. 


## <a name="related-topics"></a>관련 항목

- [상황적 IoC 만들기](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [끝점 표시기 API에 Microsoft Defender 사용](ti-indicator.md)
- [파트너 통합 솔루션 사용](partner-applications.md)
