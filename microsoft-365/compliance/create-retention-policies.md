---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책을 만들고 구성하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 정책을 사용하여 콘텐츠를 보존할지, 삭제할지, 아니면 보존한 다음 삭제할지 사전에 결정할 수 있습니다. 조직 전체 또는 특정 위치 또는 사용자에게 단일 정책을 적용할 수 있고 모든 콘텐츠 또는 특정 조건에 부합하는 콘텐츠에 정책을 적용할 수 있습니다.
ms.openlocfilehash: ab6a61e0cedfd91d642823f0c459a5a1699df000
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083620"
---
# <a name="create-and-configure-retention-policies"></a>보존 정책 만들기 및 구성

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정하기 위해 보존 정책을 사용합니다. 

보존 정책이 작동하는 방식에 대한 자세한 내용은 [보존 정책 정보](retention-policies.md)를 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

보존 정책을 만들고 관리할 규정 준수 팀의 구성원에게는 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에 대한 권한이 필요합니다. 기본적으로 테넌트 관리자(전역 관리자)는 이 위치에 액세스할 수 있으며, 규정 준수 책임자와 기타 사용자에게 테넌트 관리자의 모든 권한을 부여하지는 않으면서 액세스 권한을 부여할 수 있습니다. 이 제한적 관리를 위한 권한을 부여하기 위해서는 사용자를 **규정 준수 관리자** 관리 역할 그룹에 추가할 것을 권장합니다. 지침은 [사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)를 참조하세요.

이러한 권한은 보존 정책을 생성하고 적용할 때만 필요합니다. 보존 정책을 구성하는 사용자는 콘텐츠에 액세스할 필요가 없습니다.

## <a name="create-and-configure-a-retention-policy"></a>보존 정책 만들기 및 구성

