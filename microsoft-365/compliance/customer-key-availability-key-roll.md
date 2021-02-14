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
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633645"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="6d5b2-104">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="6d5b2-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="6d5b2-105">보안 또는 규정 준수 요구 사항에 따라 키를 롤해야 하도록 규정된 경우 고객 키와 함께 사용하는 암호화 키만 롤링합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="6d5b2-106">또한 정책에 연결되거나 연결된 키는 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="6d5b2-107">키를 롤아웃하면 이전 키로 암호화된 콘텐츠가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="6d5b2-108">예를 들어 활성 사서함이 자주 다시 암호화되는 동안 비활성, 연결이 끊어진 사서함 및 비활성화된 사서함은 이전 키로 계속 암호화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="6d5b2-109">SharePoint Online은 복원 및 복구를 위해 콘텐츠 백업을 수행하여 이전 키를 사용하여 보관된 콘텐츠가 계속 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="6d5b2-110">가용성 키 롤링</span><span class="sxs-lookup"><span data-stu-id="6d5b2-110">About rolling the availability key</span></span>

<span data-ttu-id="6d5b2-111">Microsoft는 고객에게 가용성 키에 대한 직접적인 제어를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="6d5b2-112">예를 들어 Azure Key Vault에서 소유한 키만 롤(회전)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="6d5b2-113">Microsoft 365는 내부에서 정의된 일정에 따라 가용성 키를 롤링합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="6d5b2-114">이러한 키 롤에는 고객에 대한 SLA(서비스 수준 계약)가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="6d5b2-115">Microsoft 365는 수동이 아닌 자동화된 프로세스에서 Microsoft 365 서비스 코드를 사용하여 가용성 키를 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="6d5b2-116">Microsoft 관리자가 롤 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="6d5b2-117">키는 키 저장소에 직접 액세스하지 않고 자동화된 메커니즘을 사용하여 롤링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="6d5b2-118">가용성 키 비밀 저장소에 대한 액세스는 Microsoft 관리자에게 프로비전되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="6d5b2-119">가용성 키 롤링은 처음에 키를 생성하는 데 사용되는 동일한 메커니즘을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="6d5b2-120">가용성 키에 대한 자세한 내용은 가용성 키 [이해를 참조하십시오.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="6d5b2-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d5b2-121">만든 각 DEP에 대해 고유한 가용성 키가 생성되어 새 DEP를 만드는 고객이 Exchange Online 및 비즈니스용 Skype 가용성 키를 효과적으로 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="6d5b2-122">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 가용성 키는 포리스트 수준에 있으며 DEP 및 고객 전체에서 공유됩니다. 즉, 롤링은 Microsoft 내부에서 정의된 일정에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="6d5b2-123">새 DEP를 만들 때마다 SharePoint, OneDrive 및 Teams가 새 DEP를 만들 때마다 고객 루트 키 및 가용성 키로 래핑된 키인 TIK(테넌트 중간 키)를 롤아웃할 때마다 가용성 키를 롤링하지 않을 위험을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="6d5b2-124">롤아웃할 각 기존 루트 키의 새 버전 요청</span><span class="sxs-lookup"><span data-stu-id="6d5b2-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="6d5b2-125">키를 롤아웃할 때 기존 키의 새 버전을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="6d5b2-126">기존 키의 새 버전을 요청하기 위해 처음에 키를 만드는 데 사용한 구문과 동일한 cmdlet인 [Add-AzKeyVaultKey를](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="6d5b2-127">DEP(데이터 암호화 정책)와 연결된 키의 롤링을 마치면 다른 cmdlet을 실행하여 고객 키가 새 키 사용을 시작하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="6d5b2-128">각 Azure Key Vault(AKV)에서 이 단계를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="6d5b2-129">예시:</span><span class="sxs-lookup"><span data-stu-id="6d5b2-129">For example:</span></span>

1. <span data-ttu-id="6d5b2-130">Azure PowerShell을 사용하여 Azure 구독에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="6d5b2-131">자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="6d5b2-131">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="6d5b2-132">다음 Add-AzKeyVaultKey cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="6d5b2-133">이 예에서는 **Contoso-O365EX-NA-VaultA1-Key001이라는** 키가 **Contoso-O365EX-NA-VaultA1** 자격 증명 모음에 존재하기 때문에 이 cmdlet은 새 버전의 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-133">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** exists in the **Contoso-O365EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="6d5b2-134">이 작업은 키의 버전 기록에 이전 키 버전을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="6d5b2-135">암호화하는 데이터의 암호를 해독하려면 이전 키 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="6d5b2-136">DEP와 연결된 키 롤링을 완료한 후 추가 cmdlet을 실행하여 고객 키가 새 키 사용을 시작하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="6d5b2-137">다음 섹션에서는 cmdlet에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="6d5b2-138">Exchange Online 및 비즈니스용 Skype의 고객 키 업데이트</span><span class="sxs-lookup"><span data-stu-id="6d5b2-138">Update the Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="6d5b2-139">Exchange Online 및 비즈니스용 Skype와 함께 사용되는 DEP와 연결된 Azure Key Vault 키를 롤할 때 새 키를 지점으로 하여 DEP를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-139">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="6d5b2-140">이 경우 가용성 키가 회전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-140">This does not rotate the availability key.</span></span>

<span data-ttu-id="6d5b2-141">고객 키에 새 키를 사용하여 사서함을 암호화할 수 있도록 지시하기 위해 다음과 Set-DataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-141">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="6d5b2-142">Azure PowerShell에서 Set-DataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-142">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   <span data-ttu-id="6d5b2-143">72시간 이내에 이 DEP와 연결된 활성 사서함이 새 키로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-143">Within 72 hours, the active mailboxes associated with this DEP become encrypted with the new key.</span></span>

2. <span data-ttu-id="6d5b2-144">사서함의 DataEncryptionPolicyID 속성 값을 확인한 다음 사서함에 할당된 DEP 확인의 단계를 [사용하세요.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="6d5b2-144">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="6d5b2-145">서비스가 업데이트된 키를 적용하면 이 속성 값이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-145">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="6d5b2-146">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 고객 키 업데이트</span><span class="sxs-lookup"><span data-stu-id="6d5b2-146">Update the Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="6d5b2-147">SharePoint Online에서는 키를 한 번만 롤링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-147">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="6d5b2-148">키 자격 증명 모음에서 두 키를 모두 롤링하려는 경우 첫 번째 작업이 완료될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-148">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="6d5b2-149">이 문제를 방지하기 위해 작업에 시차를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-149">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="6d5b2-150">SharePoint Online 및 비즈니스용 OneDrive와 함께 사용되는 DEP와 연결된 Azure Key Vault 키를 롤링할 때 새 키를 지점으로 하여 DEP를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-150">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="6d5b2-151">이 경우 가용성 키가 회전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-151">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="6d5b2-152">다음과 Update-SPODataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-152">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="6d5b2-153">이 cmdlet은 SharePoint Online 및 비즈니스용 OneDrive에 대한 키 롤 작업을 시작하나 작업이 즉시 완료되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-153">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="6d5b2-154">키 롤 작업의 진행률을 표시하기 위해 다음과 Get-SPODataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5b2-154">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="6d5b2-155">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6d5b2-155">Related articles</span></span>

- [<span data-ttu-id="6d5b2-156">Office 365용 고객 키를 사용하여 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="6d5b2-156">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="6d5b2-157">Office 365의 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="6d5b2-157">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="6d5b2-158">Office 365의 고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="6d5b2-158">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="6d5b2-159">가용성 키에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="6d5b2-159">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)
