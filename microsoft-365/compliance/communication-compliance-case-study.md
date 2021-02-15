---
title: 사례 연구 - Contoso는 Microsoft Teams, Exchange 및 커뮤니케이션에 대한 공격적인 언어 Yammer 구성합니다.
description: Contoso에 대한 사례 연구 및 Microsoft Teams, Exchange Online 및 커뮤니케이션에서 공격적인 언어를 모니터링하도록 통신 준수 정책을 빠르게 구성하는 Yammer 있습니다.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 1b9bef180fed9c3afa3b3d8d2319a1fa0260ed14
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126597"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>사례 연구 - Contoso는 Microsoft Teams, Exchange 및 커뮤니케이션에 대한 공격적인 언어 Yammer 구성합니다.

Microsoft 365의 통신 규정 준수는 조직에서 부적절한 메시지를 검색, 캡처 및 처리하도록 하여 통신 위험을 최소화하는 데 도움이 됩니다. 미리 정의된 정책 및 사용자 지정 정책을 사용하면 내부 및 외부 통신에서 정책 일치를 검사하여 지정된 검토자에 의해 검사될 수 있습니다. 검토자는 조직에서 검사된 전자 메일, Microsoft Teams, Yammer 또는 타사 커뮤니케이션을 조사하고 적절한 수정 조치를 취하여 조직의 메시지 표준을 준수하는지 검사할 수 있습니다.

Contoso Corporation은 공격 언어를 모니터링하는 정책을 빠르게 구성해야 하는 소설 조직입니다. Microsoft 365는 주로 전자 메일, Microsoft Teams 및 사용자에 대한 Yammer 지원에 사용했지만 회사 괴롭음에 대해 회사 정책을 적용하기 위한 새로운 요구 사항이 있습니다. Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365 작업의 기본에 대한 기본 지식이 있으며 커뮤니케이션 규정 준수를 빠르게 시작하는 방법에 대한 종단 간 지침을 찾고 있습니다.

이 사례 연구에서는 공격적인 언어에 대한 통신을 모니터링하도록 통신 준수 정책을 신속하게 구성하기 위한 기본에 대해 다루게 됩니다. 이 지침에는 다음이 포함됩니다.

- 1단계 - 통신 준수 계획
- 2단계 - Microsoft 365에서 통신 준수에 액세스
- 3단계 - 선행 구성 및 통신 준수 정책 만들기
- 4단계 - 경고 조사 및 수정

## <a name="step-1-planning-for-communication-compliance"></a>1단계: 통신 준수 계획

Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365의 규정 준수 솔루션에 대한 온라인 웨비나에 참석하고 커뮤니케이션 규정 준수 정책이 직장 괴롭혔을 수 있는 업데이트된 회사 정책 요구 사항을 충족하는 데 도움이 된다고 결정했습니다. 함께 협력하여 Microsoft Teams에서 전송된 채팅, 개인 메시지 및 커뮤니티 대화, Exchange Online에서 보낸 전자 메일 메시지에 대한 공격적인 언어를 모니터링하는 Yammer 정책을 만들고 사용하도록 설정하는 계획을 개발했습니다. 계획에는 다음을 식별하는 것이 포함됩니다.

- 통신 준수 기능에 액세스해야 하는 IT 관리자
- 커뮤니케이션 정책을 만들고 관리해야 하는 규정 준수 전문가.
- 커뮤니케이션 규정 준수 경고를 조사하고 수정해야 하는 기타 부서(인사, 법률 등)의 규정 준수 전문가 및 기타 동료
- 통신 준수 비방 언어 정책에 대한 범위 내 사용자입니다.

### <a name="licensing"></a>라이선싱

첫 번째 단계는 Contoso의 Microsoft 365 라이선스에 통신 준수 솔루션에 대한 지원이 포함되어 있는지 확인하는 것입니다. Contoso IT 관리자는 통신 규정 준수에 액세스하고 사용하려면 Contoso에 다음 중 하나가 있는지 확인해야 합니다.