1. [Microsoft 365 준수 센터](https://compliance.microsoft.com/)에서 **정책** > **보존**을 선택합니다.

2. **새 보존 정책**을 선택하거나 기존 보존 정책 편집을 선택합니다.

3. **설정**에서 먼저 컨텐츠 유지 및 삭제에 대한 구성 옵션을 지정하세요. 삭제하지 않고 콘텐츠를 유지하거나 지정된 기간 후에 콘텐츠를 유지한 다음 삭제하거나 지정된 기간 후에 콘텐츠를 삭제하는 보존 정책을 만들 수 있습니다. 자세한 내용은 이 페이지에서 [콘텐츠를 보존하고 삭제하는 방법에 대한 설정](#settings-for-retaining-and-deleting-content)을 참조하세요.
    
    그런 다음 보존 정책을 모든 콘텐츠 또는 특정 조건을 충족하는 콘텐츠에 적용할지 결정합니다. 이러한 고급 보존 설정에 대한 자세한 내용은 이 페이지의 [특정 조건을 충족하는 콘텐츠를 식별하는 고급 설정](#advanced-settings-to-identify-content-that-meets-specific-conditions)을 참조하세요. 

4. **위치 선택** 페이지에서 보존 정책을 조직 전체에서 지원되는 모든 위치에 적용할 것인지 또는 위치를 지정할 것인지 선택하세요. 특정 위치를 선택하면 포함 및 제외를 지정할 수도 있습니다. 
    
    Microsoft Teams의 경우: 
    - Teams 채널 메시지 또는 Teams 채팅을 삭제하거나 유지하려면 특정 위치를 선택하는 옵션을 선택해야 합니다. 이러한 옵션 중 하나를 위치로 선택하면 이 Teams 데이터를 포함하는 보존 정책에 다른 위치를 포함할 수 없으므로 다른 위치는 자동으로 제외됩니다. 
    - **Teams 채널 메시지**의 경우 표준 채널이지만 [비공개 채널](https://docs.microsoft.com/microsoftteams/private-channels)의 메시지는 포함되지 않습니다. 현재 개인 채널은 보존 정책에서 지원 되지 않습니다.
    
    조직 또는 특정 위치에 대한 보존 정책을 선택하는 방법에 대한 자세한 내용은 이 페이지의 [전체 조직 또는 특정 위치에 보존 정책 적용](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)을 참조하세요.
    
    **Office 365 그룹** 및 **비즈니스용 Skype**에 대한 자세한 내용은 [Microsoft 365 그룹의 구성 정보](#configuration-information-for-microsoft-365-groups) 및 [비즈니스용 Skype의 구성 정보](#configuration-information-for-skype-for-business) 섹션을 참조하세요.

5. 마법사를 완료하여 설정을 저장합니다.

보존 정책이 두 개 이상인 경우 [보존 원칙 또는 우선 순위](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)를 참조하세요.

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 그룹에 대한 구성 정보

Microsoft 365 그룹(과거 Office 365 그룹)에 대한 콘텐츠를 유지하거나 삭제하려면 보존 정책의 위치를 선택할 때 **Office 365 그룹** 위치를 선택하세요. Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 **Exchange 전자 메일** 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다. 또한 **Exchange 전자 메일** 위치에서 처음에 포함하거나 제외할 그룹 사서함을 지정할 수 있지만 보존 정책을 저장하려고 하면 "RemoteGroupMailbox"가 Exchange 위치에 대해 올바른 선택이 아니라는 오류가 발생합니다.

Microsoft 365 그룹에 적용되는 보존 정책에는 그룹 사서함과 사이트가 모두 포함됩니다. Microsoft 365 그룹에 적용된 보존 정책은 Microsoft Teams를 포함하여 Microsoft 365 그룹에서 생성한 리소스를 보호합니다.

### <a name="configuration-information-for-skype-for-business"></a>비즈니스용 Skype에 대한 구성 정보

Exchange 전자 메일과 달리, Skype 위치의 상태는 간단히 설정으로 전환하여 모든 사용자를 포함할 수 없습니다. 그렇지만 해당 위치를 켜면 해당 대화를 보존하려는 사용자를 수동으로 선택할 수 있습니다.

![보존 정책을 위한 Skype 위치 선택](../media/skype-location-retention-policies.png)
  
**사용자 선택**을 선택하면 열 헤더에서 **이름** 상자를 선택하여 모든 사용자를 빠르게 포함할 수 있습니다. 그러나 각 사용자가 정책의 특정 포함사항으로 간주된다는 점을 이해해야 합니다. 따라서 1,000명이 넘는 사용자를 포함하게 되면 이전 섹션에서 설명한 제한 사항이 적용됩니다. 여기에서 모든 Skype 사용자를 선택하는 것은 조직 전체 정책에 기본적으로 모든 Skype 사용자를 포함하는 것과 다르게 작동합니다. 
  
![Skype 사용자 선택 페이지](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.


## <a name="settings-for-retaining-and-deleting-content"></a>콘텐츠를 보존 및 삭제하기 위한 설정

보존 정책에서 콘텐츠를 보존하고 삭제하기 위한 설정을 선택하면 보존 정책에 지정된 기간 동안 다음 구성 중 하나를 사용할 수 있습니다.

- 보존 전용
- 보존 후 삭제
- 삭제 전용

### <a name="retaining-content-for-a-specific-period-of-time"></a>특정 기간 동안 콘텐츠 보존

보존 정책을 구성하면 콘텐츠를 영구적으로 또는 며칠, 몇 달, 몇 년 동안만 보존을 선택할 수 있습니다. 콘텐츠 보존 기간은 보존 정책이 적용된 시점이 아닌 콘텐츠 생성 시점을 기준으로 계산됩니다. 콘텐츠의 생성 시점 또는 (OneDrive 및 SharePoint의 경우) 수정 시점 중 어느 것을 기준으로 할지 선택할 수 있습니다.

예제:
  
- SharePoint: 콘텐츠가 마지막으로 수정된 후 7년 동안 사이트 모음에 콘텐츠를 유지하고 해당 사이트 모음에 있는 문서가 6년 내에 수정되지 않은 경우 문서가 수정되지 않으면 다른 해에만 보존됩니다. 문서를 다시 편집하면 문서 사용 기간은 마지막으로 수정한 날부터 계산되고 앞으로 7년 동안 더 보존됩니다.
  
- Exchange: 사서함의 콘텐츠를 7년 동안 보존하려고 하고 메시지가 6년 전에 발송되었다면, 사서함은 1년 동안만 더 보존됩니다. Exchange 콘텐츠의 경우 해당 기간은 받는 전자 메일의 받은 날짜 또는 보내는 전자 메일에 대해 보낸 날짜를 기준으로 합니다. 콘텐츠를 수정된 시점을 기준으로 보존하는 것은 OneDrive 및 SharePoint의 사이트 콘텐츠에만 해당됩니다.
  
보존 기간이 끝나면 콘텐츠를 영구적으로 삭제할지 여부를 선택합니다.
  
![보존 설정 페이지](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>특정 사용 기간보다 오래된 콘텐츠 삭제

보존 정책은 콘텐츠를 보존했다가 삭제하거나, 보존하지 않고 오래된 콘텐츠를 단순히 삭제할 수 있습니다.
  
보존 정책이 콘텐츠를 삭제할 경우 보존 정책에 대해 지정된 기간은 정책이 할당된 시점이 아니라 콘텐츠가 만들어졌거나 수정된 이후부터 계산된다는 사실에 유의해야 합니다.
  
![삭제 설정](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
예를 들어, 3년이 지난 콘텐츠를 삭제하는 보존 정책을 만든 다음 해당 정책을 모든 OneDrive 계정에 적용한다고 가정하겠습니다. 이때 OneDrive 계정에는 4~5년 전에 생성된 콘텐츠가 매우 많습니다. 이 경우 보존 정책을 최초로 적용한 뒤 얼마 지나지 않아 다량의 콘텐츠가 삭제되게 됩니다. 이러한 이유로 인해 콘텐츠를 삭제하는 보존 정책은 콘텐츠에 상당한 영향을 주게 됩된다는 것을 이해하는 것이 중요합니다.. 
  
Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.
  
![콘텐츠 삭제 경고](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>특정 조건을 충족하는 콘텐츠를 식별하는 고급 설정

보존 정책을 포함하는 위치의 모든 콘텐츠에 적용할 수도 있고, 특정 키워드 또는 [특정 유형의 중요 정보](what-the-sensitive-information-types-look-for.md)를 포함하는 콘텐츠에만 보존 정책을 적용하도록 선택할 수 있습니다.
  
![고급 보존 옵션](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>특정 키워드를 포함하는 콘텐츠 식별

특정 조건을 충족하는 콘텐츠에만 보존 정책을 적용하고 해당 콘텐츠에 대해서만 보존 작업을 수행할 수 있습니다. 사용 가능한 조건은 특정 단어 나 문구가 포함된 콘텐츠에 보존 정책을 적용하는 것을 지원합니다. 검색 연산자(예: AND, OR 및 NOT)를 사용하여 쿼리를 구체화할 수 있습니다. 연산자에 대한 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.
  
검색 가능한 속성(예: **제목:**)을 추가하는 기능이 곧 지원될 예정입니다.
  
쿼리 기반 보존은 검색 인덱스를 사용하여 콘텐츠를 식별합니다.
  
![쿼리 편집기](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>중요한 정보가 포함된 콘텐츠 식별

You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.
  
![중요한 정보 유형 페이지](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
참고:
  
- 중요한 정보에 대한 고급 보존이 Exchange 공용 폴더 및 비즈니스용 Skype에는 적용되지 않습니다. 이러한 위치는 중요한 정보 유형을 지원하지 않기 때문입니다.
    
- Exchange Online은 메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 중요한 정보를 식별하므로 이미 사서함에 저장된 모든 항목이 아니라 전송 중인 메시지에서만 작동합니다. 즉, Exchange Online의 경우 사서함에 정책이 적용된 **뒤에** 수신된 메시지에 대해서만 보존 정책이 중요한 정보를 식별하고 보존 작업을 수행할 수 있습니다. 이전 섹션에서 설명하는 쿼리 기반 보존의 경우 콘텐츠 식별을 위해 검색 인덱스를 사용하므로 이러한 제한 사항이 적용되지 않습니다. 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>전체 조직 또는 특정 위치에 보존 정책 적용

전체 조직, 전체 위치 또는 특정 위치나 사용자에 보존 정책을 쉽게 적용할 수 있습니다.
  
### <a name="org-wide-policy"></a>조직 전체 정책

보존 정책의 가장 강력한 기능 중 하나는 다음을 비롯한 Microsoft 365의 위치에 적용할 수 있다는 것입니다.
  
- Exchange 전자 메일
    
- SharePoint 사이트 모음
    
- OneDrive 계정
    
- Microsoft 365 그룹(그룹의 사서함 및 관련 SharePoint 사이트의 콘텐츠에 적용됩니다.)
    
- Exchange 공용 폴더
    

![모든 위치 옵션](../media/retention-policies-all-locations.png)

조직 전체 보존 정책의 기타 중요한 기능은 다음과 같습니다.
  
- 정책이 포함할 수 있는 사서함 또는 사이트 개수에 제한이 없습니다.
    
- Exchange의 경우 정책이 적용된 후에 만들어진 모든 새 사서함은 해당 정책을 자동으로 상속합니다.
  
### <a name="a-policy-that-applies-to-entire-locations"></a>전체 위치에 적용되는 정책

위치를 선택할 때 Exchange 전자 메일이나 OneDrive 계정 등 전체 위치를 간편하게 포함하거나 배제할 수 있습니다. 해당 위치의 **상태를** 켜거나 끄면 됩니다. 
  
조직 전체 정책과 마찬가지로 전체 위치의 임의의 조합에 정책이 적용되는 경우 정책에 포함할 수 있는 사서함 또는 사이트 개수에 제한이 없습니다. 

예를 들어, 정책에 Exchange 전자 메일과 SharePoint 사이트가 모두 포함된다면, 개수와 상관없이 모든 사이트와 사서함이 포함됩니다. 또한 Exchange의 경우 정책이 적용된 후 만들어진 모든 새 사서함은 자동으로 정책을 상속합니다.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>특정 포함 또는 제외가 적용된 정책

특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 보존 정책을 적용할 수도 있습니다. 해당 위치의 **상태**를 켜거나 끈 다음 링크를 사용하여 특정 사용자, Microsoft 365 그룹 또는 사이트를 포함하거나 배제하면 됩니다. 
  
그러나 이 구성을 사용하는 경우 보존 정책에는 다음과 같은 1000개의 특정 위치를 포함하거나 제외하는 몇 가지 제한이 있습니다.
  
- 보존 정책의 최대 수:
    - 1,000개의 사서함
    - 1,000개의 Microsoft 365 그룹
    - Teams 비공개 채팅에 참여하는 1,000명의 사용자
    - 100개의 사이트(OneDrive 또는 SharePoint)

테넌트에 대해 지원되는 최대 정책 수는 10,000입니다. 이러한 항목에는 보존 정책, 보존 레이블 정책, 자동 적용 보존 정책이 포함됩니다.

보존 정책에 이러한 제한이 적용되는 경우 전체 위치에 적용되는 구성 옵션을 선택하거나 조직 전체 정책을 사용하세요.

## <a name="updating-retention-policies"></a>보존 정책 업데이트

보존 정책을 편집하고 콘텐츠가 보존 정책의 원래 설정에 이미 적용되어 있는 경우 업데이트된 설정은 새로 식별된 콘텐츠 외에 이 콘텐츠에도 자동으로 적용됩니다.

일반적으로 이 업데이트는 아주 간단하지만 며칠이 걸릴 수 있습니다. Microsoft 365 위치에서 정책 복제가 완료되면 Microsoft 365 준수 센터의 보존 정책 상태가 **켜기(보류)** 에서 **켜기(성공)** 으로 변경됩니다.

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>보존 정책에 대한 PowerShell cmdlet 찾기

보존 정책 cmdlet을 사용하려면 다음을 수행합니다.
  
1. [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 다음 Office 365 보안 및 준수 센터 cmdlet 사용:
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a>PowerShell을 사용하여 보존 정책 잠금

규정 요구 사항을 준수하기 위해 [보존 잠금](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)을 사용해야 하는 경우 PowerShell을 사용해야 합니다.

1. [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)

2. 보존 정책을 나열하고 `Get-RetentionCompliancePolicy`을(를) 실행하여 잠그려는 정책의 이름을 찾으세요.
    
    ![PowerShell의 보존 정책 목록](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. 보존 정책에 유지 잠금을 적용하려면 `RestrictiveRetention` 매개 변수가 true로 설정된 `Set-RetentionCompliancePolicy`를 실행합니다. 예시:

   ```powershell
   Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
   ```
   
    ![PowerShell의 RestrictiveRetention 매개 변수](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    이 cmdlet을 실행한 후 **모두 예**를 선택합니다.
    
    ![PowerShell에서 보존 정책 잠금을 원하는지 확인하는 메시지](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

이제 보존 정책에 보존 잠금이 적용됩니다. `Get-RetentionCompliancePolicy`을 실행할 경우, `RestrictiveRetention` 매개 변수가 True로 설정됩니다. 예시는 다음과 같습니다:

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![PowerShell에 모든 매개 변수와 함께 표시된 잠긴 정책](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

