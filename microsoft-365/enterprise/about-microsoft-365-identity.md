---
title: Microsoft 365 ID 모델 및 Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 클라우드 전용 또는 하이브리드 ID 모델을 사용하여 Microsoft 365에서 Azure AD 사용자 ID 서비스를 관리하는 방법을 설명합니다.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327954"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="c06b2-103">Microsoft 365 ID 모델 및 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c06b2-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="c06b2-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c06b2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c06b2-105">Microsoft 365는 Microsoft 365 구독에 포함된 클라우드 기반 사용자 ID 및 인증 서비스인 Azure AD(Azure Active Directory)를 사용하여 Microsoft 365에 대한 ID 및 인증을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="c06b2-106">조직에 대한 Microsoft 365 사용자 액세스 및 사용 권한을 관리하려면 ID 인프라를 올바르게 구성하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="c06b2-107">시작하기 전에 Microsoft 365에 대한 인증과 ID 모델의 개요에 대한 비디오를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="c06b2-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="c06b2-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="c06b2-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="c06b2-109">첫 번째 계획 선택은 Microsoft 365 ID 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="c06b2-110">Microsoft 365 ID 모델</span><span class="sxs-lookup"><span data-stu-id="c06b2-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="c06b2-111">사용자 계정을 계획하려면 먼저 Microsoft 365의 두 ID 모델을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="c06b2-112">조직의 ID는 클라우드에서만 유지 관리하거나, 사용자가 Microsoft 365 클라우드 서비스에 액세스할 때 인증에 사용할 수 있도록 AD DS(Active Directory 도메인 서비스) ID를 유지 관리하고 인증에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="c06b2-113">다음은 두 가지 유형의 ID와 가장 적합한 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="c06b2-114">특성</span><span class="sxs-lookup"><span data-stu-id="c06b2-114">Attribute</span></span> | <span data-ttu-id="c06b2-115">클라우드 전용 ID</span><span class="sxs-lookup"><span data-stu-id="c06b2-115">Cloud-only identity</span></span> | <span data-ttu-id="c06b2-116">하이브리드 ID</span><span class="sxs-lookup"><span data-stu-id="c06b2-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="c06b2-117">**정의**</span><span class="sxs-lookup"><span data-stu-id="c06b2-117">**Definition**</span></span> | <span data-ttu-id="c06b2-118">사용자 계정은 Microsoft 365 구독에 대한 Azure AD 테넌트에만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="c06b2-119">사용자 계정이 AD DS에 있으며 복사본은 Microsoft 365 구독에 대한 Azure AD 테넌트에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="c06b2-120">Azure AD의 사용자 계정에 해시된 해시된 AD DS 사용자 계정 암호도 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="c06b2-121">**Microsoft 365에서 사용자 자격 증명을 인증하는 방법**</span><span class="sxs-lookup"><span data-stu-id="c06b2-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="c06b2-122">Microsoft 365 구독에 대한 Azure AD 테넌트는 클라우드 ID 계정으로 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="c06b2-123">Microsoft 365 구독에 대한 Azure AD 테넌트는 인증 프로세스를 처리하거나 사용자를 다른 ID 공급자로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="c06b2-124">**최적 시나리오**</span><span class="sxs-lookup"><span data-stu-id="c06b2-124">**Best for**</span></span> | <span data-ttu-id="c06b2-125">조직에 대한 AD DS가 없는 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="c06b2-126">AD DS 또는 다른 ID 공급자를 사용하는 조직</span><span class="sxs-lookup"><span data-stu-id="c06b2-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="c06b2-127">**가장 큰 혜택**</span><span class="sxs-lookup"><span data-stu-id="c06b2-127">**Greatest benefit**</span></span> | <span data-ttu-id="c06b2-128">간단하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-128">Simple to use.</span></span> <span data-ttu-id="c06b2-129">추가 디렉터리 도구 또는 서버는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="c06b2-130">사용자는 On-premises 또는 클라우드 기반 리소스에 액세스할 때 동일한 자격 증명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="c06b2-131">클라우드 전용 ID</span><span class="sxs-lookup"><span data-stu-id="c06b2-131">Cloud-only identity</span></span>

