---
title: 테넌트 수준에서 Microsoft 365의 고객 키(공개 미리 보기)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Microsoft 365 테넌트 내의 모든 데이터에 대해 고객 키를 설정하는 방법을 알아보고
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712531"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>테넌트 수준의 Microsoft 365 고객 키 개요(공개 미리 보기)

제공한 키를 사용하여 DEP(데이터 암호화 정책)를 만들고 테넌트에 할당할 수 있습니다. DEP는 이러한 워크로드에 대한 테넌트에서 데이터를 암호화합니다.

- Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)
- Teams 미디어 메시지(이미지, 코드, 비디오, 위키 이미지)
- Teams 저장소에 저장된 Teams 통화 및 모임 녹음/녹화
- Teams 채팅 알림
- Cortana의 Teams 채팅 제안
- Teams 상태 메시지
- Exchange Online에 대한 사용자 및 신호 정보

Microsoft Teams의 경우 테넌트 수준의 고객 키는 DEP가 테넌트에 할당된 시간부터 새 데이터를 암호화합니다. 공개 미리 보기에서는 과거의 데이터 암호화를 지원하지 않습니다. Exchange Online의 경우 고객 키는 기존 데이터와 새 데이터를 모두 암호화합니다.

테넌트당 여러 DEP를 만들 수 있지만 특정 시점에 하나의 DEP만 할당할 수 있습니다. DEP를 할당하면 암호화가 자동으로 시작되지만 테넌트의 크기에 따라 완료하는 데 시간이 걸릴 수 있습니다.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>테넌트 수준 정책은 Microsoft 365의 고객 키에 더 광범위한 제어를 추가합니다.

Exchange Online 및 Sharepoint Online에 대해 이미 고객 키를 설정한 경우 새 테넌트 수준 공개 미리 보기가 어떻게 설정되어 있는가?

만든 테넌트 수준 암호화 정책은 Microsoft 365의 Microsoft Teams 및 Exchange Online 워크로드에 대한 모든 데이터를 암호화합니다. 이 정책은 고객 키에서 이미 만든 세부적으로 조정된 DEP를 방해하지 않습니다.

예제:

비즈니스용 OneDrive 및 SharePoint에 저장된 Microsoft Teams 파일 및 일부 Teams 통화 및 모임 녹음/녹화는 SharePoint Online DEP에 의해 암호화됩니다. 단일 SharePoint Online DEP는 단일 지리적으로 콘텐츠를 암호화합니다. 테넌트 수준 DEP는 새 정책으로 암호화된 데이터를 다시 암호화합니다.

Exchange Online의 경우 고객 키를 사용하여 하나 이상의 사용자 사서함을 암호화하는 DEP를 만들 수 있습니다. 테넌트 수준 정책을 만들 때 해당 정책은 암호화된 사서함을 암호화하지 않습니다. 그러나 테넌트 수준 키는 이미 DEP의 영향을 받지 않는 사서함을 암호화합니다.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>테넌트 수준에서 고객 키 설정(공개 미리 보기)

이러한 단계는 응용 프로그램 수준에서 고객 키를 설정하는 단계와 비슷하지만 동일하지는 않습니다. 이 공개 미리 보기는 테스트 테넌트의 테스트 데이터와 함께만 사용해야 합니다. 프로덕션 데이터 또는 프로덕션 환경에서는 이 릴리스를 사용하지 않습니다. 고객 키의 프로덕션 배포가 이미 있는 경우 다음 단계를 사용하여 테스트 환경의 테넌트 수준에서 고객 키를 설정하십시오.

Azure PowerShell에 원격으로 연결하여 이러한 대부분의 작업을 완료합니다. 최상의 결과를 얻기 위해 Azure PowerShell 버전 4.4.0 이상을 사용하세요.

시작하기 전에 다음을 반드시 확인하십시오.

- 테넌트 수준에서 고객 키를 설정하려면 준수 관리자 역할이 있는 직장 또는 학교 계정을 사용해야 합니다.
- 조직에 적절한 라이선스가 있도록 합니다. 클라우드 서비스 공급자 또는 클라우드 서비스 공급자를 사용하여 기업계약 송장된 Azure 구독을 사용합니다. 결제 플랜 또는 신용 카드를 사용하여 구입한 Azure 구독은 고객 키에 지원되지 않습니다. 2020년 4월 1일부터 Office 365의 고객 키는 Office 365 E5, M365 E5, M365 E5 규정 준수 및 M365 E5 정보 보호 & 관리 SKUS에서 제공됩니다. Office 365 Advanced Compliance SKU는 더 이상 새 라이선스를 조달할 수 없습니다. 기존 Office 365 고급 준수 라이선스는 계속 지원됩니다. 적절한 라이선스가 있는 테넌트에서 최소 하나의 라이선스로 서비스를 사용하도록 설정하는 것이 가능하기는 하지만, 서비스를 통해 혜택을 받은 모든 사용자에게 적절한 라이선스가 있는지도 여전히 확인해야 합니다. 다음 라이선스 중 하나가 필요합니다.

