---
title: Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용하기
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
ms.openlocfilehash: b9ca945ac90ab27d3bc25f1022070eff4737bc10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631305"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="0f8af-103">민감도 레이블 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 콘텐츠 보호하기</span><span class="sxs-lookup"><span data-stu-id="0f8af-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites (public preview)</span></span>

><span data-ttu-id="0f8af-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="0f8af-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0f8af-105">[Microsoft 365 규정 준수 센터](https://protection.office.com/)에서 민감도 레이블을 만들 때 이제 레이블을 Microsoft Teams 사이트, Microsoft 365 그룹, SharePoint 사이트 등의 컨테이너에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-105">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="0f8af-106">다음 레이블 설정을 사용하여 이러한 컨테이너의 콘텐츠를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-106">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="0f8af-107">Microsoft 365 그룹에 연결된 팀 사이트의 개인 정보(공개 또는 비공개)</span><span class="sxs-lookup"><span data-stu-id="0f8af-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="0f8af-108">외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="0f8af-108">External users access</span></span>
- <span data-ttu-id="0f8af-109">관리되지 않는 장치에서 액세스</span><span class="sxs-lookup"><span data-stu-id="0f8af-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="0f8af-110">지원되는 컨테이너에 이 레이블을 적용하면, 레이블은 연결된 사이트 또는 그룹에 구성된 옵션을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-110">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="0f8af-111">그러나 이러한 컨테이너의 콘텐츠는 레이블 이름, 시각적 표시 또는 암호화와 같은 설정에 대한 레이블을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-111">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="0f8af-112">SharePoint 사이트 또는 팀 사이트에서 문서에 레이블을 지정할 수 있도록 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-112">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="0f8af-113">Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트의 공개 미리 보기에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="0f8af-113">About the public preview for Microsoft Teams, Microsoft 365 Groups, and SharePoint sites</span></span>

<span data-ttu-id="0f8af-114">Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트의 민감도 레이블은 테넌트에 점진적으로 배포되고 있으며 최종 출시 전에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-114">Sensitivity labels for Microsoft Teams, Microsoft 365 Groups, and SharePoint sites are in gradual rollout to tenants and might change before final release.</span></span> <span data-ttu-id="0f8af-115">이 공개 미리 보기는 Office 365 Content Delivery Network(CDNs)에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-115">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="0f8af-116">이 미리보기를 활성화하고 새 설정에 대한 민감도 레이블을 구성하기 전에 사용자는 앱에서 민감도 레이블을 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-116">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="0f8af-117">예를 들어 Word의 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-117">For example, from Word:</span></span>

![Word 데스크톱 앱에 표시되는 민감도 레이블](../media/sensitivity-label-word.png)

