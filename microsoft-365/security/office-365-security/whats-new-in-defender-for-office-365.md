---
title: Microsoft Defender for Office 365
description: Microsoft Defender for Office 365.
keywords: microsoft Defender for Office 365, ga, 일반적으로 사용 가능, 기능, 사용 가능, 새로운 기능
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 07/27/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae01a929121488399ac3a016f0b33ae7b28ff96d
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533618"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

이 문서에서는 Microsoft Defender for Office 365. 현재 미리 보기에 있는 기능은 (미리 **보기)로 표시됩니다.**

[이 비디오](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)를 시청하여 자세히 확인하세요.

> [!TIP]
> 아직 Microsoft Defender for Office 365 없는가요? [영업 담당자에게 평가판을 시작해 을(를) 시작해 을(를) 평가](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="august-2021"></a>2021년 8월

- [보고된](admin-review-reported-message.md)메시지에 대한 관리자 검토: 관리자는 이제 보고된 메시지를 검토한 후 템플릿 기반 메시지를 최종 사용자에게 다시 보낼 수 있습니다. 이는 조직에 맞게 사용자 지정하고 관리자의 판결에 따라 사용자 지정될 수 있습니다. 
=======
## <a name="september-2021"></a>2021년 9월

- [Quarantine policies:](quarantine-policies.md)Admins can configure granular control for recipient access to quarantined messages and customize end-user spam notifications.
  - [관리자 환경 비디오](https://youtu.be/vnar4HowfpY)
  - [최종 사용자 환경 비디오](https://youtu.be/s-vozLO43rI)
  - 이 블로그 게시물에는 "검지 환경 간소화"에 제공될 다른 새로운 기능이 [설명되어 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388)

## <a name="august-2021"></a>2021년 8월

- [보고된](admin-review-reported-message.md)메시지에 대한 관리자 검토: 관리자는 이제 보고된 메시지를 검토한 후 템플릿 기반 메시지를 최종 사용자에게 다시 보낼 수 있습니다. 템플릿은 조직에 맞게 사용자 지정하고 관리자의 판결에 따라 사용자 지정될 수 있습니다.
- [테넌트 허용/차단](manage-tenant-allows.md)목록에서 허용 추가: 차단된 메시지가 관리자 제출 프로세스의 일부로 제출된 경우 테넌트 허용/차단 목록에 허용 항목을 추가할 수 있습니다. 차단의 특성에 따라 제출된 URL, 파일 및/또는 보낸 사람 허용이 테넌트 허용/차단 목록에 추가됩니다. 대부분의 경우 허용을 추가하여 시스템에 시간을 주고, 허용되는 경우 자연스럽게 허용합니다. 경우에 따라 Microsoft에서 허용을 관리합니다.

## <a name="july-2021"></a>2021년 7월

- [자동화된 조사에서 향상된 전자 메일 분석](email-analysis-investigations.md)
- [고급](configure-advanced-delivery.md)배달: 사용자에게 타사 피싱 시뮬레이션을 배달하고 필터가 없는 메시지를 보안 작업 사서함으로 배달하는 새로운 기능을 도입했습니다.
- [금고 Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams)
- 손상된 사서함, 양식 피싱, 오버라이드 및 ZAP 반올리로 인해 배달된 악의적인 메일과 같은 시나리오에 대한 새로운 경고 정책
  - 의심스러운 전자 메일 전달 활동
  - 양식 공유 및 응답 수집이 제한된 사용자
  - 잠재적인 피싱 시도로 인해 양식이 차단됩니다.
  - 피싱으로 플래그가 지정 및 확인된 양식
  - [ZAP에 대한 새 경고 정책](../../compliance/new-defender-alert-policies.md)
- microsoft Defender for Office 365 통합 알림이 통합된 Microsoft 365 Defender - Microsoft 365 Defender 경고 큐에 [통합됩니다.](../defender/investigate-alerts.md)
- [이제](user-tags.md) 사용자 태그는 Office 365 Security & Compliance의 경고 큐 및 세부 정보를 포함하여 Office 365 경고 환경을 위한 Microsoft Defender에 통합되고, 사용자 태그에 사용자 지정 경고 정책을 지정하여 대상 경고 정책을 만들 수 있습니다. 
  - 태그는 Microsoft 365 Defender 센터의 통합 경고 큐에서도 사용할 수 있습니다(Office 365 계획 2용 Microsoft Defender).

## <a name="june-2021"></a>2021년 6월

- 피싱 방지 보안 팁 새 첫 번째 연락처 연락처 설정입니다. 이 보안 팁 보낸 사람이 보낸 전자 메일을 처음 받거나 보낸 사람의 전자 메일을 받지 않는 경우 표시됩니다. 이 설정 및 구성 방법에 대한 자세한 내용은 다음 문서를 참조하세요.
  - [첫 번째 보안 팁](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [EOP에서 스팸 방지 정책 구성](configure-anti-phishing-policies-eop.md)
  - [Microsoft Defender에서 피싱 방지 정책 Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>2021년 4월/5월

- [전자 메일 엔터티 페이지:](mdo-email-entity-page.md)위협, 인증 및 감지, 검색 세부 정보 및 새로운 새로운 전자 메일 미리 보기 환경과 관련한 강화된 정보가 있는 전자 메일의 통합된 360도 보기입니다.
- [Office 365 관리 API:](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events)배달 작업, 원본 및 최신 배달 위치 및 업데이트된 검색 세부 정보를 추가하기 위한 EmailEvents(RecordType 28)에 대한 업데이트입니다.
- [Threat Analytics for Defender for Office 365](/microsoft-365/security/defender/threat-analytics): 지속적인 캠페인에 대한 Microsoft 연구원의 광범위한 보고와 함께 활성 위협자, 인기 있는 기술 및 공격 표면을 볼 수 있습니다.

## <a name="februarymarch-2021"></a>2021년 2월/3월

- 헌팅 환경의 경고 ID 통합(경고 ID [](threat-explorer.md) 및 Alert-Explorer 탐색을 사용하여 검색)
- 헌팅 환경의 레코드 내보내기 제한을 9990에서 200,000으로 [늘리기](threat-explorer.md)
- 헌팅 환경의 평가판 테넌트에 대한 탐색기(및 실시간 검색) 데이터 보존 및 검색 제한을 7일(이전 제한)에서 30일로 [확장](threat-explorer.md)
- 탐색기 내에서 가장된  도메인 및 가장된 사용자라는 새로운 헌팅 피벗을 사용하여 보호된 사용자 또는 도메인에 대한 가장 공격을 검색합니다.  자세한 내용은 세부 [정보를 참조하세요.](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains) (Microsoft Defender for Office 365 요금제 1 또는 계획 2)

## <a name="december-2020"></a>2020년 12월

- [기본적으로 보안은 Office 365](secure-by-default.md)
- 자동화된 조사 개선 사항: 수동으로 트리거된 전자 메일 조사에 대한 일반 경고, 사서함 변경을 별도의 엔터티 범주로 처리, 중복 URL 차단 작업을 제거하고, 사용자 손상된 조사를 위한 아웃바운드 전자 메일 클러스터를 만듭니다.

## <a name="november-2020"></a>2020년 11월

- Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2)의 내보내기 제한이 업데이트되었습니다.

## <a name="septemberoctober-2020"></a>2020년 9월/10월

- 새 첫 보안 팁 받는 사람이 보낸 사람의 전자 메일을 처음 받거나 보낸 사람의 전자 메일을 자주 받지 않는 경우를 위한 연락처입니다. 이 설정과 메일 흐름 규칙(전송 규칙)을 Exchange 구성하는 방법에 대한 자세한 내용은 첫 번째 연락처 [보안 팁.](set-up-anti-phishing-policies.md#first-contact-safety-tip)
- [구성 분석기를 사용하여 정책 확인](configuration-analyzer-for-security-policies.md)
- 위협 탐색기에서 상위 대상 [사용자,](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) 전송 규칙 및 커넥터를 포함한 확장된 [기능(위협](threat-explorer.md) 탐색기에서 Office 365 정보에 대한 Defender(테넌트/사용자 정책에 의해 전자 메일이 허용/차단)(Office 365 계획 2용 Defender)
- 위협 탐색기에서 [](threat-explorer.md#threats-in-urls) URL 위협(맬웨어, 피싱, 스팸 또는 없음)(맬웨어, 피싱, 스팸 또는 없음)(Office 365 계획 2용 Defender)
- [위협,](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) 추가 작업, 배달 위치 및 업데이트된 타임라인 보기에 대한 업데이트가 있는 헌팅 환경 위협 탐색기 개선(계획 Office 365 2용 Defender)

## <a name="julyaugust-2020"></a>2020년 7월/8월

- [헌팅](threat-explorer.md#improvements-to-threat-hunting-experience) 환경 개선(Office 365 계획 1 또는 계획 2용 Microsoft Defender)
- [미리 설정한 보안 정책을 사용하여 권장 설정을 쉽게 적용](preset-security-policies.md)

## <a name="marchapril-2020"></a>2020년 3월/4월

- 자동화된 [조사](address-compromised-users-quickly.md) 및 응답을 통해 손상된 사용자 계정을 해결할 수 있는 기능을 이제 일반적으로 사용할 수 있습니다. (Microsoft Defender for Office 365 요금제 2)

## <a name="januaryfebruary-2020"></a>2020년 1월/2월

- [Microsoft Defender for Office 365](campaigns.md) 캠페인 보기의 일반 가용성(Office 365 계획 2용 Microsoft Defender)
- 보안 [운영](threat-explorer.md) 팀이 전자 메일을 조사하는 동안 여러 필드를 검색하고 필터링할 수 있도록 위협 탐색기 기능 [향상:](investigate-malicious-email-that-was-delivered.md)(Microsoft Defender for Office 365 Plan 2)
  - 배달 위치 및 특수 작업
  - 방향성(인바운드, 아웃바운드 또는 반도)
  - 고급 NOT 필터(포함하지 않는 고급 필터링 옵션, 포함하지 않는 등)
  - 세분화 시간 필터(일, 시간, 반시간)

- **인시던트 위젯이** 이제 작업 센터 **위젯이** 됩니다. (보안 및 준수 센터에서 보안 위젯을 & 위협 **관리로 이동** \> **검토**.) (Microsoft Defender for Office 365 요금제 2)

- [금고 문서의](safe-docs.md) **Microsoft 365(미리 보기)**

## <a name="december-2019"></a>2019년 12월

- [오프라인 분석을 위한 URL 클릭](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) 데이터 내보내기(Office 365 계획 1 또는 계획 2용 Microsoft Defender)

- [Microsoft Defender에서 캠페인 보기를 **Office 365(미리** 보기)(Office 365](campaigns.md) 계획 2용 Microsoft Defender)

## <a name="november-2019"></a>2019년 11월

- [새로운 손상된](address-compromised-users-quickly.md) 사용자 검색 및 응답 기능 **확인(미리** 보기)(Microsoft Defender for Office 365 Plan 2)

## <a name="september-2019"></a>2019년 9월

- [자동화된 조사](automated-investigation-response-office.md) 및 대응 기능 사용(Microsoft Defender for Office 365 계획 2)

- [microsoft Defender와](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 통합하여 Office 365 관리 활동 API(Office 365 계획 2용 Defender)를 사용하여 자동화된 조사 및 대응 Office 365 통합

- [전자 메일 헤더 보기 및](investigate-malicious-email-that-was-delivered.md) 전자 메일 본문 다운로드(Office 365 계획 1 또는 계획 2용 Microsoft Defender)

## <a name="august-2019"></a>2019년 8월

- [전자 메일 일정 보기(Microsoft](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) Defender for Office 365 계획 1 또는 계획 2)

## <a name="july-2019"></a>2019년 7월

- [전자 메일 메시지의](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) 배달 작업 및 위치 확인(Office 365 계획 1 또는 2에 대한 Microsoft Defender)

## <a name="june-2019"></a>2019년 6월

- [피싱 URL 보기 및](threat-explorer.md#view-phishing-url-and-click-verdict-data) 판정 데이터 클릭(Office 365 계획 1 또는 계획 2용 Microsoft Defender)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Office 365용 Microsoft Defender 플랜 1 및 플랜 2

Microsoft Defender for Office 365 계획으로 사용할 수 있나요? [각 계획에 포함된 내용에 대해 자세히 알아보시고 을(를) 포함합니다.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="see-also"></a>참고 항목

[Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 서비스 설명](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
