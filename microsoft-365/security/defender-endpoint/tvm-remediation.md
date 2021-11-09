---
title: 보안 문제를 해결하여 취약성 위협 및 취약성 관리
description: 보안 권장 사항을 통해 발견된 보안 약점을 수정하고 필요한 경우 예외를 위협 및 취약성 관리.
keywords: Microsoft Defender for Endpoint tvmmediation, Microsoft Defender for Endpoint tvm, 위협 및 취약성 관리, threat & 취약성 관리, threat & 취약성 관리 remediation, tvm remediation intune, tvm remediation sccm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8126021051f939a08fb0ea5ef6bd07d8f67c1662
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883404"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>보안 문제를 해결하여 취약성 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>요청 수정

끝점용 Microsoft Defender의 위협 및 취약성 관리 기능은 업데이트 관리 요청 워크플로를 통해 보안 관리자와 IT 관리자 간의 격차를 해소합니다. 보안 관리자는 IT 관리자에게 보안 권장 페이지에서 Intune으로의  취약점 수정을 요청할 수 있습니다.

### <a name="enable-microsoft-intune-connection"></a>연결 Microsoft Intune 사용

이 기능을 사용하려면 사용자 Microsoft Intune 사용하도록 설정해야 합니다. Microsoft 365 Defender 포털에서 일반 고급 **설정** \>  \> **로 이동합니다.** 아래로 스크롤하여 연결 **Microsoft Intune 확인합니다.** 기본적으로 토글은 꺼져 있습니다. 사용자 Microsoft Intune **켜기** **토글합니다.**

**참고:** Intune 연결을 사용하도록 설정한 경우 수정 요청을 만들 때 Intune 보안 작업을 만드는 옵션이 제공됩니다. 연결이 설정되어 있지 않은 경우 이 옵션이 나타나지 않습니다.

자세한 [내용은 Intune을 사용하여 끝점용 Microsoft Defender로](/intune/atp-manage-vulnerabilities) 식별된 취약점 수정을 참조합니다.

### <a name="remediation-request-steps"></a>재구성 요청 단계

1. Microsoft 365 Defender **포털에서** 위협 및 취약성 관리 탐색 메뉴로  이동하고 보안 권장 사항 [**선택합니다.**](tvm-security-recommendation.md)

2. 재구성 요청을 할 보안 권장을 선택한 다음 수정 옵션을 **선택합니다.**

3. 수정을 요청하는 사항, 해당 장치 그룹, 우선 순위, 기한 및 선택적 메모를 포함하여 양식을 작성합니다.
    1. "주의 필요" 수정 옵션을 선택하는 경우 특정 작업이 아니기 때문에 기한을 선택할 수 없습니다.

4. 요청 **제출을 선택합니다.** 재구성 요청을 제출하면 이 권장 위협 및 취약성 관리 재구성 진행 상황을 모니터링하는 데 사용할 수 있는 재구성 활동 항목이 생성됩니다. 이렇게 하면 수정이 트리거되거나 장치에 변경 내용이 적용되지 않습니다.

5. IT 관리자에게 새 요청을 알리고 Intune에 로그인하여 요청을 승인하거나 거부하고 패키지 배포를 시작하게 합니다.

6. [**재구성 페이지로 이동하여**](tvm-remediation.md) 재구성 요청의 상태를 시청하세요.

Intune에서 티켓이 어떻게 표시하는지 확인하려는 경우 [Intune을 사용하여 끝점용 Microsoft Defender로](/intune/atp-manage-vulnerabilities) 식별된 취약점 수정을 참조하세요.

> [!NOTE]
> 요청에 10,000개가 넘는 장치를 수정해야 하는 경우 수정을 위해 10,000개가 넘는 장치만 Intune에 보낼 수 있습니다.

조직의 사이버 보안 약점을 식별하고 실행 가능한 보안 권장 사항에 매핑한 후 [보안](tvm-security-recommendation.md)작업 만들기를 시작하세요. 재구성 티켓이 만들어진 위치와 통합하여 Microsoft Intune 만들 수 있습니다.

보안 권장 사항을 수정하여 취약성에 대한 조직의 노출을 낮추고 보안 구성을 강화합니다.

## <a name="view-your-remediation-activities"></a>재구성 활동 보기

보안 권장 사항 페이지에서 재구성 요청을 제출하면 수정 활동이 시작됩니다. 업데이트 관리 페이지에서 추적할 수 있는 보안  작업이 위협 및 취약성 관리 업데이트 관리 페이지에서 업데이트 관리 티켓이 Microsoft Intune.

"주의 필요" 수정 옵션을 선택한 경우 모니터링할 수 있는 실제 작업이 아니기 때문에 진행률 표시줄, 티켓 상태 또는 기한이 없습니다.

재구성 페이지에 있는 경우 보게 할 수정 활동을 선택합니다. 재구성 단계를 따르거나 진행 상황을 추적하거나 관련 권장 지침을 보거나 CSV로 내보내거나 완료로 표시할 수 있습니다.

:::image type="content" source="../../media/remediation-flyouteolswnew.png" lightbox="../../media/remediation-flyouteolswnew.png" alt-text="선택한 수정 활동이 있는 재구성 페이지의 예와 해당 활동의 플라이아웃에 설명, IT 서비스 및 장치 관리 도구, 장치 수정이 나열됩니다.":::

> [!NOTE]
> 완료된 재구성 활동에 대한 보존 기간은 180일입니다. 재구성 페이지를 최적으로 유지하기 위해 재구성 활동은 완료 후 6개월 후에 제거됩니다.

### <a name="completed-by-column"></a>완료한 열

재구성 페이지의 "완료한 사람" 열을 통해 재구성 활동을 닫은 사람 추적

- **전자 메일 주소:** 작업을 수동으로 완료한 사람의 전자 메일입니다.
- **시스템 확인:** 작업이 자동으로 완료되었습니다(모든 장치 수정).
- **해당 이전** 작업의 완료 방법을 모르는 경우: 정보를 사용할 수 없습니다.

:::image type="content" alt-text="행이 두 개 있는 열에 의해 만들어지며 완료됩니다. 완료한 행의 한 행에는 전자 메일의 예가, 다른 행에는 시스템 확인이 표시됩니다." source="images/tvm-completed-by.png":::

### <a name="top-remediation-activities-in-the-dashboard"></a>대시보드의 상위 수정 활동

위협 **및 취약성** 관리 대시보드에서 상위 수정 [활동을 볼 **수** 있습니다.](tvm-dashboard-insights.md) 수정 페이지로 이동하려면 항목을 **선택합니다.** IT 관리자 팀이 작업을 수정한 후 재구성 활동을 완료된 것으로 표시하면 됩니다.

![보안 권장 사항에서 생성된 주요 활동을 나열하는 표가 있는 상위 수정 활동 카드의 예](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>관련 문서

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [대시보드](tvm-dashboard-insights.md)
- [보안 권장 사항](tvm-security-recommendation.md)