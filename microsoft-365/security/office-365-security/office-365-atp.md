---
title: Office 365 Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 02/24/2020
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection에는 안전한 첨부 파일, 안전한 링크, 고급 피싱 방지 도구, 보고 도구 및 위협 인텔리전스 기능이 포함되어 있습니다.
ms.openlocfilehash: 993939027962bd51ad4fdc3381c1e7d8ea4eddd4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634535"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> 이 문서는 [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)이 있는 비즈니스 고객을 대상으로 합니다. Outlook.com, Microsoft 365 Family 또는 Microsoft 365 Personal을 사용하고 있고 Outlook의 안전한 링크 또는 안전한 첨부 파일에 대한 정보를 찾고 있다면 [Office 365 구독자용 고급 Outlook.com 보안](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)을 참조하세요.

## <a name="overview"></a>개요

Office 365 ATP (Advanced Threat Protection)는 전자 메일 메시지, 링크 (URL) 및 공동 작업 도구로 인한 악의적인 위협으로부터 조직을 보호합니다. ATP는 다음을 포함합니다.

- **[위협 방지 정책](#configure-atp-policies)**: 위협 방지 정책을 정의하여 조직에 맞는 적절한 수준의 보호를 설정합니다.

- **[보고서](#view-office-365-atp-reports)**: 조직의 ATP 성능을 모니터링하는 실시간 보고서를 볼 수 있습니다.

- **[위협 조사 및 응답 기능](#use-threat-investigation-and-response-capabilities)**: 최신 도구를 사용하여 위협의 조사, 이해, 시뮬레이션 및 예방 등을 할 수 있습니다.

- **[자동화된 조사 및 응답 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: 위협에 대한 조사 및 위협을 낮추기 위한 시간과 노력을 줄입니다.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP 플랜 1 및 플랜 2

다음 표에는 각 계획에 포함된 항목이 요약되어 있습니다.

|||
|---|---|
|**Office 365 ATP 플랜 1**|**Office 365 ATP 플랜 2**|
|구성, 보호 및 검색 기능:<br/>• [안전한 첨부 파일](atp-safe-attachments.md)<br/>• [안전한 링크](atp-safe-links.md)<br/>• [SharePoint, OneDrive 및 Microsoft Teams용 ATP](atp-for-spo-odb-and-teams.md)<br/>• [ATP 피싱 방지 보호 기능](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)<br/>• [실시간 탐지](threat-explorer.md)|Office 365 ATP 계획 1 기능<br/>--- 추가 ---<br/>자동화, 조사, 수정 및 교육 기능:<br/>• [위협 추적기](threat-trackers.md)<br/>• [위협 탐색기](threat-explorer.md)<br/>• [자동 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>• [공격 시뮬레이터](attack-simulator.md)|
|

- Office 365 ATP 계획 2는 Office 365 E5, Office 365 A5 및 Microsoft 365 E5에 포함되어 있습니다.

- Office 365 ATP 계획 1은 Microsoft 365 Business Premium에 포함되어 있습니다.

- Office 365 ATP 계획 1과 Office 365 ATP 계획 2는 특정 구독의 추가 기능으로 사용할 수 있습니다. 자세한 내용은 [ATP 계획에서의 기능 가용성](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)을 참조하세요.

- 현재 구독에 Office 365 ATP가 포함되어 있지 않은 경우 [평가판을 시작하고 ATP가 조직에 대해 작동하는 방법을 알아보려면 영업 담당자에게 문의](https://go.microsoft.com/fwlink/p/?LinkId=518644)하세요.

## <a name="configure-atp-policies"></a>ATP 정책 구성

Office 365 ATP를 사용하여 조직의 보안팀이 보안 및 준수 센터에서 정책을 정의하여 보호를 구성할 수 있습니다.([https://protection.office.com](https://protection.office.com) > **위협 관리** > **정책**.)

> [!TIP]
> 정의할 정책의 빠른 목록을 보려면 [위협으로부터 보호](protect-against-threats.md)를 참조하세요.

조직에 정의된 정책에 따라 미리 정의된 위협에 대한 동작 및 보호 수준이 결정됩니다. 정책 옵션은 매우 유동적입니다. 예를 들어 조직의 보안팀은 사용자, 조직, 수신자 및 도메인 수준에서 세분화된 위협 방지를 설정할 수 있습니다. 새로운 위협과 문제점이 매일 발생하므로 정책을 정기적으로 검토하는 것이 중요합니다.

- **[ATP 안전한 첨부파일](atp-safe-attachments.md)**: 전자 메일의 첨부 파일에서 악성 콘텐츠가 있는지 확인하여 메시징 시스템을 보호하는 제로-데이 보호 기능을 제공합니다. 바이러스/맬웨어 서명이 없는 모든 메시지 및 첨부 파일을 특수 환경으로 경로 지정한 다음 기계 학습 및 분석 기법을 사용하여 악의적인 의도를 탐지합니다. 의심스러운 활동이 없는 경우 메시지가 사서함으로 전달됩니다. 자세한 내용은 [Office 365 ATP 안전한 첨부 파일 정책 설정](set-up-atp-safe-attachments-policies.md)을 참조하세요.

- **[ATP 안전한 링크](atp-safe-links.md)**: 전자 메일 메시지 및 Office 파일 등에서 URL의 클릭시간 확인기능을 제공합니다. 보호가 진행 중이며 메시징 및 Office 환경에 적용됩니다. 클릭 할 때마다 링크가 검색됩니다. 안전한 링크는 계속 액세스할 수 있으며 악성 링크는 동적으로 차단됩니다. 자세한 내용은 [Office 365 ATP 안전한 링크 정책 설정](set-up-atp-safe-links-policies.md)을 참조하세요.

- **[SharePoint, OneDrive 및 Microsoft Teams용 ATP](atp-for-spo-odb-and-teams.md)**: 팀 사이트 및 문서 라이브러리에서 악성 파일을 식별하고 차단하여 사용자가 파일을 공동 작업하고 공유할 때 사용자 조직을 보호합니다. 자세한 내용은 [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP 실행](turn-on-atp-for-spo-odb-and-teams.md)을 참조하세요.

- **[ATP 피싱 방지 보호](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: 사용자와 내부 또는 사용자 지정 도메인으로 위장하려는 시도를 탐지합니다. 피싱 공격을 피하기 위해 기계 학습 모델과 고급 위장 탐지 알고리즘을 적용합니다. 자세한 내용은 [Office 365에서 ATP 피싱 방지 정책 구성](configure-atp-anti-phishing-policies.md)을 참조하세요.

## <a name="view-office-365-atp-reports"></a>Office 365 ATP 보고서 보기

Office 365 ATP에는 ATP 성능을 모니터링하는 고급 [보고 대시보드](view-reports-for-atp.md)가 포함되어 있습니다. 보안 및 준수 센터의 **보고서** > **대시보드**에서 액세스할 수 있습니다.

보고서는 실시간으로 업데이트되어 최신 정보를 제공합니다. 이 보고서는 또한 권장 사항을 제공하고 임박한 위협에 대해 경고합니다. 사전 정의된 보고서에는 다음이 포함됩니다.

- [위협 탐색기 (또는 실시간 검출)](threat-explorer.md)

- [위협 방지 상태 보고서](view-reports-for-atp.md#threat-protection-status-report)

- [ATP 파일 형식 보고서](view-reports-for-atp.md#atp-file-types-report)

- [ATP 메시지 폐기 보고서](view-reports-for-atp.md#atp-message-disposition-report)

- ... 그리고 그 외에 몇 가지가 더 있습니다.

## <a name="use-threat-investigation-and-response-capabilities"></a>위협 조사 및 응답 기능 사용

Office 365 ATP Plan 2에는 조직의 보안팀이 악의적인 공격을 예측하고 이해하고 예방하는 데 사용할 수 있는 동급 최고의 [위협 조사 및 응답 도구](office-365-ti.md)가 포함되어 있습니다.

- **[위협 트래커](threat-trackers.md)** 는 일반적인 사이버 보안 문제에 대한 최신 인텔리전스를 제공합니다. 예를 들어 최신 맬웨어에 대한 정보를 확인하고, 실제로 조직에 위협이 되기 전에 대응책을 사용할 수 있습니다. 사용 가능한 트래커에는 [주목할만한 트래커](threat-trackers.md#noteworthy-trackers), [인기 트래커](threat-trackers.md#trending-trackers), [추적 쿼리](threat-trackers.md#tracked-queries) 및 [저장된 쿼리](threat-trackers.md#saved-queries)가 포함됩니다.

- **[위협 탐색기 (또는 실시간 검출)](threat-explorer.md)** (탐색기라고도 함)는 최근 위협을 식별하고 분석할 수있는 실시간 보고서입니다. 사용자 지정 기간에 대한 데이터를 표시하도록 탐색기를 구성할 수 있습니다.

- **[공격 시뮬레이터](attack-simulator.md)** 를 사용하면 사용자 조직에서 실제적인 공격 시나리오를 실행하여 취약성을 식별할 수 있습니다. 스피어 피싱 자격 증명 수집 및 첨부 파일 공격과 비밀번호 분무 및 무차별 비밀번호 대입 공격 등을 포함하여 최근 유형의 공격에 대한 시뮬레이션을 사용할 수 있습니다.

## <a name="save-time-with-automated-investigation-and-response"></a>자동화된 조사 및 응답으로 시간 절약하기

(**새로운 기능!**) 잠재적인 사이버 공격을 조사할 때는 시간이 가장 중요합니다. 위협을 빨리 식별하고 완화할 수록 조직을 보호하는데 더욱 좋습니다. [자동화된 조사 및 대응](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)(AIR) 기능에는 알림이 트리거되는 경우와 같이 자동으로 시작되거나 또는 Explorer의 보기와 같이 수동으로 시작할 수 있는 보안 플레이북 세트가 포함되어 있습니다. AIR을 사용하면 보안 운영팀이 위협을 효과적이고 효율적으로 완화하도록 하는데 드는 시간과 노력을 절약할 수 있습니다. 자세한 내용은 [Office 365의 AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)를 참조하세요.

## <a name="permissions-required-to-use-atp-features"></a>ATP 기능을 사용하는 데 필요한 사용 권한

보안 및 준수 센터의 ATP 기능에 액세스하려면 적절한 역할을 할당받아야 합니다. 다음 표에 몇 가지 예제가 나와 있습니다.

|역할 또는 역할 그룹|자세한 정보를 알아볼 수 있는 리소스|
|---------|---------|
|전역 관리자(Azure Active Directory 또는 보안 & 규정 준수 센터에서 할당할 수 있습니다.) |[Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|보안 관리자 (Azure Active Directory 또는 보안 & 규정 준수 센터에서 할당할 수 있습니다.) |[Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online 조직 관리(Exchange Online에서 할당합니다.)|[Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|검색 및 제거(보안 & 규정 준수 센터에서만 할당합니다.) |[보안 & 규정 준수 센터의 사용 권한] (permissions-in-the-security-and-compliance-center.md|

자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

## <a name="get-office-365-atp"></a>Office 365 ATP 받기

Office 365 ATP는 Microsoft 365 E5, Office 365 E5, Office 365 A5, Microsoft 365 Business Premium 등의 특정 구독에 포함되어 있습니다. 구독에 Office 365 ATP가 포함되어있지 않은 경우 ATP 플랜 1 또는 ATP 플랜 2를 특정 구독에 대한 추가 기능으로 구매할 수 있습니다. 자세한 내용은 다음 리소스를 참조하세요.

- ATP 플랜이 포함된 구독 목록은 [Office 365 Advanced Threat Protection 제공 여부](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)

- 플랜 1 및 2에 포함된 기능 목록은 [ATP(Advanced Threat Protection) 플랜의 기능 제공 여부](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- 플랜을 비교하고 Office 365 ATP를 구매하려면 [올바른 Office 365 Advanced Threat Protection 구매하기](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)

- [무료 평가판 시작](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Office 365 ATP의 새로운 기능

새 기능은 Office 365 ATP에 계속해서 추가됩니다. 자세한 내용은 다음 리소스를 참조하세요.

- [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)은 개발 및 출시에 대한 새로운 기능 목록을 제공합니다.

- [Office 365 Advanced Threat Protection 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)에서는 ATP 플랜에 대한 기능 및 제공 여부에 대해 설명합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft 위협 방지](../mtp/microsoft-threat-protection.md)

- [Microsoft 위협 방지의 자동화된 조사 및 대응(AIR)](../mtp/mtp-autoir.md)
