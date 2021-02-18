---
title: 격리된 SharePoint Online 팀 사이트 디자인
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 권한 수준 결정, 액세스 그룹이 있는 사용자에게 사용 권한 할당 및 중첩된 Azure AD 그룹을 포함하여 격리된 SharePoint Online 팀 사이트를 디자인합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288338"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="db4b7-103">격리된 SharePoint Online 팀 사이트 디자인</span><span class="sxs-lookup"><span data-stu-id="db4b7-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db4b7-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="db4b7-104">**Applies to**</span></span>
- [<span data-ttu-id="db4b7-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="db4b7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="db4b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db4b7-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="db4b7-107">**요약:** 격리된 SharePoint Online 팀 사이트에 대한 디자인 프로세스를 단계적으로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="db4b7-108">이 문서에서는 격리된 SharePoint Online 팀 사이트를 만들기 전에 결정해야 하는 주요 디자인 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="db4b7-109">1단계: SharePoint 그룹 및 사용 권한 수준 결정</span><span class="sxs-lookup"><span data-stu-id="db4b7-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="db4b7-110">기본적으로 모든 SharePoint Online 팀 사이트는 다음 SharePoint 그룹으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="db4b7-111">\<site name> 구성원</span><span class="sxs-lookup"><span data-stu-id="db4b7-111">\<site name> Members</span></span>

- <span data-ttu-id="db4b7-112">\<site name> 방문자</span><span class="sxs-lookup"><span data-stu-id="db4b7-112">\<site name> Visitors</span></span>

- <span data-ttu-id="db4b7-113">\<site name> 소유자</span><span class="sxs-lookup"><span data-stu-id="db4b7-113">\<site name> Owners</span></span>

<span data-ttu-id="db4b7-114">이러한 그룹은 Microsoft 365 및 Azure AD(Active Directory) 그룹과는 별개로, 사이트의 리소스에 대한 사용 권한을 할당하기 위한 기초입니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="db4b7-115">SharePoint 그룹의 구성원이 사이트에서 할 수 있는 작업을 결정하는 특정 권한 집합은 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="db4b7-116">SharePoint Online 팀 사이트에는 기본적으로 편집, 읽기 및 모든 권한의 세 가지 권한 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="db4b7-117">다음 표에서는 SharePoint 그룹 및 할당된 사용 권한 수준의 기본 상관 관계에 대한 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="db4b7-118">SharePoint 그룹</span><span class="sxs-lookup"><span data-stu-id="db4b7-118">SharePoint group</span></span>|<span data-ttu-id="db4b7-119">사용 권한 수준</span><span class="sxs-lookup"><span data-stu-id="db4b7-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="db4b7-120">\<site name> 구성원</span><span class="sxs-lookup"><span data-stu-id="db4b7-120">\<site name> Members</span></span>|<span data-ttu-id="db4b7-121">편집</span><span class="sxs-lookup"><span data-stu-id="db4b7-121">Edit</span></span>|
|<span data-ttu-id="db4b7-122">\<site name> 방문자</span><span class="sxs-lookup"><span data-stu-id="db4b7-122">\<site name> Visitors</span></span>|<span data-ttu-id="db4b7-123">읽기</span><span class="sxs-lookup"><span data-stu-id="db4b7-123">Read</span></span>|
|<span data-ttu-id="db4b7-124">\<site name> 소유자</span><span class="sxs-lookup"><span data-stu-id="db4b7-124">\<site name> Owners</span></span>|<span data-ttu-id="db4b7-125">모든 권한</span><span class="sxs-lookup"><span data-stu-id="db4b7-125">Full control</span></span>|
|

 <span data-ttu-id="db4b7-126">**모범 사례:** 추가 SharePoint 그룹 및 권한 수준을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="db4b7-127">그러나 격리된 SharePoint Online 사이트에 기본 SharePoint 그룹 및 사용 권한 수준을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="db4b7-128">기본 SharePoint 그룹 및 권한 수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-128">Here are the default SharePoint groups and permission levels.</span></span>

![SharePoint Online 사이트의 기본 SharePoint 그룹 및 권한 수준입니다.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="db4b7-130">2단계: 액세스 그룹이 있는 사용자에게 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="db4b7-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="db4b7-131">SharePoint 그룹에 사용자 계정 또는 사용자 계정이 구성원으로 있는 Microsoft 365 또는 Azure AD 그룹을 추가하여 사용자에게 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="db4b7-132">추가된 사용자 계정에는 Microsoft 365 또는 Azure AD 그룹의 구성원 자격을 통해 직접 또는 간접적으로 SharePoint 그룹과 연결된 사용 권한 수준이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="db4b7-133">기본 SharePoint 그룹을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="db4b7-134">사용자 계정과 그룹을 모두 포함할 수 있는 **\<site name> Members** SharePoint 그룹의 구성원에게는 편집 **권한** 수준이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="db4b7-135">사용자 계정과 그룹을 모두 포함할 수 있는 **\<site name> Visitors** SharePoint 그룹의 구성원에게는 읽기 **권한** 수준이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="db4b7-136">사용자 계정과 그룹을 모두 포함할 수 있는 **\<site name> Owners** SharePoint 그룹의 구성원에게는 모든 권한 **수준이** 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="db4b7-137">**모범 사례:** 개별 사용자 계정을 통해 사용 권한을 관리할 수 있는 경우 액세스 그룹으로 알려진 단일 Azure AD 그룹을 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="db4b7-138">이렇게 하면 각 SharePoint 그룹의 사용자 계정 목록을 관리하는 대신 액세스 그룹의 구성원 자격을 통해 사용 권한 관리를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="db4b7-139">Microsoft 365용 Azure AD 그룹은 서로 다른 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="db4b7-140">Azure AD 그룹은 유형이 보안으로 설정되어  있으며  전자 메일 주소가 없는 Microsoft 365 관리 센터에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="db4b7-141">Azure AD 그룹은 다음 내에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="db4b7-142">AD DS(Active Directory 도메인 서비스)</span><span class="sxs-lookup"><span data-stu-id="db4b7-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="db4b7-143">이러한 그룹은 프레미스 AD DS 인프라에서 만들어지며 Microsoft 365 구독과 동기화된 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="db4b7-144">Microsoft 365 관리 센터에서 이러한  그룹은 Active Directory와 동기화된 **상태입니다.**</span><span class="sxs-lookup"><span data-stu-id="db4b7-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="db4b7-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="db4b7-145">Office 365</span></span>

    <span data-ttu-id="db4b7-146">Microsoft 365 관리 센터, Azure Portal 또는 Microsoft PowerShell을 사용하여 만든 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="db4b7-147">Microsoft 365 관리 센터에서 이러한 그룹에는 클라우드 **상태가** **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="db4b7-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="db4b7-148">**모범 사례:** AD DS를 사용하고 Microsoft 365 구독과 동기화하는 경우 AD DS를 사용하여 사용자 및 그룹 관리를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="db4b7-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="db4b7-149">격리된 SharePoint Online 팀 사이트의 경우 권장되는 그룹 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="db4b7-150">SharePoint 그룹</span><span class="sxs-lookup"><span data-stu-id="db4b7-150">SharePoint group</span></span>|<span data-ttu-id="db4b7-151">Azure AD 기반 액세스 그룹</span><span class="sxs-lookup"><span data-stu-id="db4b7-151">Azure AD-based access group</span></span>|<span data-ttu-id="db4b7-152">권한 수준</span><span class="sxs-lookup"><span data-stu-id="db4b7-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="db4b7-153">\<site name> 구성원</span><span class="sxs-lookup"><span data-stu-id="db4b7-153">\<site name> Members</span></span>|<span data-ttu-id="db4b7-154">\<site name> 구성원</span><span class="sxs-lookup"><span data-stu-id="db4b7-154">\<site name> Members</span></span>|<span data-ttu-id="db4b7-155">편집</span><span class="sxs-lookup"><span data-stu-id="db4b7-155">Edit</span></span>|
|<span data-ttu-id="db4b7-156">\<site name> 방문자</span><span class="sxs-lookup"><span data-stu-id="db4b7-156">\<site name> Visitors</span></span>|<span data-ttu-id="db4b7-157">\<site name> 뷰어</span><span class="sxs-lookup"><span data-stu-id="db4b7-157">\<site name> Viewers</span></span>|<span data-ttu-id="db4b7-158">읽기</span><span class="sxs-lookup"><span data-stu-id="db4b7-158">Read</span></span>|
|<span data-ttu-id="db4b7-159">\<site name> 소유자</span><span class="sxs-lookup"><span data-stu-id="db4b7-159">\<site name> Owners</span></span>|<span data-ttu-id="db4b7-160">\<site name> 관리자</span><span class="sxs-lookup"><span data-stu-id="db4b7-160">\<site name> Admins</span></span>|<span data-ttu-id="db4b7-161">모든 권한</span><span class="sxs-lookup"><span data-stu-id="db4b7-161">Full control</span></span>|
|

 <span data-ttu-id="db4b7-162">**모범 사례:** Microsoft 365 또는 Azure AD 그룹을 SharePoint 그룹의 구성원으로 사용할 수 있는 경우 Azure AD 그룹을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="db4b7-163">AD DS 또는 Microsoft 365를 통해 관리되는 Azure AD 그룹은 중첩된 그룹을 사용하여 권한을 할당할 수 있는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="db4b7-164">Azure AD 기반 액세스 그룹을 사용하도록 구성된 기본 SharePoint 그룹은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![액세스 그룹을 기본 SharePoint Online 사이트 그룹의 구성원으로 사용](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="db4b7-166">세 가지 액세스 그룹을 디자인할 때 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="db4b7-167">**\<site name> Admins** 액세스 그룹에는 팀 사이트를 관리하는 소수의 SharePoint Online 관리자에 해당하는 구성원만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="db4b7-168">대부분의 사이트 구성원은 구성원 **\<site name>** 또는 뷰어 **\<site name> 액세스 그룹에** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="db4b7-169">구성원 액세스 그룹의 **\<site name>** 사이트 구성원은 사이트의 리소스를 삭제하거나 수정할 수 있기 때문에 구성원 자격을 신중하게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="db4b7-170">의심스러우면 Viewers 액세스 그룹에 **\<site name> 사이트 구성원을** 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="db4b7-171">다음은 ProjectX라는 격리된 사이트에 대한 SharePoint 그룹 및 액세스 그룹의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![ProjectX라는 SharePoint Online 사이트에 액세스 그룹을 사용하는 예입니다.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="db4b7-173">3단계: 중첩된 Azure AD 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="db4b7-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="db4b7-174">소수의 사용자로 제한되는 프로젝트의 경우 사이트의 SharePoint 그룹에 추가된 단일 수준의 Azure AD 기반 액세스 그룹이 대부분의 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="db4b7-175">그러나 사용자가 많은 경우 이미 설정한 Azure AD 그룹의 구성원인 경우 중첩된 그룹 또는 다른 그룹을 구성원으로 포함하는 그룹을 사용하여 SharePoint 사용 권한을 보다 쉽게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="db4b7-176">예를 들어 영업, 마케팅, 엔지니어링, 법률 및 지원 부서의 임원과 임원 사용자 계정 멤버 자격이 있는 해당 부서의 임원들이 공동 작업을 위해 격리된 SharePoint 온라인 팀 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="db4b7-177">새 사이트 구성원에 대해 새 그룹을 만들고 모든 개별 임원 사용자 계정을 배치하는 대신 새 그룹에 각 부서의 기존 임원 그룹을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="db4b7-178">여러 조직 간에 Microsoft 365 구독을 공유하는 경우 매우 많은 수의 사용자 계정으로 인해 조직에 대해 격리된 사이트에 대한 단일 수준의 그룹 구성원 자격을 관리하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="db4b7-179">이 경우 조직 내의 그룹이 포함된 각 조직에 대해 중첩된 Azure AD 그룹을 사용하여 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="db4b7-180">중첩된 Azure AD 그룹을 사용:</span><span class="sxs-lookup"><span data-stu-id="db4b7-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="db4b7-181">사용자 계정을 포함할 Azure AD 그룹을 식별하거나 만들고 적절한 사용자 계정을 구성원으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="db4b7-182">다른 Azure AD 그룹을 포함할 컨테이너 Azure AD 기반 액세스 그룹을 만들고 해당 그룹을 구성원으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="db4b7-183">컨테이너 액세스 그룹에 대한 적절한 액세스 수준에 대해 SharePoint 그룹 및 해당 사용 권한 수준을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="db4b7-184">중첩된 Microsoft 365 그룹은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="db4b7-185">ProjectX 구성원 액세스 그룹에 대한 중첩된 Azure AD 그룹의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![ProjectX 사이트의 구성원 액세스 그룹에 중첩된 액세스 그룹을 사용하는 예입니다.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="db4b7-187">리서치, 엔지니어링 및 프로젝트 잠재 고객 팀의 모든 사용자 계정은 사이트 구성원으로 고안된 것이기 때문에 Azure AD 그룹을 ProjectX 구성원 액세스 그룹에 더 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4b7-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="db4b7-188">다음 단계</span><span class="sxs-lookup"><span data-stu-id="db4b7-188">Next step</span></span>

<span data-ttu-id="db4b7-189">프로덕션에서 격리된 사이트를 만들고 구성할 준비가 되면 격리된 SharePoint Online 팀 사이트 배포를 [참조하세요.](deploy-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="db4b7-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db4b7-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db4b7-190">See Also</span></span>

[<span data-ttu-id="db4b7-191">격리된 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="db4b7-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="db4b7-192">격리된 SharePoint Online 팀 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="db4b7-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="db4b7-193">격리된 SharePoint Online 팀 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="db4b7-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