- Microsoft 365 E5 구독(유료 또는 평가판)
- Microsoft 365 E3 구독 + Microsoft 365 E5 규정 준수 추가 기능
- Microsoft 365 E3 구독 + Microsoft 365 E5 Insider Risk Management 추가 기능
- Microsoft 365 A5 구독(유료 또는 평가판)
- Microsoft 365 A3 구독 + Microsoft 365 A5 준수 추가 기능
- Microsoft 365 A3 구독 + Microsoft 365 A5 내부자 위험 관리 추가 기능
- Microsoft 365 G5 구독(유료 또는 평가판)
- Microsoft 365 G5 구독 + Microsoft 365 G5 규정 준수 추가 기능
- Microsoft 365 G5 구독 + Microsoft 365 G5 Insider Risk Management 추가 기능
- Office 365 Enterprise E5 구독(유료 또는 평가판)
- Office 365 Enterprise E3 구독 + Office 365 고급 준수 추가 기능(더 이상 새 구독에 사용할 수 없음, 참고 참조)

또한 통신 준수 정책에 포함된 사용자에게 위의 라이선스 중 하나를 할당해야 하는지도 확인해야 합니다.

>[!IMPORTANT]
>Office 365 Advanced Compliance는 더 이상 독립 실행형 구독으로 판매하지 않습니다. 현재 구독이 만료되면 고객은 동일한 또는 추가 규정 준수 기능을 포함하는 위의 구독 중 하나로 전환해야 합니다.

Contoso IT 관리자는 다음 단계를 수행하여 Contoso에 대한 라이선스 지원을 확인해야 합니다.