### <a name="create-two-new-azure-subscriptions"></a>새 Azure 구독 2개 만들기

고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다. 이를 위해서는 Azure 구독을 두 개 만들어야 합니다. 조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다. 이러한 Azure 구독만 사용하여 Microsoft 365의 암호화 키를 관리합니다. 이렇게 하여 운영자 중 한 명이 실수로 의도적으로 또는 악의적으로 삭제하거나 책임이 있는 키를 잘못 관리한 경우 조직을 보호합니다.

조직에 대해 만들 수 있는 Azure 구독 수에는 실질적으로 제한이 없습니다. 이 모범 사례를 사용하면 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>필수 보존 기간을 사용하기 위해 Azure 구독 등록

루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다. 이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다. 고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다. Azure 구독은 즉시 취소할 수 없는 취소를 방지하는 방식으로 태그를 지정하거나 등록할 수 있습니다. 이를 필수 보존 기간에 등록이라고 합니다. 필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft와 공동 작업해야 합니다. 이 프로세스는 영업일 최대 5일이 걸릴 수 있습니다. 이전에는 이 작업을 "Do Not Cancel"이라고도 합니다.
  
Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다. 시작하기 전에 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 모듈을 설치해야 합니다.

1. Azure PowerShell로 로그인합니다. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다. 각 구독에 대해 이 작업을 수행하십시오.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Microsoft에 문의하여 프로세스가 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com) 전자 메일에 다음을 포함합니다.

   **제목:** 고객 키 \<*Your tenant's fully-qualified domain name*\>

   **본문:** 필수 보존 기간을 마무리할 구독 신분
   각 구독에 대한 Get-AzProviderFeature 출력입니다.

   이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft가 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.

4. Microsoft로부터 등록이 완료했다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인하면 됩니다. 확인된 Get-AzProviderFeature 명령은 Registration State 속성에 **대해 Registered** 값을 **반환합니다.** 각 구독에 대해 이 작업을 수행하십시오.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다. 각 구독에 대해 이 작업을 수행하십시오.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>각 구독에서 프리미엄 Azure Key Vault 만들기

키 자격 증명 모음을 만드는 단계는 Azure PowerShell 설치 및 시작, Azure 구독에 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 자격 증명 모음 만들기를 안내하는 [Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)시작에 설명되어 있습니다.
  
키 자격 증명 모음을 만들 때 SKU(Standard 또는 Premium)를 선택해야 합니다. Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있습니다. HSM(하드웨어 보안 모듈) 키 보호가 없습니다. Premium SKU는 키 자격 증명 모음 키 보호를 위해 HSM을 사용할 수 있습니다. 고객 키는 두 SKU 중 하나를 사용하는 주요 자격 증명 모음을 수락합니다. 그러나 Microsoft는 Premium SKU만 사용하는 것이 좋습니다. 두 유형의 키 중 하나를 사용하는 작업 비용은 동일하기 때문에 비용의 유일한 차이는 각 HSM으로 보호되는 키에 대한 월별 비용입니다. 자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.
  
> [!IMPORTANT]
> 프로덕션 데이터에는 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사를 위해 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.

키 자격 증명 모음에 공통적인 도우미를 사용하며 키 자격 증명 모음 및 키의 사용 및 범위에 대한 약어를 포함합니다. 예를 들어 북미에 자격 증명 모음이 위치할 Contoso 서비스의 경우 가능한 이름 쌍은 Contoso-O365-NA-VaultA1 및 Contoso-O365-NA-VaultA2입니다. 자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 요구하는 경우 원하는 이름의 변형을 시도해야 할 수 있습니다. 구성한 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 설치 계획을 서면으로 작성하고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것이 가장 좋습니다.

