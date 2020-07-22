---
title: Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 민감도 레이블 사용하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 민감도 레이블을 사용하여 SharePoint 및 Microsoft Teams 사이트, Microsoft 365 그룹의 콘텐츠를 보호합니다.
ms.openlocfilehash: b9168320b5764a3d7ed4e1570c32f0f35ccbc44d
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199628"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="dabda-103">민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기</span><span class="sxs-lookup"><span data-stu-id="dabda-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="dabda-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="dabda-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dabda-105">[민감도 레이블](sensitivity-labels.md)을 사용하여 문서와 전자 메일을 분류하고 보호하는 것 외에도 민감도 레이블을 사용하여 Microsoft Teams 사이트, Microsoft 365 그룹([이전 이름: Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) 및 SharePoint 사이트와 같은 컨테이너의 콘텐츠를 보호할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="dabda-106">이 컨테이너 수준 분류 및 보호를 위해서는 다음 레이블 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="dabda-107">Microsoft 365 그룹에 연결된 팀 사이트의 개인 정보(공개 또는 비공개)</span><span class="sxs-lookup"><span data-stu-id="dabda-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="dabda-108">외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="dabda-108">External users access</span></span>
- <span data-ttu-id="dabda-109">관리되지 않는 장치에서 액세스</span><span class="sxs-lookup"><span data-stu-id="dabda-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="dabda-110">지원되는 컨테이너에 이 민감도 레이블을 적용하면, 레이블은 연결된 사이트 또는 그룹에 분류 및 보호 설정을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-110">When you apply this sensitivity label to a supported container, the label automatically applies the classification and protection settings to the connected site or group.</span></span>

<span data-ttu-id="dabda-111">그러나 이러한 컨테이너의 콘텐츠는 시각적 표시 또는 암호화와 같은 분류와 설정에 대한 레이블을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-111">Content in these containers however, do not inherit the labels for the classification and settings such as visual markings, or encryption.</span></span> <span data-ttu-id="dabda-112">SharePoint 사이트 또는 팀 사이트에서 문서에 레이블을 지정할 수 있도록 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-112">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dabda-113">컨테이너에 대한 민감도 레이블은 Office 365 CDN(콘텐츠 배달 네트워크)에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-113">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="dabda-114">Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 민감도 레이블 사용하기</span><span class="sxs-lookup"><span data-stu-id="dabda-114">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="dabda-115">컨테이너에서 민감도 레이블을 사용하도록 설정하고 새 설정에 대한 민감도 레이블을 구성하기 전에 사용자는 앱에서 민감도 레이블을 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-115">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="dabda-116">예를 들어 Word의 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-116">For example, from Word:</span></span>

![Word 데스크톱 앱에 표시되는 민감도 레이블](../media/sensitivity-label-word.png)

<span data-ttu-id="dabda-118">컨테이너에서 민감도 레이블을 사용하도록 설정하고 구성한 후 사용자는 Microsoft Teams 사이트, Microsoft 365 그룹 및 SharePoint 사이트에 대한 민감도 레이블을 추가로 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-118">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="dabda-119">예를 들어 SharePoint에서 새 팀 사이트를 만드는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-119">For example, when you create a new team site from SharePoint:</span></span>

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="dabda-121">컨테이너에서 민감도 레이블을 사용하도록 설정하고 레이블을 동기화하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabda-121">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="dabda-122">이 기능은 Azure AD 기능을 사용하므로 Azure AD 설명서의 지침에 따라 민감도 레이블 지원을 사용하도록 설정하세요. [Azure Active Directory의 Microsoft 365 그룹에 민감도 레이블 지정하기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="dabda-122">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="dabda-123">이제 민감도 레이블을 Azure AD로 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-123">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="dabda-124">우선 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-124">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="dabda-125">예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="dabda-126">그런 다음, 다음 명령을 실행하여 민감도 레이블을 Microsoft 365 그룹에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-126">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a><span data-ttu-id="dabda-127">사이트 및 그룹 설정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabda-127">How to configure site and group settings</span></span>