<span data-ttu-id="c06b2-132">클라우드 전용 ID는 Azure AD에만 있는 사용자 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="c06b2-133">클라우드 전용 ID는 일반적으로 로컬 ID를 관리하는 데 AD DS를 사용하지 않는 소규모 조직에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="c06b2-134">다음은 클라우드 전용 ID의 기본 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-134">Here are the basic components of cloud-only identity.</span></span>
 
![클라우드 전용 ID의 기본 구성 요소](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="c06b2-136">모든온-프레미스 및 원격(온라인) 사용자는 Azure AD 사용자 계정 및 암호를 사용하여 Microsoft 365 클라우드 서비스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="c06b2-137">Azure AD는 저장된 사용자 계정 및 암호를 기반으로 사용자 자격 증명을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="c06b2-138">관리</span><span class="sxs-lookup"><span data-stu-id="c06b2-138">Administration</span></span>
<span data-ttu-id="c06b2-139">사용자 계정은 Azure AD에만 저장되어 있기 때문에 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/) 관리 센터와 같은 도구를 사용하여 클라우드 ID를 관리하고 [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="c06b2-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="c06b2-140">하이브리드 ID</span><span class="sxs-lookup"><span data-stu-id="c06b2-140">Hybrid identity</span></span>

<span data-ttu-id="c06b2-141">하이브리드 ID는 Microsoft 365 구독의 Azure AD 테넌트에 복사본이 있는 계정을 사용하며,</span><span class="sxs-lookup"><span data-stu-id="c06b2-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="c06b2-142">그러나 대부분의 변경 내용은 한 가지 방법으로만 흐를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-142">However, most changes only flow one way.</span></span> <span data-ttu-id="c06b2-143">AD DS 사용자 계정의 변경 내용은 Azure AD의 복사본과 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="c06b2-144">그러나 Azure AD의 클라우드 기반 계정(예: 새 사용자 계정)에 대한 변경 내용은 AD DS와 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="c06b2-145">Azure AD Connect는 지속적인 계정 동기화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="c06b2-146">이 서버는 On-premises 서버에서 실행되어 AD DS의 변경 내용을 확인한 다음 Azure AD에 해당 변경 내용을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="c06b2-147">Azure AD Connect는 동기화되는 계정과 PHS(암호 해시 동기화)라고 하는 해시된 버전의 사용자 암호를 동기화할지 여부를 필터링하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="c06b2-148">하이브리드 ID를 구현하는 경우, 계정 정보에 대한 권한이 있는 원본은 On-premises AD DS입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="c06b2-149">즉, 관리 작업은 대부분 On-premises에서 수행한 다음 Azure AD와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="c06b2-150">다음은 하이브리드 ID의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-150">Here are the components of hybrid identity.</span></span>

![하이브리드 ID의 구성 요소](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="c06b2-152">Azure AD 테넌트에는 AD DS 계정의 복사본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="c06b2-153">이 구성에서는 Microsoft 365 클라우드 서비스에 액세스하는 원격 사용자와 모든 사용자가 Azure AD에 대해 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="c06b2-154">항상 Azure AD Connect를 사용하여 하이브리드 ID에 대한 사용자 계정을 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="c06b2-155">라이선스 할당 및 그룹 관리를 수행하고, 사용 권한을 구성하고, 사용자 계정과 관련된 기타 관리 작업을 수행하려면 Azure AD의 동기화된 사용자 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="c06b2-156">관리</span><span class="sxs-lookup"><span data-stu-id="c06b2-156">Administration</span></span>

<span data-ttu-id="c06b2-157">원본 및 권한이 있는 사용자 계정은 On-premises AD DS에 저장되어 있기 때문에 AD DS 관리와 동일한 도구를 사용하여 ID를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="c06b2-158">Azure AD에서 동기화된 사용자 계정을 관리하는 데 Microsoft 365 관리 센터 또는 Microsoft 365용 PowerShell을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b2-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="c06b2-159">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c06b2-159">Next step</span></span>

<span data-ttu-id="c06b2-160">클라우드 전용 ID 모델이 필요한 경우 클라우드 전용 [ID를 참조합니다.](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="c06b2-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="c06b2-161">하이브리드 ID 모델이 필요한 경우 하이브리드 [ID를 참조합니다.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="c06b2-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="c06b2-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c06b2-162">See also</span></span>

[<span data-ttu-id="c06b2-163">Microsoft 365 Enterprise 개요</span><span class="sxs-lookup"><span data-stu-id="c06b2-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
