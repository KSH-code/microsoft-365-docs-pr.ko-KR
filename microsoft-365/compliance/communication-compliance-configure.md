---
title: 커뮤니케이션 규정 준수 시작
description: 검토를 위해 사용자 통신을 구성하도록 통신 준수 정책을 설정합니다.
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 2a63f13885311ba4a794ca1c25c5e90d320472f5
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753520"
---
# <a name="get-started-with-communication-compliance"></a>커뮤니케이션 규정 준수 시작

커뮤니케이션 준수 정책을 사용하여 내부 또는 외부 검토자에 의해 검사할 사용자 커뮤니케이션을 식별합니다. 통신 준수 정책이 조직의 통신을 모니터링하는 데 도움이 되는 방법에 대한 자세한 내용은 에서 통신 [준수 정책을 Microsoft 365.](communication-compliance.md) Contoso가 Microsoft Teams, Exchange Online 및 Yammer 통신에서 부적절한 콘텐츠를 모니터링하도록 통신 준수 정책을 빠르게 구성한 방법을 검토하고자 하는 경우 이 사례 연구를 [참조하세요.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>구독 및 라이선스

통신 규정 준수를 시작하기 전에 Microsoft 365 [추가](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 기능을 확인해야 합니다. 통신 규정 준수에 액세스하고 사용하려면 조직에 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

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
- Office 365 A5 구독(유료 또는 평가판)
- Office 365 Enterprise E3 구독 + Office 365 Advanced Compliance 추가 기능(새 구독에서 더 이상 사용할 수 없음, 참고 참조)

통신 준수 정책에 포함된 사용자에게 위의 라이선스 중 하나를 할당해야 합니다.

> [!IMPORTANT]
> Office 365 Advanced Compliance 독립 실행형 구독으로 더 이상 판매하지 않습니다. 현재 구독이 만료되면 고객은 동일한 또는 추가 규정 준수 기능을 포함하는 위의 구독 중 하나로 전환해야 합니다.

기존 Office 365 Enterprise E5 요금제가 없는 경우 통신 규정 준수를 시도하려는 경우 기존 구독에 Microsoft 365 [](https://www.microsoft.com/microsoft-365/enterprise) 구독을 추가하거나 E5의 평가판을 등록할 Office 365 Enterprise 있습니다. [](/office365/admin/try-or-buy-microsoft-365)

## <a name="recommended-actions-preview"></a>권장 작업(미리 보기)

권장되는 작업은 조직이 커뮤니케이션 규정 준수 기능과 기존 정책을 가장 잘 아는 데 도움이 될 수 있습니다. 개요 페이지에 **포함된** 권장 작업은 인사이트를 제공하고 중요한 정보 유형과 조직의 커뮤니케이션에서 부적절한 콘텐츠 활동을 요약합니다.

![통신 준수 권장 작업.](../media/communication-compliance-recommended-actions.png)

부적절한 콘텐츠가 포함된 메시지의 활동은 부적절한 콘텐츠에 대해 분류기를 사용하는 부적절한 콘텐츠 서식 파일 또는 사용자 지정 정책을 사용하는 기존 정책의 분류자 유형에 의해 열적됩니다. 정책에 대한 경고 대시보드에서 이러한 메시지에 대한 경고를 조사합니다.

중요한 정보 유형과 관련된 활동은 기존 정책에서 다루는 메시지 및 기존 정책에서 다루지 않는 메시지에서 검색됩니다. Insights 기존 통신 준수 정책에서 이전에 정의하지 않은 정보 유형을 포함하여 모든 중요한 정보 유형에 대한 정보가 제공됩니다. 이러한 인사이트를 사용하여 새 통신 준수 정책을 만들거나 기존 정책을 업데이트합니다.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>1단계(필수): 통신 규정 준수에 대한 사용 권한 사용

> [!IMPORTANT]
> 기본적으로 전역 관리자는 통신 준수 기능에 액세스할 수 없습니다. 이 단계에서 할당된 역할은 통신 준수 기능에 액세스하기 전에 필요합니다. 역할 그룹을 구성한 후 역할 그룹 사용 권한을 조직 전체의 할당된 사용자에게 적용하는 데 최대 30분이 걸릴 수 있습니다.

통신 준수 기능을 관리하기 위한 사용 권한을 구성하는 데 사용되는 5개의 역할 그룹이 있습니다. 통신 **규정** 준수를 Microsoft 365 규정 준수 센터 메뉴 옵션으로 사용할 수 있도록 설정하고 이러한 구성 단계를  계속하려면 통신 준수 또는 통신 준수 관리자 역할 그룹에 *할당해야* 합니다. 초기 구성 후 통신 준수 기능에 액세스하고 관리하려면 사용자가 하나 이상의 통신 준수 역할 그룹의 구성원이 되어야 합니다.

통신 정책 및 경고를 관리하는 방법에 따라 사용자를 특정 역할 그룹에 할당해야 합니다. 커뮤니케이션 규정 준수 기능의 다른 영역을 관리하기 위해 특정 역할 그룹에 다른 준수 책임이 있는 사용자를 할당할 수 있습니다. 또는 지정된 관리자, 분석가, 조사자 및 뷰어에 대한 모든 사용자 계정을 *통신* 준수 역할 그룹에 할당할 수 있습니다. 단일 역할 그룹 또는 여러 역할 그룹을 사용하여 규정 준수 관리 요구 사항에 가장 잘 맞도록 합니다.

통신 규정 준수를 구성할 때 다음 역할 그룹 옵션 중 선택합니다.

| 역할 | 역할 권한 |
|:-----|:-----|
| **통신 규정 준수** | 이 역할 그룹을 사용하여 단일 그룹에서 조직에 대한 통신 규정 준수를 관리합니다. 지정된 관리자, 분석가, 조사자 및 뷰어에 대한 모든 사용자 계정을 추가하여 단일 그룹에서 통신 준수 권한을 구성할 수 있습니다. 이 역할 그룹에는 모든 통신 준수 권한 역할이 포함되어 있습니다. 이 구성은 통신 규정 준수를 빠르게 시작하는 가장 쉬운 방법으로, 별도의 사용자 그룹에 대해 정의된 별도의 사용 권한이 필요하지 않은 조직에 적합한 구성입니다. |
| **커뮤니케이션 규정 준수 관리자** | 이 역할 그룹을 사용하여 처음에 통신 준수를 구성하고 나중에 통신 준수 관리자를 정의된 그룹으로 나란히 구성합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 정책, 전역 설정 및 역할 그룹 할당을 만들고, 읽고, 업데이트하고, 삭제할 수 있습니다. 이 역할 그룹에 할당된 사용자는 메시지 알림을 볼 수 없습니다. |
| **커뮤니케이션 준수 분석가** | 이 그룹을 사용하여 커뮤니케이션 규정 준수 분석가 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 검토자로 할당된 정책을 보거나, 메시지 메타데이터(메시지 콘텐츠 아미타)를 보거나, 추가 검토자로 에스컬레이터하거나, 사용자에게 알림을 보낼 수 있습니다. 분석가가 보류 중인 경고를 해결할 수 없습니다. |
| **커뮤니케이션 규정 준수 조사자** | 이 그룹을 사용하여 커뮤니케이션 준수 조사자 역할을 할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 메시지 메타데이터 및 콘텐츠를 보고, 추가 검토자로 에스컬레이터하고, Advanced eDiscovery 사례로 에스컬레이터하고, 사용자에게 알림을 보내고, 경고를 해결할 수 있습니다. |
| **커뮤니케이션 규정 준수 뷰어** | 이 그룹을 사용하여 통신 보고서를 관리할 사용자에게 사용 권한을 할당합니다. 이 역할 그룹에 할당된 사용자는 통신 준수 홈 페이지의 모든 보고 위젯에 액세스할 수 있으며 모든 통신 준수 보고서를 볼 수 있습니다. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>옵션 1: 모든 준수 사용자를 통신 준수 역할 그룹에 할당

1. 조직에서 관리자 계정의 자격 [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) 증명을 사용하여 Microsoft 365 로그인합니다.

2. 보안 및 &amp; 준수 센터에서 사용 **권한 으로 이동 합니다.** 웹에서 역할을 보고 관리하려면 링크를 Office 365.

3. 통신 준수 *역할 그룹을* 선택한 다음 역할 그룹 **편집 을 선택합니다.**

4. 왼쪽 **탐색 창에서** 구성원 선택을 선택한 다음 편집 **을 선택합니다.**

5. **추가를** 선택한 다음 통신 준수 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다. 

6. **추가** 를 선택한 다음 **완료** 를 선택합니다.

7. **저장을** 선택하여 역할 그룹에 사용자를 추가합니다. 닫기 **를** 선택하여 단계를 완료합니다.

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>옵션 2: 특정 통신 준수 역할 그룹에 사용자 할당

이 옵션을 사용하여 특정 역할 그룹에 사용자를 할당하여 조직의 여러 사용자 사이에서 통신 준수 액세스 및 책임을 구분할 수 있습니다.

1. Microsoft 365 규정 준수 센터 조직의 관리자 계정에 대한 자격 증명을 사용하여 Microsoft 365 로그인한 다음 사용 권한으로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**이동하십시오.**</a>

2. 웹에서 역할을 보고 관리하려면 링크를 Office 365.

3. 통신 준수 역할 그룹 중 하나를 선택한 다음 역할 그룹 **편집 을 선택합니다.**

4. 왼쪽 **탐색 창에서** 구성원 선택을 선택한 다음 편집 **을 선택합니다.**

5. **추가를** 선택한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.

6. **추가** 를 선택한 다음 **완료** 를 선택합니다.

7. **저장을** 선택하여 역할 그룹에 사용자를 추가합니다.

8. 다음 통신 준수 역할 그룹을 선택한 다음 필요한 각 역할 그룹에 대해 4-7단계를 반복합니다.

9. 닫기 **를** 선택하여 단계를 완료합니다.

역할 그룹 및 사용 권한에 대한 자세한 내용은 [Permissions in the Compliance Center을 참조하세요.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>2단계(필수): 감사 로그 사용

커뮤니케이션 규정 준수를 수행하려면 감사 로그가 경고를 표시하고 검토자가 수행한 교정 작업을 추적해야 합니다. 감사 로그는 정의된 조직 정책 또는 커뮤니케이션 규정 준수 정책이 변경될 때마다 연결된 모든 작업의 요약입니다.

감사는 기본적으로 Microsoft 365 사용하도록 설정되어 있습니다. 일부 조직에서는 특정 이유로 감사를 사용하지 않도록 설정한 경우도 있습니다. 조직에서 감사를 사용하지 않도록 설정한 경우 다른 관리자가 감사 기능을 해제한 것일 수 있습니다. 이 단계를 완료할 때 감사를 다시 설정하는 것이 좋습니다.

감사를 켜는 단계별 지침은 감사 로그 검색 켜기 또는 [끄기 를 참조하세요.](turn-audit-log-search-on-or-off.md) 감사를 설정하면 감사 로그가 준비되고 있으며 준비가 완료된 후 몇 시간 내에 검색을 실행할 수 있다는 메시지가 표시됩니다. 이 작업은 한 번만 수행하면 됩니다. 감사 로그 사용에 대한 자세한 내용은 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>3단계(선택 사항): 통신 규정 준수를 위한 그룹 설정

 통신 준수 정책을 만들 때 커뮤니케이션을 검토한 사용자와 검토를 수행하는 사용자 정의합니다. 정책에서 전자 메일 주소를 사용하여 개인 또는 사용자 그룹을 식별합니다. 설정을 단순화하기 위해 커뮤니케이션을 검토한 사용자에 대한 그룹과 해당 커뮤니케이션을 검토하는 사용자에 대한 그룹을 만들 수 있습니다. 그룹을 사용하는 경우 몇 가지가 필요할 수 있습니다. 예를 들어 두 사용자 그룹 간의 통신을 모니터링하려는 경우 또는 감독되지 않을 그룹을 지정하려는 경우입니다.

다음 차트를 사용하여 조직에서 통신 준수 정책에 대한 그룹을 구성할 수 있습니다.

| **정책 구성원** | **지원되는 그룹** | **미지원 그룹** |
|:-----|:-----|:-----|
|감독된 사용자 <br> 제외된 사용자 | 메일 그룹 <br> Microsoft 365 그룹 | 동적 메일 그룹 <br> 중첩된 메일 그룹 <br> 메일 사용 가능 보안 그룹 <br> Microsoft 365 구성원으로 그룹화 |
| 검토자 | 없음 | 메일 그룹 <br> 동적 메일 그룹 <br> 중첩된 메일 그룹 <br> 메일 사용 가능 보안 그룹 |

정책에서 메일 그룹을 할당하면 정책은 메일 그룹의 각 사용자의 모든 전자 메일 Teams 모니터링합니다. 정책에서 Microsoft 365 그룹을 할당하면 정책은 각 그룹 구성원이 수신한 개별 전자 메일 및 Teams 아닌 해당 그룹에 전송된 모든 전자 메일 및 Teams 채팅을 모니터링합니다.

Exchange 배포 또는 외부 전자 메일 공급자가 있는 조직에서 사용자의 Microsoft Teams 채팅을 모니터링하려는 경우 모니터링할 메일 그룹을 만들어야 합니다. 이 단계의 나중에 이 메일 그룹을  정책 마법사에서 감독된 사용자 및 그룹 선택으로 할당합니다. 클라우드 기반 저장소를 사용하도록 설정하기 위한 요구 사항 및 제한 사항에 대한 자세한 내용은 Teams 사용자에 대한 Teams 채팅 데이터 검색을 [참조하세요.](search-cloud-based-mailboxes-for-on-premises-users.md)

대규모 엔터프라이즈 조직에서 감독되는 사용자를 관리하려면 대규모 그룹의 모든 사용자를 모니터링해야 할 수 있습니다. PowerShell을 사용하여 할당된 그룹에 대한 전역 통신 준수 정책에 대한 메일 그룹을 구성할 수 있습니다. 이렇게 하면 단일 정책으로 수천 명의 사용자를 모니터링하고 신입 사원이 조직에 가입할 때 통신 준수 정책을 업데이트할 수 있습니다.

1. 다음 속성을 [](/powershell/module/exchange/new-distributiongroup) 사용하여 전역 통신 규정 준수 정책에 대한 전용 메일 그룹을 만들 수 있습니다. 이 메일 그룹이 다른 목적이나 다른 Office 365 없는지 확인

    - **MemberDepartRestriction = Closed**. 사용자가 메일 그룹에서 자신을 제거할 수 없는지 확인
    - **MemberJoinRestriction = Closed**. 사용자가 메일 그룹에 자신을 추가할 수 없는지 확인
    - **ModerationEnabled = True**. 이 그룹으로 전송된 모든 메시지에 승인이 적용되고 해당 그룹이 통신 준수 정책 구성 외부에서 통신하는 데 사용되지 않도록 합니다.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 조직의 통신 [준수 Exchange](/Exchange/recipients/mailbox-custom-attributes) 추가된 사용자를 추적하려면 사용되지 않는 사용자 지정 특성을 선택합니다.

3. 다음 PowerShell 스크립트를 일정에 따라 실행하여 통신 준수 정책에 사용자를 추가합니다.

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx)
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

그룹 설정에 대한 자세한 내용은 다음을 참조하세요.

- [메일 그룹 만들기 및 관리](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Microsoft 365 그룹 개요](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>4단계(선택 사항): Yammer 테넌트가 기본 모드에 있는지 확인

기본 모드에서는 모든 Yammer 사용자가 Azure Active Directory(Azure AD)에 있으며 모든 그룹은 Office 365 그룹으로 설정되고 모든 파일은 SharePoint Online에 저장됩니다. 사용자 Yammer 개인 메시지 및 커뮤니티 대화에서 위험한 대화를 검색하고 식별하기 위해 통신 규정 준수 정책을 위해 기본 모드에 있어야 Yammer.

기본 모드에서 구성하는 Yammer 자세한 내용은 다음을 참조하세요.

- [Yammer 기본 모드 개요 Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Microsoft 365 기본 모드에 사용할 Yammer 네트워크 구성](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>5단계(필수): 통신 준수 정책 만들기

>[!IMPORTANT]
>PowerShell을 사용하여 커뮤니케이션 규정 준수 정책을 만들고 관리하는 것은 지원되지 않습니다. 이러한 정책을 만들고 관리하려면 통신 규정 준수 솔루션의 정책 관리 [Microsoft 365 합니다.](https://compliance.microsoft.com/supervisoryreview)

>[!TIP]  
>새 통신 규정 준수 정책을 설정하고 경고를 수정하는 심층적인 워크스루를 보고 싶나요? 이 [15분](communication-compliance-plan.md#creating-a-communication-compliance-policy-walkthrough) 분의 비디오를 통해 통신 규정 준수 정책이 부적절한 메시지를 감지하고 잠재적인 위반을 조사하고 규정 준수 문제를 수정하는 데 어떻게 도움이 될 수 있는지 확인할 수 있습니다.

1. 조직에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a> 계정의 자격 증명을 사용하여 조직에 Microsoft 365 로그인합니다.

2. 다음 Microsoft 365 규정 준수 센터 통신 준수 **를 선택합니다.**

3. **정책** 탭을 선택합니다.

4. 정책 **만들기를** 선택하여 템플릿에서 새 정책을 만들고 구성하거나 사용자 지정 정책을 만들고 구성합니다.

    정책을 만들 정책 템플릿을 선택하면 다음을 할 수 있습니다.

    - 정책 이름을 확인하거나 업데이트합니다. 정책을 만든 후 정책 이름을 변경할 수 없습니다.

    - 제외할 사용자 또는 그룹 선택을 포함하여 감독할 사용자 또는 그룹을 선택 합니다. 이해 상충 템플릿을 사용하는 경우 내부 통신을 모니터링할 두 그룹 또는 두 사용자를 선택합니다.

    - 정책에 대한 검토자 선택 검토자는 개별 사용자로, 모든 검토자는 해당 사용자에 대해 호스트된 사서함을 Exchange Online. 여기에 추가된 검토자는 조사 및 수정 워크플로에서 경고를 에스컬레이터할 때 선택할 수 있는 검토자입니다. 검토자는 정책에 추가될 때 정책에 할당을 알림하는 전자 메일 메시지를 자동으로 받고 검토 프로세스에 대한 정보에 대한 링크를 제공합니다.

    - 제한된 조건 필드(일반적으로 정책에 적용할 중요한 정보 유형 또는 키워드 사전)를 선택하십시오.

    > [!NOTE]
    > [OCR(광학](communication-compliance-policies.md#optical-character-recognition-ocr) 문자 인식)을 사용하여 메시지에 포함된 이미지나 첨부된 이미지를 정책 조건과 일치하는 인쇄 또는 필기 텍스트로 스캔하려면 정책 조건 및 백분율 사용자 지정을 선택하고 평가를 위해 이미지에서 인쇄 또는 필기 텍스트 추출을 사용하도록 설정을  >   선택합니다. 

    정책 마법사를 사용하여 사용자 지정 정책을 만들면 다음을 실행합니다.

    - 정책에 이름과 설명을 지정합니다. 정책을 만든 후에는 정책 이름을 변경할 수 없습니다.

    - 조직의 모든 사용자, 특정 사용자 및 그룹, 제외할 기타 사용자 및 그룹을 포함하여 감독할 사용자 또는 그룹을 선택하십시오.

    - 정책에 대한 검토자 선택 검토자는 개별 사용자로, 모든 검토자는 해당 사용자에 대해 호스트된 사서함을 Exchange Online. 여기에 추가된 검토자는 조사 및 수정 워크플로에서 경고를 에스컬레이터할 때 선택할 수 있는 검토자입니다. 검토자는 정책에 추가될 때 정책에 할당을 알림하는 전자 메일 메시지를 자동으로 받고 검토 프로세스에 대한 정보에 대한 링크를 제공합니다.

    - 검색할 통신 채널(Exchange, Microsoft Teams, Yammer 또는 비즈니스용 Skype. 또한 Microsoft 365에서 커넥터를 구성한 경우 타사 소스를 검색하도록 선택합니다.

    - 인바운드, 아웃바운드 또는 내부 통신을 포함하여 모니터링할 통신 방향을 선택 합니다.

    - 통신 준수 정책 조건을 [정의합니다.](communication-compliance-policies.md#ConditionalSettings) 메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.

    - 중요한 정보 유형을 포함할지 선택하십시오. 이 단계에서는 기본 및 사용자 지정 중요한 정보 유형을 선택할 수 있습니다. 통신 준수 정책 마법사의 기존 사용자 지정 중요한 정보 유형 또는 사용자 지정 키워드 사전에서 선택하세요. 필요한 경우 마법사를 실행하기 전에 이러한 항목을 만들 수 있습니다. 또한 통신 준수 정책 마법사 내에서 중요한 정보 유형을 새로 만들 수 있습니다.

    - 분류자 사용 하도록 설정 하도록 선택 합니다. 분류기는 전자 메일 메시지의 본문이나 다른 유형의 텍스트로 보내거나 받은 부적절한 언어 및 이미지를 검색할 수 있습니다. 위협, 비언어, 대상 괴롭음,  성인 *이미지,* 인종 이미지 및 고리 이미지의 기본 제공 분류자 *를* 선택할 *수 있습니다.* 

    - [OCR(광학](communication-compliance-policies.md#optical-character-recognition-ocr) 문자 인식)을 사용하면 메시지에 포함되거나 첨부된 이미지에서 정책 조건과 일치하는 인쇄 또는 필기 텍스트를 검색할 수 있습니다. 사용자 지정 정책의 경우 광학 문자 인식 검색을 선택하려면 정책에서 텍스트, 키워드, 분류자 또는 중요한 정보 유형과 관련된 조건부 설정을 하나 이상 구성해야 합니다.

    - 리뷰할 통신의 %를 정의합니다.

    - 정책 선택을 검토하고 정책을 생성합니다.

5. 템플릿을 사용할 때 정책 만들기를 선택하거나 **사용자** 지정 정책 마법사를 사용할 때 제출을 선택합니다. 

6. **정책이 생성됨** 페이지가 표시되고 정책이 활성화될 시기와 캡처될 통신에 대한 지침이 표시됩니다.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>6단계(선택 사항): 알림 서식 파일 만들기 및 사용자 비동기화 구성

연결된 사용자에게 미리 알림 메시지를 보내 정책 경고에 응답하는 옵션을 사용하려면 조직에서 알림 템플릿을 하나 이상 만들어야 합니다. 알림 템플릿 필드는 알림 수정 프로세스의 일부로 전송되기 전에 편집할 수 있으며, 각 통신 준수 정책에 대해 사용자 지정된 알림 템플릿을 만드는 것이 좋습니다.

정책 일치를 조사하고 메시지에 대한 작업을 수행 할 때 표시되는 사용자 이름에 대해 동의어를 사용하도록 선택할 수도 있습니다.

1. 조직에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a> 계정의 자격 증명을 사용하여 조직에 Microsoft 365 로그인합니다.

2. 다음 Microsoft 365 규정 준수 센터 통신 준수 **로 이동합니다.**

3. 사용자 이름에 대한 동의어를 구성하려면 개인 정보 **탭을** 선택합니다.

4. To enable anonymization, select **Show anonymized versions of usernames**.

5. **저장** 을 선택합니다.

6. 알림 서식 **파일 탭으로** 이동한 다음 알림 서식 **파일 만들기 를 선택합니다.**

7. 알림 서식 **파일 수정 페이지에서** 다음 필드를 입력합니다.

    - 템플릿 이름(필수)
    - 보내기(필수)
    - Cc 및 Bcc(선택 사항)
    - 제목(필수)
    - 메시지 본문(필수)

8. **저장을** 선택하여 알림 서식 파일을 만들고 저장합니다.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>7단계(선택 사항): 통신 준수 정책 테스트

통신 준수 정책을 만든 후 정의한 조건이 정책에 의해 제대로 적용되고 있는지 테스트하는 것이 좋습니다. 통신 준수 정책에 중요한 정보 유형이 포함된 [경우 DLP(데이터](create-test-tune-dlp-policy.md) 손실 방지) 정책을 테스트할 수도 있습니다. 테스트할 통신을 캡처할 수 있도록 정책을 활성화할 시간을 제공해야 합니다.

다음 단계에 따라 통신 준수 정책을 테스트합니다.

1. 테스트할 정책에 정의된 감독된 Microsoft Teams 로그인하는 동안 전자 메일 클라이언트를 열거나 Yammer 클라이언트를 열 수 있습니다.

2. 전자 메일, Microsoft Teams 채팅 또는 Yammer 준수 정책에서 정의한 기준을 충족하는 메시지를 전송합니다. 이 테스트는 키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성된 조건부 설정이 너무 제한적이거나 너무 적합한지 확인합니다.

    > [!NOTE]
    > 정책에서 전자 메일 메시지를 완전히 처리하는 데 최대 24시간이 걸릴 수 있습니다. 정책에서 Microsoft Teams, Yammer 및 타사 플랫폼의 통신을 완전히 처리하기까지 최대 48시간이 걸릴 수 있습니다.

3. 통신 준수 Microsoft 365 지정된 검토자로 로그인합니다. 커뮤니케이션 규정 **준수**  >  **경고로 이동하여** 정책에 대한 알림을 볼 수 있습니다.

4. 수정 컨트롤을 사용하여 경고를 수정하고 경고가 제대로 해결되었는지 확인합니다.

## <a name="next-steps"></a>다음 단계

이러한 단계를 완료하여 첫 번째 통신 준수 정책을 만든 후 24-48시간 후에 활동 표시기에서 경고를 받기 시작할 수 있습니다. 이 문서의 5단계에 있는 지침을 사용하여 필요한 경우 추가 정책을 구성합니다.

통신 준수 경고 조사에 대한 자세한 내용은 커뮤니케이션 준수 경고 조사 및 [수정을 참조합니다.](communication-compliance-investigate-remediate.md)
