---
title: 권장 보안 문서 정책 - 엔터프라이즈용 Microsoft 365 | Microsoft Docs
description: SharePoint 파일 액세스를 보호하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 5c739a47ccab79561277436812c36f842b6b578c
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142816"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="61d50-103">SharePoint 사이트 및 파일 보안에 대한 정책 권장 사항</span><span class="sxs-lookup"><span data-stu-id="61d50-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="61d50-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="61d50-104">**Applies to**</span></span>
- [<span data-ttu-id="61d50-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="61d50-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="61d50-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="61d50-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- <span data-ttu-id="61d50-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="61d50-107">SharePoint Online</span></span> 


<span data-ttu-id="61d50-108">이 문서에서는 SharePoint 및 비즈니스용 OneDrive를 보호하기 위해 권장되는 ID 및 장치 액세스 정책을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="61d50-109">이 지침은 공통 ID 및 장치 액세스 [정책을 빌드합니다.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="61d50-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="61d50-110">이러한 권장 사항은 요구의 세분성에 따라 적용할 수 있는 세 가지 SharePoint 파일의 보안 및 보호 계층인 **기준,** 중요 및 높은 규제 계층을 기반으로 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="61d50-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="61d50-111">이러한 보안 계층 및 권장되는 클라이언트 운영 체제에 대한 자세한 내용은 개요에서 이러한 권장 사항을 [참조하세요.](microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="61d50-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="61d50-112">이 지침을 구현하는 것 외에도 중요하고 높은 규제 대상 콘텐츠에 적절한 사용 권한을 설정하는 등 적절한 양의 보호를 사용하여 SharePoint 사이트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="61d50-113">SharePoint 및 비즈니스용 OneDrive를 포함하기 위해 일반 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="61d50-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="61d50-114">SharePoint 및 OneDrive의 파일을 보호하기 위해 다음 다이어그램에서는 공통 ID 및 장치 액세스 정책에서 업데이트할 정책을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="61d50-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="61d50-115">[![Teams 및 해당 종속 서비스에 대한 액세스를 보호하기 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="61d50-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="61d50-116">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="61d50-116">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="61d50-117">공통 정책을 만들 때 SharePoint를 포함한 경우 새 정책만 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-117">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="61d50-118">조건부 액세스 정책의 경우 SharePoint에는 OneDrive가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-118">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="61d50-119">새 정책은 지정한 SharePoint 사이트에 특정 액세스 요구 사항을 적용하여 중요하고 높은 규제 대상 콘텐츠에 대한 장치 보호를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-119">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="61d50-120">다음 표에는 SharePoint에 대한 검토 및 업데이트 또는 새 만들기에 필요한 정책이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-120">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="61d50-121">일반 정책은 일반 ID 및 장치 액세스 정책 문서의 관련 구성 [지침에 연결됩니다.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="61d50-121">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="61d50-122">보호 수준</span><span class="sxs-lookup"><span data-stu-id="61d50-122">Protection level</span></span>|<span data-ttu-id="61d50-123">정책</span><span class="sxs-lookup"><span data-stu-id="61d50-123">Policies</span></span>|<span data-ttu-id="61d50-124">추가 정보</span><span class="sxs-lookup"><span data-stu-id="61d50-124">More information</span></span>|
|---|---|---|
|<span data-ttu-id="61d50-125">**기준**</span><span class="sxs-lookup"><span data-stu-id="61d50-125">**Baseline**</span></span>|[<span data-ttu-id="61d50-126">로그인 위험이 중간 또는 높음인 경우 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="61d50-126">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="61d50-127">클라우드 앱 할당에 SharePoint를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-127">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="61d50-128">최신 인증을 지원하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="61d50-128">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="61d50-129">클라우드 앱 할당에 SharePoint를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-129">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="61d50-130">APP 데이터 보호 정책 적용</span><span class="sxs-lookup"><span data-stu-id="61d50-130">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="61d50-131">모든 권장 앱이 앱 목록에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-131">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="61d50-132">각 플랫폼(iOS, Android, Windows)에 대한 정책을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-132">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="61d50-133">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="61d50-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="61d50-134">클라우드 앱 목록에 SharePoint를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-134">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="61d50-135">SharePoint에서 앱 적용 제한 사용</span><span class="sxs-lookup"><span data-stu-id="61d50-135">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="61d50-136">이 새 정책을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-136">Add this new policy.</span></span> <span data-ttu-id="61d50-137">그러면 Azure AD(Azure Active Directory)가 SharePoint에 지정된 설정을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-137">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="61d50-138">이 정책은 모든 사용자에게 적용되지만 SharePoint 액세스 정책에 포함된 사이트에 대한 액세스에만 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-138">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="61d50-139">**중요**</span><span class="sxs-lookup"><span data-stu-id="61d50-139">**Sensitive**</span></span>|[<span data-ttu-id="61d50-140">로그인 위험이 낮음, 중간 또는  높음인 경우 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="61d50-140">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="61d50-141">클라우드 앱 할당에 SharePoint를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-141">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="61d50-142">호환 PC 및 *모바일* 장치 필요</span><span class="sxs-lookup"><span data-stu-id="61d50-142">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="61d50-143">클라우드 앱 목록에 SharePoint를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-143">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="61d50-144">[SharePoint 액세스 제어 정책:](#sharepoint-access-control-policies)관리되지 않는 장치에서 특정 SharePoint 사이트에 대한 브라우저 전용 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-144">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="61d50-145">이렇게 하면 파일을 편집하고 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-145">This prevents edit and download of files.</span></span> <span data-ttu-id="61d50-146">PowerShell을 사용하여 사이트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-146">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="61d50-147">**매우 엄격한 규제**</span><span class="sxs-lookup"><span data-stu-id="61d50-147">**Highly regulated**</span></span>|[<span data-ttu-id="61d50-148">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="61d50-148">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="61d50-149">클라우드 앱 할당에 SharePoint를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-149">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="61d50-150">[SharePoint 액세스 제어 정책:](#use-app-enforced-restrictions-in-sharepoint)관리되지 않는 장치에서 특정 SharePoint 사이트에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-150">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="61d50-151">PowerShell을 사용하여 사이트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-151">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="61d50-152">SharePoint에서 앱 적용 제한 사용</span><span class="sxs-lookup"><span data-stu-id="61d50-152">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="61d50-153">SharePoint에서 액세스 제어를 구현하는 경우 Azure AD에서 이 조건부 액세스 정책을 만들어 SharePoint에서 구성한 정책을 적용하도록 Azure AD에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-153">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="61d50-154">이 정책은 모든 사용자에게 적용되지만 SharePoint에서 액세스 컨트롤을 만들 때 PowerShell을 사용하여 지정한 사이트에 대한 액세스에만 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-154">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="61d50-155">해당 정책을 구성하는 경우 관리되지 않는 장치의 액세스 제어에서 "특정 SharePoint 사이트 모음 또는 OneDrive 계정에 대한 액세스 차단 또는 [제한"을 참조하세요.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="61d50-155">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="61d50-156">SharePoint 액세스 제어 정책</span><span class="sxs-lookup"><span data-stu-id="61d50-156">SharePoint access control policies</span></span>

<span data-ttu-id="61d50-157">장치 액세스 제어를 사용하여 중요하고 높은 규제 대상 콘텐츠를 사용하여 SharePoint 사이트의 콘텐츠를 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-157">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="61d50-158">이 작업을 위해 보호 수준을 지정하는 정책과 보호를 적용할 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-158">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="61d50-159">중요한 사이트: 브라우저 전용 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-159">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="61d50-160">이렇게 하면 사용자가 파일을 편집하고 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-160">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="61d50-161">높은 규제 대상 사이트: 관리되지 않는 장치에서 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-161">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="61d50-162">관리되지 않는 장치의 액세스 제어에서 "특정 SharePoint 사이트 모음 또는 OneDrive 계정에 대한 액세스 차단 또는 [제한"을 참조하세요.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="61d50-162">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="61d50-163">이러한 정책이 함께 작동 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61d50-163">How these policies work together</span></span>

<span data-ttu-id="61d50-164">SharePoint 사이트 권한은 일반적으로 사이트에 대한 액세스에 대한 비즈니스 필요성을 기반으로 한다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-164">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="61d50-165">이러한 사용 권한은 사이트 소유자가 관리하며 매우 동적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-165">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="61d50-166">SharePoint 장치 액세스 정책을 사용하면 사용자가 기준, 중요 또는 높은 규제 대상 보호와 연결된 Azure AD 그룹에 할당되어 있는지 여부에 관계없이 이러한 사이트를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-166">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="61d50-167">다음 그림에서는 SharePoint 장치 액세스 정책이 사용자의 사이트에 대한 액세스를 보호하는 방법의 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-167">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="61d50-168">[![SharePoint 장치 액세스 정책이 사이트를 보호하는 방법의 예](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="61d50-168">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="61d50-169">이 이미지의 더 큰 버전 보기</span><span class="sxs-lookup"><span data-stu-id="61d50-169">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="61d50-170">James는 기본 조건부 액세스 정책을 할당했지만 중요하거나 높은 규제 대상 보호를 통해 SharePoint 사이트에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-170">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="61d50-171">James가 중요하거나 높은 규제 대상 사이트에 액세스하는 경우 해당 PC를 사용하는 구성원인 경우 PC가 규격인 한 액세스 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-171">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="61d50-172">James가 관리되지 않는 전화(기준 사용자에 대해 허용되는)를 사용하는 구성원인 중요한 사이트에 액세스하는 경우 이 사이트에 대해 구성된 장치 액세스 정책으로 인해 중요한 사이트에 대한 브라우저 전용 액세스를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-172">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="61d50-173">James가 높은 규제 대상 사이트에 액세스하는 경우 관리되지 않는 휴대폰을 사용하는 구성원인 경우 이 사이트에 대해 구성된 액세스 정책으로 인해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-173">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="61d50-174">관리되고 호환되는 PC를 사용하여 이 사이트에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61d50-174">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="61d50-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="61d50-175">Next step</span></span>

![4단계: Microsoft 365 클라우드 앱에 대한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="61d50-177">조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="61d50-177">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="61d50-178">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61d50-178">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="61d50-179">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="61d50-179">Exchange Online</span></span>](secure-email-recommended-policies.md)