<span data-ttu-id="dabda-128">이제 사이트 및 그룹에 사용할 민감도 레이블을 만들거나 편집할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="dabda-129">컨테이너에서 민감도 레이블을 사용하도록 설정하면 민감도 레이블 마법사에서 새 **사이트 및 그룹 설정** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-129">Enabling sensitivity labels for containers makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="dabda-130">민감도 레이블 작성 또는 편집에 도움이 필요한 경우 [민감도 레이블 생성 및 구성](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)의 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="dabda-131">이 새 **사이트 및 그룹 설정** 페이지에서 다음과 같이 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="dabda-132">**Office 365 그룹에 연결된 팀 사이트의 개인 정보**: 조직의 모든 사용자가 이 레이블이 적용된 팀 사이트에 액세스할 수 있도록 하려면 기본값 **공개 - 조직의 모든 사용자가 사이트에 액세스할 수 있음**으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-132">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
    
    <span data-ttu-id="dabda-133">조직에서 허용한 구성원에게만 액세스를 제한하려면 **비공개**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-133">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
    
    <span data-ttu-id="dabda-134">민감도 레이블을 사용하여 컨테이너에서 콘텐츠를 보호하려고 하지만 사용자가 계속 개인 정보 설정을 구성할 수 있도록 하려면 **없음 - 사용자가 사이트에 액세스할 수 있는 사용자를 선택하도록 허용**을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="dabda-134">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="dabda-135">**공개** 또는 **비공개** 설정은 컨테이너에 이 레이블을 적용할 때 개인 정보 설정을 설정하고 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-135">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="dabda-136">선택한 설정은 팀 또는 그룹에 대해 구성할 수 있는 이전 개인 정보 설정을 대체하며, 개인 정보 값을 잠가 컨테이너에서 민감도 레이블을 먼저 제거해야만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-136">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="dabda-137">민감도 레이블을 제거한 후에도 레이블의 개인 정보 설정이 유지되며 이제 사용자가 다시 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="dabda-138">**외부 사용자 액세스**: 그룹 소유자가 [그룹에 게스트를 추가](/office365/admin/create-groups/manage-guest-access-in-groups)할 수 있는지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="dabda-139">**관리되지 않는 장치**: [관리되지 않는 장치](/sharepoint/control-access-from-unmanaged-devices)의 경우 전체 액세스, 웹 전용 액세스를 허용하거나 액세스를 완벽하게 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> <span data-ttu-id="dabda-140">테넌트 수준이나 특정 사이트에 대해 이 설정을 구성한 경우, 여기서 지정하는 설정은 더 제한적인 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-140">If you have configured this setting at the tenant level or for a specific site, the setting you specify here will be applied only if it's more restrictive.</span></span>

