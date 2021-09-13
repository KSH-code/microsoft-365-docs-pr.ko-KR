---
title: Microsoft Defender에서 자동화된 조사 및 Office 365
keywords: AIR, autoIR, Endpoint용 Microsoft Defender, 자동화, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender에서 자동화된 조사 및 응답 기능을 사용하여 Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cc1ddac10ddea4ea50ab1fc339db77a3240552b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214335"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender의 자동화된 조사 및 대응(AIR)Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md) 보안 운영 팀의 시간과 노력을 절약할 수 있는 강력한 자동화된 조사 및 대응(AIR) 기능이 포함되어 있습니다. 경고가 트리거되면 보안 운영 팀이 해당 경고를 검토, 우선 순위 지정 및 대응해야 합니다. 들어오는 경고의 양을 따라야 하는 부담이 있을 수 있습니다. 이러한 작업 중 일부를 자동화하면 도움이 될 수 있습니다.

AIR을 사용하면 보안 운영 팀이 보다 효율적이고 효율적으로 작업할 수 있습니다. AIR 기능에는 현재 존재하는 잘 알려진 위협에 대응하는 자동화된 조사 프로세스가 포함됩니다. 적절한 수정 작업은 승인을 대기하여 보안 운영 팀이 감지된 위협에 효과적으로 대응할 수 있도록 합니다. AIR을 사용하여 보안 운영 팀은 트리거되는 중요한 경고를 잃지 않고 우선 순위가 높은 작업에 집중할 수 있습니다.

이 문서에서는 다음에 대해 설명합니다.