가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오. 페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다. 따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다. 즉, 한 지역에 배치된 Azure 리소스가 페어링된 지역을 통해 내결점성을 자동으로 얻게 됩니다. 이러한 이유로 지역이 페어링된 데이터 암호화 정책에서 사용되는 두 자격 증명 모음의 지역을 선택하면 총 두 개의 가용성 영역만 사용 중입니다. 대부분의 지역에는 두 개의 지역만 있으므로 아직 페어링되지 않은 지역을 선택할 수 없습니다. 가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 페어링되지 않은 두 지역을 선택하십시오. 이 혜택은 총 네 가지 가용성 영역의 이점입니다. 자세한 내용은 [BCDR(비즈니스](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 연속성 및 재해 복구): 현재 지역 쌍 목록은 Azure 페어링된 지역을 참조하세요.

### <a name="assign-permissions-to-each-key-vault"></a>각 키 자격 증명 모음에 사용 권한 할당

각 키 자격 증명 모음에 대해 구현에 따라 고객 키에 대한 세 가지 사용 권한 집합을 정의해야 합니다. 예를 들어 다음 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.
  
- **조직의 주요** 자격 증명 모음을 매일 관리하기 위한 주요 자격 증명 모음 관리자 이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.

  > [!IMPORTANT]
  > 키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키 삭제 권한이 포함되어 있지 않습니다. 이는 의도적인 것이고 중요한 사례입니다. 암호화 키를 삭제하는 작업은 일반적으로 수행되지 않습니다. 이렇게 하면 데이터가 영구적으로 삭제됩니다. 이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다. 대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게만 할당합니다.
  
  조직의 사용자에게 이러한 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

   Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   예를 들어,

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다. 직원이 팀을 떠나거나 팀에 합류할 때 또는 키 자격 증명 모음 관리자가 키를 삭제하거나 복원할 수 있는 권한이 합법적으로 필요한 드문 상황에서 이러한 권한을 변경해야 합니다. 이 주요 자격 증명 모음 참가자 집합은 키 자격 증명 모음에 대한 참가자 역할을 부여해야 합니다. Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다. 자세한 단계는 [Role-Based](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 액세스 제어를 사용하여 Azure 구독 리소스에 대한 액세스를 관리하세요. 구독을 만드는 관리자는 기본적으로 이 액세스 권한과 참가자 역할에 다른 관리자를 할당할 수 있습니다.

- 테넌트 수준에서 고객 키의 작업을 하는 미사용 암호화 서비스의 **Microsoft 365** 데이터입니다. Microsoft 365에 대한 사용 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  여기서,

  - *자격 증명* 모음 이름은 만든 키 자격 증명 모음의 이름입니다.

  예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인

키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다. 고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다. 소프트 삭제를 사용하도록 설정하면 삭제 후 90일 이내에 키나 자격 증명 모음을 백업에서 복원하지 않고도 복구할 수 있습니다.
  
키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.
  
1. 사용자 계정을 사용하여 Azure 구독에 Windows PowerShell. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다. 이 예에서 *자격* 증명 모음 이름은 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지를 확인할 수 있습니다. 키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가

Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다. 키 자격 증명 모음에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다. RSA 키를 사용 합니다. Azure Key Vault는 타원형 곡선 키로 래핑 및 래핑을 지원하지 않습니다.
  
키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

여기서,

- *자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.

- *키 이름은* 새 키를 제공하려는 이름입니다.

  > [!TIP]
  > 키 자격 증명 모음에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하여 키의 이름을 지정합니다. 이렇게 하면 키 이름만 표시하는 도구에서 문자열이 자체 설명을 합니다.
  
HSM을 사용하여 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 **Software를 지정합니다.**

예를 들면 다음과 같습니다.
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>키의 복구 수준 확인

Microsoft 365를 사용하려면 Azure Key Vault 구독이 Do Not Cancel으로 설정되고 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다. 키의 복구 수준을 확인하여 확인할 수 있습니다.
  
키의 복구 수준을 확인하기 위해 Azure PowerShell에서 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 이 문서를 검토하고 취소 금지 목록에 구독을 추가하고 각 키 자격 증명 모음에서 "소프트 삭제"를 사용하도록 설정한 모든 단계를 따라야 합니다. 다음으로, 전자 메일로 출력된 스크린샷을 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Azure Key Vault 백업

키를 만들거나 변경한 직후 온라인과 오프라인에서 백업을 수행하고 백업 복사본을 저장합니다. 오프라인 복사본을 네트워크에 연결하지 않습니다. 대신 물리적 안전 또는 상업용 저장소 시설에 저장합니다. 재해가 발생할 경우 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다. 키 자격 증명 모음 키를 영구적으로 삭제하거나 그렇지 않으면 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다. Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키에 필요한 메타데이터가 외부 키와 함께 존재하지 않습니다. Azure Key Vault에서 사용한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다. 따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.
  
Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

출력 파일에 접미사가 사용되도록 `.backup` 합니다.
  
이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서는 사용할 수 없습니다. 백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.
  
예를 들어,
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 구성 설정 유효성 검사

DEP에서 키를 사용하기 전에 유효성 검사를 수행하는 것은 선택 사항이지만 매우 권장됩니다. 특히 단계에 따라 이 항목에 설명된 키와 자격 증명 모음을 설정하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태 유효성을 검사해야 합니다.
  
키가 Get, wrapKey 및 unwrapKey 작업을 사용하도록 설정되어 있는지 확인:
  
[Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 다음과 같이 실행합니다.
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

출력에서 액세스 정책과 Microsoft 365 GUID(앱 ID)를 적절하게 찾아 봐야 합니다. Get, wrapKey 및 unwrapKey의 세 가지 작업은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.
  
액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

예: Rest 암호화 서비스의 Microsoft 365 데이터에서 *Microsoft 365 appID를*`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

만료된 키는 고객 키에서 사용할 수 없습니다. 만료된 키로 시도한 작업이 실패하여 서비스 작동이 종료될 수 있습니다. 고객 키와 함께 사용되는 키에는 만료 날짜가 없는 것이 좋습니다. 일단 설정된 만료 날짜는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다. 만료 날짜가 설정된 키를 사용하려면 만료 값을 9999년 12월 31일로 변경합니다. 만료 날짜가 12/31/9999가 아닌 날짜로 설정된 키는 Microsoft 365 유효성 검사를 통과하지 못합니다.
  
9999년 12월 31일이 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>각 Azure Key Vault 키에 대한 URI 획득

Azure의 모든 단계를 완료하여 키 자격 증명 모음을 설정하고 키를 추가한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다. 나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하여 이 정보를 안전한 장소에 저장해야 합니다. 각 키 자격 증명 모음에 대해 이 명령을 한 번 실행해야 합니다.
  
Azure PowerShell에서:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>테넌트에 대한 고객 키 암호화 정책 설정

이러한 cmdlet을 실행하려면 먼저 사용 권한을 할당해야 합니다. 이 문서에서는 cmdlet의 모든 매개 변수를 나열하기는 하지만 사용자에게 할당된 사용 권한에 포함되지 않은 일부 매개 변수에는 액세스할 수 없습니다. 조직에서 cmdlet 또는 매개 변수를 실행하는 데 필요한 사용 권한을 확인하려면 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)를 참조하세요.

### <a name="create-policy"></a>정책 만들기

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

설명: 준수 관리자가 두 개의 AKV 루트 키를 사용하여 DEP(새 데이터 암호화 정책)를 만들 수 있도록 합니다. 만든 정책은 cmdlet을 사용하여 할당할 Set-M365DataAtRestEncryptionPolicy 있습니다. 키를 처음 할당하거나 키를 회전한 후 새 키를 적용하는 데 최대 24시간이 걸릴 수 있습니다. 새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.

예제:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

매개 변수:

| 이름 | 설명 | 선택 사항(Y/N) |
|--|--|--|
|이름|데이터 암호화 정책의 이름|N|
|AzureKeyIDs|데이터 암호화 정책과 연결하기 위해 Azure Key Vault 키의 URI 값 두 개를 콤보로 구분하여 지정합니다.|N|
|설명|데이터 암호화 정책에 대한 설명|N|

### <a name="assign-policy"></a>정책 할당

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

설명: 이 cmdlet은 기본 데이터 암호화 정책을 구성하는 데 사용됩니다. 이 정책은 모든 지원 워크로드에서 데이터를 암호화하는 데 사용됩니다. 

예제:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

매개 변수:
| 이름 | 설명 | 선택 사항(Y/N) |
|--|--|--|
-Policy|할당해야 하는 데이터 암호화 정책을 지정합니다. 정책 이름 또는 정책 ID를 지정합니다.|N|

### <a name="modify-or-refresh-policy"></a>정책 수정 또는 새로 고침

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

설명: 이 cmdlet을 사용하여 기존 정책을 수정하거나 새로 고칠 수 있습니다. 또한 정책을 활성화 또는 비활성화하는 데 사용할 수 있습니다. 키를 처음 할당하거나 키를 회전한 후 새 키를 적용하는 데 최대 24시간이 걸릴 수 있습니다. 새 DEP를 적용하는 데 24시간 이상 소요된 경우 Microsoft에 문의합니다.

예제:

데이터 암호화 정책을 사용하지 않도록 설정

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

데이터 암호화 정책을 새로 고침합니다.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

매개 변수:
| 이름 | 설명 | 선택 사항(Y/N) |
|--|--|--|
|-Identity|수정할 데이터 암호화 정책을 지정합니다.|N|
|-Refresh|Azure Key Vault에서 연결된 키를 회전한 후 새로 고침 스위치를 사용하여 데이터 암호화 정책을 업데이트합니다. 이 스위치를 사용하면 값을 지정할 필요가 없습니다.|Y|
|-Enabled|Enabled 매개 변수는 데이터 암호화 정책을 사용하도록 설정하거나 사용하지 않도록 설정합니다. 정책을 사용하지 않도록 설정하기 전에 테넌트에서 정책을 해제해야 합니다. 유효한 값은 다음과 같습니다.</br > $true: 정책 사용</br > $true: 이 정책은 사용하도록 설정되어 있습니다. 이 값은 기본값입니다.
|Y|
|-Name|Name 매개 변수는 데이터 암호화 정책의 고유 이름을 지정합니다.|Y
|-Description|Description 매개 변수는 데이터 암호화 정책에 대한 선택적 설명을 지정합니다.|Y|

### <a name="get-policy-details"></a>정책 세부 정보 확인

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

설명: 이 cmdlet은 테넌트에 대해 만들어진 모든 M365DataAtRest 암호화 정책 또는 특정 정책에 대한 세부 정보를 나열합니다.

예제:

이 예에서는 조직의 M365DatAtRest 암호화 정책 요약 목록을 반환합니다.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

이 예에서는 "NAM Policy"라는 데이터 암호화 정책에 대한 자세한 정보를 반환합니다.

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

매개 변수:

| 이름 | 설명 | 선택 사항(Y/N) |
|--|--|--|
|-Identity|세부 정보를 나열할 데이터 암호화 정책을 지정합니다.|Y|

### <a name="get-policy-assignment-info"></a>정책 할당 정보 보기

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

설명: 이 cmdlet은 현재 테넌트에 할당된 정책을 나열합니다.

## <a name="offboarding-from-customer-key"></a>고객 키에서 오프보더

Microsoft 관리 키로 되돌려야 하는 경우 다시 사용할 수 있습니다. 오프보드를 해제하면 각 개별 워크로드에서 지원하는 기본 암호화를 사용하여 데이터가 다시 암호화됩니다. 예를 들어 Exchange Online에서는 Microsoft에서 관리하는 키를 사용하여 기본 암호화를 지원할 수 있습니다.

테넌트 수준에서 고객 키에서 테넌트의 등록을 해제하기로 결정한 경우 전자 메일을 통해 Microsoft에 연락하여 테넌트에 대한 서비스를 "사용하지 않도록 설정"하여 [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)

> [!IMPORTANT]
> 오프보더는 데이터 제거와는 동일하지 않습니다. 데이터를 삭제하면 조직 데이터가 Microsoft 365에서 영구적으로 삭제되고, 오프보더는 삭제되지 않습니다. 테넌트 수준 정책에 대한 데이터 제거는 수행할 수 없습니다. 데이터 제거 경로에 대한 자세한 내용은 키 해지 및 데이터 제거 경로 프로세스 [시작을 참조하세요.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

## <a name="about-the-availability-key"></a>가용성 키

가용성 키에 대한 자세한 내용은 [가용성 키에 대한 자세한 내용을 참조하십시오.](customer-key-availability-key-understand.md)

## <a name="key-rotation"></a>키 회전

고객 키와 함께 사용되는 키 회전 또는 롤링에 대한 자세한 내용은 고객 키 또는 가용성 키 롤 또는 회전을 [참조하세요.](customer-key-availability-key-roll.md) 새 버전의 키를 사용하기 위해 DEP를 업데이트하면 이 문서의 앞부분에서 설명한 대로 Set-M365DataAtRestEncryptionPolicy cmdlet을 실행합니다.

## <a name="related-articles"></a>관련 문서:

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키에 대해 자세히](customer-key-availability-key-understand.md)

- [서비스 암호화](office-365-service-encryption.md)
