---
title: 고객 키 관리
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
description: 고객 키를 설정한 후에는 AKV 키를 복원 하 고 사용 권한 및 데이터 암호화 정책을 관리 하 여이를 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 4796fcef69e052725b635acb4170d73bb36de787
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635604"
---
# <a name="manage-customer-key"></a><span data-ttu-id="7afe3-103">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="7afe3-103">Manage Customer Key</span></span>

<span data-ttu-id="7afe3-104">Office 365에 대 한 고객 키를 설정한 후에는이 문서에 설명 된 대로 키를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="7afe3-105">자세한 내용은 관련 항목의 고객 키를 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7afe3-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="7afe3-106">Azure 키 자격 증명 모음 키 복원</span><span class="sxs-lookup"><span data-stu-id="7afe3-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="7afe3-107">복원을 수행 하기 전에 일시 삭제로 제공 되는 복구 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="7afe3-108">사용자 키와 함께 사용 되는 모든 키는 소프트 삭제를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="7afe3-109">일시 삭제는 휴지통 처럼 작동 하며 복원할 필요 없이 최대 90 일 동안 복구를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="7afe3-110">복구는 키 또는 키 보관소가 손실 된 경우와 같이 극단적인 상황 또는 예외적인 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="7afe3-111">고객 키와 함께 사용 하기 위해 키를 복원 해야 하는 경우 Azure PowerShell에서 다음과 같이 AzureKeyVaultKey cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="7afe3-112">예시:</span><span class="sxs-lookup"><span data-stu-id="7afe3-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="7afe3-113">키 보관소에 이름이 같은 키가 이미 있는 경우 복원 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="7afe3-114">AzKeyVaultKey는 키 이름을 포함 하 여 키에 대 한 모든 키 버전 및 메타 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="7afe3-115">키 보관소 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="7afe3-115">Manage key vault permissions</span></span>

