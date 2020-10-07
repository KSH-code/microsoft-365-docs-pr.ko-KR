---
title: 조직의 데이터 개인 정보 취급 방침 모니터링 및 대응
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
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
description: 감사 및 경고 정책 및 데이터 주체 요청을 사용 하 여 개인 데이터 인시던트를 모니터링 하 고 대응 합니다.
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377202"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>조직의 데이터 개인 정보 취급 방침 모니터링 및 대응

Microsoft 365 기능을 사용 하 여 관련 기능을 operationalize 때 조직의 데이터 개인 정보 인시던트를 모니터링, 조사 및 대응 하는 데 도움이 됩니다. 이러한 각 단계에 대 한 프로세스, 절차 및 기타 설명서도 규정 된 본문에 대 한 준수를 시연 하는 것이 중요할 수 있습니다.

여기에는 다음이 포함됩니다. 

- 감사 및 경고 정책
- 데이터 주체 요청 (콘텐츠 검색 및 eDiscovery 포함)
- 추가 조사 도구 및 보고

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>모니터링 및 응답 도구 사용에 영향을 주는 데이터 개인 정보 규정

다음은 정보 거 버 넌 스 컨트롤과 관련이 있을 수 있는 데이터 개인 정보 규정의 예입니다.

- LGPD 문서 46
- LGPD 문서 48
- GDPR 문서 (5) (1) (f)
- GDPR 문서 (15) (1) (e)
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (1) (2) (D)
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (6) (ii)
- HIPAA-HITECH (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 정보 식별](information-protection-deploy-assess.md)을 참조 하세요.

데이터 개인 정보 규정은 일반적으로 모니터링 및 대응을 위해 다음을 호출 합니다.

- 개인 데이터의 저장, 공유 및 처리와 관련 된 활동에 대 한 감사, 경고 및 보고
- DSR (데이터 주체 요청)에 응답 하 고, 경우에 따라 조사 및 기타 관리 조치를 수행 하 여 이러한 요청을 준수 하는 기능입니다.

조직에서는 기타 규정 요구 사항 또는 비즈니스 이유와 같은 다른 목적으로 모니터링 및 대응 활동을 수행 하고자 할 수도 있습니다. 데이터 개인 정보에 대 한 모니터링 및 대응 구성표 설정은 전체 모니터링 및 대응 계획, 구현 및 관리의 일부로 수행 해야 합니다.

이 문서에서는 365 Microsoft 365에서 데이터 개인 정보 규정에 대 한 모니터링 및 대응 체계를 시작 하는 데 도움이 되는 다음과 같은 사항을 설명 하는 유용한 기능을 소개 합니다. 

- 다양 한 데이터 형식 및 원본에 대해 사용할 수 있는 일상적인 모니터링, 조사 및 보고 기술
- Dsr (데이터 주체 요청) 및 익명화, 교정, 삭제와 같은 교정 작업을 처리 하는 데 필요한 메커니즘

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>보안 및 준수 센터의 감사 및 경고 정책

감사, 고급 감사 및 경고 정책을 설정 하려면 다음 문서를 참조 하세요.

- [통합 감사](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [사서함 감사](../compliance/enable-mailbox-auditing.md)
- [고급 감사](../compliance/advanced-audit.md)
- [알림 정책](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대 한 데이터 주체 요청

Microsoft 365에서 DSR에 응답 하는 방법에 대 한 자세한 내용은 [GDPR 및 CCPA에 대 한 데이터 주체 요청](../compliance/gdpr-dsr-office365.md) 을 참조 하세요.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Stream에서 삭제 된 사용자 관리

Microsoft Stream의 경우 사용자가 Azure Active Directory에서 삭제 되는 경우 (Azure AD)이 지점 이전에 게시 된 스트림 비디오와 연결 된 경우 해당 전자 메일 주소는 비디오와 연결 된 상태로 유지 됩니다. 제거 하려면 [Microsoft Stream에서 삭제 된 사용자 관리](https://docs.microsoft.com/stream/managing-deleted-users) 를 참조 하세요.

## <a name="additional-investigative-tools"></a>추가 조사 도구

다음은 조직에서 데이터 개인 정보 보호 관련 인시던트를 모니터링, 조사 및 수정 하는 데 유용할 수 있는 두 가지 추가 도구입니다.

- 사용자 [의 참가자 위험 관리 microsoft 365에서](../compliance/insider-risk-management.md)조직의 위험한 활동을 감지, 조사 하 고 작업을 수행할 수 있도록 하 여 내부 위험을 최소화 하는 데 도움이 되는 microsoft 준수 관리 센터의 기능입니다.
- Microsoft [365의 데이터 조사](../compliance/overview-data-investigations.md)에서 microsoft 365의 중요, 악성 또는 잘못 된 데이터를 검색 하 고 문제를 수정 하는 데 적절 한 조치를 취하는 상황을 조사 하는 microsoft 준수 관리 센터의 기능입니다.
