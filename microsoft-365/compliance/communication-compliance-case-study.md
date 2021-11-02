---
title: 사례 연구 - Contoso는 통신에 대한 부적절한 콘텐츠 정책을 Microsoft Teams, Exchange Yammer 구성합니다.
description: Contoso에 대한 사례 연구 및 이러한 사례 연구를 통해 통신, Microsoft Teams, Exchange Online 및 통신에서 부적절한 콘텐츠를 모니터링하도록 통신 준수 정책을 빠르게 Yammer 있습니다.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: ff326544d2485fa3ca7385f9ad8b924514aec1a5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60647561"
---
# <a name="case-study---contoso-quickly-configures-an-inappropriate-content-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>사례 연구 - Contoso는 통신에 대한 부적절한 콘텐츠 정책을 Microsoft Teams, Exchange Yammer 구성합니다.

조직의 Microsoft 365 규정 준수는 조직에서 부적절한 콘텐츠가 있는 메시지를 검색, 캡처 및 처리하도록 하여 통신 위험을 최소화하는 데 도움이 됩니다. 부적절한 콘텐츠에는 비언어, 위협, 괴롭히기 및 부적절한 이미지가 포함되어 있을 수 있습니다. 미리 정의된 정책과 사용자 지정 정책을 사용하면 내/외부 커뮤니케이션에서 정책 일치 사항을 검사하여 지정된 검토자가 검토할 수 있습니다. 검토자는 조직에서 검사된 전자 메일, Microsoft Teams, Yammer 또는 타사 통신을 조사하고 적절한 수정 조치를 취하여 조직의 메시지 표준을 준수하는지 검사할 수 있습니다.

Contoso Corporation은 부적절한 콘텐츠를 모니터링하도록 정책을 신속하게 구성해야 하는 소설 조직입니다. 주로 전자 메일, Microsoft 365 및 사용자에 대한 Microsoft Teams Yammer 지원에 대해 사용했지만 직장 괴롭음에 대한 회사 정책을 적용하기 위한 새로운 요구 사항이 있습니다. Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365 작업의 기본 원칙을 이해하고 있으며 통신 규정 준수를 빠르게 시작하는 방법에 대한 종단 간 지침을 찾고 있습니다.

이 사례 연구에서는 부적절한 콘텐츠에 대한 통신을 모니터링하도록 통신 준수 정책을 신속하게 구성하기 위한 기본 내용을 다 가정합니다. 이 지침에는 다음이 포함됩니다.

- 1단계 - 커뮤니케이션 준수 계획
- 2단계 - Microsoft 365의 커뮤니케이션 규정 준수 액세스
- 3단계 - 필수 구성 요소 구성 및 커뮤니케이션 규정 준수 정책 생성
- 4단계 - 경고 조사 및 업데이트 적용

## <a name="step-1-planning-for-communication-compliance"></a>1단계: 통신 규정 준수 계획

Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365 규정 준수 솔루션에 대한 온라인 웨비나에 참석하고 커뮤니케이션 규정 준수 정책이 작업 공간 괴롭침을 줄이기 위해 업데이트된 회사 정책 요구 사항을 충족하는 데 도움이 된다고 결정했습니다. 함께 협력하여 Microsoft Teams, Yammer의 개인 메시지 및 커뮤니티 대화, Exchange Online에서 전송된 전자 메일 메시지에 대한 부적절한 콘텐츠를 모니터링하는 통신 준수 정책을 만들고 사용하도록 설정하는 계획을 세우고 Exchange Online. 해당 계획에서는 다음 사항을 식별합니다.

- 통신 규정 준수 기능에 액세스해야 하는 IT 관리자
- 커뮤니케이션 정책을 만들고 관리해야 하는 규정 준수 전문가.
- 커뮤니케이션 규정 준수 경고를 조사하고 수정해야 하는 기타 부서의 준수 전문가 및 기타 동료(인사, 법률 등)입니다.
- 통신 규정 준수에 대한 범위 내 사용자 부적절한 콘텐츠 정책입니다.

### <a name="licensing"></a>라이선싱

첫 번째 단계는 Contoso의 Microsoft 365 라이선스에 통신 준수 솔루션에 대한 지원이 포함되는지 확인하는 것입니다. 통신 규정 준수에 액세스하고 사용하려면 Contoso IT 관리자가 Contoso에 다음 중 하나가 있는지 확인해야 합니다.