![사이트 및 그룹 설정 탭](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="dabda-142">팀, 그룹 또는 사이트에 레이블을 적용할 때 이러한 사이트 및 그룹 설정만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-142">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="dabda-143">팀, 그룹 또는 사이트 내의 콘텐츠에는 암호화 및 콘텐츠 표시와 같은 다른 레이블 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-143">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="dabda-144">테넌트에 점진적으로 배포: 사용자가 팀, 그룹 및 사이트를 만들 때 사이트 및 그룹 설정을 포함하는 레이블만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-144">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="dabda-145">레이블에 사이트 및 그룹 설정을 사용할 수 없는 경우 현재 레이블을 컨테이너에 적용할 수 있는 경우에는 레이블 이름만 컨테이너에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-145">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="dabda-146">민감도 레이블이 아직 게시되지 않은 경우 [민감도 레이블 정책에 추가](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)하여 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-146">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="dabda-147">이 레이블을 포함하는 민감도 레이블 정책이 할당된 사용자는 해당 레이블을 사이트 및 그룹에 대해 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-147">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="dabda-148">레이블 정책에서 이 레이블을 컨테이너에 적용하는 경우에는 **이 레이블을 기본적으로 문서와 전자 메일에 적용** 정책 설정만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-148">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="dabda-149">필수 레이블, 사용자 사유 필요, 사용자 지정 도움말 페이지에 대한 링크를 포함하는 기타 정책 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-149">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="dabda-150">민감도 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="dabda-150">Sensitivity label management</span></span>

<span data-ttu-id="dabda-151">사이트 및 그룹에 대해 구성된 민감도 레이블을 만들거나, 수정하거나, 삭제하는 경우 다음 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-151">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="dabda-152">사이트 및 그룹에 대해 구성된 레이블 만들기 및 게시하기</span><span class="sxs-lookup"><span data-stu-id="dabda-152">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="dabda-153">새 민감도 레이블을 만들고 게시하면 팀, 그룹 및 사이트의 사용자가 한 시간 내에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-153">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="dabda-154">그러나 기존 레이블을 수정하는 경우 최대 24시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-154">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="dabda-155">사이트 및 그룹 설정에 대해 레이블이 구성된 경우 다음 지침에 따라 사용자 레이블을 게시하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-155">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="dabda-156">민감도 레이블을 만들고 구성한 후에는 소수의 테스트 사용자에게만 적용되는 레이블 정책에 이 레이블을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-156">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="dabda-157">변경 내용이 복제될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-157">Wait for the change to replicate:</span></span>
    - <span data-ttu-id="dabda-158">새 레이블: 1시간 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-158">New label: Wait for one hour.</span></span>
    - <span data-ttu-id="dabda-159">기존 레이블: 24시간 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-159">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="dabda-160">이 대기 시간이 지나면 테스트 사용자 계정 중 하나를 사용하여 1단계에서 만든 레이블이 있는 팀, Microsoft 365 그룹 또는 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-160">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="dabda-161">만들기 작업 중에 오류가 없으면 테넌트의 모든 사용자에게 레이블을 게시해도 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-161">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="dabda-162">사이트 및 그룹에 대해 구성된 게시된 레이블 수정하기</span><span class="sxs-lookup"><span data-stu-id="dabda-162">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="dabda-163">가장 좋은 방법은 여러 팀, 그룹 또는 사이트에 민감도 레이블을 적용한 후 레이블의 사이트와 그룹 설정을 변경하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-163">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="dabda-164">그럴 경우 변경 내용이 레이블이 적용된 모든 컨테이너에 복제될 때까지 24시간 동안 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-164">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span> 

<span data-ttu-id="dabda-165">또한 변경 내용에 **외부 사용자 액세스** 설정이 포함된 경우:</span><span class="sxs-lookup"><span data-stu-id="dabda-165">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="dabda-166">새 설정은 새 사용자에게는 적용되지만 기존 사용자에게는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-166">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="dabda-167">예를 들어, 이전에 이 설정을 선택했고 그 결과 게스트 사용자가 사이트에 액세스한 경우 이 설정을 레이블 구성에서 지운 후에도 해당 게스트 사용자는 계속해서 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-167">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="dabda-168">그룹 속성 hiddenMembership 및 roleEnabled에 대한 개인 정보 설정은 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-168">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>


### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="dabda-169">사이트 및 그룹에 대해 구성된 게시된 레이블 삭제하기</span><span class="sxs-lookup"><span data-stu-id="dabda-169">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="dabda-170">사이트 및 그룹 설정을 사용하도록 설정된 민감도 레이블을 삭제하고 해당 레이블이 하나 이상의 레이블 정책에 포함된 경우, 이 작업으로 새 팀, 그룹 및 사이트 만들기 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-170">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="dabda-171">이러한 상황을 방지하려면 다음의 지침을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-171">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="dabda-172">레이블이 포함된 모든 레이블 정책에서 민감도 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-172">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="dabda-173">1시간 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-173">Wait for one hour.</span></span>

3. <span data-ttu-id="dabda-174">이 대기 시간이 지나면 팀, 그룹 또는 사이트 만들기를 시도해보고 해당 레이블이 더 이상 표시되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-174">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="dabda-175">민감도 레이블이 표시되지 않는 경우에는 안전하게 레이블을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-175">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="dabda-176">컨테이너에 민감도 레이블을 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabda-176">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="dabda-177">이제 민감도 레이블을 다음 컨테이너에 적용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-177">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="dabda-178">Azure AD의 Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="dabda-178">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="dabda-179">Microsoft Teams 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="dabda-179">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="dabda-180">웹용 Outlook의 Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="dabda-180">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="dabda-181">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="dabda-181">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="dabda-182">[여러 사이트에 민감도 레이블을 적용](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites)해야 하는 경우 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-182">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="dabda-183">Microsoft 365 그룹에 민감도 레이블 적용하기</span><span class="sxs-lookup"><span data-stu-id="dabda-183">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="dabda-184">이제 민감도 레이블을 Microsoft 365 그룹에 적용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-184">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="dabda-185">Azure AD 문서로 돌아가서 다음 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-185">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="dabda-186">Azure 포털의 새 그룹에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="dabda-186">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="dabda-187">Azure 포털의 기존 그룹에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="dabda-187">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="dabda-188">[Azure 포털의 기존 그룹에서 레이블 제거](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="dabda-188">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="dabda-189">새 팀에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="dabda-189">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="dabda-190">사용자는 Microsoft Teams에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-190">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="dabda-191">**민감도** 드롭다운에서 레이블을 선택할 때 개인 정보 설정은 레이블 구성을 반영하여 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-191">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="dabda-192">사용자가 레이블에 대해 선택한 외부 사용자 액세스 설정에 따라 조직 외부의 사용자를 팀에 추가할 수 있는지의 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-192">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="dabda-193">Teams용 민감도 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="dabda-193">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![새 팀을 만드는 경우 개인 정보 설정](../media/privacy-setting-new-team.png)

<span data-ttu-id="dabda-195">팀을 만든 후에는 모든 채널의 우측 상단 모서리에 민감도 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-195">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![민감도 레이블이 팀에 표시됩니다.](../media/privacy-setting-teams.png)

<span data-ttu-id="dabda-197">이 서비스는 Microsoft 365 그룹과 연결된 SharePoint 팀 사이트에 자동으로 동일한 민감도 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-197">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="dabda-198">웹용 Outlook의 새 그룹에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="dabda-198">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="dabda-199">웹용 Outlook에서 새 그룹을 만들 때 게시된 레이블에 대한 **민감도** 옵션을 선택하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-199">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![그룹 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="dabda-201">새 사이트에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="dabda-201">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="dabda-202">관리자 및 최종 사용자는 [최신 팀 사이트 및 커뮤니케이션 사이트를 만들고](/sharepoint/create-site-collection), **고급 설정**을 확장하는 경우 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-202">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![사이트 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="dabda-204">드롭다운 상자에는 선택에 대한 레이블 이름이 표시되고 도움말 아이콘에는 사용자가 적용할 올바른 레이블을 결정할 수 있도록 도구 설명과 함께 모든 레이블 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-204">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="dabda-205">레이블이 적용되고, 사용자가 사이트로 이동할 때 레이블의 이름과 적용된 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-205">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="dabda-206">예를 들어 이 사이트에는 **기밀** 레이블이 지정되고 개인 정보 설정은 **비공개**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-206">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![민감도 레이블이 적용된 사이트](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="dabda-208">PowerShell을 사용하여 여러 사이트에 민감도 레이블 적용하기</span><span class="sxs-lookup"><span data-stu-id="dabda-208">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="dabda-209">현재 SharePoint Online 관리 셸의 *SensitivityLabel* 매개 변수와 함께 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps)와 [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용하여 여러 사이트에 민감도 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-209">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *SensitivityLabel* parameter from the current SharePoint Online Management Shell to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="dabda-210">사이트는 모든 SharePoint 사이트 모음이나 OneDrive 사이트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-210">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="dabda-211">SharePoint Online 관리 셸의 버전 16.0.19418.12000 이상을 보유하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-211">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="dabda-212">**관리자 권한으로 실행** 옵션을 사용하여 PowerShell 세션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-212">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="dabda-213">레이블 GUID를 모르는 경우: [Office 365 보안 및 규정 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)한 후 민감도 레이블과 해당 GUID 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-213">If you don't know your label GUID: [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="dabda-214">이제 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)하여 레이블 GUID를 변수로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-214">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) and store your label GUID as a variable.</span></span> <span data-ttu-id="dabda-215">예제:</span><span class="sxs-lookup"><span data-stu-id="dabda-215">For example:</span></span> 
    
    ```powershell
    $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
    ```

4. <span data-ttu-id="dabda-216">URL에서 공통 식별 문자열을 포함하는 여러 사이트를 식별하는 새 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-216">Create a new variable that identifies multiple sites that have an identifying string in common in their URL.</span></span> <span data-ttu-id="dabda-217">예제:</span><span class="sxs-lookup"><span data-stu-id="dabda-217">For example:</span></span>
    
    ```powershell
    $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents" 
    ```

5. <span data-ttu-id="dabda-218">다음 명령을 실행하여 이러한 사이트에 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-218">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="dabda-219">예제 사용:</span><span class="sxs-lookup"><span data-stu-id="dabda-219">Using our examples:</span></span>
    
    ```powershell
    $sites | ForEach-Object {Set-SpoTenant $_.url -SensitivityLabel $Id}
    ```

<span data-ttu-id="dabda-220">다른 사이트에 다른 레이블을 적용하려면 각 사이트에 대해 `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"` 명령을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-220">To apply different labels to different sites, repeat the following command for each site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="dabda-221">SharePoint 관리 센터에서 민감도 레이블을 보고 관리하기</span><span class="sxs-lookup"><span data-stu-id="dabda-221">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="dabda-222">적용된 민감도 레이블을 보고, 정렬하고, 검색하려면 새 SharePoint 관리 센터의 **활성 사이트** 페이지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-222">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="dabda-223">먼저 **민감도** 열을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-223">You might need to first add the **Sensitivity** column:</span></span>

![활성 사이트 페이지의 민감도 열](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="dabda-225">열을 추가하는 방법을 포함하여 활성 사이트 페이지에서 사이트를 관리하는 방법에 대한 자세한 내용은 [새 SharePoint 관리 센터에서 사이트 관리하기](/sharepoint/manage-sites-in-new-admin-center)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-225">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="dabda-226">이 페이지에서 레이블을 변경하고 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-226">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="dabda-227">사이트 이름을 선택하여 세부 정보 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-227">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="dabda-228">**정책** 탭을 선택한 다음 **민감도** 설정에 대한 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-228">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="dabda-229">**민감도 설정 편집** 창에서 사이트에 적용할 민감도 레이블을 선택한 다음 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-229">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="dabda-230">민감도 레이블 지원</span><span class="sxs-lookup"><span data-stu-id="dabda-230">Support for sensitivity labels</span></span>

<span data-ttu-id="dabda-231">다음 앱 및 서비스에서는 사이트 및 그룹 설정에 대해 구성된 민감도 레이블을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-231">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="dabda-232">관리 센터:</span><span class="sxs-lookup"><span data-stu-id="dabda-232">Admin centers:</span></span>
    - <span data-ttu-id="dabda-233">SharePoint 관리 센터</span><span class="sxs-lookup"><span data-stu-id="dabda-233">SharePoint admin center</span></span>
    - <span data-ttu-id="dabda-234">Azure Active Directory 포털</span><span class="sxs-lookup"><span data-stu-id="dabda-234">Azure Active Directory portal</span></span>
    - <span data-ttu-id="dabda-235">Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터, Office 365 보안 및 준수 센터</span><span class="sxs-lookup"><span data-stu-id="dabda-235">Microsoft 365 compliance center, Microsoft 365 security center, Office 365 Security & Compliance Center</span></span>

- <span data-ttu-id="dabda-236">사용자 앱 및 서비스:</span><span class="sxs-lookup"><span data-stu-id="dabda-236">User apps and services:</span></span>
    - <span data-ttu-id="dabda-237">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dabda-237">SharePoint</span></span>
    - <span data-ttu-id="dabda-238">Teams</span><span class="sxs-lookup"><span data-stu-id="dabda-238">Teams</span></span>
    - <span data-ttu-id="dabda-239">웹용, Windows, MacOS, iOS, Android용 Outlook</span><span class="sxs-lookup"><span data-stu-id="dabda-239">Outlook on the web and for Windows, MacOS, iOS, and Android</span></span>
    - <span data-ttu-id="dabda-240">Forms</span><span class="sxs-lookup"><span data-stu-id="dabda-240">Forms</span></span>
    - <span data-ttu-id="dabda-241">Stream</span><span class="sxs-lookup"><span data-stu-id="dabda-241">Stream</span></span>

<span data-ttu-id="dabda-242">다음 앱 및 서비스에서는 현재 사이트 및 그룹 설정에 대해 구성된 민감도 레이블을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-242">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="dabda-243">관리 센터:</span><span class="sxs-lookup"><span data-stu-id="dabda-243">Admin centers:</span></span>
    - <span data-ttu-id="dabda-244">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="dabda-244">Microsoft 365 admin center</span></span>
    - <span data-ttu-id="dabda-245">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="dabda-245">Teams admin center</span></span>
    - <span data-ttu-id="dabda-246">Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="dabda-246">Exchange admin center</span></span>

- <span data-ttu-id="dabda-247">사용자 앱 및 서비스:</span><span class="sxs-lookup"><span data-stu-id="dabda-247">User apps and services:</span></span>
    - <span data-ttu-id="dabda-248">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="dabda-248">Dynamics 365</span></span>
    - <span data-ttu-id="dabda-249">Yammer</span><span class="sxs-lookup"><span data-stu-id="dabda-249">Yammer</span></span>
    - <span data-ttu-id="dabda-250">Planner</span><span class="sxs-lookup"><span data-stu-id="dabda-250">Planner</span></span>
    - <span data-ttu-id="dabda-251">Project</span><span class="sxs-lookup"><span data-stu-id="dabda-251">Project</span></span>
    - <span data-ttu-id="dabda-252">PowerBI</span><span class="sxs-lookup"><span data-stu-id="dabda-252">PowerBI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="dabda-253">클래식 Azure AD 그룹 분류</span><span class="sxs-lookup"><span data-stu-id="dabda-253">Classic Azure AD group classification</span></span>

<span data-ttu-id="dabda-254">컨테이너에서 민감도 레이블을 사용하도록 설정하면 Microsoft 365는 더 이상 새 Microsoft 365 그룹 및 SharePoint 사이트에 대해 이전 분류를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-254">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="dabda-255">그러나 민감도 레이블을 사용하도록 변환할 때까지 민감도 레이블을 지원하는 기존 그룹 및 사이트는 여전히 이전 분류 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-255">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="dabda-256">SharePoint에 이전 그룹 분류를 사용하는 방법에 대한 예제는 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-256">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="dabda-257">이와 같은 분류는 Azure AD PowerShell 또는 PnP 핵심 라이브러리를 사용하고 `ClassificationList` 설정의 값을 정의하여 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-257">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="dabda-258">테넌트에 분류 값이 정의되어 있는 경우, [AzureADPreview PowerShell 모듈](https://www.powershellgallery.com/packages/AzureADPreview)에서 다음 명령을 실행하면 이 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-258">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="dabda-259">이전 분류를 민감도 레이블로 변환하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-259">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="dabda-260">기존 레이블 사용: 이미 게시된 기존 민감도 레이블을 편집하여 사이트 및 그룹에 대해 원하는 레이블 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-260">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="dabda-261">새 레이블 만들기: 기존 분류와 이름이 같은 새 민감도 레이블을 만들고 게시하여 사이트 및 그룹에 대해 원하는 레이블 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-261">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="dabda-262">그런 다음 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-262">Then:</span></span> 

1. <span data-ttu-id="dabda-263">이름 매핑과 함께 PowerShell을 사용하여 민감도 레이블을 기존 Microsoft 365 그룹 및 SharePoint 사이트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-263">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="dabda-264">지침은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-264">See the next section for instructions.</span></span>

2. <span data-ttu-id="dabda-265">기존 그룹과 사이트에서 이전 분류를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-265">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="dabda-266">사용자가 아직 민감도 레이블을 지원하지 않는 앱과 서비스에서 새 그룹을 만들지 못하도록 할 수는 없지만, 반복적인 PowerShell 스크립트를 실행하여 사용자가 이전 분류로 만든 새 그룹을 찾고, 이러한 그룹을 민감도 레이블을 사용하도록 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-266">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

<span data-ttu-id="dabda-267">사이트 및 그룹에 대한 민감도 레이블과 Azure AD 분류의 공존을 관리하는 데 도움이 되도록 [Microsoft 365 그룹에 대한 Azure Active Directory 분류 및 민감도 레이블](migrate-aad-classification-sensitivity-labels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-267">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="dabda-268">PowerShell을 사용하여 Microsoft 365 그룹 분류를 민감도 레이블로 변환하기</span><span class="sxs-lookup"><span data-stu-id="dabda-268">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="dabda-269">우선 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-269">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="dabda-270">예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-270">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="dabda-271">[Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet을 사용하여 민감도 레이블 및 GUID 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-271">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="dabda-272">Microsoft 365 그룹에 적용할 민감도 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-272">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="dabda-273">이제 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-273">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="dabda-274">예시:</span><span class="sxs-lookup"><span data-stu-id="dabda-274">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. <span data-ttu-id="dabda-275">다음 명령을 예로 사용하여 현재 "일반" 분류”를 포함하는 그룹 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-275">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="dabda-276">각 그룹에 새 민감도 레이블 GUID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-276">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="dabda-277">예시:</span><span class="sxs-lookup"><span data-stu-id="dabda-277">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="dabda-278">나머지 그룹 분류에 대해 5단계와 6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-278">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="dabda-279">민감도 레이블 활동 감사</span><span class="sxs-lookup"><span data-stu-id="dabda-279">Auditing sensitivity label activities</span></span>

<span data-ttu-id="dabda-280">누군가가 민감도 레이블로 보호된 사이트에 문서를 업로드하고 해당 문서에 사이트에 적용된 민감도 레이블보다 [높은 우선 순위](sensitivity-labels.md#label-priority-order-matters)의 레이블이 있는 경우 이 작업이 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-280">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="dabda-281">예를 들어 **일반** 레이블을 SharePoint 사이트에 적용하고 누군가가 이 사이트에 **기밀** 레이블이 지정된 문서를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-281">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="dabda-282">우선 순위가 높은 민감도 레이블은 우선 순위가 낮은 컨텐츠보다 민감도가 높은 컨텐츠를 먼저 식별하므로 이 상황은 보안상의 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-282">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="dabda-283">작업이 차단되는 것은 아니지만 감사를 받고 문서를 업로드한 사람과 사이트 관리자에게 전자 메일을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-283">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="dabda-284">따라서 사용자와 관리자가 모두 레이블 우선 순위에 대한 이러한 잘못된 문서를 확인하고 필요한 경우 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-284">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="dabda-285">예를 들어 업로드된 문서를 사이트에서 삭제하거나 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-285">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="dabda-286">사이트에 적용된 민감도 레이블보다 우선 순위가 낮은 레이블이 문서에 지정되어 있다면 보안 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-286">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="dabda-287">예를 들어 **일반** 레이블이 지정된 문서가 **기밀** 레이블이 지정된 사이트에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-287">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="dabda-288">이 시나리오에서는 감사 이벤트와 전자 메일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-288">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="dabda-289">이 이벤트에 대한 감사 로그를 검색하려면 **파일 및 페이지 활동** 범주에서 **발견된 문서 감도 불일치**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-289">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="dabda-290">자동 생성된 전자 메일에는 **호환되지 않는 민감도 레이블이 탐지됨**이라는 제목이 있고, 전자 메일 메시지에서는 업로드한 문서 및 사이트에 대한 링크와 레이블 불일치를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-290">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="dabda-291">또한 사용자가 민감도 레이블을 변경하는 방법을 설명하는 문서 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-291">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="dabda-292">현재로서는 이러한 자동화된 전자 메일을 사용하지 않도록 설정하거나 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-292">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="dabda-293">누군가가 사이트 또는 그룹에 민감도 레이블을 추가하거나 제거하는 경우에도 이러한 활동도 감사되지만 전자 메일을 자동으로 생성하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-293">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span> 

<span data-ttu-id="dabda-294">이러한 모든 감사 이벤트는 [민감도 레이블 활동](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 범주에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-294">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="dabda-295">감사 로그를 검색하기 위한 지침은 [보안 및 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-295">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="dabda-296">컨테이너에서 민감도 레이블을 사용하지 않도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabda-296">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="dabda-297">[PowerShell에서 민감도 레이블 지원 활성화하기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)와 동일한 지침을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에 대한 민감도 레이블을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-297">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="dabda-298">그러나 이 기능을 사용하지 않도록 설정하려면 5단계에서 `$setting["EnableMIPLabels"] = "False"`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-298">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="dabda-299">민감도 레이블을 만들거나 편집할 때 **사이트 및 그룹 설정** 페이지를 숨기는 것 외에도 이 작업은 컨테이너에서 구성에 사용하는 속성을 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-299">In addition to hiding the **Sites and group settings** page when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="dabda-300">Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 민감도 레이블을 사용하도록 설정하면 **분류**에서 사용되는 속성([Azure AD 그룹 분류](#classic-azure-ad-group-classification)에 사용됨)이 **민감도**로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-300">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="dabda-301">컨테이너에서 민감도 레이블을 사용하지 않도록 설정하면 컨테이너에서 민감도 속성을 무시하고 분류 속성을 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-301">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="dabda-302">즉, 이전에 컨테이너에 적용된 사이트 및 그룹의 레이블 설정이 적용되지 않고 컨테이너에서는 더 이상 레이블이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-302">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="dabda-303">이러한 컨테이너에 Azure AD 분류 값이 적용되면 컨테이너는 분류를 다시 사용하도록 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-303">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="dabda-304">이 기능을 사용하도록 설정한 후에 만든 새 사이트나 그룹은 레이블을 표시하지 않거나 분류를 갖지 않는다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-304">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="dabda-305">이러한 컨테이너와 새 컨테이너의 경우 이제 분류 값을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-305">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="dabda-306">자세한 내용은 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) 및 [조직에서 Office 그룹의 분류 만들기](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-306">For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dabda-307">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="dabda-307">Additional resources</span></span>

<span data-ttu-id="dabda-308">[Microsoft Teams, O365 그룹, SharePoint Online 사이트에서 민감도 레이블 사용에](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) 대한 웨비나 기록 및 질응답을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dabda-308">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="dabda-309">이 웨비나는 기능이 미리 보기에 있을 때 녹화되었기 때문에 UI에 약간의 차이가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-309">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="dabda-310">그러나 이 기능에 대한 정보는 이 페이지에 설명된 새 기능과 함께 여전히 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="dabda-310">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>
