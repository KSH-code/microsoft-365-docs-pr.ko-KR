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
description: 고객 키를 설정한 후 AKV 키를 복원하고 사용 권한 및 데이터 암호화 정책을 관리하여 키 관리 방법을 배워야 합니다.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547088"
---
# <a name="manage-customer-key"></a><span data-ttu-id="d18c1-103">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="d18c1-103">Manage Customer Key</span></span>

<span data-ttu-id="d18c1-104">Office 365에 대한 고객 키를 설정한 후 이 문서에 설명된 바와 같이 키를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="d18c1-105">관련 항목에서 고객 키에 대한 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d18c1-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="d18c1-106">Azure Key Vault 키 복원</span><span class="sxs-lookup"><span data-stu-id="d18c1-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="d18c1-107">복원을 수행하기 전에 소프트 삭제에서 제공하는 복구 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="d18c1-108">고객 키와 함께 사용되는 모든 키는 소프트 삭제를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="d18c1-109">소프트 삭제는 재활용란처럼 사용하며 복원할 필요 없이 최대 90일 동안 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="d18c1-110">복원은 키 또는 키 자격 증명 모음이 손실되는 경우와 같은 극단적인 상황이나 비정상적인 상황에서만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="d18c1-111">고객 키와 함께 사용할 키를 복원해야 하는 경우 Azure PowerShell에서 다음과 Restore-AzureKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="d18c1-112">예시:</span><span class="sxs-lookup"><span data-stu-id="d18c1-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="d18c1-113">키 자격 증명 모음에 이름이 같은 키가 이미 포함되어 있는 경우 복원 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="d18c1-114">Restore-AzKeyVaultKey 이름을 포함하여 키의 모든 키 버전 및 모든 메타데이터를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="d18c1-115">주요 자격 증명 모음 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="d18c1-115">Manage key vault permissions</span></span>

