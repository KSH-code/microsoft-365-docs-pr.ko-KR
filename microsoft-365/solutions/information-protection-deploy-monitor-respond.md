---
title: 조직의 데이터 개인 정보 보호 인시던트 모니터링 및 대응
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 감사 및 경고 정책 및 데이터 주체 요청을 사용하여 개인 데이터 인시던트 모니터링 및 대응
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213185"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>조직의 데이터 개인 정보 보호 인시던트 모니터링 및 대응

Microsoft 365 기능을 운영할 때 조직의 데이터 개인 정보 보호 인시던트 모니터링, 조사 및 대응에 도움이 되는 다양한 기능을 사용할 수 있습니다. 이러한 각 문서에 대한 프로세스, 절차 및 기타 설명서를 가지는 것은 규제 기관의 규정 준수를 입증하는 데도 중요할 수 있습니다.

다음이 포함되어 있습니다. 

- 감사 및 경고 정책
- 데이터 주체 요청(콘텐츠 검색 및 eDiscovery 포함)
- 추가 조사 도구 및 보고

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>모니터링 및 응답 도구 사용에 영향을 미치는 데이터 개인 정보 규정

다음은 정보 거버넌스 제어와 관련이 있을 수 있는 데이터 개인 정보 보호 규정의 샘플 목록입니다.

- LGPD 문서 46
- LGPD 문서 48
- GDPR 문서 (5)(1)(f)
- GDPR 문서 (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA(1798.105(c))

자세한 내용은 데이터 개인 정보 보호 위험 평가 [및 중요한 정보 식별을 참조하세요.](information-protection-deploy-assess.md)

데이터 개인 정보 규정은 일반적으로 모니터링 및 응답을 위해 다음을 요구합니다.

- 개인 데이터의 저장, 공유 및 처리와 관련된 활동에 대한 감사, 경고 및 보고
- DSR(데이터 주체 요청)에 응답하고 경우에 따라 조사 및 기타 관리 조치를 수행하여 이러한 요청을 준수할 수 있습니다.

조직은 다른 규정 준수 요구 또는 비즈니스상의 이유로 모니터링 및 대응 활동을 수행하고자 할 수도 있습니다. 데이터 개인 정보 보호에 대한 모니터링 및 응답 체계를 설정하는 것이 전체 모니터링 및 응답 계획, 구현 및 관리의 일부로 수행됩니다.

이 문서에서는 데이터 개인 정보 보호 규정에 대한 Microsoft 365 모니터링 및 응답 체계를 시작하는 데 도움이 되는 Microsoft 365 정보를 제공합니다. 

- 다양한 데이터 형식 및 원본에 대해 어떤 종류의 모니터링, 조사 및 보고 기술을 사용할 수 있나요?
- 데이터 주체 요청(DSRs)을 처리하는 데 필요한 메커니즘 및 수정 작업(예: 비음성, 수정 및 수정)입니다.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>보안 및 준수 센터의 감사 및 경고 정책

감사, 고급 감사 및 경고 정책 설정에 대한 자세한 내용은 다음 문서를 참조합니다.

- [통합 감사](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [사서함 감사](../compliance/enable-mailbox-auditing.md)
- [고급 감사](../compliance/advanced-audit.md)
- [알림 정책](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 데이터 주체 요청

DSR에 응답하는 데 대한 자세한 내용은 GDPR 및 [CCPA에](/compliance/regulatory/gdpr-dsr-Office365) 대한 데이터 주체 요청을 Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Stream에서 삭제된 사용자 관리

Microsoft Stream의 경우 사용자가 Azure AD(Azure Active Directory)에서 삭제될 때 해당 이름이 이전에 게시된 Stream 비디오와 연결되어 있는 경우 해당 전자 메일 주소는 비디오와 연결된 상태로 남아 있습니다. Microsoft [Stream에서 삭제된 사용자 관리를](/stream/managing-deleted-users) 참조하여 제거합니다.

## <a name="insider-risk-management-as-an-investigative-tool"></a>조사 도구로 내부자 위험 관리

[Microsoft 365](../compliance/insider-risk-management.md) 내부자 위험 관리는 조직에서 위험한 활동을 감지, 조사 및 조치를 취할 수 있도록 하여 내부 위험을 최소화하는 데 도움이 되는 Microsoft 규정 준수 관리 센터의 기능입니다.