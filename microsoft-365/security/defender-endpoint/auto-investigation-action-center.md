---
title: 관리 센터를 방문하여 수정 작업 보기
description: 관리 센터를 사용하여 자동화된 조사 후 세부 정보 및 결과 보기
keywords: action, center, autoir, automated, investigation, response, remediation
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: a22850b6bc668e62e8db98884f61d264b529df79
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963153"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>관리 센터를 방문하여 수정 작업 보기

자동화된 조사가 진행되는 동안 및 이후에 위협 감지에 대한 수정 작업이 식별됩니다. 특정 위협 및 조직에 대해 [Microsoft Defender for Endpoint가](/windows/security/threat-protection) 구성된 방식에 따라 일부 수정 작업이 자동으로 수행되고 다른 작업은 승인을 요구합니다. 조직의 보안 운영 팀에 참여하는 경우 관리 센터에서 보류 중 [](manage-auto-investigation.md#remediation-actions) 및 완료된 수정 작업을 볼 **수 있습니다.**


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!) 통합된 동작 센터


새로운 통합된 통합 동작 센터( )를 발표하게 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 됩니다.

:::image type="content" source="images/mde-action-center-unified.png" alt-text="보안 센터의 Microsoft 365 센터.":::

다음 표에서는 새로운 통합된 작업 센터와 이전 작업 센터를 비교합니다.

|새로운 통합된 동작 센터  |이전 작업 센터  |
|---------|---------|
|장치 및 전자 메일에 대해 보류 중인 작업과 완료된 작업을 한 위치에 나열합니다. <br/>([Endpoint용 Microsoft Defender와](microsoft-defender-endpoint.md) [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))|장치에 대한 보류 중인 작업 및 완료된 작업 목록 <br/> [(끝점용 Microsoft Defender만 해당)](microsoft-defender-endpoint.md)   |
|에 있습니다.<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |에 있습니다.<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 에서</a>관리 **센터 를 선택 합니다.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="보안 센터의 관리 센터로 Microsoft 365."::: | In the Microsoft Defender 보안 센터, choose **Automated investigations**  >  **Action center**. <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Microsoft Defender 보안 센터.":::  |

통합 관리 센터는 Endpoint용 Defender 및 2016용 Defender에 대한 수정 Office 365. 모든 수정 작업에 대한 공통 언어를 정의하고 통합 조사 환경을 제공합니다.

적절한 사용 권한 및 다음 구독 중 하나 이상이 있는 경우 통합 관리 센터를 사용할 수 있습니다.

- [엔드포인트용 Defender](microsoft-defender-endpoint.md)
- [Office 365용 Defender](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection)

> [!TIP]
> 자세한 내용은 요구 사항을 [참조하세요.](/microsoft-365/security/mtp/prerequisites)

## <a name="using-the-action-center"></a>동작 센터 사용

향상된 보안 센터의 통합 Microsoft 365:

1. 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">센터로 Microsoft 365 로그인합니다.</a>
2. 탐색 창에서 작업 센터 **를 선택합니다.**

작업 센터를 방문하면 보류 중인 작업 및 **기록의 두 개의 탭이** **표시됩니다.** 다음 표에서는 각 탭에 표시하는 내용을 요약하여 제공합니다.

|Tab|설명|
|---|---|
|**보류 중**|주의가 필요한 작업 목록을 표시합니다. 작업을 한 번씩 승인하거나 거부하거나 동일한 유형의 작업(예: 파일 **Quarantine file)이** 있는 경우 여러 작업을 선택할 수 있습니다. <p> **팁:** 자동화된 [](manage-auto-investigation.md) 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인(또는 거부)해야 합니다.|
|**기록**|다음을 수행한 작업에 대한 감사 로그 역할을 합니다. <ul><li>자동화된 조사의 결과로 수행된 수정 작업</li><li>보안 운영 팀에서 승인한 수정 작업</li><li>라이브 응답 세션 중에 적용된 실행된 명령 및 수정 작업</li><li>위협 방지 기능에서 수행한 수정 Microsoft Defender 바이러스 백신</li></ul> <p> 특정 작업을 취소하는 방법을 제공합니다(완료된 작업 취소 [참조).](manage-auto-investigation.md#undo-completed-actions)|

관리 센터에서 데이터를 사용자 지정, 정렬, 필터링 및 내보낼 수 있습니다.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="작업 센터의 열 및 필터입니다.":::

- 열 제목을 선택하여 항목을 오차 또는 내선 순서로 정렬합니다.
- 기간 필터를 사용하여 지난 일, 주, 30일 또는 6개월의 데이터를 볼 수 있습니다.
- 보하려는 열을 선택 합니다.
- 각 데이터 페이지에 포함할 항목 수를 지정합니다.
- 필터를 사용하여 보 원하는 항목만 볼 수 있습니다.
- 내보내기 **를** 선택하여 결과를 파일로 .csv 선택합니다.

## <a name="next-steps"></a>다음 단계

- [수정 조치 보기 및 승인](manage-auto-investigation.md)
- [대화형 가이드를 참조하세요. Endpoint용 Microsoft Defender로 위협 조사 및 수정](https://aka.ms/MDATP-IR-Interactive-Guide)

## <a name="see-also"></a>참고 항목

- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)
