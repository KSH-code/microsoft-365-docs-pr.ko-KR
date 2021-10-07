---
title: Exchange Online 사서함의 보류 유형을 식별하는 방법
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: Exchange Online 사서함에 배치할 수 있는 다양한 유형의 보류를 식별하는 Microsoft 365.
ms.openlocfilehash: 8696ab52fdb0826dddd9f1a186f56f853b6fae3d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201856"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Exchange Online 사서함의 보류 유형을 식별하는 방법

이 문서에서는 특정 사서함의 사서함에 Exchange Online 보류를 식별하는 Microsoft 365.

Microsoft 365 조직에서 사서함 콘텐츠가 영구적으로 삭제되는 것을 방지할 수 있는 여러 가지 방법을 제공합니다. 이를 통해 조직은 규정 준수 규정 또는 법적 및 기타 유형의 조사 중에 콘텐츠를 보존할 수 있습니다. 다음은 보류라고도 하는 보존 기능의 Office 365. 

- **[소송 보류](create-a-litigation-hold.md):** 사서함의 사용자 사서함에 적용되는 Exchange Online.

- **[eDiscovery 보류](create-ediscovery-holds.md):** 보안 및 규정 준수 센터의 Core eDiscovery 사례와 연결된 보류. eDiscovery 보류는 사용자 사서함 및 Microsoft 365 그룹의 해당 사서함에 적용할 수 Microsoft Teams.

- **[In-Place Hold](/Exchange/security-and-compliance/create-or-remove-in-place-holds):** In-Place 관리 센터의 Exchange eDiscovery & 보류 도구를 사용하여 사용자 사서함에 적용되는 Exchange Online. 

   > [!NOTE]
   > In-Place 보류가 사용 중지되어 더 이상 보류를 만들거나 사서함에 In-Place 수 없습니다. 그러나 In-Place 사서함에 여전히 보류가 적용될 수 있습니다. 따라서 보류가 이 문서에 포함되어 있습니다. 자세한 내용은 레거시 [eDiscovery](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)도구의 사용 중지를 참조하세요.