- Microsoft 365 E5 구독(유료 또는 평가판)
- Microsoft 365 E3 구독 + Microsoft 365 E5 Compliance 추가 기능
- Microsoft 365 E3 + Microsoft 365 E5 내부자 위험 관리 추가 기능
- Microsoft 365 A5 구독(유료 또는 평가판)
- Microsoft 365 A3 구독 + Microsoft 365 A5 준수 추가 기능
- Microsoft 365 A3 + Microsoft 365 A5 내부자 위험 관리 추가 기능
- Microsoft 365 G5 구독(유료 또는 평가판 버전)
- Microsoft 365 G5 구독 + Microsoft 365 G5 준수 추가 기능
- Microsoft 365 G5 구독 + Microsoft 365 G5 내부자 위험 관리 추가 기능
- Office 365 Enterprise E5 구독(유료 또는 평가판)
- Office 365 Enterprise E3 구독 + Office 365 Advanced Compliance 추가 기능(새 구독에서 더 이상 사용할 수 없음, 참고 참조)

또한 통신 준수 정책에 포함된 사용자에게 위의 라이선스 중 하나를 할당해야 합니다.

> [!IMPORTANT]
> Office 365 Advanced Compliance 독립 실행형 구독으로 더 이상 판매하지 않습니다. 현재 구독이 만료되면 고객은 동일한 또는 추가 규정 준수 기능을 포함하는 위의 구독 중 하나로 전환해야 합니다.

Contoso IT 관리자는 다음 단계를 수행하여 Contoso에 대한 라이선스 지원을 확인할 수 있습니다.

1. IT 관리자는 에 로그인하여 Microsoft 365 관리 센터 청구 <https://admin.microsoft.com> Microsoft 365 관리 센터 >   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">**로 이동 합니다.**</a>