<span data-ttu-id="d18c1-116">필요한 경우 키 자격 증명 모음 권한을 제거할 수 있는 몇 가지 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="d18c1-117">예를 들어 직원이 팀을 떠날 때 사용 권한을 제거해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="d18c1-118">이러한 각 작업에 대해 Azure PowerShell을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="d18c1-119">Azure Powershell에 대한 자세한 내용은 [Azure PowerShell 개요를 참조하세요.](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="d18c1-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="d18c1-120">키 자격 증명 모음 사용 권한을 보시다가 자격 증명 Get-AzKeyVault 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="d18c1-121">예시:</span><span class="sxs-lookup"><span data-stu-id="d18c1-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="d18c1-122">관리자의 사용 권한을 제거하려면 다음 Remove-AzKeyVaultAccessPolicy 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="d18c1-123">예시:</span><span class="sxs-lookup"><span data-stu-id="d18c1-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="d18c1-124">고객 키를 사용하여 DEP(데이터 암호화 정책) 관리</span><span class="sxs-lookup"><span data-stu-id="d18c1-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="d18c1-125">고객 키는 서비스마다 다르게 DEP를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="d18c1-126">예를 들어 각 서비스에 대해 다른 수의 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="d18c1-127">**Exchange Online 및 비즈니스용 Skype:** 최대 50개 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="d18c1-128">자세한 내용은 Exchange Online 및 비즈니스용 Skype에서 사용할 DEP(데이터 암호화 정책 [만들기)를 참조하세요.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="d18c1-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="d18c1-129">**SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일:** DEP는 지리적 위치(지리적 위치)의 데이터에 _적용됩니다._</span><span class="sxs-lookup"><span data-stu-id="d18c1-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="d18c1-130">Office 365의 Multi-Geo 기능을 사용하는 경우 지역당 하나의 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="d18c1-131">Multi-Geo를 사용하지 않는 경우 DEP를 하나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="d18c1-132">일반적으로 고객 키를 설정할 때 DEP를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="d18c1-133">자세한 내용은 각 SharePoint Online 및 비즈니스용 [OneDrive 지리적으로 DEP(데이터](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)암호화 정책) 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d18c1-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d18c1-134">Exchange Online 및 비즈니스용 Skype에 대해 만든 DEP 보기</span><span class="sxs-lookup"><span data-stu-id="d18c1-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d18c1-135">Get-DataEncryptionPolicy PowerShell cmdlet을 사용하여 Exchange Online 및 비즈니스용 Skype에 대해 만든 모든 DEP 목록을 보시고 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="d18c1-136">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d18c1-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d18c1-137">조직의 모든 DEP를 반환하기 위해 매개 변수 없이 Get-DataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="d18c1-138">cmdlet에 대한 Get-DataEncryptionPolicy [Get-DataEncryptionPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="d18c1-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="d18c1-139">클라우드로 사서함을 마이그레이션하기 전에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="d18c1-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="d18c1-140">DEP를 할당하면 Microsoft 365는 마이그레이션 중에 할당된 DEP를 사용하여 사서함의 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="d18c1-141">이 프로세스는 사서함을 마이그레이션하고 DEP를 할당한 다음 암호화가 진행될 때까지 기다리는 것보다 더 효율적이며, 이 작업에는 몇 시간 또는 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="d18c1-142">OFFICE 365로 마이그레이션하기 전에 사서함에 DEP를 할당하려면 Exchange Online PowerShell에서 Set-MailUser cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="d18c1-143">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d18c1-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d18c1-144">cmdlet을 Set-MailUser 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="d18c1-145">여기서 *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 *DataEncryptionPolicyIdParameter는* DEP의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="d18c1-146">이 cmdlet에 대한 Set-MailUser [Set-MailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="d18c1-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="d18c1-147">사서함에 할당된 DEP 확인</span><span class="sxs-lookup"><span data-stu-id="d18c1-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="d18c1-148">사서함에 할당된 DEP를 확인하기 위해 Get-MailboxStatistics cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="d18c1-149">이 cmdlet은 GUID(고유 식별자)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="d18c1-150">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d18c1-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="d18c1-151">*GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 DataEncryptionPolicyID는 DEP의 GUID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="d18c1-152">이 cmdlet에 대한 Get-MailboxStatistics [Get-MailboxStatistics를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="d18c1-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="d18c1-153">Get-DataEncryptionPolicy cmdlet을 실행하여 사서함이 할당된 DEP의 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="d18c1-154">여기서 *GUID는* 이전 단계에서 Get-MailboxStatistics cmdlet에서 반환된 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="d18c1-155">고객 키가 암호화를 완료한지 확인</span><span class="sxs-lookup"><span data-stu-id="d18c1-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="d18c1-156">고객 키를 롤링하거나 새 DEP를 할당하거나 사서함을 마이그레이션한 경우 이 섹션의 단계를 사용하여 암호화가 완료되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d18c1-157">Exchange Online 및 비즈니스용 Skype에 대한 암호화 완료 확인</span><span class="sxs-lookup"><span data-stu-id="d18c1-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d18c1-158">사서함 암호화에는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="d18c1-159">DEP를 변경하거나 사서함에 DEP를 처음 할당할 때 암호화 유효성을 검사하기 전에 72시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="d18c1-160">이 Get-MailboxStatistics cmdlet을 사용하여 사서함이 암호화되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="d18c1-161">사서함이 암호화된 경우 IsEncrypted 속성은 **true** 값을 반환하고 사서함이 암호화되지 않은 경우 **false** 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="d18c1-162">사서함 이동을 완료하는 데 시간은 사서함의 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="d18c1-163">새 DEP를 할당한 후 72시간이 지난 후에 고객 키가 사서함을 완전히 암호화하지 않은 경우 Microsoft 지원에 도움을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="d18c1-164">로컬 New-MoveRequest 더 이상 이 cmdlet을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="d18c1-165">추가 [정보는 이 공지 사항을](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d18c1-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="d18c1-166">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 암호화 완료 확인</span><span class="sxs-lookup"><span data-stu-id="d18c1-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d18c1-167">다음과 같이 Get-SPODataEncryptionPolicy cmdlet을 실행하여 암호화 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="d18c1-168">이 cmdlet의 출력에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="d18c1-169">기본 키의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-169">The URI of the primary key.</span></span>

- <span data-ttu-id="d18c1-170">보조 키의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="d18c1-171">지리적 암호화 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-171">The encryption status for the geo.</span></span> <span data-ttu-id="d18c1-172">가능한 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-172">Possible states include:</span></span>

  - <span data-ttu-id="d18c1-173">**등록이 등록되지 않은 경우:** 고객 키 암호화가 아직 적용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="d18c1-174">**등록:** 고객 키 암호화가 적용되고 파일이 암호화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="d18c1-175">지리적 키가 등록되는 경우 암호화 진행률을 모니터링할 수 있도록 지리적으로 완료된 사이트의 백분율에 대한 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="d18c1-176">**등록된:** 고객 키 암호화가 적용되고 모든 사이트의 모든 파일이 암호화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="d18c1-177">**롤링:** 키 롤이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="d18c1-178">지리적 키가 롤링되는 경우 진행 상황을 모니터링할 수 있도록 키 롤 작업을 완료한 사이트의 비율에 대한 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="d18c1-179">사서함에서 DEP의 제거</span><span class="sxs-lookup"><span data-stu-id="d18c1-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="d18c1-180">Set-mailbox PowerShell cmdlet을 사용하여 사서함에서 DEP를 제거하고 를 으로 `DataEncryptionPolicy` 설정하면 `$NULL` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="d18c1-181">이 cmdlet을 실행하면 현재 할당된 DEP의 할당을 해제하고 기본 Microsoft 관리 키와 연결된 DEP를 사용하여 사서함을 다시 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="d18c1-182">Microsoft 관리 키에 사용되는 DEP의 사용은 Unassignign을 unassignens(Microsoft 관리 키)할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="d18c1-183">Microsoft 관리 키를 사용하지 않는 경우 사서함에 다른 DEP를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="d18c1-184">PowerShell cmdlet을 사용하여 사서함에서 DEP를 Set-Mailbox 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="d18c1-185">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d18c1-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d18c1-186">cmdlet을 Set-Mailbox 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="d18c1-187">키를 해지하고 데이터 제거 경로 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="d18c1-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="d18c1-188">가용성 키를 포함하여 모든 루트 키의 해지 제어</span><span class="sxs-lookup"><span data-stu-id="d18c1-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="d18c1-189">고객 키는 규정 요구 사항의 종료 계획 측면을 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="d18c1-190">데이터를 삭제하고 서비스를 종료하기 위해 키를 해지하기로 결정한 경우 데이터 삭제 프로세스가 완료되면 서비스에서 가용성 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="d18c1-191">Microsoft 365는 데이터 제거 경로를 감사하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="d18c1-192">자세한 내용은 Service Trust Portal에서 사용할 수 있는 SSAE 18 SOC 2 [보고서를 참조하세요.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="d18c1-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="d18c1-193">또한 Microsoft는 다음 문서를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="d18c1-194">Microsoft 클라우드의 금융 기관에 대한 위험 평가 및 규정 준수 가이드</span><span class="sxs-lookup"><span data-stu-id="d18c1-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="d18c1-195">O365 종료 계획 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d18c1-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="d18c1-196">데이터 제거 경로는 서비스마다 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d18c1-197">Exchange Online 및 비즈니스용 Skype에 대한 고객 키 및 가용성 키 해지</span><span class="sxs-lookup"><span data-stu-id="d18c1-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d18c1-198">Exchange Online 및 비즈니스용 Skype에 대한 데이터 삭제 경로를 시작할 때 DEP에 대해 영구 데이터 삭제 요청을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="d18c1-199">이렇게 하면 DEP가 할당된 사서함 내에서 암호화된 데이터가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="d18c1-200">한 번의 DEP에 대해 PowerShell cmdlet을 실행할 수만 있는 경우 데이터 삭제 경로를 시작하기 전에 모든 사서함에 단일 DEP를 다시 배정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="d18c1-201">데이터 삭제 경로를 사용하여 사서함의 하위 집합을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="d18c1-202">이 프로세스는 서비스를 종료하는 고객에게만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="d18c1-203">데이터 제거 경로를 시작하고 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="d18c1-204">Azure Key Vaults에서 "O365 Exchange Online"에 대한 래핑 및 래핑 제거</span><span class="sxs-lookup"><span data-stu-id="d18c1-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="d18c1-205">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d18c1-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="d18c1-206">삭제할 사서함이 포함된 각 DEP에 대해 다음과 같이 [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="d18c1-207">명령이 실패하면 이 작업의 앞부분에서 지정한 대로 Azure Key Vault의 두 키에서 Exchange Online 사용 권한을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="d18c1-208">Set-DataEncryptionPolicy cmdlet을 사용하여 PermanentDataPurgeRequested 스위치를 설정하면 더 이상 이 DEP를 사서함에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="d18c1-209">Microsoft 지원에 문의하여 데이터 제거 eDocument를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="d18c1-210">요청 시 Microsoft는 데이터 선택을 승인하고 승인하기 위해 법적 문서를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="d18c1-211">등록하는 동안 FastTrack 제품에서 승인자로 등록한 조직의 사람이 이 문서에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="d18c1-212">일반적으로 이 임원 또는 다른 지정된 사람은 조직을 대신하여 문서에 서명할 수 있는 법적 권한이 있는 임원 또는 기타 지정된 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="d18c1-213">담당자가 법적 문서에 서명한 후 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).</span><span class="sxs-lookup"><span data-stu-id="d18c1-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="d18c1-214">Microsoft가 법적 문서를 받으면 Microsoft는 cmdlet을 실행하여 정책을 먼저 삭제하는 데이터 삭제를 트리거하고 사서함을 영구 삭제로 표시한 다음 가용성 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="d18c1-215">데이터 삭제 프로세스가 완료되면 데이터가 제거되고 Exchange Online에 액세스하지 못하며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="d18c1-216">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키 및 가용성 키 해지</span><span class="sxs-lookup"><span data-stu-id="d18c1-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d18c1-217">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 데이터 삭제 경로를 시작하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="d18c1-218">Azure Key Vault 액세스를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="d18c1-219">모든 주요 자격 증명 모음 관리자는 액세스를 해지하는 데 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="d18c1-220">SharePoint Online용 Azure Key Vault는 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="d18c1-221">주요 자격 증명 모음은 여러 SharePoint Online 테넌트 및 DEP에서 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="d18c1-222">가용성 키를 삭제하려면 Microsoft에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d18c1-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="d18c1-223">가용성 키를 삭제하기 위해 Microsoft에 문의하면 법적 문서가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="d18c1-224">등록하는 동안 FastTrack 제품에서 승인자로 등록한 조직의 사람이 이 문서에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="d18c1-225">일반적으로 이 임원 또는 다른 지정된 사람이 조직을 대신하여 문서에 서명할 수 있는 법적 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="d18c1-226">담당자가 법적 문서에 서명하면 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).</span><span class="sxs-lookup"><span data-stu-id="d18c1-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="d18c1-227">Microsoft에서 법적 문서를 받으면 cmdlet을 실행하여 테넌트 키, 사이트 키 및 문서별 모든 개별 키의 암호화 삭제를 수행하여 키 계층 구조가 끊어지는 것을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="d18c1-228">데이터 삭제 cmdlet이 완료되면 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18c1-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d18c1-229">관련 문서</span><span class="sxs-lookup"><span data-stu-id="d18c1-229">Related articles</span></span>

- [<span data-ttu-id="d18c1-230">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="d18c1-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="d18c1-231">가용성 키에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="d18c1-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="d18c1-232">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="d18c1-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="d18c1-233">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="d18c1-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="d18c1-234">고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="d18c1-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="d18c1-235">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="d18c1-235">Service Encryption</span></span>](office-365-service-encryption.md)