- [AIR의 전체 흐름;](#the-overall-flow-of-air)
- [AIR을 얻는 방법](#how-to-get-air); 및
- AIR [기능을](#required-permissions-to-use-air-capabilities) 구성하거나 사용하는 데 필요한 권한입니다.
- 사용자 포털에 곧 변경될 Microsoft 365 Defender 변경 사항

이 문서에는 다음 [단계](#next-steps)및 자세한 내용에 대한 리소스도 포함되어 있습니다.

## <a name="the-overall-flow-of-air"></a>AIR의 전체 흐름

경고가 트리거되고 보안 플레이북이 자동화된 조사를 시작하여 발견된 결과 및 권장 조치가 생성됩니다. 다음은 AIR의 전체 흐름입니다. 단계별 흐름은 다음과 같습니다.

1. 자동화된 조사는 다음 방법 중 하나를 통해 시작됩니다.
   - 전자 [메일에서](#which-alert-policies-trigger-automated-investigations) 의심스러운 경고(예: 메시지, 첨부 파일, URL 또는 손상된 사용자 계정)에 의해 경고가 트리거됩니다. 인시던트가 생성되고 자동화된 조사가 시작됩니다. 또는
   - 보안 [분석가가 Explorer를](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 사용하는 동안 자동화된 조사를 [시작합니다.](threat-explorer.md)
2. 자동화된 조사가 실행되는 동안 문제의 전자 메일 및 전자 메일과 관련된 엔터티에 대한 데이터를 수집합니다. 이러한 엔터티에는 파일, URL 및 받는 사람이 포함됩니다. 신규 및 관련 경고가 트리거되면 조사 범위가 늘어날 수 있습니다.
3. 자동화된 조사가 진행되는 동안 및 이후에 세부 정보 및 [결과를](air-view-investigation-results.md) 볼 수 있습니다. 결과에는 [발견된](air-remediation-actions.md) 위협에 대응하고 수정하기 위해 수행할 수 있는 권장 작업이 포함됩니다.
4. 보안 운영 팀은 조사 [](air-view-investigation-results.md)결과 및 권장 사항을 검토하고 수정 작업을 승인하거나 [거부합니다.](air-review-approve-pending-completed-actions.md)
5. 보류 중인 수정 작업이 승인되거나 거부되면 자동화된 조사가 완료됩니다.

Microsoft Defender for Office 365 수정 작업은 자동으로 수행되지 않습니다. 수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다. AIR 기능은 수정 작업을 식별하고 정보를 토대한 결정을 내리는 데 필요한 세부 정보를 제공하여 보안 운영 팀의 시간을 절약합니다.

자동화된 조사가 진행되는 동안 및 이후에 보안 운영 팀은 다음을 할 수 있습니다.

- [조사와 관련된 경고에 대한 세부 정보 보기](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [조사 결과 세부 정보 보기](air-view-investigation-results.md#view-details-of-an-investigation)
- [조사 결과 작업 검토 및 승인](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 자세한 개요는 AIR 작동 [방법을 참조하세요.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>AIR을 얻을 수 있는 방법

정책 및 경고가 구성된 경우 Office 365 대한 [Microsoft Defender에](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)AIR 기능이 포함되어 있습니다. 도움이 필요하세요? 위협으로부터 [보호의](protect-against-threats.md) 지침에 따라 다음 보호 설정을 설정하거나 구성합니다.

- [감사 로깅(켜져](../../compliance/turn-audit-log-search-on-or-off.md) 있어야 합니다.
- [맬웨어 방지 보호 기능](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [피싱 방지 보호 기능](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [스팸 방지 보호 기능](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [금고 첨부 파일 금고 링크 및 링크](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

또한 조직의 경고 [](../../compliance/alert-policies.md)정책, 특히 위협 관리 범주의 기본 정책을 [검토해야 합니다.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>자동화된 조사를 트리거하는 경고 정책은 무엇입니까?

Microsoft 365 관리자 권한 남용, 맬웨어 활동Exchange 잠재적인 외부 및 내부 위협 및 정보 거버넌스 위험을 식별하는 데 도움이 되는 다양한 기본 제공 경고 정책을 제공합니다. 일부 기본 경고 [정책은](../../compliance/alert-policies.md#default-alert-policies) 자동화된 조사를 트리거할 수 있습니다. 다음 표에서는 자동화된 조사를 트리거하는 경고, Microsoft 365 Defender 포털의 심각도 및 경고 생성 방법에 대해 설명되어 있습니다.

<br>

****

|경고|심각도|경고 생성 방법|
|---|---|---|
|악의적인 URL 클릭이 감지되었습니다.|**High**|이 경고는 다음과 같은 경우 생성됩니다. <ul><li>조직에서 링크로 [금고](safe-links.md) 악의적인 링크를 클릭하는 사용자</li><li>URL에 대한 판정 변경 내용은 Microsoft Defender에서 Office 365</li><li>사용자는 조직의 금고 링크 정책에 따라 링크 경고 금고 [무시합니다.](set-up-safe-links-policies.md)</li></ul> <p> 이 경고를 트리거하는 이벤트에 대한 자세한 내용은 [Set up 금고 Links policies을 참조하십시오.](set-up-safe-links-policies.md)|
|사용자가 전자 메일 메시지를 맬웨어 또는 피싱으로 보고|**정보**|이 경고는 조직의 사용자가 보고서 메시지 추가 기능 또는 [](enable-the-report-message-add-in.md) 피싱 보고 추가 기능을 사용하여 메시지를 피싱 전자 메일로 보고할 [때 생성됩니다.](enable-the-report-phish-add-in.md)|
|배달 후 맬웨어가 포함된 전자 메일 메시지 제거|**정보**|이 경고는 맬웨어가 포함된 전자 메일 메시지가 조직의 사서함으로 배달될 때 생성됩니다. 이 이벤트가 발생하면 Microsoft는 ZAP(제로 아워 Exchange Online 제거)를 사용하여 감염된 메시지를 사서함에서 [제거합니다.](zero-hour-auto-purge.md)|
|배달 후 피싱 URL이 포함된 전자 메일 메시지 제거|**정보**|이 경고는 피싱이 포함된 메시지가 조직의 사서함으로 배달될 때 생성됩니다. 이 이벤트가 발생하면 Microsoft는 ZAP를 사용하여 감염된 Exchange Online [제거합니다.](zero-hour-auto-purge.md)|
|의심스러운 전자 메일 전송 패턴이 감지됩니다.|**Medium**|이 경고는 조직의 누군가가 의심스러운 전자 메일을 보낸 경우 생성되고 전자 메일을 보내지 못하도록 제한될 위험이 있습니다. 경고는 계정이 손상된 것일 수 있지만 사용자를 제한할 만큼 심각하지는 않은 동작에 대한 초기 경고입니다. <p> 드물지만 이 정책에 의해 생성된 경고는 이상일 수 있습니다. 그러나 사용자 계정이 손상 된지 여부를 확인 하는 [것이 좋습니다.](responding-to-a-compromised-email-account.md)|
|사용자가 전자 메일을 보낼 수 없습니다.|**High**|이 경고는 조직의 사용자가 아웃바운드 메일을 보낼 수 없습니다. 이 경고는 일반적으로 전자 메일 계정이 [손상될 때 생성됩니다.](responding-to-a-compromised-email-account.md) <p> 제한된 사용자에 대한 자세한 내용은 에서 제한된 사용자 포털에서 차단된 [사용자 제거를 Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> 경고 정책에 대한 자세한 내용을 보거나 기본 설정을 편집하려면 에서 경고 정책을 [Microsoft 365 규정 준수 센터.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 기능을 사용하는 데 필요한 사용 권한

사용 권한은 다음 표에 설명된 역할과 같은 특정 역할을 통해 부여됩니다.

<br>

****

|작업|역할 필요|
|---|---|
|AIR 기능 설정|다음 역할 중 하나: <ul><li>전역 관리자</li><li>보안 관리자</li></ul> <p> 이러한 역할은 Azure Active Directory [](/azure/active-directory/roles/permissions-reference) 포털에서 할당할 [Microsoft 365 Defender 있습니다.](permissions-microsoft-365-security-center.md)|
|자동 조사 시작 <p> --- 또는 --- <p> 권장 작업 승인 또는 거부|다음 역할 중 하나는 Azure Active Directory [또는](/azure/active-directory/roles/permissions-reference) Microsoft 365 Defender [포털에서 할당됩니다.](permissions-microsoft-365-security-center.md) <ul><li>전역 관리자</li><li>보안 관리자</li><li>보안 운영자</li><li>보안 읽기 권한자 <br> --- 및 --- </li><li>검색 및 제거(이 역할은 Microsoft 365 Defender [포털에서만 할당됩니다.](permissions-microsoft-365-security-center.md) 새 전자 메일 그룹 공동 작업 & 그룹을 만들고 해당 새 역할 **그룹에** 검색 및 제거 역할을 추가해야 할 수 있습니다.</li></ul>|

## <a name="required-licenses"></a>필수 라이선스

[Microsoft Defender for Office 365 계획 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 라이선스를 할당해야 합니다.

- 보안 관리자(전역 관리자 포함)
- 조직의 보안 운영 팀(보안 독자 및 검색 및 제거 **역할이 있는** 사용자 포함)
- 최종 사용자

## <a name="changes-are-coming-soon-in-your-microsoft-365-defender-portal"></a>웹 사이트 포털에서 곧 변경 Microsoft 365 Defender 있습니다.

Microsoft Defender for Office 365 이미 AIR 기능을 사용 중이면 개선된 Microsoft 365 Defender 포털에서 일부 변경 [사항을 보게 될 것입니다.](../defender/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="통합된 동작 센터.":::

새 기능과 향상된 Microsoft 365 Defender 포털은 Microsoft [Defender for Office 365](defender-for-office-365.md) 및 [끝점용 Microsoft Defender의](../defender-endpoint/automated-investigations.md)AIR 기능을 제공합니다. 이러한 업데이트 및 개선 사항을 통해 보안 운영 팀에서는 전자 메일, 공동 작업 콘텐츠, 사용자 계정 및 장치 전체에서 자동 조사 및 수정 작업에 대한 세부 정보를 한 장소에서 볼 수 있습니다.

> [!TIP]
> 새 Microsoft 365 Microsoft 365 Defender 포털( <https://security.microsoft.com> )이 다음 가운데를 대체합니다.
>
> - 보안 & 준수 센터( <https://protection.office.com> )
> - Microsoft Defender 보안 센터( <https://securitycenter.windows.com> )
>
> URL을 변경하는 것 외에도 보안 팀에게 더 간소화된 환경을 제공하도록 설계된 새로운 모양과 느낌이 있으며, 한 장소에서 더 많은 위협 감지를 볼 수 있습니다.

### <a name="what-to-expect"></a>예상할 일

다음 표에는 Microsoft Defender for Office 365.

<br>

****

|항목|변경된 바는 무엇입니까?|
|---|---|
|**조사** 페이지|업데이트된 조사 **페이지는** [끝점용 Microsoft Defender에 있는 페이지와 더 일치합니다.](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 새로운 통합 조사 보기에 맞게 몇 가지 일반적인 형식 및 스타일 변경 내용이 **표시됩니다.** 예를 들어 조사 그래프의 형식은 보다 통합되어 있습니다.|
|**사용자** 탭|이제 **사용자 탭이** **사서함 탭이** 됩니다. 사용자에 대한 세부 정보는 사서함 **탭에 나열됩니다.**|
|**전자 메일** 탭|전자 **메일 탭이** 제거되었습니다. 엔터티 **탭을 방문하여** 전자 메일 및 전자 메일 클러스터 항목 목록을 볼 수 있습니다.|
|**엔터티 탭**|엔터티 **탭에는** 전체 요약 보기와 엔터티 유형별로 필터링하는 기능을 포함하는 탭 탭 스타일이 있습니다. 이제 **엔터티 탭에**  탐색기에서 열기 옵션 외에 이동 헌팅 **옵션이 포함되어** 있습니다. 이제 탐색기 또는 [](threat-explorer.md) 고급 [](../defender-endpoint/advanced-hunting-overview.md) 헌팅을 사용하여 엔터티와 위협을 찾고 결과를 필터링할 수 있습니다.|
|**작업** 탭|업데이트된 **작업** 탭에는  보류 중인 작업 탭과 작업 기록 **탭이 포함됩니다.** 보류 중인 작업을 선택할 때 열 수 있는 쪽 창에서 작업을 승인(또는 거부)할 수 있습니다.|
|**증거 탭**|새 증거 **탭에는** 작업과 관련된 주요 엔터티 찾은 것이 표시됩니다. 보류 중인 작업을 선택할 때 여는 쪽 창에서 각 증거 조각과 관련된 작업을 승인(또는 거부)할 수 있습니다.|
|**알림 센터**|업데이트된 **알림 센터(** )는 전자 메일, 장치 및 ID에서 보류 중인 작업과 완료된 작업을 <https://security.microsoft.com/action-center> 함께 제공합니다. 자세한 내용은 작업 센터를 참조합니다. (자세한 내용은 동작 [센터를 참조합니다.)](../defender/m365d-action-center.md)|
|**인시던트** 페이지|**인시던트** 페이지는 이제 여러 조사를 함께 연결하여 조사에 대한 더 나은 통합된 보기를 제공합니다. [(인시던트에 대한 자세한 내용은 을(를)](../defender/incidents-overview.md)|
|

## <a name="next-steps"></a>다음 단계

- [자동화된 조사의 세부 정보 및 결과 보기](air-view-investigation-results.md#view-details-of-an-investigation)
- [보류 중인 작업 검토 및 승인](air-remediation-actions.md)
