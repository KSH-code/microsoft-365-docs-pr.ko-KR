---
title: 2016년 8월 Microsoft 365 Defender
description: 2013에서 자동화된 조사를 따르는 수정 작업의 개요를 Microsoft 365 Defender
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: da12be831aa93032b5d087d36e551df0f6370560
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191518"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>2016년 8월 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

2016에서 자동화된 조사를 Microsoft 365 Defender 또는 의심스러운 항목에 대해 수정 작업이 식별됩니다. 일부 종류의 수정 작업은 끝점이라고도 하는 장치에서 수행됩니다. 기타 수정 작업은 전자 메일 콘텐츠에 대해 수행됩니다. 재구성 작업을 수행, 승인 또는 거부한 후에 자동화된 조사가 완료됩니다.

> [!IMPORTANT]
> 재구성 작업이 자동으로 수행될지 승인에만 수행될지는 자동화 수준과 같은 특정 설정에 따라 결정됩니다. 자세한 내용은 다음 문서를 참조합니다.
> - [2013에서 자동화된 조사 및 대응 기능을 Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [장치에서 위협을 수정하는 방법](../defender-endpoint/automated-investigations.md)
> - [전자 메일 및 공동 작업 콘텐츠에 & 수정 작업](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

다음 표에는 현재 2013에서 지원되는 수정 작업이 Microsoft 365 Defender. 

|장치(끝점) 수정 작업  |전자 메일 수정 작업  |
|:---------|:---------|
|- 조사 패키지 수집 <br/>- 장치 격리(이 작업은 실행을 엽니다.)<br/>- 컴퓨터 오프보드 <br/>- 릴리스 코드 실행 <br/>- 릴리스 <br/>- 샘플 요청 <br/>- 코드 실행 제한(이 작업은 실행을 실행 중지할 수 있습니다. <br/>- 바이러스 백신 검사 실행 <br/>- 중지 및 검사      |- 차단 URL(클릭 시간)<br/>- 전자 메일 메시지 또는 클러스터를 소프트 삭제<br/>- 전자 메일 검지<br/>- 전자 메일 첨부 파일 Quarantine<br/>- 외부 메일 전달 끄기          |

승인 보류 중이든 이미 완료 상태든 재구성 작업은 관리 센터 에서 볼 [수 있습니다.](m365d-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>자동화된 조사를 따르는 수정 작업

자동화된 조사가 완료되면 관련된 모든 증거에 대한 판결에 도달합니다. 판정에 따라 수정 작업이 식별됩니다. 경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다. 자동화된 조사 및 응답이 구성된 방식에 [따라 모두 에 따라 다를 수 있습니다.](m365d-configure-auto-investigation-response.md)

도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. 

| 의견    | 영향을 받는 엔터티    | 결과|
|------|------|------|
| 악성    | 장치 (끝점)    | 재구성 작업이 자동으로 수행됩니다(조직의 장치 그룹이 전체 - 자동으로 위협 수정으로 설정되어 있는 **경우)** [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)|
| 악성    | 전자 메일 콘텐츠 (Url 또는 첨부 파일) | 승인 보류 중인 재구성 활동 |
| 피싱    | 장치 또는 전자 메일 콘텐츠 | 승인 보류 중인 재구성 활동 |
| 위협이 발견되지 않음    | 장치 또는 전자 메일 콘텐츠    | 재구성 작업이 필요 하지 않습니다.|


## <a name="remediation-actions-that-are-taken-manually"></a>수동으로 수행한 수정 작업

자동화된 조사를 따르는 수정 작업 외에도 보안 운영 팀은 특정 수정 작업을 수동으로 수행할 수 있습니다. 이러한 경계 및 제한은 다음과 같습니다.

- 장치 고리 또는 파일 검지와 같은 수동 장치 작업
- 수동 전자 메일 작업(예: 전자 메일 메시지 소프트 삭제) 
- [장치 또는 전자](../defender-endpoint/advanced-hunting-overview.md) 메일에 대한 고급 헌팅 작업
- [전자](../office-365-security/threat-explorer.md) 메일 콘텐츠에 대한 탐색기 작업(예: 정크 메일로 이동, 전자 메일 소프트 삭제 또는 하드 삭제 전자 메일)
- 파일 [삭제,](/windows/security/threat-protection/microsoft-defender-atp/live-response) 프로세스 중지, 예약된 작업 제거와 같은 수동 실시간 응답 작업
- [Microsoft Defender for Endpoint API를](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)사용하여 실시간 응답 작업(예: 장치 차단, 바이러스 백신 검사 실행, 파일에 대한 정보 수집)

## <a name="next-steps"></a>다음 단계

- [알림 센터 방문](m365d-action-center.md)
- [수정 작업 보기 및 관리](m365d-autoir-actions.md)
- [가짓 긍정 또는 거짓 부정 해결](m365d-autoir-report-false-positives-negatives.md)