1. IT 관리자는 **Microsoft 365** [ https://admin.microsoft.com)](https://admin.microsoft.com) 관리 센터에 로그인하고 **Microsoft 365** 관리 센터 청구  >    >  **라이선스로 이동합니다.**

2. 여기에서 통신 준수에 대한 [](communication-compliance-configure.md#subscriptions-and-licensing) 지원을 포함하는 라이선스 옵션 중 하나를 사용할 수 있습니다.

![통신 규정 준수 라이선싱](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>통신 규정 준수에 대한 사용 권한

통신 준수 기능을 관리하기 위한 사용 권한을 구성하는 데 사용되는 5개의 역할 그룹이 있습니다. 커뮤니케이션 **규정** 준수를 Microsoft 365 규정 준수 센터의 메뉴 옵션으로 사용할 수 있도록 설정하고 이러한 구성 단계를 계속하기 위해 Contoso 관리자에게 통신 준수 관리자 역할이 *할당됩니다.*

Contoso는 통신 준수  역할 그룹을 사용하여 모든 통신 준수 관리자, 분석가, 조사자 및 뷰어를 그룹에 할당하기로 결정했습니다. 이렇게 하면 Contoso가 보다 쉽고 규정 준수 관리 요구 사항에 가장 잘 맞게 시작할 수 있습니다.

|**역할**|**역할 권한**|
|:-----|:-----|
| **커뮤니케이션 규정 준수** | 이 역할 그룹을 사용하여 단일 그룹에서 조직의 통신 준수를 관리합니다. 지정된 관리자, 분석가, 조사자 및 뷰어에 대한 모든 사용자 계정을 추가하여 단일 그룹에서 통신 준수 권한을 구성할 수 있습니다. 이 역할 그룹에는 모든 통신 준수 권한 역할이 포함되어 있습니다. 이 구성은 통신 규정 준수를 빠르게 시작하는 가장 쉬운 방법으로, 별도의 사용자 그룹에 대해 별도의 사용 권한이 정의되지 않은 조직에 적합한 구성입니다. |
| **커뮤니케이션 준수 관리자** | 이 역할 그룹을 사용하여 처음에 통신 준수를 구성하고 나중에 통신 준수 관리자를 정의된 그룹으로 나갈 수 있습니다. 이 역할 그룹에 할당된 사용자는 통신 준수 정책, 전역 설정 및 역할 그룹 할당을 만들고, 읽고, 업데이트하고, 삭제할 수 있습니다. 이 역할 그룹에 할당된 사용자는 메시지 알림을 볼 수 없습니다. |
| **커뮤니케이션 준수 분석가** | 이 그룹을 사용하여 커뮤니케이션 준수 분석가 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 검토자로 할당된 정책을 보거나, 메시지 콘텐츠가 아닌 메시지 메타데이터를 보거나, 추가 검토자로 에스컬레이터하거나, 사용자에게 알림을 보낼 수 있습니다. 분석가가 보류 중인 경고를 해결할 수 없습니다. |
| **커뮤니케이션 준수 조사자** | 이 그룹을 사용하여 커뮤니케이션 준수 조사자 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 메시지 메타데이터 및 콘텐츠를 보고, 추가 검토자로 에스컬레이터하고, Advanced eDiscovery 사례로 에스컬레이터하고, 사용자에게 알림을 보내고, 경고를 해결할 수 있습니다. |
| **통신 준수 뷰어** | 이 그룹을 사용하여 통신 보고서를 관리할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 홈 페이지에서 모든 보고 위젯에 액세스할 수 있으며 모든 통신 준수 보고서를 볼 수 있습니다. |

1. Contoso IT 관리자는 **Office 365** 보안 & [ https://protection.office.com/permissions)](https://protection.office.com/permissions) 준수 센터 권한 페이지에 로그인합니다(전역 관리자 계정에 대한 자격 증명을 사용하여 Microsoft 365에서 역할을 보고 관리하기 위한 링크를 선택).
2. 보안 **&** 준수 센터에서 사용 권한으로  이동하여 Office 365에서 역할을 보고 관리할 링크를 선택합니다.
3. 관리자가 통신 준수 역할 *그룹을* 선택한 다음 역할 **그룹 편집을 선택합니다.**
4. 관리자가 왼쪽 **탐색** 창에서 구성원 선택을 선택한 다음 편집을 **선택합니다.**
5. 추가를  선택한 다음 커뮤니케이션 규정 준수를 관리하고, 조사하고, 경고를 검토할 모든 Contoso 사용자에 대한 확인란을 선택합니다.
6. 관리자가 추가를 **선택한** 다음 **완료를 선택합니다.**
7. 역할 **그룹에** Contoso 사용자를 추가하려면 저장을 선택합니다. **닫기(Close)를** 선택하여 단계를 완료합니다.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>2단계: Microsoft 365에서 통신 준수에 액세스

통신 준수에 대한 사용 권한을 구성한 후 통신 준수 역할 그룹에 할당된 Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365의 통신 준수 솔루션에 액세스할 수 있습니다. Contoso IT 관리자 및 규정 준수 전문가는 통신 규정 준수에 액세스하고 새 정책 만들기를 시작하는 여러 가지 방법을 사용할 수 있습니다.

- 통신 준수 솔루션에서 직접 시작
- Microsoft 365 규정 준수 센터에서 시작
- Microsoft 365 솔루션 카탈로그에서 시작
- Microsoft 365 관리 센터에서 시작

### <a name="starting-directly-from-the-communication-compliance-solution"></a>통신 준수 솔루션에서 직접 시작

솔루션에 액세스하는 가장 빠른 방법은 통신 준수() 솔루션에 직접 로그인하는  <https://compliance.microsoft.com/supervisoryreview> 것입니다. 이 링크를 사용하여 Contoso IT 관리자 및 규정 준수 전문가는 알림 상태를 신속하게 검토하고 미리 정의된 템플릿에서 새 정책을 만들 수 있는 커뮤니케이션 준수 개요 대시보드로 연결됩니다.

![커뮤니케이션 규정 준수 개요](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Microsoft 365 규정 준수 센터에서 시작

Contoso IT 관리자 및 규정 준수 전문가가 통신 준수 솔루션에 액세스하는 또 다른 쉬운 방법은 **Microsoft 365** [ https://compliance.microsoft.com)](https://compliance.microsoft.com)규정 준수 센터(. 로그인한 후 사용자는 모든 준수  솔루션을 표시하기 위해 모든 컨트롤 표시를  선택한 다음 시작하려면 통신 준수 솔루션을 선택하기만하면 됩니다.

![준수 센터](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Microsoft 365 솔루션 카탈로그에서 시작

Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365 솔루션 카탈로그를 선택하여 통신 준수 솔루션에 액세스하도록 선택할 수도 있습니다. Microsoft 365 규정 준수 센터에서 왼쪽 탐색의 솔루션 섹션에서 카탈로그를 선택하면 모든 **Microsoft 365** 규정 준수 솔루션을 나열하는 솔루션 카탈로그를 열 수 있습니다.   Contoso IT  관리자는 내부자 위험 관리 섹션으로 스크롤하여 통신 준수를 선택하여 시작할 수 있습니다. Contoso IT 관리자는 또한 탐색에 표시 컨트롤을 사용하여 앞으로 로그인할 때 더 빠르게 액세스할 수 있도록 통신 준수 솔루션을 왼쪽 탐색 창에 고정하기로 결정했습니다.

![솔루션 카탈로그](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 시작

Microsoft 365 관리 센터에서 시작할 때 통신 준수에 액세스하려면 Contoso IT 관리자 및 규정 준수 [ https://admin.microsoft.com)](https://admin.microsoft.com) 전문가가 Microsoft 365 관리 센터에 로그인하고 **Microsoft 365** 관리 센터 규정 준수로  >  이동합니다.

![통신 준수 링크](../media/communication-compliance-case-compliance-link.png)

이 작업을 수행하면 **Office 365** 보안 및 준수 센터가 열리며 페이지 상단의 배너에 제공된 **Microsoft 365** 규정 준수 센터 링크를 선택해야 합니다.

![Office 365 보안 및 규정 준수 센터](../media/communication-compliance-case-scc.png)

**Microsoft 365** 규정 준수 센터에서 일단 Contoso IT 관리자는 모두 표시를 선택하여 준수 솔루션의 전체 목록을 표시합니다. 

![커뮤니케이션 준수 메뉴](../media/communication-compliance-case-show-all.png)

모두 **표시를 선택한** 후 Contoso IT 관리자는 통신 준수 솔루션에 액세스할 수 있습니다.

![커뮤니케이션 규정 준수 개요](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>3단계: 선행 구성 및 통신 준수 정책 만들기

통신 준수 정책을 시작하기 위해 Contoso IT 관리자가 비방 언어를 모니터링하도록 새 정책을 설정하기 전에 구성해야 하는 몇 가지 선행 조건이 있습니다. 이러한 선행 요구가 완료되면 Contoso IT 관리자 및 규정 준수 전문가는 새 정책 및 규정 준수 전문가를 구성하여 조사를 시작하고 생성된 모든 경고를 재구성할 수 있습니다.

### <a name="enabling-auditing-in-microsoft-365"></a>Microsoft 365에서 감사 사용

커뮤니케이션 규정 준수를 위해서는 감사 로그를 통해 경고를 표시하고 검토자에 의해 수행된 수정 작업을 추적해야 합니다. 감사 로그는 정의된 조직 정책과 연결된 모든 활동 또는 커뮤니케이션 준수 정책이 변경될 경우를 요약한 것입니다.

Contoso IT 관리자는 감사를 [](turn-audit-log-search-on-or-off.md) 켜는 단계별 지침을 검토하고 완료합니다. 감사를 켜면 감사 로그가 준비되고 있으며 준비가 완료된 후 몇 시간 후에 검색을 실행할 수 있습니다. Contoso IT 관리자는 이 작업을 한 번만 수행하면 됩니다.

### <a name="configuring-yammer-tenant-for-native-mode"></a>기본 Yammer 테넌트 구성

커뮤니케이션 규정 준수를 위해서는 조직의 Yammer 테넌트가 개인 메시지 및 공용 커뮤니티 대화에서 비방 언어를 모니터링해야 합니다.

Contoso IT 관리자는 Microsoft 365 문서의 Yammer 기본 모드 개요에 있는 정보를 검토하고 [Microsoft 365용](/yammer/configure-your-yammer-network/overview-native-mode) 기본 모드에 대한 Yammer 네트워크 구성에서 마이그레이션 도구를 실행하기 위한 단계를 따르도록 합니다. [](/yammer/configure-your-yammer-network/native-mode)

### <a name="setting-up-a-group-for-in-scope-users"></a>범위 내 사용자에 대한 그룹 설정

Contoso 규정 준수 전문가는 비방 언어를 모니터링할 통신 정책에 모든 사용자를 추가하려는 경우 각 사용자 계정을 정책에 별도로 추가할 수도 있지만, 이 정책의 사용자에 대해 모든  사용자 메일 그룹을 사용하는 것이 훨씬 더 쉬우고 시간을 절약할 수 있습니다.

모든 Contoso 사용자를 포함하려면 새 그룹을 만들어야 하여 다음 단계를 수행합니다.

1. Contoso IT 관리자 IT가 **Microsoft 365** [ https://admin.microsoft.com)](https://admin.microsoft.com) 관리 센터에 로그인하고 **Microsoft 365** 관리 센터  >  **그룹 그룹으로**  >  **이동합니다.**
2. 그룹 **추가를 선택하고** 마법사를 완료하여 *새 Microsoft 365* 그룹 또는 메일 그룹을 *만들 수 있습니다.*

    ![그룹](../media/communication-compliance-case-all-employees.png)

3. 새 그룹을 만든 후 모든 Contoso 사용자를 새 그룹에 추가해야 합니다. Exchange 관리 **센터를 열고** [ https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) **Exchange 관리 센터** 받는 사람  >  **그룹으로**  >  **이동합니다.** Contoso IT 관리자는 구성원 자격 영역과 새로 만든 *모든* 직원  그룹을 선택하고 편집 컨트롤을 선택하여 모든 Contoso 사용자를 마법사의 새 그룹에 추가합니다.

    ![Exchange 관리 센터](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>비방 언어를 모니터링하는 정책 만들기

모든 선행 조건이 완료되면 Contoso의 IT 관리자와 규정 준수 전문가가 공격 언어를 모니터링하도록 통신 준수 정책을 구성할 준비가 완료되었습니다. 새 공격 언어 정책 템플릿을 사용하여 이 정책을 구성하는 것은 간단하고 빠르습니다.

1. Contoso IT 관리자 및 규정 준수 전문가는 **Microsoft 365** 규정 준수 센터에 로그인하고 왼쪽 탐색 창에서 커뮤니케이션 규정 준수를 선택합니다.  이 작업을 수행하면 커뮤니케이션 준수 정책 템플릿에 대한 빠른 링크가 있는 개요 대시보드가 열립니다.  템플릿 **시작을** 선택하여 비방성 언어 서식 파일 **모니터링을** 선택합니다.

    ![통신 규정 준수 비방 언어 서식 파일](../media/communication-compliance-case-template.png)

2. 정책 템플릿 마법사에서 Contoso IT 관리자 및 규정 준수 전문가는 세 가지 필수 필드인 정책 **이름,** 감독할 사용자 또는 그룹 및 검토자 필드를 **작성합니다.**
3. 정책 마법사가 정책의 이름을 이미 제안한 것이기 때문에 IT 관리자와 규정 준수 전문가는 제안된 이름을 유지하며 나머지 필드에 집중하기로 결정합니다. 사용자는 필드를 감독할  사용자 또는 그룹의 모든 사용자 그룹을 선택하고 검토자 필드에 대한 정책 경고를 조사하고 수정해야 하는 준수 전문가를 **선택합니다.**  정책을 구성하고 경고 정보 수집을 시작하는 마지막 단계는 정책 **만들기를 선택하는 것입니다.**

    ![통신 규정 준수 비방 언어 마법사](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>4단계: 경고 조사 및 수정

비방 언어를 모니터링하는 통신 준수 정책이 구성되면 Contoso 규정 준수 전문가를 위한 다음 단계는 정책에 의해 생성된 경고를 조사하고 수정하는 것입니다. 정책이 모든 통신 원본 채널의 통신을 완전히 처리하고 경고 대시보드에 알림을 표시하는 데 최대 24시간이 **소요됩니다.**

경고가 생성된 후 Contoso 규정 준수 [](communication-compliance-investigate-remediate.md) 전문가는 워크플로 지침에 따라 공격적인 언어 문제를 조사하고 수정합니다.