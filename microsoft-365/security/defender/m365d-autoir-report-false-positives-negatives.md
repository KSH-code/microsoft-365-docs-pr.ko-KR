---
title: Defender에서 AIR에서 가긍성 또는 Microsoft 365 처리
description: Defender에서 AIR에서 누락되거나 잘못 감지된 Microsoft 365 있나요? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 727ca529dc1a16af778e01a08c9adcfe42b9b974
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245471"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

가짓 긍정/음수는 경우에 따라 위협 방지 솔루션에서 발생할 수 있습니다. [Defender에서](m365d-autoir.md) 누락되거나 잘못 감지된 Microsoft 365 자동화된 조사 및 대응 기능이 있는 경우 보안 운영 팀이 취할 수 있는 단계가 있습니다.

- [Microsoft에 가짓 긍정/음수 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및 
- [장치에서 수행된 수정 작업을 취소합니다.](#undo-a-remediation-action-that-was-taken-on-a-device) 

다음 섹션에서는 이러한 작업을 수행하는 방법에 대해 설명합니다.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 가짓 긍정/음수 보고

|누락되거나 잘못 검색된 항목 |서비스  |수행할 작업  |
|---------|---------|---------|
|- 전자 메일 메시지 <br/>- 전자 메일 첨부 파일 <br/>- 전자 메일 메시지의 URL<br/>- Office URL      |[Office 365용 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365)        |[검색을 위해 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출](../office-365-security/admin-submission.md)         |
|디바이스의 파일 또는 앱    |[엔드포인트용 Microsoft Defender](/windows/security/threat-protection)         |[맬웨어 분석을 위해 Microsoft에 파일 제출](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>가식이 재발하지 않도록 경고 조정

|시나리오 |서비스 |수행할 작업 |
|--------|--------|--------|
|- 합법적인 사용에 의해 경고가 트리거됩니다. <br/>- 경고가 부정확합니다.    |[Microsoft Cloud App Security](/cloud-app-security)<br/> 또는 <br/>[Azure Advanced Threat Detection](/azure/security/fundamentals/threat-detection)         |[사이트 포털에서 Cloud App Security 관리](/cloud-app-security/managing-alerts)         |
|안전한 경우에도 파일, IP 주소, URL 또는 도메인이 장치에서 맬웨어로 처리됩니다.|[엔드포인트용 Microsoft Defender](/windows/security/threat-protection) |["허용" 작업을 사용하여 사용자 지정 표시기 만들기](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>장치에서 수행된 수정 작업 실행 취소

엔터티에 대해 수정 작업이 수행된 경우(예: 장치 또는 전자 메일 메시지) 영향을 받는 엔터티가 실제로 위협이 아닌 경우 보안 운영 팀은 알림 센터에서 수정 작업을 실행 취소할 [수 있습니다.](m365d-action-center.md)

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 
2. 탐색 창에서 **작업 센터** 를 선택합니다. 
3. 사용 **기록 탭에서** 실행 취소할 작업을 선택합니다. 플라이아웃 창이 열립니다.
4. 플라이아웃 창에서 **취소를 선택합니다.**

> [!TIP]
> 완료된 [작업 취소를 참조합니다.](m365d-autoir-actions.md#undo-completed-actions)

## <a name="see-also"></a>참고 항목

- [자동화 조사 세부정보 및 결과 보기](m365d-autoir-results.md)
- [Defender에서 고급 헌팅을 통해 위협을 Microsoft 365 헌팅](advanced-hunting-overview.md)
- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)