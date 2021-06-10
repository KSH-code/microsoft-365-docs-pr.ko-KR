---
title: 고객 키 관리
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키를 설정한 후 AKV 키를 복원하고 사용 권한을 관리하고 데이터 암호화 정책을 만들고 할당하여 키 관리 방법을 배워야 합니다.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345061"
---
# <a name="manage-customer-key"></a><span data-ttu-id="b7599-103">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="b7599-103">Manage Customer Key</span></span>

<span data-ttu-id="b7599-104">사용자에 대해 고객 키를 설정한 Office 365 하나 이상의 DEP(데이터 암호화 정책)를 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="b7599-105">DEP를 할당한 후 이 문서에 설명된 바와 같이 키를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="b7599-106">관련 항목에서 고객 키에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="b7599-107">모든 테넌트 사용자에 대해 여러 워크로드에 사용할 DEP 만들기</span><span class="sxs-lookup"><span data-stu-id="b7599-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="b7599-108">시작하기 전에 Customer를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="b7599-109">자세한 내용은 고객 키 [설정 을 참조하세요.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="b7599-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="b7599-110">DEP를 만들하려면 설치 중에 획득한 키 자격 증명 모음 UR이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="b7599-111">자세한 내용은 [각 Azure Key Vault 키에 대한 URI 얻기를 참조하세요.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="b7599-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="b7599-112">다중 워크로드 DEP를 만들 수 있도록 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="b7599-113">로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="b7599-114">DEP를 만들 수 있는 New-M365DataAtRestEncryptionPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="b7599-115">여기서,</span><span class="sxs-lookup"><span data-stu-id="b7599-115">Where:</span></span>

   - <span data-ttu-id="b7599-116">*PolicyName은* 정책에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="b7599-117">이름에는 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-117">Names can't contain spaces.</span></span> <span data-ttu-id="b7599-118">예를 들어 Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="b7599-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="b7599-119">*KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="b7599-120">예를 들면 <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="b7599-121">*KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="b7599-122">예를 들면 <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="b7599-123">두 URIS를 콤보와 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="b7599-124">*정책 설명은* 정책에 대한 정보를 기억하는 데 도움이 되는 정책에 대한 사용자에게 친숙한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="b7599-125">설명에 공백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-125">You can include spaces in the description.</span></span> <span data-ttu-id="b7599-126">예를 들어 "테넌트의 모든 사용자에 대한 여러 워크로드에 대한 루트 정책"을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="b7599-127">예제:</span><span class="sxs-lookup"><span data-stu-id="b7599-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="b7599-128">다중 작업 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b7599-128">Assign multi-workload policy</span></span>

<span data-ttu-id="b7599-129">cmdlet을 사용하여 DEP를 Set-M365DataAtRestEncryptionPolicyAssignment.</span><span class="sxs-lookup"><span data-stu-id="b7599-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="b7599-130">정책을 할당한 Microsoft 365 DEP에 식별된 키로 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="b7599-131">여기서 *PolicyName은* 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="b7599-132">예를 들어 Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="b7599-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="b7599-133">예제:</span><span class="sxs-lookup"><span data-stu-id="b7599-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="b7599-134">사서함에 사용할 DEP Exchange Online 만들기</span><span class="sxs-lookup"><span data-stu-id="b7599-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="b7599-135">시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="b7599-136">자세한 내용은 고객 키 [설정 을 참조하세요.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="b7599-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="b7599-137">원격으로 원격으로 사용자와 연결하여 Exchange Online 단계를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7599-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="b7599-138">DEP는 Azure Key Vault에 저장된 키 집합과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="b7599-139">사서함에 DEP를 할당할 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7599-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="b7599-140">Microsoft 365 정책에 식별된 키를 사용하여 사서함을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="b7599-141">DEP를 만들하려면 설치 중에 획득한 키 자격 증명 모음 UR이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="b7599-142">자세한 내용은 [각 Azure Key Vault 키에 대한 URI 얻기를 참조하세요.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="b7599-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="b7599-143">기억하세요!</span><span class="sxs-lookup"><span data-stu-id="b7599-143">Remember!</span></span> <span data-ttu-id="b7599-144">DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="b7599-145">두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="b7599-146">사서함에 사용할 DEP를 만들 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="b7599-147">로컬 컴퓨터에서 전역 관리자 또는 조직에서 전역 관리자 또는 Exchange Online 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerSh Windows PowerShell ell에](/powershell/exchange/connect-to-exchange-online-powershell) 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="b7599-148">DEP를 만들 New-DataEncryptionPolicy 명령을 입력하여 New-DataEncryptionPolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="b7599-149">여기서,</span><span class="sxs-lookup"><span data-stu-id="b7599-149">Where:</span></span>

   - <span data-ttu-id="b7599-150">*PolicyName은* 정책에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="b7599-151">이름에는 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-151">Names can't contain spaces.</span></span> <span data-ttu-id="b7599-152">예를 들어 USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="b7599-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="b7599-153">*정책 설명은* 정책에 대한 정보를 기억하는 데 도움이 되는 정책에 대한 사용자에게 친숙한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="b7599-154">설명에 공백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-154">You can include spaces in the description.</span></span> <span data-ttu-id="b7599-155">예를 들어 "미국 사서함과 해당 지역의 루트 키"를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="b7599-156">*KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="b7599-157">예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="b7599-158">*KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="b7599-159">예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="b7599-160">두 URIS를 콤보와 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="b7599-161">예제:</span><span class="sxs-lookup"><span data-stu-id="b7599-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="b7599-162">구문과 매개 변수에 대한 자세한 내용은 [New-DataEncryptionPolicy를 참조하십시오.](/powershell/module/exchange/new-data-encryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="b7599-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="b7599-163">사서함에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="b7599-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="b7599-164">사용자 지정 cmdlet을 사용하여 사서함에 DEP를 Set-Mailbox 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="b7599-165">정책을 할당하면 Microsoft 365 DEP에 식별된 키로 사서함을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="b7599-166">여기서 *MailboxIdParameter는* 사용자 사서함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="b7599-167">cmdlet에 대한 Set-Mailbox 자세한 내용은 [Set-Mailbox를 참조하십시오.](/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="b7599-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="b7599-168">하이브리드 환경에서는 시스템 테넌트에 동기화되는 사내 사서함 데이터에 DEP를 할당할 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="b7599-169">이 동기화된 사서함 데이터에 DEP를 할당하기 위해 이 cmdlet을 Set-MailUser 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="b7599-170">하이브리드 환경의 사서함 데이터에 대한 자세한 내용은 하이브리드 최신 인증을 사용하는 iOS 및 android용 Outlook 사용하는 [Outlook 사서함을 참조하세요.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="b7599-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="b7599-171">여기서 *MailUserIdParameter는* 메일 사용자(메일 사용이 가능한 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="b7599-172">cmdlet에 대한 Set-MailUser 자세한 내용은 [Set-MailUser 를 참조하십시오.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="b7599-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="b7599-173">SharePoint Online, 비즈니스용 OneDrive 및 Teams DEP 만들기</span><span class="sxs-lookup"><span data-stu-id="b7599-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="b7599-174">시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="b7599-175">자세한 내용은 고객 키 [설정 을 참조하세요.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="b7599-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="b7599-176">SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키를 설정하려면 SharePoint Online에 원격으로 연결하여 이러한 단계를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7599-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="b7599-177">DEP를 Azure Key Vault에 저장된 키 집합과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="b7599-178">지역이라고도 하는 한 지리적 위치에 있는 모든 데이터에 DEP를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="b7599-179">Office 365 Multi-Geo 기능을 사용하는 경우 지역마다 다른 키를 사용할 수 있는 기능을 사용하여 지역당 DEP를 하나씩 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="b7599-180">Multi-Geo를 사용하지 않는 경우 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 Teams 사용할 DEP를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="b7599-181">Microsoft 365 DEP에 식별된 키를 사용하여 그 지리적으로 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="b7599-182">DEP를 만들하려면 설치 중에 획득한 키 자격 증명 모음 UR이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="b7599-183">자세한 내용은 [각 Azure Key Vault 키에 대한 URI 얻기를 참조하세요.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="b7599-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="b7599-184">기억하세요!</span><span class="sxs-lookup"><span data-stu-id="b7599-184">Remember!</span></span> <span data-ttu-id="b7599-185">DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="b7599-186">두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b7599-187">DEP를 만들 수 있도록 원격으로 SharePoint Online에 연결해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7599-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="b7599-188">로컬 컴퓨터에서 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 커넥트 [PowerShell을](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="b7599-189">Microsoft Office SharePoint Online 관리 셸에서 다음과 Register-SPODataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="b7599-190">예제:</span><span class="sxs-lookup"><span data-stu-id="b7599-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="b7599-191">DEP를 등록하면 지리적 데이터에 대한 암호화가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="b7599-192">암호화에는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-192">Encryption can take some time.</span></span> <span data-ttu-id="b7599-193">이 매개 변수를 사용하는 데 대한 자세한 내용은 [Register-SPODataEncryptionPolicy를 참조하세요.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="b7599-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="b7599-194">사서함에 대해 만든 DEP Exchange Online 보기</span><span class="sxs-lookup"><span data-stu-id="b7599-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="b7599-195">사서함에 대해 만든 모든 DEP의 목록을 보기 위해 powerShell cmdlet을 Get-DataEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="b7599-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="b7599-196">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b7599-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b7599-197">조직의 모든 DEP를 반환하기 위해 매개 변수 없이 Get-DataEncryptionPolicy cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="b7599-198">cmdlet에 대한 자세한 Get-DataEncryptionPolicy [Get-DataEncryptionPolicy를 참조하세요.](/powershell/module/exchange/get-dataencryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="b7599-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="b7599-199">클라우드로 사서함을 마이그레이션하기 전에 DEP 할당</span><span class="sxs-lookup"><span data-stu-id="b7599-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="b7599-200">DEP를 할당할 때 Microsoft 365 할당된 DEP를 사용하여 사서함의 내용을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="b7599-201">이 프로세스는 사서함을 마이그레이션하고 DEP를 할당한 다음 암호화가 진행될 때까지 기다리는 것보다 더 효율적이며, 이 작업에는 몇 시간 또는 며칠이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="b7599-202">사서함으로 마이그레이션하기 전에 사서함에 DEP를 할당하려면 Office 365 PowerShell에서 Set-MailUser cmdlet을 Exchange Online 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="b7599-203">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b7599-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b7599-204">cmdlet을 Set-MailUser 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="b7599-205">여기서 *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 *DataEncryptionPolicyIdParameter는* DEP의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="b7599-206">cmdlet에 대한 Set-MailUser 자세한 내용은 [Set-MailUser 를 참조하십시오.](/powershell/module/exchange/set-mailuser)</span><span class="sxs-lookup"><span data-stu-id="b7599-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="b7599-207">사서함에 할당된 DEP 확인</span><span class="sxs-lookup"><span data-stu-id="b7599-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="b7599-208">사서함에 할당된 DEP를 확인하기 위해 Get-MailboxStatistics cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="b7599-209">이 cmdlet은 GUID(고유 식별자)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="b7599-210">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b7599-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="b7599-211">여기서 *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 DataEncryptionPolicyID는 DEP의 GUID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="b7599-212">이 cmdlet에 대한 자세한 Get-MailboxStatistics [Get-MailboxStatistics 를 참조하세요.](/powershell/module/exchange/get-mailboxstatistics)</span><span class="sxs-lookup"><span data-stu-id="b7599-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="b7599-213">Get-DataEncryptionPolicy cmdlet을 실행하여 사서함이 할당된 DEP의 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="b7599-214">여기서 *GUID는* 이전 단계에서 Get-MailboxStatistics cmdlet에서 반환된 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="b7599-215">고객 키의 암호화가 완료되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b7599-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="b7599-216">고객 키를 롤링하거나 새 DEP를 할당하거나 사서함을 마이그레이션한 경우 이 섹션의 단계를 사용하여 암호화가 완료되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="b7599-217">사서함의 암호화가 Exchange Online 확인</span><span class="sxs-lookup"><span data-stu-id="b7599-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="b7599-218">사서함 암호화에는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="b7599-219">또한 서비스가 사서함을 암호화하려면 먼저 사서함을 데이터베이스에서 다른 데이터베이스로 완전히 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="b7599-220">Get-MailboxStatistics cmdlet을 사용하여 사서함이 암호화되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="b7599-221">IsEncrypted 속성은 사서함이 암호화된 경우 **true** 값을 반환하고 사서함이 암호화되지 않은 경우 **false** 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="b7599-222">사서함 이동을 완료하는 시간은 처음으로 DEP를 할당하는 사서함 수와 사서함의 크기에 따라 달라 니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="b7599-223">DEP를 할당한 후 1주일 후에도 사서함이 암호화되지 않은 경우 Microsoft에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="b7599-224">로컬 New-MoveRequest 사서함 이동에는 더 이상 이 cmdlet을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="b7599-225">추가 [정보는 이 공지 사항을](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7599-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="b7599-226">SharePoint Online, 비즈니스용 OneDrive 및 Teams 암호화 완료 확인</span><span class="sxs-lookup"><span data-stu-id="b7599-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="b7599-227">다음과 같이 cmdlet을 실행하여 Get-SPODataEncryptionPolicy 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="b7599-228">이 cmdlet의 출력에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="b7599-229">기본 키의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-229">The URI of the primary key.</span></span>

- <span data-ttu-id="b7599-230">보조 키의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="b7599-231">지리적 암호화 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-231">The encryption status for the geo.</span></span> <span data-ttu-id="b7599-232">가능한 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-232">Possible states include:</span></span>

  - <span data-ttu-id="b7599-233">**등록이 등록되지 않은 경우:** 고객 키 암호화가 아직 적용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="b7599-234">**등록:** 고객 키 암호화가 적용되고 파일이 암호화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="b7599-235">지역 키가 등록되는 경우 암호화 진행률을 모니터링할 수 있도록 지리적 사이트의 완료율에 대한 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="b7599-236">**등록:** 고객 키 암호화가 적용되고 모든 사이트의 모든 파일이 암호화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="b7599-237">**롤링:** 키 롤이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="b7599-238">지역 키가 롤링되는 경우 진행 상황을 모니터링할 수 있도록 키 롤 작업을 완료한 사이트의 비율에 대한 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="b7599-239">여러 워크로드에서 사용하는 DEP에 대한 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="b7599-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="b7599-240">여러 워크로드에서 사용하기 위해 만든 모든 DEP에 대한 세부 정보를 얻습니다. 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="b7599-241">로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="b7599-242">조직의 모든 다중 작업 DEP 목록을 반환하기 위해 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="b7599-243">특정 DEP에 대한 세부 정보를 반환하기 위해 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="b7599-244">이 예에서는 "Contoso_Global"라는 DEP에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="b7599-245">다중 작업 DEP 할당 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="b7599-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="b7599-246">테넌트에 현재 할당된 DEP를 확인하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="b7599-247">로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="b7599-248">이 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="b7599-249">다중 작업 DEP를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b7599-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="b7599-250">다중 작업 DEP를 사용하지 않도록 설정하기 전에 테넌트의 워크로드에서 DEP를 배정 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="b7599-251">여러 워크로드에 사용되는 DEP를 사용하지 않도록 설정하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="b7599-252">로컬 컴퓨터에서 조직의 전역 관리자 또는 규정 준수 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange Online 창에서 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="b7599-253">cmdlet을 Set-M365DataAtRestEncryptionPolicy 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="b7599-254">여기서 *PolicyName은* 정책의 이름 또는 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="b7599-255">예를 들어 Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="b7599-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="b7599-256">예제:</span><span class="sxs-lookup"><span data-stu-id="b7599-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="b7599-257">Azure Key Vault 키 복원</span><span class="sxs-lookup"><span data-stu-id="b7599-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="b7599-258">복원을 수행하기 전에 소프트 삭제에서 제공하는 복구 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="b7599-259">고객 키와 함께 사용되는 모든 키는 소프트 삭제를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="b7599-260">소프트 삭제는 재활용 쓰레기 수거란처럼 사용하며 복원할 필요 없이 최대 90일 동안 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="b7599-261">복원은 키 또는 키 자격 증명 모음이 분실된 경우와 같은 극단적인 상황이나 비정상적인 상황에서만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="b7599-262">고객 키와 함께 사용할 키를 복원해야 하는 경우 Azure PowerShell cmdlet을 Restore-AzureKeyVaultKey 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="b7599-263">예:</span><span class="sxs-lookup"><span data-stu-id="b7599-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="b7599-264">키 자격 증명 모음에 이름이 같은 키가 이미 포함되어 있는 경우 복원 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="b7599-265">Restore-AzKeyVaultKey 키 이름을 포함하여 키의 모든 메타데이터 및 키 버전을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="b7599-266">주요 자격 증명 모음 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="b7599-266">Manage key vault permissions</span></span>

<span data-ttu-id="b7599-267">필요한 경우 주요 자격 증명 모음 권한을 보고 제거할 수 있는 여러 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="b7599-268">예를 들어 직원이 팀을 떠날 때 사용 권한을 제거해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="b7599-269">이러한 각 작업에 대해 이러한 작업을 Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7599-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="b7599-270">자세한 내용은 Azure PowerShell [개요를 Azure PowerShell.](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="b7599-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="b7599-271">키 자격 증명 모음 사용 권한을 보기 위해 Get-AzKeyVault 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="b7599-272">예:</span><span class="sxs-lookup"><span data-stu-id="b7599-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="b7599-273">관리자의 사용 권한을 제거하려면 다음 Remove-AzKeyVaultAccessPolicy 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="b7599-274">예:</span><span class="sxs-lookup"><span data-stu-id="b7599-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="b7599-275">고객 키에서 Microsoft 관리 키로 롤백</span><span class="sxs-lookup"><span data-stu-id="b7599-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="b7599-276">Microsoft 관리 키로 되전해야 하는 경우 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="b7599-277">오프보드를 해제하면 각 개별 워크로드에서 지원하는 기본 암호화를 사용하여 데이터가 다시 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="b7599-278">예를 들어 microsoft Exchange Online 키를 사용하여 기본 암호화를 지원하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7599-279">오프보더는 데이터 제거와는 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="b7599-280">데이터 삭제는 조직의 데이터를 영구적으로 암호화로 삭제하고 Microsoft 365, 오프보더는 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="b7599-281">여러 작업 정책에 대해 데이터 제거를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="b7599-282">다중 작업 DEP를 할당하는 데 고객 키를 사용하지 않을 경우 고객 키에서 "오프보드"를 요청하여 Microsoft 지원에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="b7599-283">지원 팀에 고객 키 팀에 대한 서비스 Microsoft 365 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="b7599-284">질문이 m365-ck@service.microsoft.com 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="b7599-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="b7599-285">더 이상 사서함 수준 DEP를 사용하여 개별 사서함을 암호화하지 않을 경우 모든 사서함에서 사서함 수준 DEP를 제거하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="b7599-286">사서함 DEP의 배정을 Set-Mailbox PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="b7599-287">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [PowerShell 에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b7599-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b7599-288">cmdlet을 Set-Mailbox 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="b7599-289">이 cmdlet을 실행하면 현재 할당된 DEP 할당을 해제하고 기본 Microsoft 관리 키와 연결된 DEP를 사용하여 사서함을 다시 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="b7599-290">Microsoft 관리 키에 사용되는 DEP의 배포를 unassign the unassign the로 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="b7599-291">Microsoft 관리 키를 사용하지 않는 경우 사서함에 다른 고객 키 DEP를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="b7599-292">키를 해지하고 데이터 제거 경로 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="b7599-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="b7599-293">가용성 키를 포함하여 모든 루트 키의 해지 제어</span><span class="sxs-lookup"><span data-stu-id="b7599-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="b7599-294">고객 키는 규정 요구 사항의 종료 계획 측면을 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="b7599-295">데이터를 삭제하고 서비스를 종료하기 위해 키를 해지하기로 결정한 경우 데이터 삭제 프로세스가 완료되면 서비스에서 가용성 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="b7599-296">개별 사서함에 할당된 고객 키 DEP에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="b7599-297">Microsoft 365 제거 경로를 감사하고 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="b7599-298">자세한 내용은 Service Trust Portal에서 사용할 수 있는 SSAE 18 SOC 2 [보고서를 참조하세요.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="b7599-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="b7599-299">또한 다음 문서가 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="b7599-300">Microsoft 클라우드의 금융 기관을 위한 위험 평가 및 규정 준수 가이드</span><span class="sxs-lookup"><span data-stu-id="b7599-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="b7599-301">O365 종료 계획 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b7599-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="b7599-302">다중 작업 DEP 제거는 고객 키에 Microsoft 365 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="b7599-303">다중 워크로드 DEP는 모든 테넌트 사용자 전체의 여러 워크로드에서 데이터를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="b7599-304">이러한 DEP를 제거하면 여러 워크로드에서 데이터에 액세스하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="b7599-305">서비스 Microsoft 365 종료하기로 결정한 경우 문서화된 프로세스에 따라 테넌트가 종료되는 경로를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="b7599-306">[Azure Active Directoy에서](/azure/active-directory/enterprise-users/directory-delete-howto)테넌트 삭제 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7599-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b7599-307">고객 키 및 사용자에 대한 가용성 키 Exchange Online 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="b7599-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="b7599-308">사용자 및 사용자 Exchange Online 비즈니스용 Skype 삭제 경로를 시작하면 DEP에 대해 영구 데이터 삭제 요청을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="b7599-309">이렇게 하면 DEP가 할당된 사서함 내에서 암호화된 데이터가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="b7599-310">한 번의 DEP에 대해 PowerShell cmdlet만 실행할 수 있도록 데이터 삭제 경로를 시작하기 전에 모든 사서함에 단일 DEP를 다시 배정하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="b7599-311">데이터 삭제 경로를 사용하여 사서함의 하위 집합을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="b7599-312">이 프로세스는 서비스를 종료하는 고객만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="b7599-313">데이터 제거 경로를 시작하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="b7599-314">Azure Key Vaults에서 "O365 Exchange Online"에 대한 래핑 및 래핑을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="b7599-315">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 PowerShell 에 [Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b7599-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="b7599-316">삭제할 사서함이 포함된 각 DEP에 대해 다음과 같이 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="b7599-317">명령이 실패하는 경우 이 작업의 앞부분에서 지정한 대로 Azure Exchange Online 두 키에서 모든 키의 사용 권한을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="b7599-318">Set-DataEncryptionPolicy cmdlet을 사용하여 PermanentDataPurgeRequested 스위치를 설정하면 더 이상 사서함에 이 DEP를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="b7599-319">Microsoft 지원에 문의하여 데이터 제거 eDocument를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="b7599-320">요청 시 Microsoft는 데이터 선택을 승인하고 승인하기 위해 법적 문서를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="b7599-321">등록하는 동안 FastTrack 제품에서 승인자로 등록한 조직의 사람이 이 문서에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="b7599-322">일반적으로 조직을 대신하여 문서에 서명할 수 있는 법적 권한이 있는 임원 또는 기타 지정된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="b7599-323">담당자가 법적 문서에 서명한 후 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).</span><span class="sxs-lookup"><span data-stu-id="b7599-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="b7599-324">Microsoft가 법적 문서를 받으면 Microsoft는 cmdlet을 실행하여 정책을 처음 삭제하는 데이터 삭제를 트리거하고 사서함에 영구 삭제를 표시한 다음 가용성 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="b7599-325">데이터 삭제 프로세스가 완료되면 데이터가 제거되고, 삭제된 데이터에 Exchange Online 수 있으며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="b7599-326">SharePoint Online, 비즈니스용 OneDrive 및 Teams 키 해지</span><span class="sxs-lookup"><span data-stu-id="b7599-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="b7599-327">SharePoint Online, 비즈니스용 OneDrive 및 Teams 삭제 경로를 시작하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="b7599-328">Azure Key Vault 액세스를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="b7599-329">모든 주요 자격 증명 모음 관리자는 액세스를 해지하는 데 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="b7599-330">온라인용 Azure Key Vault는 SharePoint 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="b7599-331">주요 자격 증명 모음은 여러 온라인 테넌트 및 SHAREPOINT 공유될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="b7599-332">Microsoft에 문의하여 가용성 키를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="b7599-333">Microsoft에 연락하여 가용성 키를 삭제하면 법적 문서가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="b7599-334">등록하는 동안 FastTrack 제품에서 승인자로 등록한 조직의 사람이 이 문서에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="b7599-335">일반적으로 조직을 대신하여 문서에 서명할 수 있는 법적 권한이 있는 임원 또는 기타 지정된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="b7599-336">담당자가 법적 문서에 서명하면 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).</span><span class="sxs-lookup"><span data-stu-id="b7599-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="b7599-337">Microsoft에서 법적 문서를 받으면 cmdlet을 실행하여 테넌트 키, 사이트 키 및 모든 문서별 개별 키의 암호화 삭제를 수행하여 키 계층 구조가 취소되는 데이터 삭제를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="b7599-338">데이터 삭제 cmdlet이 완료되면 데이터가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7599-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b7599-339">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b7599-339">Related articles</span></span>

- [<span data-ttu-id="b7599-340">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="b7599-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="b7599-341">가용성 키에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="b7599-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="b7599-342">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="b7599-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="b7599-343">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="b7599-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="b7599-344">고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="b7599-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="b7599-345">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="b7599-345">Service Encryption</span></span>](office-365-service-encryption.md)