- **[Microsoft 365 보존 정책](retention.md):** 사용자 사서함의 사용자 사서함 및 Exchange Online 그룹 및 사서함의 해당 사서함에 콘텐츠를 Microsoft 365 구성할 수 Microsoft Teams. 사용자 사서함에 저장되는 비즈니스용 Skype 보존 정책을 만들 수도 있습니다.

  사서함에 할당할 수 있는 Microsoft 365 정책에는 두 가지 유형이 있습니다.

    - **특정 위치 보존 정책:** 특정 사용자의 콘텐츠 위치에 할당되는 정책입니다. PowerShell에서 **Get-Mailbox** cmdlet을 Exchange Online 특정 사서함에 할당된 보존 정책에 대한 정보를 얻습니다. 이 유형의 보존 정책에 대한 자세한 [](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) 내용은 보존 정책 설명서에서 특정 포함 또는 제외가 있는 정책 섹션을 참조하세요.

    - **조직 전체 보존 정책:** 다음은 조직의 모든 콘텐츠 위치에 할당되는 정책입니다. PowerShell에서 **Get-OrganizationConfig** cmdlet을 Exchange Online 조직 전체 보존 정책에 대한 정보를 얻습니다. 이 유형의 보존 정책에 대한 자세한 내용은 보존 정책 설명서에서 [전체](create-retention-policies.md#a-policy-that-applies-to-entire-locations) 위치에 적용되는 정책 섹션을 참조하세요.

- **[Microsoft 365](retention.md)** 보존 레이블: 사용자가 사서함의 폴더 또는 항목에 Microsoft 365 보존 레이블(콘텐츠를 보존하거나 보존한 다음 삭제하도록 구성된  레이블)을 적용하는 경우 사서함이 소송 보존 상태 또는 Microsoft 365 보존 정책에 할당된 경우처럼 사서함에 보류가 적용됩니다. 자세한 내용은 이 [](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) 문서의 폴더 또는 항목에 보존 레이블이 적용되어 보류된 사서함 식별 섹션을 참조하세요.

보류된 사서함을 관리하기 위해 보류 기간을 변경하거나, 일시적으로 또는 영구적으로 보류를 제거하거나, 보존 정책에서 사서함을 제외하는 등의 작업을 수행할 수 있도록 사서함에 배치되는 보류 유형을 식별해야 Microsoft 365 있습니다. 이러한 경우 첫 번째 단계는 사서함에 배치된 보류 유형을 식별하는 것입니다. 또한 여러 보류 및 여러 유형의 보류를 단일 사서함에 배치할 수 있기 때문에 보류를 제거하거나 변경하려는 경우 사서함에 배치된 모든 보류를 식별해야 합니다.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>1단계: 사서함에 배치된 보류에 대한 GUID 얻기

PowerShell에서 다음 두 cmdlet을 Exchange Online 사서함에 배치된 보류의 GUID를 얻을 수 있습니다. GUID를 얻은 후 이 GUID를 사용하여 2단계에서 특정 보류를 식별합니다. 소송 보류는 GUID로 식별되지 않습니다. 사서함에 대해 소송 보류를 사용하도록 설정하거나 사용하지 않도록 설정합니다.

- **Get-Mailbox:** 이 cmdlet을 사용하여 사서함에 대해 소송 보존을 사용하도록 설정되어 있는지 여부를 결정하고 사서함에 특별히 할당된 eDiscovery 보류, In-Place 보류 및 Microsoft 365 보존 정책의 GUID를 얻을 수 있습니다. 이 cmdlet의 출력은 사서함이 조직 전체 보존 정책에서 명시적으로 제외된지도 나타냅니다.

- **Get-OrganizationConfig:** 이 cmdlet을 사용하여 조직 전체 보존 정책에 대한 GUID를 얻을 수 있습니다.

Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

### <a name="get-mailbox"></a>Get-Mailbox

다음 명령을 실행하여 사서함에 적용된 보존 Microsoft 365 및 보존 정책에 대한 정보를 얻습니다.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> InPlaceHolds 속성에 값이 너무 많고 모든 값이 표시되지 않는 경우 명령을 실행하여 각 GUID를 별도의 줄에 표시할 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 수 있습니다.

다음 표에서는 **Get-Mailbox** cmdlet을 실행할 때 *InPlaceHolds* 속성의 값에 따라 서로 다른 유형의 보류를 식별하는 방법에 대해 설명하고 있습니다.

| 보류 유형                                                          | 예제 값                                                                                  | 보류를 식별하는 방법                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 소송 대기                                                    | `True`                                                                                         | *LitigationHoldEnabled* 속성을 로 설정하면 사서함에 대해 소송 보류가 사용하도록 `True` 설정됩니다.                                                                                                                                                                                                                                         |
| eDiscovery 보류                                                    | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`                                                     | *InPlaceHolds* 속성에는 보안 및 준수 센터의 eDiscovery 사례와 연결된 모든 보류의 GUID가 포함되어 있습니다. GUID는 통합 보류를 나타남으로 시작하기 때문에 이 보류는 eDiscovery 보류라고 `UniH` 알 수 있습니다.                                                                                   |
| 원본 위치 유지                                                      | `c0ba3ce811b6432a8751430937152491` <br/> 또는 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`        | *InPlaceHolds* 속성에는 사서함에 In-Place Hold의 GUID가 포함되어 있습니다. GUID가 In-Place 시작하지 않는 경우 또는 이 GUID가 prefix로 시작하기 때문에 보류 중 하나라고 알 `cld` 수 있습니다.                                                                                                               |
| Microsoft 365 특별히 적용된 보존 정책 | `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 또는 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3` | InPlaceHolds 속성에는 사서함에 적용되는 특정 위치 보존 정책의 GUID가 포함되어 있습니다. GUID는 또는 prefix로 시작하기 때문에 보존 정책을 `mbx` `skp` 식별할 수 있습니다. 이 prefix는 보존 정책이 사용자 비즈니스용 Skype 대화에 `skp` 적용된 것일 수 있습니다. |
| 조직 전체의 보존 정책에서 Microsoft 365 제외  | `-mbxe9b52bf7ab3b46a286308ecb29624696`                                                         | 사서함이 조직 전체의 Microsoft 365 보존 정책에서 제외되는 경우 사서함이 제외된 보존 정책의 GUID가 InPlaceHolds 속성에 표시되고 이 GUID는 `-mbx` Prefix로 식별됩니다.                                                                                                     |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
**Get-Mailbox** cmdlet을 실행할 때 *InPlaceHolds* 속성이 비어 있는 경우 사서함에 적용된 보존 정책이 조직 전체에 Microsoft 365 있을 수 있습니다. PowerShell에서 Exchange Online 명령을 실행하여 조직 전체의 보존 정책에 Microsoft 365.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> InPlaceHolds 속성에 값이 너무 많고 모든 값이 표시되지 않는 경우 명령을 실행하여 각 GUID를 별도의 줄에 표시할 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 수 있습니다.

다음 표에서는 조직 전체 보류의 다양한 유형과 **Get-OrganizationConfig** cmdlet을 실행할 때 *InPlaceHolds* 속성에 포함된 GUID에 따라 각 유형을 식별하는 방법에 대해 설명하고 있습니다.

| 보류 유형                                                                                                | 예제 값                           | 설명                                                                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft 365 사서함, Exchange 공용 폴더 및 Exchange 채팅에 적용되는 Teams 보존 정책 | `mbx7cfb30345d454ac0a989ab3041051209:2` | Exchange 사서함, Exchange 공용 폴더 및 1xN 채팅에 적용되는 조직 전체 보존 정책은 Microsoft Teams 시작되는 GUID로 `mbx` 식별됩니다. 참고 1xN 채팅은 개별 채팅 참가자의 사서함에 저장됩니다.  |
| Microsoft 365 및 Microsoft 365 채널 메시지에 Teams 보존 정책 적용                | `grp1a0a132ee8944501a4bb6a452ec31171:3` | Microsoft 365 그룹 및 채널 메시지에 적용되는 조직 전체 보존 정책은 Microsoft Teams 시작되는 GUID로 `grp` 식별됩니다. 참고 채널 메시지는 Microsoft 팀과 연결된 그룹 사서함에 저장됩니다. |

사용자에 적용된 보존 정책에 Microsoft Teams 자세한 내용은 에 대한 보존 정책 [Microsoft Teams.](retention-policies-teams.md)

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>보존 정책에 대한 InPlaceHolds 값의 형식 이해

InPlaceHolds 속성의 항목을 Microsoft 365 보존 정책으로 식별하는 접두사(mbx, skp 또는 grp) 외에도 이 값에는 정책에 대해 구성된 보존 작업 유형을 식별하는 접미사도 포함되어 있습니다. 예를 들어 다음 예제에서는 동작 접미사에 굵게 강조 표시됩니다.

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

다음 표에서는 세 가지 가능한 보존 작업을 정의합니다.

| 값 | 설명                                                                                                                          |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | 보존 정책이 항목을 삭제하도록 구성되어 있는지 나타냅니다. 정책은 항목을 보존하지 않습니다.                                  |
| **2** | 보존 정책이 항목을 보류하도록 구성되어 있는지 나타냅니다. 보존 기간이 만료된 후 정책은 항목을 삭제하지 않습니다. |
| **3** | 보존 정책이 항목을 보존한 다음 보존 기간이 만료된 후 삭제하도록 구성되어 있는지 나타냅니다.             |

보존 작업에 대한 자세한 내용은 특정 기간 동안 콘텐츠 보존 [섹션을 참조하세요.](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>2단계: GUID를 사용하여 보류 식별

사서함에 적용되는 보류의 GUID를 얻은 후 다음 단계는 해당 GUID를 사용하여 보류를 식별하는 것입니다. 다음 섹션에서는 보류 GUID를 사용하여 보류의 이름(및 기타 정보)을 식별하는 방법을 보여 제공합니다.

### <a name="ediscovery-holds"></a>eDiscovery 보존

Security & Compliance Center PowerShell에서 다음 명령을 실행하여 사서함에 적용되는 eDiscovery 보류를 식별합니다. 1단계에서 식별한 eDiscovery 보류에 대한 GUID(UniH prefix 포함 안 )를 사용 합니다. 

보안 및 준수 & PowerShell에 연결하기 위해 커넥트 및 준수 센터 [PowerShell에 & 참조합니다.](/powershell/exchange/connect-to-scc-powershell)

첫 번째 명령은 보류에 대한 정보가 포함된 변수를 만듭니다. 이 변수는 다른 명령에 사용됩니다. 두 번째 명령은 보류가 연결된 eDiscovery 사례의 이름을 표시합니다. 세 번째 명령은 보류의 이름과 보류가 적용되는 사서함 목록을 표시합니다.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>원본 위치 유지

PowerShell에서 Exchange Online 명령을 실행하여 사서함에 In-Place 보류를 식별합니다. 1단계에서 In-Place 보류에 대한 GUID를 사용 합니다. 이 명령은 보류의 이름과 보류가 적용되는 사서함 목록을 표시합니다.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

보류의 GUID가 In-Place 시작되는 경우 이전 명령을 실행하는 경우 반드시 `cld` prefix를 포함해야 합니다.

> [!IMPORTANT]
> 사서함 콘텐츠를 보존하는 다양한 방식으로 계속 투자함에 따라 EAC(In-Place 관리 센터)에서 In-Place 보존의 Exchange 발표하고 있습니다. 2020년 7월 1일부터는 새 보류를 In-Place 수 Exchange Online. 그러나 여전히 EAC에서 또는 PowerShell에서 **Set-MailboxSearch** cmdlet을 In-Place 보류를 관리할 Exchange Online 있습니다. 그러나 2020년 10월 1일부터는 보류를 관리할 In-Place 없습니다. EAC에서 또는 **Remove-MailboxSearch** cmdlet을 사용 하여만 제거됩니다. 보류의 사용 중지에 대한 In-Place 레거시 [eDiscovery](legacy-ediscovery-retirement.md)도구의 사용 중지를 참조하세요.

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 보존 정책

Security & Compliance Center PowerShell에서 다음 명령을 실행하여 사서함에 적용되는 Microsoft 365 보존 정책(조직 전체 또는 특정 위치)을 ID로 지정합니다. 1단계에서 식별한 GUID(mbx, skp 또는 grp 접두사 또는 작업 접미사는 포함하지 않습니다)를 사용 합니다.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>보존 레이블이 폴더 또는 항목에 적용되어 보류된 사서함 식별

사용자가 콘텐츠를 보존하거나 보존한 다음 사서함의 폴더 또는 항목에 콘텐츠를 삭제하도록 구성된 보존 레이블을 적용하면 *ComplianceTagHoldApplied* 사서함 속성이 **True로** 설정됩니다. 이 경우 사서함은 소송 보존에 배치되거나 사서함 보존 정책에 할당된 경우처럼 보류된 Microsoft 365 간주됩니다. *ComplianceTagHoldApplied* 속성을 **True로 설정하면** 다음과 같은 상황이 발생할 수 있습니다.

- 사서함 또는 사용자의 사용자 계정이 삭제되면 사서함은 비활성 [사서함이 됩니다.](inactive-mailboxes-in-office-365.md)
- 사서함(기본 사서함 또는 보관 사서함이 사용하도록 설정된 경우)을 사용하지 않도록 설정할 수 없습니다.
- 사서함의 항목은 예상보다 오래 보존될 수 있습니다. 사서함이 보류 중이기 때문에 항목이 영구적으로 삭제(제거)되지 않습니다.

*ComplianceTagHoldApplied* 속성의 값을 보기 위해 PowerShell에서 Exchange Online 실행합니다.

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

보존 레이블에 대한 자세한 내용은 보존 [레이블을 참조하세요.](retention.md#retention-labels)

## <a name="managing-mailboxes-on-delay-hold"></a>사서함을 지연된 보류로 관리

사서함에서 모든 유형의 보류를 제거하면 지연 *보류가* 적용됩니다. 즉, 데이터가 사서함에서 영구적으로 삭제(제거)되지 않도록 보류의 실제 제거가 30일 동안 지연됩니다. 이렇게 하면 관리자가 보류가 제거된 후 제거될 사서함 항목을 검색하거나 복구할 수 있습니다. 다음에 관리되는 폴더 도우미가 사서함을 처리하고 보류가 제거된 경우 사서함에 지연 보류가 적용됩니다. 특히 관리되는 폴더 도우미가 다음 사서함 속성 중 하나를 True로 설정하면 사서함에 지연 보류가 **적용됩니다.**

- **DelayHoldApplied:** 이 속성은 사용자 사서함에 저장된 전자 메일 관련 콘텐츠(Outlook 및 웹용 Outlook 사용하여 생성)에 적용됩니다.

- **DelayReleaseHoldApplied:** 이 속성 Outlook은 사용자 사서함에 저장된 클라우드 기반 콘텐츠(Microsoft Teams, Microsoft Forms 및 Microsoft Yammer와 같은 비영구 앱에 의해 생성)에 적용됩니다. Microsoft 앱에서 생성된 클라우드 데이터는 일반적으로 사용자 사서함의 숨겨진 폴더에 저장됩니다.

사서함에 지연 보류가 설정되어 있는 경우(이전 속성 중 하나를 **True로** 설정한 경우) 사서함은 사서함이 소송 보류에 있는 경우처럼 무제한 보류 기간 동안 여전히 보류된 것으로 간주됩니다. 30일이 지난 후 지연 보류가 만료되고 Microsoft 365 지연 보류가 제거될 수 있도록 DelayHoldApplied 또는 DelayReleaseHoldApplied 속성을 **False로** 설정하여 지연 보류를 자동으로 제거합니다. 이러한 속성 중 하나를 **False로** 설정하면 제거로 표시된 해당 항목은 다음에 관리되는 폴더 도우미에서 사서함을 처리하면 제거됩니다.

사서함에 대한 DelayHoldApplied 및 DelayReleaseHoldApplied 속성의 값을 확인하기 위해 PowerShell에서 Exchange Online 실행합니다.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

만료되기 전에 지연 보류를 제거하려면 변경하려는 속성에 따라 Exchange Online PowerShell에서 다음 명령 중 하나 또는 둘 다를 실행할 수 있습니다.

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

또는

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied 또는 RemoveDelayReleaseHoldApplied* Exchange Online  매개 변수를 사용하려면 법적 보유 역할이 할당되어야 합니다. 

비활성 사서함에 대한 지연 보류를 제거하려면 PowerShell에서 다음 Exchange Online 실행합니다.

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

또는

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 이전 명령에서 비활성 사서함을 지정하는 가장 좋은 방법은 고유 이름 또는 GUID Exchange 것입니다. 이러한 값 중 하나를 사용하면 잘못된 사서함을 실수로 지정하는 것을 방지할 수 있습니다. 

이러한 매개 변수를 사용하여 지연 보류를 관리하는 데 대한 자세한 내용은 [Set-Mailbox를 참조하십시오.](/powershell/module/exchange/set-mailbox)

사서함을 지연 보류할 때 다음에 유의해야 합니다.

- DelayHoldApplied 또는 DelayReleaseHoldApplied 속성을 **True로** 설정하고 사서함(또는 해당 사용자 계정)이 삭제되면 사서함이 비활성 사서함이 됩니다. 두 속성 중 하나를 **True로** 설정하면 사서함이 보류된 것으로 간주되어 보류된 사서함을 삭제하면 비활성 사서함이 됩니다. 사서함을 삭제하고 비활성 사서함으로 설정하지 않은 경우 두 속성을 **모두 False로 설정해야 합니다.**

- 앞서 말한 것 처럼 DelayHoldApplied 또는 DelayReleaseHoldApplied 속성이 **True로** 설정된 경우 사서함은 무제한 보류 기간 동안 보류된 것으로 간주됩니다. 그러나 사서함의 모든 콘텐츠가 보존되는 것은 아니며,  이 속성은 각 속성에 설정된 값에 따라 다를 수 있습니다. 예를 들어 사서함에서 보류가 제거되어 두 속성이 **모두 True로** 설정되어 있는 경우를 예로 들어 보겠습니다. 그런 다음 *RemoveDelayReleaseHoldApplied* 매개 변수를 사용하여 비클라우드 데이터에 Outlook 지연 보류만 제거합니다. 다음에 관리되는 폴더 도우미가 사서함을 처리하면 제거된 Outlook 항목이 제거됩니다. DelayHoldApplied 속성은 여전히 True로 설정되어 있기 때문에 Outlook 표시된 모든 항목은 **제거되지 않습니다.** 또한 DelayHoldApplied를 **False로** 설정하고 DelayReleaseHoldApplied를 **True로** 설정하면 제거된 Outlook 항목만 제거됩니다.

## <a name="how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox"></a>조직 전체 보존 정책이 사서함에 적용되는지 확인하는 방법

조직 전체 보존 정책이 사서함에 적용되거나 제거되면 사서함 진단 로그를 내보내면 사서함에 보존 Exchange Online 실제로 적용하거나 제거한 보존 정책을 쉽게 쉽게 만들 수 있습니다. 이 정보를 확인하려면 먼저 [Powershell을](/powershell/exchange/connect-to-exchange-online-powershell)사용하여 몇 가지 Exchange Online 합니다.

### <a name="obtain-the-guids-for-any-retention-policies-explicitly-applied-to-a-mailbox"></a>사서함에 명시적으로 적용된 보존 정책의 GUID 획득

```powershell
Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="obtain-the-guids-for-any-organization-wide-retention-policies-appled-to-mailboxes"></a>사서함으로 사과된 조직 전체 보존 정책의 GUID 획득

```powershell
Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="get-the-mailbox-diagnostics-for-holdtracking"></a>HoldTracking에 대한 사서함 진단을 얻습니다.

보류 추적 사서함 진단 로그는 사용자 사서함에 적용된 보류의 기록을 유지 관리합니다.

```powershell
$ht = Export-MailboxDiagnosticLogs <username> -ComponentName HoldTracking
$ht.MailboxLog | Convertfrom-Json
```

### <a name="review-the-results-of-the-mailbox-diagnostics-logs"></a>사서함 진단 로그의 결과 검토

이전 단계에서 데이터를 수집하는 경우 결과 데이터는 다음과 같이 될 수 있습니다.

> **ed** `  : 0001-01-01T00:00:00.0000000` 
>  **hid** ` : mbx7cfb30345d454ac0a989ab3041051209:1` 
>  **ht** `  : 4` 
>  **lsd** ` : 2020-03-23T18:24:37.1884606Z` 
>  **osd**` : 2020-03-23T18:24:37.1884606Z`

다음 표를 사용하여 진단 로그에 나열된 각 이전 값을 쉽게 이해할 수 있습니다.

| 값   | 설명 |
|:------- |:----------- |
| **ed**  | 보존 정책을 사용하지 않도록 설정한 날짜인 종료 날짜를 나타냅니다. MinValue는 정책이 사서함에 여전히 할당되어 있는 것입니다. |
| **hid** | 보존 정책의 GUID를 나타냅니다. 이 값은 사서함에 할당된 명시적 또는 조직 전체 보존 정책에 대해 수집한 GUID와 관련이 있습니다.|
| **lsd** | 보존 정책이 사서함에 할당된 마지막 시작 날짜를 나타냅니다.|
| **osd** | 보존 정책에 대한 정보를 처음 Exchange 원래 시작 날짜를 나타냅니다. |
|||

보존 정책이 사서함에 더 이상 적용되지는 경우 콘텐츠 삭제를 방지하기 위해 사용자에게 일시적인 지연이 적용됩니다. 명령을 실행하여 지연 보류를 사용하지 않도록 설정할 수 `Set-Mailbox -RemoveDelayHoldApplied` 있습니다.

## <a name="next-steps"></a>다음 단계

사서함에 적용되는 보류를 식별한 후 보존 기간 변경, 일시적 또는 영구적으로 보류 제거 또는 비활성 사서함을 보존 정책에서 제외하는 등의 작업을 수행할 Microsoft 365 있습니다. 보류와 관련된 작업을 수행하는 데 대한 자세한 내용은 다음 항목 중 하나를 참조하십시오.

- 보안 및 준수 센터 PowerShell에서 [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationExcept & ion \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy) 명령을 실행하여 조직 Microsoft 365 보존 정책에서 사서함을 제외합니다. 이 명령은 *ExchangeLocation* 속성 값이 같은 보존 정책에만 사용할 수 `All` 있습니다.

- [비활성 사서함의 유지 보존 기간 변경](change-the-hold-duration-for-an-inactive-mailbox.md)

- [비활성 사서함 삭제](delete-an-inactive-mailbox.md)

- [보류 중인 클라우드 기반 사서함의 복구 가능한 항목 폴더에서 항목 삭제](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