<span data-ttu-id="0f8af-119">이 미리 보기를 활성화하고 구성한 후 사용자는 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에 대한 민감도 레이블을 추가로 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-119">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Microsoft 365 Groups, and SharePoint sites.</span></span> <span data-ttu-id="0f8af-120">예를 들어 SharePoint에서 새 팀 사이트를 만드는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-120">For example, when you create a new team site from SharePoint:</span></span>

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="0f8af-122">이 미리 보기를 사용하고 레이블을 동기화</span><span class="sxs-lookup"><span data-stu-id="0f8af-122">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="0f8af-123">이 기능은 Azure AD 기능을 사용하므로 Azure AD 설명서의 지침에 따라 미리 보기를 활성화하세요. [Azure Active Directory의 Microsoft 365 그룹에 민감도 레이블 지정하기(미리 보기)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="0f8af-123">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="0f8af-124">이제 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-124">Now [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="0f8af-125">예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="0f8af-126">다음 명령을 실행하여 민감도 레이블을 Azure AD와 동기화하여 Microsoft 365 그룹과 함께 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Microsoft 365 Groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="0f8af-127">민감도 레이블을 만들거나 편집할 때 사이트 및 그룹 설정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="0f8af-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="0f8af-128">이제 사이트 및 그룹에 사용할 민감도 레이블을 만들거나 편집할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="0f8af-129">미리보기를 활성화하면 민감도 레이블 마법사에서 새 페이지가 표시됩니다. **사이트 및 그룹 설정**</span><span class="sxs-lookup"><span data-stu-id="0f8af-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="0f8af-130">민감도 레이블 작성 또는 편집에 도움이 필요한 경우 [민감도 레이블 생성 및 구성](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)의 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="0f8af-131">이 새 **사이트 및 그룹 설정** 페이지에서 다음과 같이 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="0f8af-132">**Microsoft 365 그룹에 연결된 팀 사이트의 개인 정보**: **없음 - 사용자가 사이트에 액세스할 수 있는 사람을 선택하도록 허용**의 기본 설정이 현재 테넌트에 롤아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-132">**Privacy of Microsoft 365 group-connected teams sites**: The default setting of **None - let user chose who can access the site** is currently rolling out to tenants.</span></span> <span data-ttu-id="0f8af-133">민감도 레이블을 사용하여 컨테이너에서 콘텐츠를 보호하려고 할 때 이 기본 설정을 유지하되, 사용자가 계속 개인 정보 설정을 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-133">Keep this default setting when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="0f8af-134">이 레이블을 컨테이너에 적용할 때 개인 정보 설정을 설정하고 잠그려면 **공개** 또는 **비공개**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-134">Select **Public** or**Private** to set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="0f8af-135">조직의 모든 사용자가 이 레이블이 적용되는 팀 사이트 또는 그룹에 액세스하도록 하는 경우에는 **공개**를 선택하거나 조직에서 허용되는 구성원으로만 액세스를 제한하려는 경우에는 **비공개**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-135">Choose **Public** if you want anyone in your organization to access the team site or group where this label is applied, or **Private** if you want access to be restricted to only approved members in your organization.</span></span> 
    
    <span data-ttu-id="0f8af-136">이 **공개** 또는 **비공개** 설정은 팀 또는 그룹에 대해 구성할 수 있는 이전 개인 정보 설정을 대체하 고 개인 정보 보호 값을 잠가 컨테이너에서 민감도 레이블을 먼저 제거해야만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-136">The **Public** or **Private** setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="0f8af-137">민감도 레이블을 제거한 후에도 레이블의 개인 정보 설정이 유지되며 이제 사용자가 다시 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="0f8af-138">**외부 사용자 액세스**: 그룹 소유자가 [그룹에 게스트를 추가](/office365/admin/create-groups/manage-guest-access-in-groups)할 수 있는지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="0f8af-139">**관리되지 않는 장치**: [관리되지 않는 장치](/sharepoint/control-access-from-unmanaged-devices)의 경우 전체 액세스, 웹 전용 액세스를 허용하거나 액세스를 완벽하게 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![사이트 및 그룹 설정 탭](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="0f8af-141">팀, 그룹 또는 사이트에 레이블을 적용할 때 이러한 사이트 및 그룹 설정만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-141">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="0f8af-142">팀, 그룹 또는 사이트 내의 콘텐츠에는 암호화 및 콘텐츠 표시와 같은 다른 레이블 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-142">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="0f8af-143">테넌트에 점진적으로 배포: 사용자가 팀, 그룹 및 사이트를 만들 때 사이트 및 그룹 설정을 포함하는 레이블만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-143">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="0f8af-144">레이블에 사이트 및 그룹 설정을 사용할 수 없는 경우 현재 레이블을 컨테이너에 적용할 수 있는 경우에는 레이블 이름만 컨테이너에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-144">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="0f8af-145">민감도 레이블이 아직 게시되지 않은 경우 [민감도 레이블 정책에 추가](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)하여 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-145">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="0f8af-146">이 레이블을 포함하는 민감도 레이블 정책이 할당된 사용자는 해당 레이블을 사이트 및 그룹에 대해 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-146">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="0f8af-147">레이블 정책에서 이 레이블을 컨테이너에 적용하는 경우에는 **이 레이블을 기본적으로 문서와 전자 메일에 적용** 정책 설정만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-147">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="0f8af-148">필수 레이블, 사용자 사유 필요, 사용자 지정 도움말 페이지에 대한 링크를 포함하는 기타 정책 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-148">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="0f8af-149">민감도 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="0f8af-149">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="0f8af-150">Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에 사용하는 민감도 레이블을 만들고, 수정하고, 삭제하려면 사용자에게 레이블 정책을 게시하는 데 세심한 조정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-150">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Microsoft 365 Groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="0f8af-151">다음의 지침을 사용하여 모든 사용자에게 영향을 줄 수 있는 사이트 및 그룹에 대한 만들기 오류를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-151">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="0f8af-152">**레이블 만들기 및 게시:**</span><span class="sxs-lookup"><span data-stu-id="0f8af-152">**Creating and publishing labels:**</span></span>

<span data-ttu-id="0f8af-153">민감도 레이블이 만들어지고 게시된 후 레이블이 팀, 그룹 및 사이트의 사용자에게 표시될 때까지는 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-153">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="0f8af-154">다음의 단계를 사용하여 테넌트의 모든 사용자에 대한 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-154">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="0f8af-155">민감도 레이블을 만들고 테넌트의 일부 사용자 계정에만 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-155">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="0f8af-156">24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-156">Wait for 24 hours.</span></span>

3. <span data-ttu-id="0f8af-157">24시간을 기다린 후에 1단계에서 지정한 사용자 계정 중 하나를 사용하여 1단계에서 만든 레이블이 있는 팀, Microsoft 365 그룹 또는 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-157">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="0f8af-158">3단계의 만들기 작업 중에 오류가 없으면 테넌트의 모든 사용자에게 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-158">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="0f8af-159">오류가 있으면 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-159">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="0f8af-160">**게시된 레이블 수정 및 삭제:**</span><span class="sxs-lookup"><span data-stu-id="0f8af-160">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="0f8af-161">사이트 및 그룹 설정을 사용하도록 설정된 민감도 레이블을 수정하거나 삭제하고 해당 레이블이 하나 이상의 레이블 정책에 포함된 경우, 이러한 작업의 수행은 모든 팀, 그룹 및 사이트에 대한 만들기 오류로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-161">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="0f8af-162">이러한 상황을 방지하려면 다음의 지침을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-162">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="0f8af-163">레이블이 포함된 모든 레이블 정책에서 민감도 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-163">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="0f8af-164">48시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-164">Wait for 48 hours.</span></span>

3. <span data-ttu-id="0f8af-165">48시간을 기다린 후에 팀, 그룹 또는 사이트 만들기를 시도해보고 해당 레이블이 더 이상 보이지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-165">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="0f8af-166">민감도 레이블이 보이지 않는 경우에는 안전하게 레이블을 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-166">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="0f8af-167">레이블이 계속 표시되면 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-167">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="0f8af-168">Microsoft 365 그룹에 민감도 레이블 지정하기</span><span class="sxs-lookup"><span data-stu-id="0f8af-168">Assign sensitivity labels to Microsoft 365 Groups</span></span>

<span data-ttu-id="0f8af-169">이제 민감도 레이블을 Microsoft 365 그룹에 적용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-169">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="0f8af-170">Azure AD 문서로 돌아가서 다음 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-170">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="0f8af-171">Azure 포털의 새 그룹에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="0f8af-171">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="0f8af-172">Azure 포털의 기존 그룹에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="0f8af-172">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="0f8af-173">[Azure 포털의 기존 그룹에서 레이블 제거](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="0f8af-173">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="0f8af-174">새 팀에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="0f8af-174">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="0f8af-175">사용자는 Microsoft Teams에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-175">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="0f8af-176">**민감도** 드롭다운에서 레이블을 선택할 때 개인 정보 설정은 레이블 구성을 반영하여 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-176">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="0f8af-177">사용자가 레이블에 대해 선택한 외부 사용자 액세스 설정에 따라 조직 외부의 사용자를 팀에 추가할 수 있는지의 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-177">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="0f8af-178">Teams용 민감도 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="0f8af-178">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![새 팀을 만드는 경우 개인 정보 설정](../media/privacy-setting-new-team.png)

<span data-ttu-id="0f8af-180">팀을 만든 후에는 모든 채널의 우측 상단 모서리에 민감도 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-180">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![민감도 레이블이 팀에 표시됩니다.](../media/privacy-setting-teams.png)

<span data-ttu-id="0f8af-182">이 서비스는 Microsoft 365 그룹과 연결된 SharePoint 팀 사이트에 자동으로 동일한 민감도 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-182">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="0f8af-183">웹용 Outlook의 새 그룹에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="0f8af-183">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="0f8af-184">웹용 Outlook에서 새 그룹을 만들 때 게시된 레이블에 대한 **민감도** 옵션을 선택하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-184">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![그룹 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="0f8af-186">새 사이트에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="0f8af-186">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="0f8af-187">관리자 및 최종 사용자는 [최신 팀 사이트 및 커뮤니케이션 사이트를 만들고](/sharepoint/create-site-collection), **고급 설정**을 확장하는 경우 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-187">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![사이트 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="0f8af-189">드롭다운 상자에는 선택에 대한 레이블 이름이 표시되고 도움말 아이콘에는 사용자가 적용할 올바른 레이블을 결정할 수 있도록 도구 설명과 함께 모든 레이블 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-189">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="0f8af-190">레이블이 적용되고, 사용자가 사이트로 이동할 때 레이블의 이름과 적용된 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-190">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="0f8af-191">예를 들어 이 사이트에는 **기밀** 레이블이 지정되고 개인 정보 설정은 **비공개**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-191">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![민감도 레이블이 적용된 사이트](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="0f8af-193">SharePoint 관리 센터에서 민감도 레이블 보기</span><span class="sxs-lookup"><span data-stu-id="0f8af-193">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="0f8af-194">적용된 민감도 레이블을 보려면 새 SharePoint 관리 센터의 **활성 사이트** 페이지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-194">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="0f8af-195">먼저 **민감도** 열을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-195">You might need to first add the **Sensitivity** column:</span></span>

![활성 사이트 페이지의 민감도 열](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="0f8af-197">[새 SharePoint 관리 센터에서의 사이트 관리에 대해 자세히 알아보기](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="0f8af-197">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="0f8af-198">레이블의 사이트 및 그룹 설정 변경</span><span class="sxs-lookup"><span data-stu-id="0f8af-198">Change site and group settings for a label</span></span>

<span data-ttu-id="0f8af-199">레이블의 사이트 및 그룹 설정을 변경할 때마다 팀, 사이트, 그룹에서 새 설정을 사용할 수 있도록 다음 PowerShell 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-199">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="0f8af-200">최상의 방법은 여러 팀, 그룹 또는 사이트에 민감도 레이블을 적용한 후 레이블의 사이트와 그룹 설정을 변경하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-200">As a best practice, don't the change site and group settings for a label after you've applied the sensitivity label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="0f8af-201">우선 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-201">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="0f8af-202">예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-202">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="0f8af-203">[Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet을 사용하여 민감도 레이블 및 GUID 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-203">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="0f8af-204">사용자가 변경한 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-204">Make a note of the GUID for the label or labels you have changed.</span></span>

4. <span data-ttu-id="0f8af-205">이제 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-205">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="0f8af-206">예시:</span><span class="sxs-lookup"><span data-stu-id="0f8af-206">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```
    
5. <span data-ttu-id="0f8af-207">[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) cmdlet을 실행하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-207">Run the [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

6. <span data-ttu-id="0f8af-208">각 그룹에 대해 민감도 레이블을 다시 적용하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-208">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="0f8af-209">민감도 레이블에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="0f8af-209">Support for the sensitivity labels</span></span>

<span data-ttu-id="0f8af-210">다음 앱 및 서비스에서 사이트 및 그룹 설정에 대해 구성한 민감도 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-210">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="0f8af-211">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0f8af-211">SharePoint Online</span></span>
- <span data-ttu-id="0f8af-212">Teams</span><span class="sxs-lookup"><span data-stu-id="0f8af-212">Teams</span></span>
- <span data-ttu-id="0f8af-213">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="0f8af-213">Outlook on the web</span></span>
- <span data-ttu-id="0f8af-214">SharePoint 관리 센터</span><span class="sxs-lookup"><span data-stu-id="0f8af-214">SharePoint admin center</span></span>
- <span data-ttu-id="0f8af-215">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="0f8af-215">Azure AD admin center</span></span>

<span data-ttu-id="0f8af-216">사이트 및 그룹 설정에 대해 구성한 민감도 레이블을 현재 사용할 수 없는 기타 앱 및 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-216">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="0f8af-217">Mac용 Outlook</span><span class="sxs-lookup"><span data-stu-id="0f8af-217">Outlook for the Mac</span></span>
- <span data-ttu-id="0f8af-218">Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="0f8af-218">Outlook mobile</span></span>
- <span data-ttu-id="0f8af-219">Windows용 Outlook 데스크톱</span><span class="sxs-lookup"><span data-stu-id="0f8af-219">Outlook desktop for Windows</span></span>
- <span data-ttu-id="0f8af-220">양식</span><span class="sxs-lookup"><span data-stu-id="0f8af-220">Forms</span></span>
- <span data-ttu-id="0f8af-221">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0f8af-221">Dynamics 365</span></span>
- <span data-ttu-id="0f8af-222">Yammer</span><span class="sxs-lookup"><span data-stu-id="0f8af-222">Yammer</span></span>
- <span data-ttu-id="0f8af-223">Stream</span><span class="sxs-lookup"><span data-stu-id="0f8af-223">Stream</span></span>
- <span data-ttu-id="0f8af-224">Planner</span><span class="sxs-lookup"><span data-stu-id="0f8af-224">Planner</span></span>
- <span data-ttu-id="0f8af-225">Project</span><span class="sxs-lookup"><span data-stu-id="0f8af-225">Project</span></span>
- <span data-ttu-id="0f8af-226">PowerBI</span><span class="sxs-lookup"><span data-stu-id="0f8af-226">PowerBI</span></span>
- <span data-ttu-id="0f8af-227">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="0f8af-227">Teams admin center</span></span>
- <span data-ttu-id="0f8af-228">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="0f8af-228">Microsoft 365 admin center</span></span>
- <span data-ttu-id="0f8af-229">Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="0f8af-229">Exchange admin center</span></span>


## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="0f8af-230">클래식 Azure AD 그룹 분류</span><span class="sxs-lookup"><span data-stu-id="0f8af-230">Classic Azure AD group classification</span></span>

<span data-ttu-id="0f8af-231">이 미리 보기를 사용하도록 설정하면 Microsoft 365에서 새 Office 365 그룹 및 SharePoint 사이트에 대해 이전 분류를 더 이상 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-231">Microsoft 365 no longer supports the old classifications for new Office 365 groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="0f8af-232">그러나 민감도 레이블을 사용하도록 변환하지 않는 한 기존 그룹 및 사이트는 여전히 이전 분류 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-232">However, existing groups and sites still display the old classification values unless you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="0f8af-233">SharePoint에 이전 그룹 분류를 사용하는 방법에 대한 예제는 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-233">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="0f8af-234">이와 같은 분류는 Azure AD PowerShell 또는 PnP 핵심 라이브러리를 사용하고 `ClassificationList` 설정의 값을 정의하여 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-234">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="0f8af-235">테넌트에 분류 값이 정의되어 있는 경우, [AzureADPreview PowerShell 모듈](https://www.powershellgallery.com/packages/AzureADPreview)에서 다음 명령을 실행하면 이 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-235">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="0f8af-236">이전 분류를 민감도 레이블로 변환하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-236">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="0f8af-237">기존 레이블 사용: 이미 게시된 기존 민감도 레이블을 편집하여 사이트 및 그룹에 대해 원하는 레이블 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-237">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="0f8af-238">새 레이블 만들기: 기존 분류와 이름이 같은 새 민감도 레이블을 만들고 게시하여 사이트 및 그룹에 대해 원하는 레이블 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-238">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="0f8af-239">그런 다음 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-239">Then:</span></span> 

1. <span data-ttu-id="0f8af-240">이름 매핑과 함께 PowerShell을 사용하여 민감도 레이블을 기존 Microsoft 365 그룹 및 SharePoint 사이트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-240">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="0f8af-241">지침은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-241">See the next section for instructions.</span></span>

2. <span data-ttu-id="0f8af-242">기존 그룹과 사이트에서 이전 분류를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-242">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="0f8af-243">사용자가 아직 민감도 레이블을 지원하지 않는 앱과 서비스에서 새 그룹을 만들지 못하도록 할 수는 없지만, 반복적인 PowerShell 스크립트를 실행하여 사용자가 이전 분류로 만든 새 그룹을 찾고, 이러한 그룹을 민감도 레이블을 사용하도록 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-243">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="0f8af-244">PowerShell을 사용하여 Microsoft 365 그룹 분류를 민감도 레이블로 변환하기</span><span class="sxs-lookup"><span data-stu-id="0f8af-244">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="0f8af-245">우선 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-245">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="0f8af-246">예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-246">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="0f8af-247">[Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet을 사용하여 민감도 레이블 및 GUID 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-247">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="0f8af-248">Office 365 그룹에 적용할 민감도 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-248">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

4. <span data-ttu-id="0f8af-249">이제 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-249">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="0f8af-250">예시:</span><span class="sxs-lookup"><span data-stu-id="0f8af-250">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

6. <span data-ttu-id="0f8af-251">Microsoft 365 그룹에 적용할 민감도 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-251">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

7. <span data-ttu-id="0f8af-252">다음 명령을 예로 사용하여 현재 "일반" 분류”를 포함하는 그룹 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-252">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="0f8af-253">각 그룹에 새 민감도 레이블 GUID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-253">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="0f8af-254">예시:</span><span class="sxs-lookup"><span data-stu-id="0f8af-254">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="0f8af-255">나머지 그룹 분류에 대해 5단계와 6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-255">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="0f8af-256">민감도 레이블 활동 감사</span><span class="sxs-lookup"><span data-stu-id="0f8af-256">Auditing sensitivity label activities</span></span>

<span data-ttu-id="0f8af-257">누군가가 민감도 레이블로 보호된 사이트에 문서를 업로드하고 해당 문서에 사이트에 적용된 민감도 레이블보다 [높은 우선 순위](sensitivity-labels.md#label-priority-order-matters)의 레이블이 있는 경우 이 작업이 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-257">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="0f8af-258">예를 들어 **일반** 레이블을 SharePoint 사이트에 적용하고 누군가가 이 사이트에 **기밀** 레이블이 지정된 문서를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-258">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="0f8af-259">우선 순위가 높은 민감도 레이블은 우선 순위가 낮은 컨텐츠보다 민감도가 높은 컨텐츠를 먼저 식별하므로 이 상황은 보안상의 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-259">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="0f8af-260">작업이 차단되는 것은 아니지만 감사가 진행되므로 레이블 우선 순위가 이처럼 잘못 정렬된 문서를 확인하고 필요한 경우 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-260">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="0f8af-261">예를 들어 업로드된 문서를 사이트에서 삭제하거나 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-261">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="0f8af-262">사이트에 적용된 민감도 레이블보다 우선 순위가 낮은 레이블이 문서에 지정되어 있다면 보안 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-262">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="0f8af-263">예를 들어 **일반** 레이블이 지정된 문서가 **기밀** 레이블이 지정된 사이트에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-263">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="0f8af-264">이 시나리오에서는 감사 이벤트가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-264">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="0f8af-265">이 이벤트에 대한 감사 로그를 검색하려면 **파일 및 페이지 활동** 범주에서 **발견된 문서 감도 불일치**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-265">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="0f8af-266">누군가가 사이트 또는 그룹에 민감도 레이블을 추가하거나 제거하는 경우에도 이러한 활동이 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-266">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="0f8af-267">이러한 이벤트는 [민감도 레이블 활동](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 범주에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-267">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="0f8af-268">감사 로그를 검색하기 위한 지침은 [보안 및 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-268">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="0f8af-269">민감도 레이블 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0f8af-269">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="0f8af-270">Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트의 민감도 레이블에 문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="0f8af-270">Having problems with sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="0f8af-271">다음을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-271">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="0f8af-272">게시 후 레이블이 보이지 않음</span><span class="sxs-lookup"><span data-stu-id="0f8af-272">Labels not visible after publishing</span></span>
<span data-ttu-id="0f8af-273">이 설정을 사용하도록 설정하거나 민감도 레이블의 이름이나 도구 설명을 수정한 후 사이트 또는 Microsoft 365 그룹을 만들 때 문제가 발생하는 경우, 레이블 변경 내용을 저장하고 몇 시간을 기다린 후에 팀 또는 그룹을 다시 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-273">If you experience issues when you create a site or Microsoft 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="0f8af-274">이에 대한 내용은 [민감도 레이블을 만들거나 변경한 후의 롤아웃 일정 예약](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-274">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="0f8af-275">아직 SharePoint Online에서 새 민감도 레이블을 표시할 수 없는 경우 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-275">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="0f8af-276">팀, 그룹 또는 SharePoint 사이트 만들기 오류</span><span class="sxs-lookup"><span data-stu-id="0f8af-276">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="0f8af-277">공개 미리 보기 중에 생성 오류가 발생하는 경우에는 [PowerShell에서 민감도 레이블 지원 활성화하기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)와 동일한 지침을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에 대한 민감도 레이블을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-277">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="0f8af-278">그러나 미리보기를 비활성화하려면 5단계에서 `$setting["EnableMIPLabels"] = "False"`을(를) 사용하여 기능을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8af-278">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f8af-279">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="0f8af-279">Additional resources</span></span>

<span data-ttu-id="0f8af-280">[Microsoft Teams, O365 그룹, SharePoint Online 사이트에서 민감도 레이블 사용에](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) 대한 웨비나 기록 및 질응답을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f8af-280">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

