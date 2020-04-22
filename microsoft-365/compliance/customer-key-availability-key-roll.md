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
description: 고객 키와 함께 사용 되는 Azure 키 자격 증명 모음에 저장 된 고객 루트 키를 롤 만드는 방법을 알아봅니다. 서비스에는 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀 파일이 포함 됩니다.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633645"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="4796f-104">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="4796f-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="4796f-105">보안 또는 규정 준수 요구 사항에 따라 키를 롤백해야 하는 경우에만 고객 키와 함께 사용 하는 암호화 키를 롤백해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="4796f-106">또한 정책과 연결 된 키를 삭제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4796f-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="4796f-107">키를 롤포워드할 때 이전 키로 암호화 된 콘텐츠가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="4796f-108">예를 들어 활성 사서함은 자주 다시 암호화 되 고 비활성, 연결 해제 및 사용 하지 않도록 설정 된 사서함은 여전히 이전 키를 사용 하 여 암호화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="4796f-109">SharePoint Online은 복원 및 복구를 위해 콘텐츠 백업을 수행 하므로 이전 키를 사용 하 여 계속 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="4796f-110">가용성 키 롤링 정보</span><span class="sxs-lookup"><span data-stu-id="4796f-110">About rolling the availability key</span></span>

<span data-ttu-id="4796f-111">Microsoft는 가용성 키에 대 한 직접 제어를 고객에 게 공개 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="4796f-112">예를 들어 Azure Key Vault에서 소유한 키만 롤 (회전) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="4796f-113">Microsoft 365는 내부적으로 정의 된 일정에 따라 가용성 키를 롤업 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="4796f-114">이러한 키 롤에는 고객 측 SLA (서비스 수준 계약)가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="4796f-115">Microsoft 365에서는 수동 자동 지원 프로세스에서 Microsoft 365 서비스 코드를 사용 하 여 가용성 키를 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="4796f-116">Microsoft 관리자가 롤 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="4796f-117">키가 키 저장소에 직접 액세스 하지 않고 자동화 된 메커니즘을 사용 하 여 롤오버 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="4796f-118">가용성 키 보안 저장소에 대 한 액세스는 Microsoft 관리자에 게 프로 비전 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="4796f-119">가용성 키 롤링은 처음에 키를 생성 하는 데 사용 되는 것과 동일한 메커니즘을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="4796f-120">가용성 키에 대 한 자세한 내용은 [가용성 키 이해](customer-key-availability-key-understand.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4796f-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4796f-121">Exchange Online 및 비즈니스용 Skype 가용성 키는 만드는 각 DEP에 대해 고유한 가용성 키가 생성 되므로 새 DEP를 만드는 고객이 효과적으로 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="4796f-122">SharePoint Online에 대 한 가용성 키, 비즈니스용 OneDrive 및 팀 파일은 포리스트 수준에 있고, DEPs 및 고객 간에 공유 되므로 Microsoft 내부적으로 정의 된 일정 으로만 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="4796f-123">새 DEP를 만들 때마다 가용성 키를 롤링 하지 않을 위험을 완화 하기 위해 SharePoint, OneDrive 및 팀은 새 DEP를 만들 때마다 고객 루트 키 및 가용성 키로 래핑된 키를 사용 하 여 테 넌 트 중개 키 (TIK)를 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="4796f-124">롤백할 각 기존 루트 키의 새 버전을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="4796f-125">키를 롤 포워드 하면 기존 키의 새 버전을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="4796f-126">기존 키의 새 버전을 요청 하려면 첫 번째 위치에서 키를 만드는 데 사용한 구문과 동일한 cmdlet, [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="4796f-127">DEP (데이터 암호화 정책)와 연결 된 키를 모두 사용한 후에는 다른 cmdlet을 실행 하 여 고객 키가 새 키를 사용 하 여 시작 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="4796f-128">각 Azure Key Vault (AKV)에서이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="4796f-129">예시:</span><span class="sxs-lookup"><span data-stu-id="4796f-129">For example:</span></span>

1. <span data-ttu-id="4796f-130">Azure PowerShell을 사용 하 여 Azure 구독에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="4796f-131">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](https://docs.microsoft.com/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4796f-131">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4796f-132">다음 예제와 같이 AzKeyVaultKey cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="4796f-133">이 예에서 contoso- **O365EX-VaultA1-Key001** 이 **contoso-O365EX-VaultA1** vault에 존재 하기 때문에 cmdlet은 키의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-133">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** exists in the **Contoso-O365EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="4796f-134">이 작업에서는 키에 대 한 버전 기록의 이전 키 버전을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="4796f-135">여전히 암호화 되는 데이터를 해독 하려면 이전 키 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="4796f-136">DEP와 연결 된 키를 모두 입력 한 후에는 추가 cmdlet을 실행 하 여 고객 키가 새 키를 사용 하 여 시작 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="4796f-137">다음 섹션에서는이 cmdlet에 대해 더 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="4796f-138">Exchange Online 및 비즈니스용 Skype에 대 한 고객 키 업데이트</span><span class="sxs-lookup"><span data-stu-id="4796f-138">Update the Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="4796f-139">Exchange Online 및 비즈니스용 Skype와 함께 사용 되는 DEP와 연결 된 Azure 키 자격 증명 키 중 하나를 롤 포워드 하려면 새 키를 가리키도록 DEP를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-139">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="4796f-140">이 경우 가용성 키가 회전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-140">This does not rotate the availability key.</span></span>

<span data-ttu-id="4796f-141">새 키를 사용 하 여 사서함을 암호화 하도록 고객 키에 게 지시 하려면 다음과 같이 Set-DataEncryptionPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-141">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="4796f-142">Azure PowerShell에서 Set-Data\ 정책 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-142">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   <span data-ttu-id="4796f-143">72 시간 이내에이 DEP와 연결 된 활성 사서함은 새 키를 사용 하 여 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-143">Within 72 hours, the active mailboxes associated with this DEP become encrypted with the new key.</span></span>

2. <span data-ttu-id="4796f-144">사서함에 대 한 Datamailbox Policyid 속성의 값을 확인 하려면 [사서함에 할당 된 DEP 확인](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)의 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-144">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="4796f-145">이 속성의 값은 서비스가 업데이트 된 키를 적용 한 경우 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-145">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="4796f-146">SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 고객 키 업데이트</span><span class="sxs-lookup"><span data-stu-id="4796f-146">Update the Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="4796f-147">SharePoint Online의 경우 한 번에 하나의 키를 롤업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-147">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="4796f-148">키 보관소에서 두 키를 롤 포워드 하려면 첫 번째 작업이 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-148">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="4796f-149">이 문제를 방지 하려면 작업을 엇갈리게 배치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-149">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="4796f-150">SharePoint Online 및 비즈니스용 OneDrive와 함께 사용 되는 DEP와 연결 된 Azure 키 자격 증명 키 중 하나를 롤 포워드 하려면 새 키를 가리키도록 DEP를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-150">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="4796f-151">이 경우 가용성 키가 회전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-151">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="4796f-152">다음과 같이 SPODataEncryptionPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-152">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="4796f-153">이 cmdlet은 SharePoint Online 및 비즈니스용 OneDrive에 대 한 키 롤 작업을 시작 하지만이 작업은 즉시 완료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-153">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="4796f-154">키 롤 작업의 진행률을 확인 하려면 다음과 같이 SPODataEncryptionPolicy cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4796f-154">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="4796f-155">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4796f-155">Related articles</span></span>

- [<span data-ttu-id="4796f-156">Office 365에 대 한 고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="4796f-156">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="4796f-157">Office 365의 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="4796f-157">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="4796f-158">Office 365의 고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="4796f-158">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="4796f-159">가용성 키에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4796f-159">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)
