---
title: 레거시 eDiscovery 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: db05b598fb0dab3cac9420b33b0bd4e12b6b7e9a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602795"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>레거시 eDiscovery 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션

Microsoft 365 준수 센터에서는 콘텐츠를 구성 하는 경우를 비롯 하 여 더 높은 안정성, 성능 향상, eDiscovery 워크플로에 맞게 조정 된 다양 한 기능 (예: 검토 집합)을 포함 하 여 eDiscovery 사용을 향상 시킵니다 콘텐츠 및 분석을 검토 하 여 거의 중복 된 그룹, 전자 메일 스레딩, 테마 분석 및 예측 코딩 등의 검토를 위한 데이터를 cull 수 있습니다.

이 문서에서는 고객이 새로운 기능과 향상 된 기능을 활용할 수 있도록 하기 위해 Exchange 관리 센터에서 Microsoft 365 준수 센터로 원본 위치 eDiscovery 검색 및 보존을 마이그레이션하는 방법에 대 한 기본 지침을 제공 합니다.

> [!NOTE]
> 다양 한 시나리오가 있으므로이 문서에서는 Microsoft 365 준수 센터의 핵심 eDiscovery 사례에 대 한 전환 검색 및 보존에 대 한 일반적인 지침을 제공 합니다. EDiscovery 사례를 사용 하는 것은 항상 필요한 것은 아니지만 조직의 eDiscovery 사례에 액세스할 수 있는 사람을 제어 하기 위해 사용 권한을 할당할 수 있도록 하 여 추가 보안 계층을 추가 합니다.

## <a name="before-you-begin"></a>시작하기 전에

- 이 문서에서 설명 하는 PowerShell 명령을 실행 하려면 Office 365 Security & 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원 이어야 합니다. 또한 Exchange 관리 센터에서 Discovery Management 역할 그룹의 구성원 이어야 합니다.

- 이 문서에서는 eDiscovery 보존을 만드는 방법에 대 한 지침을 제공 합니다. 비동기 프로세스를 통해 사서함에 보존 정책이 적용 됩니다. EDiscovery 보류를 만들 때 New-caseholdpolicy 및 New-caseholdrule를 모두 만들어야 하며 그렇지 않으면 보류가 만들어지지 않으며 콘텐츠 위치가 보류 되지 않습니다.

## <a name="step-1-connect-to-exchange-online-powershell-and-office-365-security--compliance-center-powershell"></a>1 단계: Exchange Online PowerShell 및 Office 365 보안 & 준수 센터 PowerShell에 연결

첫 번째 단계는 Exchange Online PowerShell 및 Office 365 Security & 준수 센터 PowerShell에 연결 하는 것입니다. 다음 스크립트를 복사 하 여 PowerShell 창에 붙여 넣은 다음 실행할 수 있습니다. 연결 하려는 조직의 자격 증명을 입력 하 라는 메시지가 표시 됩니다. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session -AllowClobber -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

이 PowerShell 세션에서는 다음 단계에서 명령을 실행 해야 합니다.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>2 단계: New-mailboxsearch을 사용 하 여 원본 위치 eDiscovery 검색 목록 가져오기

인증을 받은 후 **new-mailboxsearch** cmdlet을 실행 하 여 원본 위치 eDiscovery 검색 목록을 가져올 수 있습니다. 다음 명령을 복사 하 여 PowerShell에 붙여 넣은 다음 실행 합니다. 검색 목록과 이름이 함께 나열 되 고 원본 위치 유지 상태가 표시 됩니다.

```powershell
Get-MailboxSearch
```

Cmdlet 출력은 다음과 유사 합니다.

