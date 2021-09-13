---
title: Office 365용 Microsoft Defender - CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Office 365용 Microsoft Defender에는 안전한 첨부 파일, 안전한 링크, 고급 피싱 방지 도구, 보고 도구 및 위협 인텔리전스 기능이 포함되어 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8651adb37640d68d0eace7aa23a134ba3b892bbd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211735"
---
# <a name="microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 이 문서는 [Office 365용 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)가 있는 비즈니스 고객을 대상으로 합니다. Outlook.com, Microsoft 365 Family 또는 Microsoft 365 Personal을 사용하고 있고 Outlook의 안전한 링크 또는 안전한 첨부 파일에 대한 정보를 찾고 있다면 [Office 365 구독자용 고급 Outlook.com 보안](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)을 참조하세요.

Office 365용 Microsoft Defender는 전자 메일 메시지, 링크(URL) 및 공동 작업 도구로 인한 악의적인 위협으로부터 조직을 보호합니다. Office 365용 Defender에는 다음이 포함됩니다.

- **[위협 방지 정책](#configure-microsoft-defender-for-office-365-policies)**: 위협 방지 정책을 정의하여 조직에 맞는 적절한 수준의 보호를 설정합니다.

- **[보고서](#view-microsoft-defender-for-office-365-reports)**: 조직의 Office 365용 Defender 성능을 모니터링하는 실시간 보고서를 볼 수 있습니다.

- **[위협 조사 및 응답 기능](#use-threat-investigation-and-response-capabilities)**: 최신 도구를 사용하여 위협의 조사, 이해, 시뮬레이션 및 예방 등을 할 수 있습니다.

- **[자동화된 조사 및 응답 기능](office-365-air.md)**: 위협에 대한 조사 및 위협을 낮추기 위한 시간과 노력을 줄입니다.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender에 대한 대화형 가이드

이 대화형 가이드에서는 Office 365용 Microsoft Defender를 사용하여 조직을 보호하는 방법에 대해 알아봅니다. Office 365용 Defender를 통해 보호 정책을 정의하고, 조직에 대한 위협을 분석하고, 공격에 대응하는 방법을 알아봅니다.

[대화형 가이드 확인](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>시작

Office 365용 Microsoft Defender가 처음이거나 *사용하면서* 배우기 가장 적합한 경우에는 초기 Office 365용 Defender 구성을 청크로 나눈 다음 이 문서를 참조로 사용하여 보고서를 조사 및 검토하는 것이 좋습니다. 아래에는 논리적 초기 구성 덩어리가 나와 있습니다.

- 이름에 '*방지*'가 포함 된 모든 항목에 구성
  - 밸웨어 방지
  - 피싱 방지
  - 스팸 방지
- 이름에 '*안전한*'을 사용한 모등 항목에 설정
  - 안전한 링크
  - 안전한 첨부 파일
- 작업을 방어할 때 (예: SharePoint Online, OneDrive 및 Teams)
- ZAP(제로 아워 자동 제거)로 보호합니다.

이 작업을 수행하여 자세한 내용을 보려면 [링크를 클릭](protect-against-threats.md).

> [!NOTE]
> Office 365용 Microsoft Defender는 두 가지 다른 플랜 유형으로 제공됩니다. ‘실시간 감지’를 가지고 있으면 **플랜 1** 이고 위협 탐색기를 가지고 있으면 **플랜2** 입니다. 어떤 플랜을 가지고 있는지 여부는 사용자에게 보여지는 도구에 영향을 미치기 때문에 배우는 동안 어떤 플랜을 가지고 있는지에 대해서 유의하세요.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Office 365용 Microsoft Defender 플랜 1 및 플랜 2

다음 표에는 각 계획에 포함된 항목이 요약되어 있습니다.

****

|Office 365용 Microsoft Defender 플랜 1|Office 365용 Microsoft Defender 플랜 2|
|---|---|
|구성, 보호 및 검색 기능: <ul><li>[안전한 첨부 파일](safe-attachments.md)</li><li>[안전한 링크](safe-links.md)</li><li>[SharePoint, OneDrive 및 Microsoft Teams용 안전한 첨부 파일](mdo-for-spo-odb-and-teams.md)</li><li>[Office 365용 Defender 보호의 피싱 방지](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[실시간 탐지](threat-explorer.md)</li></ul>|Office 365용 Microsoft Defender 플랜 1 기능 <br>--- 추가 ---<br> 자동화, 조사, 수정 및 교육 기능:<ul><li>[위협 트래커](threat-trackers.md)</li><li>[위협 탐색기](threat-explorer.md)</li><li>[자동화된 조사 및 응답](office-365-air.md)</li><li>[공격 시뮬레이션 교육](attack-simulation-training.md)</li><li>[캠페인 보기](campaigns.md)</li></ul>|
|

- Office 365용 Microsoft Defender 플랜 2는 Office 365 E5, Office 365 A5, Microsoft 365 E5 Security 및 Microsoft 365 E5에 포함되어 있습니다.

- Office 365용 Microsoft Defender 플랜 1은 Microsoft 365 Business Premium에 포함되어 있습니다.

- Office 365용 Microsoft Defender 플랜 1과 Office365용 Microsoft Defender 플랜 2를 각각 특정 구독의 추가 기능으로 사용할 수 있습니다. 자세한 내용은 [Office 365용 Microsoft Defender 플랜의 기능 가용성을 참좌세요](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- [안전한 문서](safe-docs.md) 기능은 Microsoft 365 E5 또는 Microsoft 365 E5 보안 라이선스가 있는 사용자만 사용할 수 있습니다. (Office 365용 Microsoft Defender 플랜에는 미포함)

- 현재 구독에 Office 365용 Microsoft Defender가 포함되어 있지 않은 경우 [평가판을 시작](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)하고 Office 365용 Defender가 조직에 대해 작동하는 방법을 알아보려면 영업 담당자에게 문의하세요.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Office 365용 Microsoft Defender 정책 구성

Office 365용 Microsoft Defender를 사용하면 조직의 보안 팀이 Microsoft 365 Defender 포털에서 정책을 정의하여 보호 기능을 구성할 수 있습니다(<https://security.microsoft.com> \> **전자 메일 및 공동 작업** \> **정책 및 규칙** \> **위협 정책** 으로 이동).

[이 비디오](https://www.youtube.com/watch?v=vivvTmWJ_3c)를 시청하여 자세히 확인하세요.

> [!TIP]
> 정의할 정책의 빠른 목록을 보려면 [위협으로부터 보호](protect-against-threats.md)를 참조하세요.

## <a name="defender-for-office-365-policies"></a>Office 365용 Defender 정책

조직에 정의된 정책에 따라 미리 정의된 위협에 대한 동작 및 보호 수준이 결정됩니다. 정책 옵션은 매우 유동적입니다. 예를 들어 조직의 보안팀은 사용자, 조직, 수신자 및 도메인 수준에서 세분화된 위협 방지를 설정할 수 있습니다. 새로운 위협과 문제점이 매일 발생하므로 정책을 정기적으로 검토하는 것이 중요합니다.

- **[안전한 첨부 파일](safe-attachments.md)**: 전자 메일의 첨부 파일에 악성 콘텐츠가 있는지 확인하여 메시지 시스템을 보호하는 제로 데이 보호 기능을 제공합니다. 바이러스/맬웨어 서명이 없는 모든 메시지 및 첨부 파일을 특수 환경으로 경로 지정한 다음 기계 학습 및 분석 기법을 사용하여 악의적인 의도를 탐지합니다. 의심스러운 활동이 없는 경우 메시지가 사서함으로 전달됩니다. 자세한 내용은 [안전한 첨부 파일 정책 설정](set-up-safe-attachments-policies.md)을 참조하세요.

- **[안전한 링크](safe-links.md)** 전자 메일 메시지 및 Office 파일 등에서 URL의 클릭시간 확인기능을 제공합니다. 보호가 진행 중이며 메시징 및 Office 환경에 적용됩니다. 클릭 할 때마다 링크가 검색됩니다. 안전한 링크는 계속 액세스할 수 있으며 악성 링크는 동적으로 차단됩니다. 자세한 내용은 [안전한 링크 정책 설정](set-up-safe-links-policies.md)을 참조하세요.

- **[SharePoint, OneDrive 및 Microsoft Teams용 안전한 첨부 파일](mdo-for-spo-odb-and-teams.md)**: 팀 사이트 및 문서 라이브러리에서 악성 파일을 식별하고 차단하여 사용자가 파일을 공동 작업하고 공유할 때 사용자 조직을 보호합니다. 자세한 내용은 [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365용 Defender 실행](turn-on-mdo-for-spo-odb-and-teams.md)을 참조하세요.

- **[Office 365용 Defender의 피싱 방지 보호](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: 사용자와 내부 또는 사용자 지정 도메인으로 위장하려는 시도를 감지합니다. 피싱 공격을 피하기 위해 기계 학습 모델과 고급 위장 탐지 알고리즘을 적용합니다. 자세한 내용은 [Office 365용 Microsoft Defender에서 피싱 방지 정책 구성](configure-mdo-anti-phishing-policies.md)을 참조하세요.

## <a name="view-microsoft-defender-for-office-365-reports"></a>Office 365용 Microsoft Defender 보고서 보기

Office 365용 Microsoft Defender에는 Office 365용 Defender를 모니터링하는 [보고서](view-reports-for-mdo.md)가 포함되어 있습니다. Microsoft 365 Defender 포털의 **보고서** \> **전자 메일 및 공동 작업** \> **전자 메일 및 공동 작업 보고서** 에서 보고서에 액세스하거나 <https://security.microsoft.com/securityreports>에서 직접 액세스할 수 있습니다.

보고서는 실시간으로 업데이트되어 최신 정보를 제공합니다. 이 보고서는 또한 권장 사항을 제공하고 임박한 위협에 대해 경고합니다. 사전 정의된 보고서에는 다음이 포함됩니다.

- [위협 탐색기 (또는 실시간 검출)](threat-explorer.md)
- [위협 방지 상태 보고서](view-reports-for-mdo.md#threat-protection-status-report)
- ... 그리고 그 외에 몇 가지가 더 있습니다.

## <a name="use-threat-investigation-and-response-capabilities"></a>위협 조사 및 응답 기능 사용

Office 365용 Microsoft Defender 플랜 2에는 조직의 보안팀이 악의적인 공격을 예측, 이해, 예방하는 데 사용할 수 있는 동급 최고의 [위협 조사 및 응답 도구](office-365-ti.md)가 포함되어 있습니다.

- **[위협 트래커](threat-trackers.md)** 는 일반적인 사이버 보안 문제에 대한 최신 인텔리전스를 제공합니다. 예를 들어 최신 맬웨어에 대한 정보를 확인하고, 실제로 조직에 위협이 되기 전에 대응책을 사용할 수 있습니다. 사용 가능한 트래커에는 [주목할만한 트래커](threat-trackers.md#noteworthy-trackers), [인기 트래커](threat-trackers.md#trending-trackers), [추적 쿼리](threat-trackers.md#tracked-queries) 및 [저장된 쿼리](threat-trackers.md#saved-queries)가 포함됩니다.

- **[위협 탐색기 (또는 실시간 검출)](threat-explorer.md)** (탐색기라고도 함)는 최근 위협을 식별하고 분석할 수있는 실시간 보고서입니다. 사용자 지정 기간에 대한 데이터를 표시하도록 탐색기를 구성할 수 있습니다.

- **[공격 시뮬레이션 교육](attack-simulation-training.md)** 은 사용자 조직에서 실제 공격 시나리오를 실행하여 취약성을 식별할 수 있습니다. 스피어 피싱 자격 증명 수집 및 첨부 파일 공격과 비밀번호 분무 및 무차별 비밀번호 대입 공격 등을 포함하여 최근 유형의 공격에 대한 시뮬레이션을 사용할 수 있습니다.

## <a name="save-time-with-automated-investigation-and-response"></a>자동화된 조사 및 응답으로 시간 절약하기

(**새로운 기능!**) 잠재적인 사이버 공격을 조사할 때는 시간이 가장 중요합니다. 위협을 빨리 식별하고 완화할 수록 조직을 보호하는데 더욱 좋습니다. [자동화된 조사 및 대응](office-365-air.md)(AIR) 기능에는 알림이 트리거되는 경우와 같이 자동으로 시작되거나 또는 Explorer의 보기와 같이 수동으로 시작할 수 있는 보안 플레이북 세트가 포함되어 있습니다. AIR을 사용하면 보안 운영팀이 위협을 효과적이고 효율적으로 완화하도록 하는데 드는 시간과 노력을 절약할 수 있습니다. 자세한 내용은 [Office 365의 AIR](office-365-air.md)를 참조하세요.

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Office 365용 Microsoft Defender 기능을 사용하는 데 필요한 사용 권한

Office 365용 Microsoft Defender 기능에 액세스하려면 적절한 역할을 할당 받아야 합니다. 다음 표에 몇 가지 예제가 나와 있습니다.

<br>

****

|역할 또는 역할 그룹|자세한 정보를 알아볼 수 있는 리소스|
|---|---|
|전역 관리자(조직 관리)|Azure Active Directory 또는 Microsoft 365 Defender 포털에서 이 역할을 할당할 수 있습니다. 자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.|
|보안 관리자|Azure Active Directory 또는 Microsoft 365 Defender 포털에서 이 역할을 할당할 수 있습니다. 자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.|
|Exchange Online의 조직 관리|[Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|검색 및 제거|이 역할은 Microsoft 365 Defender 포털 또는 Microsoft 365 규정 준수 센터에서만 사용할 수 있습니다. 자세한 내용은 [Microsoft 365 Defender 포털에서의 액세스 권한](permissions-microsoft-365-security-center.md) 및 [Microsoft 365 규정 준수 센터에서의 액세스 권한](../../compliance/microsoft-365-compliance-center-permissions.md)을 참조하세요.|
|||

## <a name="get-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender 다운로드

Office 365용 Microsoft Defender는 Microsoft 365 E5, Office 365 E5, Office 365 A5, Microsoft 365 Business Premium 등의 특정 구독에 포함되어 있습니다. 구독에 Office 365용 Defender가 포함되어 있지 않은 경우 Office 365용 Defender 플랜 1 또는 Office 365용 Defender 플랜 2를 특정 구독에 대한 추가 기능으로 구매할 수 있습니다. 자세한 내용은 다음 리소스를 참조하세요.

- Office 365용 Defender 플랜을 포함하는 구독 목록에 대한 [Office 365용 Microsoft Defender 가용성](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability).

- 플랜 1 및 플랜 2에 포함된 기능 목록에 대한 [Office 365용 Microsoft Defender 플랜의 기능 가용성](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- [Office 365용 Microsoft Defender를 다운로드하여](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) 플랜을 비교하고 Office 365용 Defender를 구매할 수 있습니다.

- [무료 평가판 시작](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 새로운 기능

Office 365용 Microsoft Defender에는 새로운 기능이 계속해서 추가됩니다. 자세한 내용은 다음 리소스를 참조하세요.

- [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365)은 개발 및 출시에 대한 새로운 기능 목록을 제공합니다.

- [Office 365용 Microsoft Office Defender 서비스 설명](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)은 Office 365용 Defender 플랜의 기능과 가용성에 대해 설명합니다.

## <a name="see-also"></a>참고 항목

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
- [Microsoft 365 Defender의 자동화된 조사 및 대응(AIR)](../defender/m365d-autoir.md)