<span data-ttu-id="7afe3-116">키 보관소 권한을 확인 하 고 제거 하는 데 사용할 수 있는 몇 가지 cmdlet이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="7afe3-117">예를 들어 직원이 팀을 떠날 때 사용 권한을 제거 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="7afe3-118">이러한 각 작업에 대해 Azure PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="7afe3-119">Azure Powershell에 대 한 자세한 내용은 [Azure Powershell 개요](https://docs.microsoft.com/powershell/azure/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7afe3-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="7afe3-120">키 보관소 권한을 확인 하려면 AzKeyVault cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="7afe3-121">예시:</span><span class="sxs-lookup"><span data-stu-id="7afe3-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="7afe3-122">관리자의 사용 권한을 제거 하려면 AzKeyVaultAccessPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="7afe3-123">예시:</span><span class="sxs-lookup"><span data-stu-id="7afe3-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="7afe3-124">고객 키를 사용 하 여 DEPs (데이터 암호화 정책) 관리</span><span class="sxs-lookup"><span data-stu-id="7afe3-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="7afe3-125">각 서비스 간에 다른 방식으로 Ps를 초기화 하는 고객 키 핸들</span><span class="sxs-lookup"><span data-stu-id="7afe3-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="7afe3-126">예를 들어 다양 한 서비스에 대해 DEPs의 수를 다르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="7afe3-127">**Exchange Online 및 비즈니스용 Skype:** 최대 50 DEPs를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="7afe3-128">자세한 내용은 [Exchange Online 및 비즈니스용 Skype에서 사용할 DEP (데이터 암호화 정책) 만들기](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7afe3-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="7afe3-129">**SharePoint Online, 비즈니스용 OneDrive 및 팀 파일:** DEP는 지리적 위치 ( _geo_라고도 함)의 데이터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="7afe3-130">Office 365의 다중 지역 기능을 사용 하는 경우에는 각 지역에 따라 하나의 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="7afe3-131">다중 geo를 사용 하지 않는 경우에는 하나의 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="7afe3-132">일반적으로 고객 키를 설정할 때 DEP를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="7afe3-133">자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive geo에 대 한 DEP (데이터 암호화 정책) 만들기](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7afe3-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7afe3-134">Exchange Online 및 비즈니스용 Skype 용으로 만든 DEPs 확인</span><span class="sxs-lookup"><span data-stu-id="7afe3-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7afe3-135">Get-DataEncryptionPolicy PowerShell cmdlet을 사용 하 여 Exchange Online 및 비즈니스용 Skype 용으로 만든 모든 DEPs의 목록을 확인 하려면 다음 단계를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="7afe3-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="7afe3-136">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="7afe3-137">조직의 모든 DEPs를 반환 하려면 매개 변수를 사용 하지 않고 Get-Data과 Policy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="7afe3-138">Get-data과 Policy cmdlet에 대 한 자세한 내용은 [get-data과 policy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-dataencryptionpolicy?view=exchange-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7afe3-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="7afe3-139">클라우드로 사서함을 마이그레이션하기 전에 DEP를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="7afe3-140">DEP를 할당 하면 Microsoft 365는 마이그레이션 중에 할당 된 DEP를 사용 하 여 사서함의 내용을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="7afe3-141">사서함을 마이그레이션하고, DEP를 할당 하 고, 암호화가 수행 될 때까지 기다리지 않고이 프로세스를 수행 하는 것이 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="7afe3-142">Office 365로 마이그레이션하기 전에 사서함에 DEP를 할당 하려면 Exchange Online PowerShell에서 설정-MailUser cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="7afe3-143">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="7afe3-144">설정-MailUser cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="7afe3-145">여기서 *GeneralMailboxOrMailUserIdParameter* 는 사서함을 지정 하 고 *Dataencryptionpolicyidparameter* 는 DEP의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="7afe3-146">설정-MailUser cmdlet에 대 한 자세한 내용은 [설정-MailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-mailuser?view=exchange-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7afe3-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="7afe3-147">사서함에 할당 된 DEP 확인</span><span class="sxs-lookup"><span data-stu-id="7afe3-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="7afe3-148">사서함에 할당 된 DEP를 확인 하려면 Get-mailboxstatistics cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="7afe3-149">Cmdlet은 고유 식별자 (GUID)를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="7afe3-150">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="7afe3-151">여기서 *GeneralMailboxOrMailUserIdParameter* 은 사서함을 지정 하 고 DataEncryptionPolicyID는 DEP의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="7afe3-152">Get-mailboxstatistics cmdlet에 대 한 자세한 내용은 [get-get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/get-mailboxstatistics?view=exchange-ps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7afe3-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="7afe3-153">Get-DataEncryptionPolicy cmdlet을 실행 하 여 사서함이 할당 된 DEP의 이름을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="7afe3-154">여기서 *GUID* 는 이전 단계의 get-mailboxstatistics cmdlet에서 반환 하는 guid입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="7afe3-155">고객 키가 암호화를 완료 했는지 확인</span><span class="sxs-lookup"><span data-stu-id="7afe3-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="7afe3-156">단순히 고객 키를 롤백하거나 새 DEP를 할당 하거나 사서함을 마이그레이션한 적이 있는지 여부에 관계 없이이 섹션의 단계를 사용 하 여 암호화가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7afe3-157">Exchange Online 및 비즈니스용 Skype에 대 한 암호화 완료 확인</span><span class="sxs-lookup"><span data-stu-id="7afe3-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7afe3-158">사서함을 암호화 하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="7afe3-159">DEP를 변경한 후 또는 사서함에 DEP를 처음 할당할 때 암호화 유효성 검사를 시도 하기 전에 72 시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="7afe3-160">Get-mailboxstatistics cmdlet을 사용 하 여 사서함이 암호화 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="7afe3-161">사서함이 암호화 된 경우 IsEncrypted 속성은 **true** 값을 반환 하 고 사서함이 암호화 되지 않은 경우에는 **false** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="7afe3-162">사서함 이동이 완료 되는 시간은 사서함의 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="7afe3-163">고객 키가 새 DEP를 할당 한 시간부터 72 시간 후 사서함을 완전히 암호화 하지 않은 경우 사서함 이동을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, initiate a mailbox move.</span></span> <span data-ttu-id="7afe3-164">이 작업을 수행 하려면 New-moverequest cmdlet을 사용 하 여 사서함의 별칭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-164">To do this, use the New-MoveRequest cmdlet and provide the alias of the mailbox.</span></span> <span data-ttu-id="7afe3-165">예시:</span><span class="sxs-lookup"><span data-stu-id="7afe3-165">For example:</span></span>
  
```powershell
New-MoveRequest <alias>
```

<span data-ttu-id="7afe3-166">이 cmdlet에 대 한 자세한 내용은 [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7afe3-166">For more information about this cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps).</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="7afe3-167">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 암호화 완료 확인</span><span class="sxs-lookup"><span data-stu-id="7afe3-167">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="7afe3-168">다음과 같이 SPODataEncryptionPolicy cmdlet을 실행 하 여 암호화 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-168">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="7afe3-169">이 cmdlet의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-169">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="7afe3-170">기본 키의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-170">The URI of the primary key.</span></span>

- <span data-ttu-id="7afe3-171">보조 키의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-171">The URI of the secondary key.</span></span>

- <span data-ttu-id="7afe3-172">Geo의 암호화 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-172">The encryption status for the geo.</span></span> <span data-ttu-id="7afe3-173">가능한 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-173">Possible states include:</span></span>

  - <span data-ttu-id="7afe3-174">**등록 취소 됨:** 고객 키 암호화가 아직 적용 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-174">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="7afe3-175">**등록:** 고객 키 암호화가 적용 되었으며 파일을 암호화 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-175">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="7afe3-176">지역 키가 등록 되 고 있는 경우에는 geo의 사이트 비율에 대 한 정보를 표시 하 여 암호화 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-176">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="7afe3-177">**등록 된 경우:** 고객 키 암호화가 적용 되었으며 모든 사이트의 모든 파일이 암호화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-177">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="7afe3-178">**롤링:** 키 롤이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-178">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="7afe3-179">지역 키가 롤링을 진행 하는 경우 진행률을 모니터링할 수 있도록 키 롤 작업을 완료 한 사이트 비율에 대 한 정보도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-179">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="7afe3-180">키 해지 및 데이터 제거 경로 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="7afe3-180">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="7afe3-181">가용성 키를 포함 하 여 모든 루트 키의 해지를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-181">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="7afe3-182">Customer 키를 통해 규정 요구 사항의 종료 계획 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-182">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="7afe3-183">키를 해지 하 여 데이터를 제거 하 고 서비스를 종료 하는 경우 서비스는 데이터 제거 프로세스가 완료 된 후에 가용성 키를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-183">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="7afe3-184">Microsoft 365에서 데이터 제거 경로를 감사 하 고 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-184">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="7afe3-185">자세한 내용은 [서비스 보안 포털](https://servicetrust.microsoft.com/)에서 사용할 수 있는 SSAE 18soc 2 보고서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7afe3-185">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="7afe3-186">또한 Microsoft는 다음 문서를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-186">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="7afe3-187">Microsoft 클라우드의 금융 기관에 대 한 위험 평가 및 준수 가이드</span><span class="sxs-lookup"><span data-stu-id="7afe3-187">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="7afe3-188">O365 종료 계획 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7afe3-188">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="7afe3-189">데이터 제거 경로가 서로 다른 서비스 간에 약간씩 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-189">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7afe3-190">Exchange Online 및 비즈니스용 Skype에 대 한 고객 키 및 가용성 키 해지</span><span class="sxs-lookup"><span data-stu-id="7afe3-190">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7afe3-191">Exchange Online 및 비즈니스용 Skype의 데이터 제거 경로를 시작할 때 DEP에 영구 데이터 제거 요청을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-191">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="7afe3-192">이렇게 하면 DEP가 할당 된 사서함 내에서 암호화 된 데이터가 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-192">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="7afe3-193">한 번에 한 명의 DEP에 대해 PowerShell cmdlet을 실행할 수 있으므로 데이터 제거 경로를 시작 하기 전에 모든 사서함에 단일 DEP를 다시 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-193">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="7afe3-194">사서함의 하위 집합을 삭제 하는 데 데이터 제거 경로를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7afe3-194">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="7afe3-195">이 프로세스는 서비스를 종료 하는 고객 에게만 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-195">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="7afe3-196">데이터 제거 경로를 시작 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-196">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="7afe3-197">Azure 키 자격 증명 모음에서 "O365 Exchange Online"에 대 한 줄 바꿈 및 래핑 해제 권한을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-197">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="7afe3-198">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-198">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="7afe3-199">삭제 하려는 사서함이 포함 된 각 DEP에 대해 다음과 같이 [Set-Data\ 정책](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-dataencryptionpolicy) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-199">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="7afe3-200">명령이 실패 하면이 작업의 앞부분에서 설명한 대로 Azure 키 자격 증명 모음의 두 키에서 Exchange Online 권한을 제거 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-200">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="7afe3-201">PermanentDataPurgeRequested 스위치를 set-DataEncryptionPolicy cmdlet을 사용 하 여 설정 하면 더 이상이 DEP를 사서함에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-201"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="7afe3-202">Microsoft 지원에 문의 하 여 데이터 삭제를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-202">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="7afe3-203">요청 시 Microsoft는 데이터 삭제를 승인 하 고 권한을 부여할 수 있는 법적 문서를 보내 달라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-203">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="7afe3-204">온 보 딩 시에이 문서에 서명 해야 하는 경우 FastTrack의 승인자로 등록 한 조직 내의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-204">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="7afe3-205">일반적으로 회사에서 조직 대신 서류에 서명할 수 있는 권한이 부여 된 임원 또는 기타 지정 된 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-205">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="7afe3-206">담당자가 법률 문서에 서명한 후에는 보통 eDoc 서명을 통해 Microsoft에 반송 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-206">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="7afe3-207">Microsoft는 유효한 문서를 받은 후에 cmdlet을 실행 하 여 먼저 정책을 삭제 하는 데이터 삭제를 트리거하여, 사서함을 영구 삭제 하도록 표시 한 다음, 가용성 키를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-207">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="7afe3-208">데이터 제거 프로세스가 완료 되 면 데이터가 제거 되 고 Exchange Online에서 액세스할 수 없으며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-208">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="7afe3-209">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키 및 가용성 키 해지</span><span class="sxs-lookup"><span data-stu-id="7afe3-209">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="7afe3-210">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 데이터 제거 경로를 시작 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-210">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="7afe3-211">Azure 키 자격 증명 모음 액세스를 해지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-211">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="7afe3-212">모든 키 자격 증명 관리자는 액세스 취소에 동의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-212">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="7afe3-213">SharePoint Online에 대 한 Azure 키 자격 증명 모음을 삭제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-213">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="7afe3-214">키 자격 증명은 여러 SharePoint Online 테 넌 트 및 DEPs 간에 공유 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-214">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="7afe3-215">Microsoft에 연락 하 여 가용성 키를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-215">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="7afe3-216">Microsoft에 연락 하 여 가용성 키를 삭제 하면 올바른 문서가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-216">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="7afe3-217">온 보 딩 시에이 문서에 서명 해야 하는 경우 FastTrack의 승인자로 등록 한 조직 내의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-217">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="7afe3-218">일반적으로 회사에서 조직 대신 서류에 서명할 수 있는 권한이 있는 임원 또는 기타 지정 된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-218">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="7afe3-219">담당자가 법률 문서에 서명 하면 일반적으로 eDoc 서명을 통해 Microsoft에 반송 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-219">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="7afe3-220">Microsoft는 법률 문서를 받은 후 cmdlet을 실행 하 여 테 넌 트 키, 사이트 키 및 모든 개별 문서에 대 한 암호화 삭제를 수행 하는 데이터 삭제를 트리거하여 키 계층 구조를 영구적으로 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-220">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="7afe3-221">데이터 제거 cmdlet이 완료 되 면 데이터가 제거 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7afe3-221">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7afe3-222">관련 문서</span><span class="sxs-lookup"><span data-stu-id="7afe3-222">Related articles</span></span>

- [<span data-ttu-id="7afe3-223">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="7afe3-223">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="7afe3-224">가용성 키에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="7afe3-224">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="7afe3-225">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="7afe3-225">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="7afe3-226">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="7afe3-226">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="7afe3-227">고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="7afe3-227">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="7afe3-228">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="7afe3-228">Service Encryption</span></span>](office-365-service-encryption.md)