![PowerShell 예제 New-mailboxsearch](media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>3 단계: 마이그레이션할 원본 위치 eDiscovery 검색 및 현재 위치 유지에 대 한 정보 가져오기

이번에는 **new-mailboxsearch** cmdlet을 사용 하지만 이번에는 검색의 속성을 가져옵니다. 이러한 속성을 변수에 저장 하 여 나중에 사용할 수 있습니다. 다음은 **new-mailboxsearch** cmdlet의 결과를 변수에 저장 한 후 검색 속성을 표시 하는 예제입니다.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

이러한 두 명령 출력은 다음과 유사 합니다.

![개별 검색에 대해 New-mailboxsearch를 사용 하는 경우의 PowerShell 출력 예제](media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> 이 예의 원본 위치 유지 기간은 무제한입니다 (*ItemHoldPeriod: 제한 없음*). 이는 eDiscovery 및 법적 조사 시나리오에서 일반적으로 발생 합니다. 보류 기간이 무기한 값과 다른 경우 보존 시나리오에서 콘텐츠를 보존 하기 위해 보류가 사용 되 고 있기 때문일 수 있습니다. 보존 시나리오에 Office 365 Security & 준수 센터 PowerShell에서 eDiscovery cmdlet을 사용 하는 대신 [new-retentioncompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy) 및 [new-retentioncompliancerule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule) 을 사용 하 여 콘텐츠를 보존 하는 것이 좋습니다. 이러한 cmdlet을 사용 하는 경우에는 **new-caseholdpolicy** 및 **new-caseholdrule**를 사용 하는 것과 유사 하지만 보존 기간 및 보존 기간이 만료 된 후에 콘텐츠를 삭제 하는 것과 같은 유지 작업을 지정할 수 있습니다. 또한 보존 cmdlet을 사용 하는 경우에는 보존 보류와 eDiscovery 사례를 연결할 필요가 없습니다.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>4 단계: Microsoft 365 준수 센터에서 사례 만들기

EDiscovery 보존을 만들려면 보류를 연결 하는 eDiscovery 사례를 만들어야 합니다. 다음 예제에서는 선택한 이름을 사용 하 여 eDiscovery 사례를 만듭니다. 나중에 사용할 수 있도록 새 사례의 속성을 변수에 저장 합니다. 사례를 만든 후에 `$case | FL` 명령을 실행 하 여 이러한 속성을 볼 수 있습니다.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

![Remove-compliancecase 명령을 실행 하는 예제](media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>5 단계: eDiscovery 보류 만들기

사례를 만든 후에는 보류를 만들어 이전 단계에서 만든 사례와 연결할 수 있습니다. 케이스 보류 정책과 케이스 보류 규칙을 모두 만들어야 한다는 점에 유의 해야 합니다. 사례 보류 정책을 만든 후에 서비스 케이스 보류 규칙을 만들지 않으면 eDiscovery 보류가 만들어지지 않고 콘텐츠가 보류 되지 않습니다.

다음 명령을 실행 하 여 마이그레이션할 eDiscovery 보존을 다시 만듭니다. 다음 예제에서는 마이그레이션하려는 3 단계의 원본 위치 유지에 대 한 속성을 사용 합니다.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
$rule = New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![NewCaseHoldPolicy 및 NewCaseHoldRule cmdlet 사용 예제](media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>6 단계: eDiscovery 보류 확인

보류를 만드는 데 문제가 없는지 확인 하려면 배포 상태가 성공 인지 확인 하는 것이 좋습니다. 배포는 이전 단계의 *ExchangeLocation* 매개 변수에 지정 된 모든 콘텐츠 위치에 보류가 적용 되었음을 의미 합니다. 이 작업을 수행 하려면 **new-caseholdpolicy** cmdlet을 실행 하면 됩니다. 이전 단계에서 만든 *$policy* 변수에 저장 된 속성은 해당 변수에 자동으로 업데이트 되지 않으므로 cmdlet을 다시 실행 하 여 배포가 정상적으로 작동 하는지 확인 해야 합니다. 케이스 보류 정책을 성공적으로 배포 하려면 5 분에서 24 시간까지 소요 될 수 있습니다.

다음 명령을 실행 하 여 eDiscovery 보류가 성공적으로 배포 되었는지 확인 합니다.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

*DistributionStatus* 속성의 **성공** 값은 해당 보류가 콘텐츠 위치에 성공적으로 설정 되었음을 나타냅니다. 배포가 아직 완료 되지 않은 경우 **보류** 중 값이 표시 됩니다.

![PowerShell Get-New-caseholdpolicy 예제](media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>7 단계: 검색 만들기

마지막 단계는 3 단계에서 식별 한 검색을 다시 만들고 사례와 연결 하는 것입니다. 검색을 만든 후에는 **ComplianceSearch** cmdlet을 사용 하거나 나중에 실행 해 서 실행할 수 있습니다.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell 새 ComplianceSearch 예제](media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>8 단계: Microsoft 365 준수 센터의 사례, 보류 및 검색 확인

모든 기능이 제대로 설정 되었는지 확인 하려면 Microsoft 365 준수 센터로 [https://compliance.microsoft.com](https://compliance.microsoft.com)이동 하 여 **eDiscovery > Core**를 클릭 합니다.

![Microsoft 365 준수 센터 eDiscovery](media/MigrateLegacyeDiscovery7.png)

3 단계에서 만든 사례가 **핵심 eDiscovery** 페이지에 나열 됩니다. 사례를 연 다음 4 단계에서 **만든 보류가 보류 탭에** 표시 되는지 확인 합니다. 보류를 클릭 하 여 보존을 적용 한 사서함 수와 배포 상태를 비롯 하 여 세부 정보를 볼 수 있습니다.

![Microsoft 365 준수 센터의 eDiscovery 보류](media/MigrateLegacyeDiscovery8.png)

7 단계에서 만든 검색이 eDiscovery 사례의 **검색** 탭에 나열 된 대로 나열 되어 있습니다.

![Microsoft 365 준수 센터의 eDiscovery 사례 검색](media/MigrateLegacyeDiscovery9.png)

원본 위치 eDiscovery 검색을 마이그레이션하는 경우 eDiscovery 사례와 연결 하지 않으면 Microsoft 365 준수 센터의 콘텐츠 검색 페이지에 나열 됩니다.

## <a name="more-information"></a>추가 정보

- Exchange 관리 센터의 원본 위치 eDiscovery & 보류에 대 한 자세한 내용은 다음 항목을 참조 하십시오.
  
  - [원본 위치 eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [원본 위치 유지 및 소송 보존](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- 문서에 사용 된 PowerShell cmdlet에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [Remove-compliancecase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [New-caseholdpolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [New-caseholdrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [New-caseholdpolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- Microsoft 365 준수 센터에 대 한 자세한 내용은 [microsoft 365 준수 센터 개요](microsoft-365-compliance-center.md)를 참조 하세요.
