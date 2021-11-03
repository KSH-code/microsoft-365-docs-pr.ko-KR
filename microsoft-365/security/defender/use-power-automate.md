---
title: Power Automate 사용
description: Power Automate in Microsoft 365 Defender 방법과 사용 방법에 대해 자세히 알아보습니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, secops
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a707de259897080f8e726aed70618ea6505bdea6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717529"
---
# <a name="use-power-automate-in-microsoft-365-defender"></a>이 Power Automate Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험하고 싶으신가요? [실험실 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

최신 보안 운영(SecOps) 팀은 효율적으로 작동하려면 자동화가 필요합니다. SecOps 팀은 실제 위협을 헌팅하고 조사하는 데 집중하기 위해 Power Automate 목록을 조사하고 위협이 아닌 경고 목록을 제거합니다.  

## <a name="criteria-for-resolving-alerts"></a>경고를 해소하기 위한 조건

- 사용자에게 부재 중 메시지가 켜져 있습니다.

- 사용자가 높은 위험으로 태그가 지정되지 않습니다.

둘 다 참이면 SecOps는 경고를 합법적인 출장으로 표시하고 해결합니다. 알림이 해결된 Microsoft Teams 게시됩니다. 

## <a name="connect-power-automate-to-microsoft-cloud-app-security"></a>커넥트 Power Automate Microsoft Cloud App Security

자동화를 만들기 위해 API 토큰이 필요하면 API 토큰을 POWER AUTOMATE(MCAS)Microsoft Cloud App Security 수 있습니다. 

1. 다음 **설정** 를 클릭하고 보안 확장을  **선택한** 다음 API 토큰 탭에서 토큰 **추가를** 클릭합니다. 

2. 토큰의 이름을 입력한 다음 생성을 **클릭합니다.** 나중에 필요할 때 토큰을 저장합니다.

## <a name="create-an-automated-flow"></a>자동화된 흐름 만들기

자세한 단계별 프로세스는 여기에서 비디오를 [참조하세요.](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn) 

이 비디오에서는 전원 자동화를 MCAS에 연결하는 방법도 설명합니다. 

## <a name="related-information"></a>관련 정보

- [통합 Power Automate 통합 Microsoft Cloud App Security](/cloud-app-security/flow-integration)

- [Microsoft Power Automate 설명서](/power-automate)