2. 여기서 통신 규정 준수에 [](communication-compliance-configure.md#subscriptions-and-licensing) 대한 지원을 포함하는 라이선스 옵션 중 하나를 사용할 수 있습니다.

![통신 규정 준수 라이선싱.](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>통신 규정 준수에 대한 사용 권한

통신 준수 기능을 관리하기 위한 사용 권한을 구성하는 데 사용되는 5개의 역할 그룹이 있습니다. 통신 **규정** 준수를 조직의 메뉴 옵션으로 사용할 수 있도록 Microsoft 365 규정 준수 센터 구성 단계를 계속하기 위해 Contoso 관리자에게 통신 준수 관리자 역할이 *할당됩니다.*

Contoso는 통신 준수  역할 그룹을 사용하여 모든 통신 준수 관리자, 분석가, 조사자 및 뷰어를 그룹에 할당하기로 결정했습니다. 이를 통해 Contoso는 규정 준수 관리 요구 사항을 보다 쉽고 빠르게 시작할 수 있습니다.

|**역할**|**역할 권한**|
|:-----|:-----|
| **통신 규정 준수** | 이 역할 그룹을 사용하여 단일 그룹에서 조직에 대한 통신 규정 준수를 관리합니다. 지정된 관리자, 분석가, 조사자 및 뷰어에 대한 모든 사용자 계정을 추가하여 단일 그룹에서 통신 준수 권한을 구성할 수 있습니다. 이 역할 그룹에는 모든 통신 준수 권한 역할이 포함되어 있습니다. 이 구성은 통신 규정 준수를 빠르게 시작하는 가장 쉬운 방법으로, 별도의 사용자 그룹에 대해 정의된 별도의 사용 권한이 필요하지 않은 조직에 적합한 구성입니다. |
| **커뮤니케이션 규정 준수 관리자** | 이 역할 그룹을 사용하여 처음에 통신 준수를 구성하고 나중에 통신 준수 관리자를 정의된 그룹으로 나란히 구성합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 정책, 전역 설정 및 역할 그룹 할당을 만들고, 읽고, 업데이트하고, 삭제할 수 있습니다. 이 역할 그룹에 할당된 사용자는 메시지 알림을 볼 수 없습니다. |
| **커뮤니케이션 준수 분석가** | 이 그룹을 사용하여 커뮤니케이션 규정 준수 분석가 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 검토자로 할당된 정책을 보거나, 메시지 메타데이터(메시지 콘텐츠 아미타)를 보거나, 추가 검토자로 에스컬레이터하거나, 사용자에게 알림을 보낼 수 있습니다. 분석가가 보류 중인 경고를 해결할 수 없습니다. |
| **커뮤니케이션 규정 준수 조사자** | 이 그룹을 사용하여 커뮤니케이션 준수 조사자 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 메시지 메타데이터 및 콘텐츠를 보고, 추가 검토자로 에스컬레이터하고, Advanced eDiscovery 사례로 에스컬레이터하고, 사용자에게 알림을 보내고, 경고를 해결할 수 있습니다. |
| **커뮤니케이션 규정 준수 뷰어** | 이 그룹을 사용하여 통신 보고서를 관리할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 홈 페이지의 모든 보고 위젯에 액세스할 수 있으며 모든 통신 준수 보고서를 볼 수 있습니다. |

1. Contoso IT 관리자는 전역 [](https://compliance.microsoft.com/permissions) 관리자 계정에 대한 자격 증명을 사용하여 Microsoft 365 규정 준수 센터 권한 페이지에 로그인하고 해당 페이지에서 역할을 보고 관리하기 위한 링크를 Microsoft 365.
2. 이 **Microsoft 365 규정 준수 센터** 에서 사용 권한으로 이동한 다음 해당 권한에서 역할을 보고 관리하기 위한 링크를 Office 365. 
3. 관리자는 통신 준수 역할 *그룹을* 선택한 다음 역할 그룹 **편집 을 선택합니다.**
4. 관리자는 왼쪽 **탐색** 창에서 구성원 선택을 선택한 다음 편집 을 **선택합니다.**
5. 사용자는 **추가를** 선택한 다음 커뮤니케이션 규정 준수를 관리하고, 조사하고, 경고를 검토할 모든 Contoso 사용자에 대한 확인란을 선택합니다.
6. 관리자는 추가 **를** 선택한 다음 완료 를 **선택합니다.**
7. Contoso 사용자를 역할 그룹에 추가하려면 저장을 선택합니다.  닫기 **를 선택하여** 단계를 완료합니다.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>2단계: 2단계: 2단계에서 통신 준수에 Microsoft 365

통신 규정 준수에 대한 사용 권한을 구성한 후, 통신 준수 역할 그룹에 할당된 Contoso IT 관리자 및 규정 준수 전문가는 통신 규정 준수 솔루션에 Microsoft 365. Contoso IT 관리자 및 규정 준수 전문가는 통신 규정 준수에 액세스하고 새 정책을 만드는 여러 가지 방법을 사용할 수 있습니다.

- 통신 준수 솔루션에서 직접 시작
- 시작점에서 Microsoft 365 규정 준수 센터
- 솔루션 카탈로그에서 Microsoft 365 시작
- 시작점에서 Microsoft 365 관리 센터

### <a name="starting-directly-from-the-communication-compliance-solution"></a>통신 준수 솔루션에서 직접 시작

솔루션에 액세스하는 가장 빠른 방법은 통신 규정 준수( ) 솔루션에 직접 **로그인하는** <https://compliance.microsoft.com/supervisoryreview> 것입니다. 이 링크를 사용하면 Contoso IT 관리자 및 규정 준수 전문가가 알림 상태를 빠르게 검토하고 미리 정의된 템플릿에서 새 정책을 만들 수 있는 커뮤니케이션 규정 준수 개요 대시보드로 연결됩니다.

![커뮤니케이션 규정 준수 개요.](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>시작점에서 Microsoft 365 규정 준수 센터

Contoso IT 관리자 및 규정 준수 전문가가 통신 규정 준수 솔루션에 액세스하는 또 다른 쉬운 방법은 에 직접 로그인하는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터.</a> 로그인 후 사용자는 **모두 표시** 컨트롤을 선택하여 모든 규정 준수 솔루션을 표시한 다음 **커뮤니케이션 규정 준수** 솔루션을 선택하여 시작하기만 하면 됩니다.

![규정 준수 센터.](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>솔루션 카탈로그에서 Microsoft 365 시작

Contoso IT 관리자 및 규정 준수 전문가는 또한 솔루션 카탈로그를 선택하여 통신 준수 솔루션에 액세스하도록 Microsoft 365 있습니다. 왼쪽 **탐색** 창에 있는 동안 솔루션에서 카탈로그 섹션을 선택하여 Microsoft 365 규정 준수 센터 솔루션 카탈로그를 열 수 Microsoft 365 있습니다.  Contoso IT 관리자는 **내부자** 위험 관리 섹션으로 스크롤하여 커뮤니케이션 규정 준수를 선택하여 시작할 수 있습니다. Contoso IT 관리자는 또한 탐색에 표시 컨트롤을 사용하여 통신 준수 솔루션을 왼쪽 탐색 창에 고정하여 로그인할 때 더 빠르게 액세스할 수 있도록 합니다.

![솔루션 카탈로그.](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>시작점에서 Microsoft 365 관리 센터

Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365 관리 센터 시작할 때 통신 규정 준수에 액세스하기 위해 Microsoft 365 관리 센터 [ https://admin.microsoft.com) (에](https://admin.microsoft.com) 로그인하고 으로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터.</a>

![커뮤니케이션 규정 준수 링크.](../media/communication-compliance-case-compliance-link.png)

이 작업을 **수행하면** Office 365 및 준수 센터가 열리며 페이지  맨 위에 있는 Microsoft 365 규정 준수 센터 제공된 보안 및 준수 센터에 대한 링크를 선택해야 합니다.

![Office 365 및 규정 준수 센터를 관리합니다.](../media/communication-compliance-case-scc.png)

다음에 **Microsoft 365 규정 준수 센터** Contoso IT 관리자는 모두  표시를 선택하여 준수 솔루션의 전체 목록을 표시합니다.

![커뮤니케이션 규정 준수 메뉴.](../media/communication-compliance-case-show-all.png)

모두 **표시를 선택한** 후 Contoso IT 관리자는 통신 준수 솔루션에 액세스할 수 있습니다.

![커뮤니케이션 규정 준수 개요.](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>3단계: 선행 구성 및 통신 준수 정책 만들기

통신 준수 정책을 시작하기 위해 Contoso IT 관리자가 부적절한 콘텐츠를 모니터링하도록 새 정책을 설정하기 전에 구성해야 하는 몇 가지 선행 조건이 있습니다. 이러한 사전 요구 사항이 완료되면 Contoso IT 관리자 및 규정 준수 전문가가 새 정책을 구성할 수 있으며 규정 준수 전문가가 조사를 시작하고 생성된 경고에 업데이트를 적용할 수 있습니다.

### <a name="enabling-auditing-in-microsoft-365"></a>2016에서 감사 Microsoft 365

커뮤니케이션 규정 준수를 수행하려면 감사 로그가 경고를 표시하고 검토자가 수행한 교정 작업을 추적해야 합니다. 감사 로그는 정의된 조직 정책과 관련된 모든 활동 또는 커뮤니케이션 규정 준수 정책이 변경될 때마다 요약된 것입니다.

ContosoIT 관리자가 [단계별 지침](turn-audit-log-search-on-or-off.md)을 검토하고 완료하여 감사를 사용하도록 설정합니다. 감사를 설정한 후에는 감사 로그를 준비하고 있으며 준비가 완료된 후 몇 시간 내에 검색을 실행할 수 있다는 메시지가 표시됩니다. Conto IT 관리자는 이 작업을 한 번만 수행하면 됩니다.

### <a name="configuring-yammer-tenant-for-native-mode"></a>기본 Yammer 테넌트 구성

커뮤니케이션 규정 준수를 위해서는 조직의 Yammer 테넌트가 개인 메시지 및 공용 커뮤니티 대화에서 부적절한 콘텐츠를 모니터링하도록 기본 모드로 설정해야 합니다.

Contoso IT 관리자는 Microsoft 365 문서의 Yammer [](/yammer/configure-your-yammer-network/overview-native-mode) 네이티브 모드 개요에 있는 정보를 검토하고 Configure your Yammer network [for Native Mode for Microsoft 365](/yammer/configure-your-yammer-network/native-mode) 문서에서 마이그레이션 도구를 실행하기 위한 단계를 수행합니다.

### <a name="setting-up-a-group-for-in-scope-users"></a>범위 내 사용자를 위한 그룹 설정

Contoso 규정 준수 전문가는 부적절한 콘텐츠가 모니터링되는 통신 정책에 모든 사용자를 추가하려는 경우 정책에 각 사용자 계정을 별도로 추가할 수도 있지만, 이 정책에 대한 사용자에 대해  모든 사용자 메일 그룹을 사용하는 것이 훨씬 더 쉬우고 시간을 절약하기도 합니다.

모든 Contoso 사용자를 포함하려면 새 그룹을 만들어야 하여 다음 단계를 수행합니다.

1. Contoso IT 관리자 IT 관리자는 Microsoft 365 관리 센터 [로그인하고 https://admin.microsoft.com)](https://admin.microsoft.com) Microsoft 365 관리 센터 >   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**그룹으로 이동 합니다.**</a>
2. 그룹 **추가를 선택하고** 마법사를 완료하여 새 Microsoft 365 *그룹* 또는 메일 그룹을 만들 *수 있습니다.*

    ![그룹.](../media/communication-compliance-case-all-employees.png)

3. 새 그룹을 만든 후에는 모든 Contoso 사용자를 새 그룹에 추가해야 합니다. 사용자는 Exchange **센터(를** [ https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) 열고 Exchange **센터** 받는  >  **사람 그룹으로**  >  **이동합니다.** Contoso IT 관리자는 구성원 자격 영역과 새로 만든 *모든* 직원  그룹을 선택하고 편집 컨트롤을 선택하여 마법사의 새 그룹에 모든 Contoso 사용자를 추가합니다.

    ![Exchange 관리 센터.](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-inappropriate-content"></a>부적절한 콘텐츠에 대해 모니터링할 정책 만들기

모든 선행 조건이 완료되면 CONtoso의 IT 관리자 및 규정 준수 전문가가 부적절한 콘텐츠를 모니터링하도록 통신 준수 정책을 구성할 준비가 완료되었습니다. 새 부적절한 콘텐츠 정책 템플릿을 사용하면 이 정책을 쉽고 빠르게 구성할 수 있습니다.

1. Contoso IT 관리자 및 규정 준수 전문가는 **Microsoft 365 규정 준수 센터** 에 로그인하고 왼쪽 탐색 창에서 **커뮤니케이션 규정 준수** 를 선택합니다. 이 작업을 수행하면 커뮤니케이션 규정 준수 정책 템플릿에 대한 빠른 링크가 있는 **개요** 대시보드가 열립니다. 서식 파일 **시작을** 선택하여 부적절한 콘텐츠  서식 파일 모니터링을 선택합니다.

    ![통신 준수 부적절한 콘텐츠 서식 파일](../media/communication-compliance-case-template.png)

2. 정책 템플릿 마법사에서 Contoso IT 관리자 및 규정 준수 전문가가 함께 작업하여 **정책 이름**, **사용자 또는 그룹**, **검토자** 의 세 가지 필수 필드를 작성합니다.
3. 정책 마법사가 이미 정책 이름을 제안했기 때문에 IT 관리자와 규정 준수 전문가는 제안된 이름을 유지하고 나머지 필드에 집중하기로 결정합니다. 해당 사용자는  필드를 감독할 사용자 또는 그룹의 모든 사용자 그룹을 선택하고 검토자 필드에 대한 정책 알림을 조사하고 수정해야 하는 준수 **전문가를** 선택합니다.  정책을 구성하고 경고 정보 수집을 시작하는 마지막 단계는 정책 만들기 **를 선택하는 것입니다.**

    ![통신 규정 준수 부적절한 콘텐츠 마법사.](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>4단계: 경고 조사 및 수정

부적절한 콘텐츠를 모니터링하는 통신 준수 정책이 구성되면 Contoso 규정 준수 전문가를 위한 다음 단계는 정책에 의해 생성된 경고를 조사하고 수정하는 것입니다. 정책이 모든 커뮤니케이션 소스 채널의 커뮤니케이션을 완전히 처리하고 **경고 대시보드** 에 경고가 표시되는 데 최대 24시간이 걸립니다.

경고가 생성된 후 Contoso 규정 준수 [](communication-compliance-investigate-remediate.md) 전문가는 워크플로 지침을 따라 부적절한 콘텐츠 문제를 조사하고 수정합니다.