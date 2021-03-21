---
title: 고객 키 또는 가용성 키 롤 또는 회전
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키와 함께 사용되는 Azure Key Vault에 저장된 고객 루트 키를 롤링하는 방법을 설명합니다. 서비스에는 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일이 포함됩니다.
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923334"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>고객 키 또는 가용성 키 롤 또는 회전

> [!CAUTION]
> 보안 또는 규정 준수 요구 사항에 따라 키를 롤해야 할 때만 고객 키와 함께 사용하는 암호화 키를 롤링합니다. 또한 정책에 연결되거나 연결된 키는 삭제하지 않습니다. 키를 롤링할 때 이전 키로 암호화된 콘텐츠가 있습니다. 예를 들어 활성 사서함은 자주 다시 암호화되는 동안 비활성, 연결이 끊어지며 비활성화된 사서함은 이전 키로 계속 암호화될 수 있습니다. SharePoint Online은 복원 및 복구를 위해 콘텐츠 백업을 수행하여 이전 키를 사용하여 보관된 콘텐츠가 계속 있을 수 있습니다.

## <a name="about-rolling-the-availability-key"></a>가용성 키 롤링

Microsoft는 고객에게 가용성 키에 대한 직접적인 제어를 노출하지 않습니다. 예를 들어 Azure Key Vault에서 소유한 키만 롤(회전)할 수 있습니다. Microsoft 365는 내부에서 정의된 일정에 따라 가용성 키를 롤링합니다. 이러한 키 롤에 대한 고객 대면 SLA(서비스 수준 계약)는 없습니다. Microsoft 365는 수동이 아닌 자동화된 프로세스에서 Microsoft 365 서비스 코드를 사용하여 가용성 키를 회전합니다. Microsoft 관리자가 롤 프로세스를 시작할 수 있습니다. 키는 키 저장소에 직접 액세스하지 않고 자동화된 메커니즘을 사용하여 롤링됩니다. 가용성 키 비밀 저장소에 대한 액세스는 Microsoft 관리자에게 프로비전되지 않습니다. 가용성 키 롤링은 키를 처음 생성하는 데 사용되는 동일한 메커니즘을 활용합니다. 가용성 키에 대한 자세한 내용은 가용성 키 [이해를 참조하세요.](customer-key-availability-key-understand.md)

> [!IMPORTANT]
> 만드는 각 DEP에 대해 고유한 가용성 키가 생성되어 고객이 새 DEP를 만들면 Exchange Online 및 비즈니스용 Skype 가용성 키를 효과적으로 롤아웃할 수 있습니다. SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 가용성 키는 포리스트 수준에 있으며 DEP 및 고객에 의해 공유됩니다. 즉, 롤링은 Microsoft 내부적으로 정의된 일정에서만 발생합니다. 새 DEP를 만들 때마다 SharePoint, OneDrive 및 Teams가 테넌트 중간 키(TIK)를 롤아웃할 때마다 가용성 키가 롤링되지 않을 위험을 완화하기 위해 새 DEP를 만들 때마다 고객 루트 키 및 가용성 키로 래핑된 키입니다.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>롤링할 각 기존 루트 키의 새 버전 요청

키를 롤링할 때 기존 키의 새 버전을 요청합니다. 기존 키의 새 버전을 요청하기 위해 처음에 키를 만드는 데 사용한 구문과 동일한 cmdlet인 [Add-AzKeyVaultKey를](/powershell/module/az.keyvault/add-azkeyvaultkey)사용하게 됩니다. DEP(데이터 암호화 정책)와 연결된 키의 롤링을 완료한 후 고객 키가 새 키를 사용할 수 있도록 다른 cmdlet을 실행합니다. 각 AKV(Azure Key Vault)에서 이 단계를 합니다.

예를 들어 다음과 같습니다.

1. Azure PowerShell을 사용하여 Azure 구독에 로그인합니다. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](/powershell/azure/authenticate-azureps)

2. 다음 Add-AzKeyVaultKey cmdlet을 실행합니다.

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   이 예제에서는 **Contoso-O365EX-NA-VaultA1-Key001이라는** 키가 **Contoso-O365EX-NA-VaultA1** 자격 증명 모음에 존재하기 때문에 이 cmdlet은 키의 새 버전을 만듭니다. 이 작업은 키의 버전 기록에서 이전 키 버전을 보존합니다. 여전히 암호화하는 데이터의 암호를 해독하려면 이전 키 버전이 필요합니다. DEP와 연결된 키의 롤링을 완료한 후 추가 cmdlet을 실행하여 고객 키가 새 키 사용을 시작하도록 합니다. 다음 섹션에서는 cmdlet에 대해 자세히 설명합니다.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype의 고객 키 업데이트

Exchange Online 및 비즈니스용 Skype와 함께 사용되는 DEP와 연결된 Azure Key Vault 키를 롤링할 때 새 키를 지점으로 하여 DEP를 업데이트해야 합니다. 이 경우 가용성 키가 회전하지 않습니다.

고객 키가 새 키를 사용하여 사서함을 암호화할 수 있도록 Set-DataEncryptionPolicy cmdlet을 실행합니다.

1. Azure PowerShell에서 Set-DataEncryptionPolicy cmdlet을 실행합니다.
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   72시간 이내에 이 DEP와 연결된 활성 사서함이 새 키로 암호화됩니다.

2. 사서함의 DataEncryptionPolicyID 속성 값을 확인한 다음 사서함에 할당된 DEP 확인의 단계를 [사용하세요.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox) 서비스가 업데이트된 키를 적용하면 이 속성의 값이 변경됩니다.
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 고객 키 업데이트

SharePoint Online에서는 한 번의 키만 롤링할 수 있습니다. 키 자격 증명 모음에서 두 키를 모두 롤아웃하려는 경우 첫 번째 작업이 완료될 때까지 기다릴 수 있습니다. 이 문제를 방지하기 위해 작업에 시차를 두는 것이 좋습니다. SharePoint Online 및 비즈니스용 OneDrive와 함께 사용되는 DEP와 연결된 Azure Key Vault 키를 롤링할 때 새 키를 지점으로 하여 DEP를 업데이트해야 합니다. 이 경우 가용성 키가 회전하지 않습니다.

1. 다음과 Update-SPODataEncryptionPolicy cmdlet을 실행합니다.
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   이 cmdlet은 SharePoint Online 및 비즈니스용 OneDrive에 대한 키 롤 작업을 시작하나 작업이 즉시 완료되지는 않습니다.

2. 키 롤 작업의 진행률을 표시하기 위해 다음과 Get-SPODataEncryptionPolicy cmdlet을 실행합니다.

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>관련 문서

- [Office 365용 고객 키를 사용하여 서비스 암호화](customer-key-overview.md)

- [Office 365의 고객 키 설정](customer-key-set-up.md)

- [Office 365의 고객 키 관리](customer-key-manage.md)

- [가용성 키에 대해 자세히 알아보기](customer-key-availability-key-understand.md)