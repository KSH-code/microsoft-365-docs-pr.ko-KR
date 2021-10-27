---
title: 2013에서 경고 Microsoft 365 Defender
description: 여러 장치, 사용자 및 사서함에 걸쳐 경고를 조사합니다.
keywords: 인시던트, 경고, 조사, 분석, 대응, 상관 관계, 공격, 컴퓨터, 장치, 사용자, ID, ID, 사서함, 전자 메일, 365, Microsoft, m365
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
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 92542fdeebd5e6bbfebd075b178a0c22b08f186e
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587764"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>2013에서 경고 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

경고는 모든 인시던트의 기반이 며 사용자 환경에서 악의적 또는 의심스러운 이벤트가 발생하는 것을 나타냅니다. 경고는 일반적으로 더 광범위한 공격의 일부로, 인시던트에 대한 단서를 제공합니다.

이 Microsoft 365 Defender 관련 경고는 인시던트 를 형성하기 위해 함께 [집계됩니다.](incidents-overview.md) 인시던트는 항상 공격의 광범위한 컨텍스트를 제공하겠지만, 심층 분석이 필요한 경우 경고를 분석하는 것이 중요할 수 있습니다. 

경고 **큐에는** 현재 경고 집합이 표시됩니다. 인시던트 및 경고  & > 포털(Microsoft 365 Defender)을 빠르게 실행하면 경고[큐로 security.microsoft.com.](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="보안 포털의 경고 큐 Microsoft 365 Defender 있습니다.":::

Endpoint용 Microsoft Defender, Microsoft Defender for Office 365 및 알림과 같은 다양한 Microsoft Microsoft 365 Defender 여기에 표시됩니다.

기본적으로 Microsoft 365 Defender 포털의 경고 큐에는 지난 30일 동안의 신규 및 진행 중인 경고가 표시됩니다. 가장 최근 경고는 목록 맨 위에 있으므로 먼저 볼 수 있습니다. 

기본 경고 큐에서 필터를  선택하여 경고의  하위 집합을 지정할 수 있는 필터 창을 볼 수 있습니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="사이트 포털의 경고 큐에 대한 필터 Microsoft 365 Defender 예입니다.":::

다음 조건에 따라 경고를 필터링할 수 있습니다.

- 심각도
- 상태
- Category
- 검색 원본
- 태그
- 정책
- 영향을 미치는 자산

## <a name="required-roles-for-defender-for-office-365-alerts"></a>경고에 대한 Defender의 Office 365 역할

알림에 대한 Microsoft Defender에 액세스하려면 다음 역할이 Office 365 있습니다.

- Azure AZURE ACTIVE DIRECTORY(Azure AD) 전역 역할의 경우:

   - 전역 관리자

   - 보안 관리자

   - 보안 운영자

   - 전역 읽기 권한자

   - 보안 읽기 권한자

- Office 365 보안 & 준수 역할 그룹

   - 규정 준수 관리자

   - 조직 관리 

- 사용자 [지정 역할](custom-roles.md)

## <a name="analyze-an-alert"></a>경고 분석

기본 경고 페이지를 표시하려면 경고의 이름을 선택합니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="알림 포털에서 경고의 세부 정보 Microsoft 365 Defender 예입니다.":::

알림 관리 창에서 기본 경고 페이지 열기 **작업을 선택할 수도** 있습니다. 

경고 페이지는 다음 섹션으로 구성됩니다. 

- 경고 스토리 - 이 경고와 관련된 이벤트 및 경고의 체인을 일련 순서로 표시
- 요약 세부 정보

경고 페이지 전체에서 모든 엔터티 옆에 있는 타원(**...**)을 선택하여 경고 페이지를 열거나 경고를 다른 인시던트에 연결하는 등의 사용 가능한 작업을 볼 수 있습니다.

### <a name="alert-sources"></a>경고 원본
Microsoft 365 Defender 경고는 Microsoft Defender for Endpoint, Microsoft Defender for Office 365 및 Microsoft Cloud App Security. 경고에 미리 문자가 있는 경고가 표시될 수 있습니다. 다음 표에서는 경고에 추가된 문자를 기반으로 경고 원본의 매핑을 이해하는 데 도움이 되는 지침을 제공합니다.

> [!NOTE]
> - 추가된 GUID는 통합 경고 큐, 통합 알림 페이지, 통합 조사 및 통합 인시던트와 같은 통합 환경 전용입니다.<br>
> - 미리 든 문자는 경고의 GUID를 변경하지 않습니다. GUID는 추가된 구성 요소뿐입니다.<br>


경고 원본 | 문자를 더한 문자 
:---|:---
Office 365용 Microsoft Defender | `fa{GUID}` <br> 예: `fa123a456b-c789-1d2e-12f1g33h445h6i` 
엔드포인트용 Microsoft Defender | `da` 또는 `ed` 사용자 지정 검색 경고용 <br> 
ID용 Microsoft Defender | `aa{GUID}` <br> 예: `aa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Cloud App Security |`ca{GUID}` <br> 예: `ca123a456b-c789-1d2e-12f1g33h445h6i` 

### <a name="analyze-affected-assets"></a>영향을 받는 자산 분석

수행된 **작업** 섹션에는 사서함, 장치 및 이 경고의 영향을 받는 사용자와 같은 영향을 받는 자산 목록이 있습니다. 

또한 **센터에서** 보기를 선택하여 포털에서 작업  센터의 사용 기록 탭을 Microsoft 365 Defender 있습니다.  

### <a name="trace-an-alerts-role-in-the-alert-story"></a>경고 스토리에서 경고의 역할 추적

경고 스토리에는 프로세스 트리 보기에서 경고와 관련된 모든 자산 또는 엔터티가 표시됩니다. 제목의 경고는 선택한 경고 페이지에 처음 방문할 때 포커스가 있는 경고입니다. 경고 스토리의 자산은 확장 가능하고 클릭할 수 있습니다. 추가 정보를 제공하고 경고 페이지의 컨텍스트에서 바로 조치를 취할 수 있도록 하여 응답을 즉석으로 제공합니다. 

> [!NOTE]
> 경고 스토리 섹션에는 두 개 이상의 경고가 포함될 수 있습니다. 이 섹션에서는 선택한 경고 전후에 동일한 실행 트리와 관련된 추가 경고가 나타납니다.

### <a name="view-more-alert-information-on-the-details-page"></a>세부 정보 페이지에서 추가 경고 정보 보기

세부 정보 페이지에는 선택한 경고의 세부 정보 및 관련 작업이 표시됩니다. 경고 스토리에서 영향을 받는 자산 또는 엔터티를 선택하면 세부 정보 페이지가 변경되어 선택한 개체에 대한 상황에 맞는 정보 및 작업을 제공합니다.

관심 있는 엔터티를 선택한 후 세부 정보 페이지가 변경되어 선택한 엔터티 유형에 대한 정보, 사용 가능한 기록 정보 및 경고 페이지에서 이 엔터티에 대해 직접 작업을 수행하기 위한 옵션이 표시됩니다.

## <a name="manage-alerts"></a>경고 관리

경고를 관리하려면 해당 행의 경고 큐에서 경고를 선택하여 경고 관리 **창을** 봐야 합니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="사이트 포털의 경고에 대한 요약 Microsoft 365 Defender 예입니다.":::

경고 **관리 창에서** 다음을 보거나 지정할 수 있습니다.

- 경고 상태(신규, 해결, 진행 중)입니다.
- 경고가 할당된 사용자 계정
- 경고의 분류(설정되지 않은, True 경고, 거짓 경고)입니다.
- 실제 경고로 분류하는 경우 결정 필드의 경고에 대한 위협 **유형입니다.**
- 경고에 대한 설명입니다.

> [!NOTE]
> 한 가지 관리 방법은 태그를 사용하여 경고합니다. Microsoft Defender for Office 365 태그 지정 기능은 증분적으로 배포되고 있으며 현재 미리 보기로 제공됩니다. <br>
> 현재 수정된 태그 이름은 업데이트 후에 만들어진 *경고에만* 적용됩니다. 수정 전에 생성된 알림에는 업데이트된 태그 이름이 반영되지 않습니다. 

이 창에서 다음 추가 작업을 수행할 수도 있습니다. 

- 기본 경고 페이지 열기
- Microsoft 위협 전문가에게 문의
- 제출 보기
- 다른 인시던트에 연결
- 타임라인에서 경고 보기
- 제거 규칙 만들기

다음은 예입니다.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="사이트 포털의 경고에 대한 Microsoft 365 Defender 예":::

추가 작업 목록은 경고 유형에 따라 다릅니다.

## <a name="resolve-an-alert"></a>경고 해결

경고 분석이 완료되고 해결할 수 있는 경우 경고에  대한 경고 관리 창으로 이동하여 경고 상태를 **해결된** 것으로 표시하고 **False** 경고 또는 True 경고로 **분류합니다.** 실제 경고의 경우 결정 필드에 경고의 위협 유형을 **지정합니다.**

경고를 분류하고 결정 값을 지정하면 경고를 Microsoft 365 Defender 보다 실제 경고와 거짓 경고를 줄이면 경고를 조정할 수 있습니다.

## <a name="next-steps"></a>다음 단계

In-process 인시던트에 필요한 경우 조사를 [계속합니다.](investigate-incidents.md)

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 관리](manage-incidents.md)
- [인시던트 조사](investigate-incidents.md)
