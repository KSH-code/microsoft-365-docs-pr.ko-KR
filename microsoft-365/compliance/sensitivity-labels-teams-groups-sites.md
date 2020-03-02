---
title: Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용
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
description: Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 레이블을 적용할 수 있습니다.
ms.openlocfilehash: 350e1906e4d645c444d772b1ade9a2ff9c850992
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313803"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="345ea-103">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="345ea-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="345ea-104">[Microsoft 365 준수 센터](https://protection.office.com/)에서 민감도 레이블을 만들 때 이제 레이블을 Microsoft Teams, Office 365 그룹 그리고 SharePoint 사이트 등의 컨테이너에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="345ea-105">레이블 설정을 사용하여 이러한 컨테이너에 대해 다음 옵션을 제어하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="345ea-106">Office 365 그룹에 연결된 팀 사이트의 개인 정보 보호 (공개 또는 비공개)</span><span class="sxs-lookup"><span data-stu-id="345ea-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="345ea-107">외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="345ea-107">External users access</span></span>
- <span data-ttu-id="345ea-108">관리되지 않는 장치에서 액세스</span><span class="sxs-lookup"><span data-stu-id="345ea-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="345ea-109">지원되는 컨테이너 중 하나에 이 레이블을 적용하면, 레이블은 연결된 SharePoint 사이트 또는 팀 사이트에 구성된 옵션을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="345ea-110">그러나 이러한 컨테이너의 콘텐츠는 레이블 이름, 시각적 표시 또는 암호화와 같은 설정에 대한 레이블을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="345ea-111">SharePoint 사이트 또는 팀 사이트에서 파일에 레이블을 지정하려면 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="345ea-112">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 공개 미리 보기에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="345ea-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="345ea-113">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 민감도 레이블은 테넌트에 점진적으로 배포되고 있으며 최종 출시 전에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="345ea-114">이 공개 미리 보기는 Office 365 Content Delivery Network(CDNs)에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="345ea-115">이 미리보기를 활성화하고 새 설정에 대한 민감도 레이블을 구성하기 전에 사용자는 앱에서 민감도 레이블을 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="345ea-116">예를 들어 Word의 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-116">For example, from Word:</span></span>

![Word 데스크톱 앱에 표시되는 민감도 레이블](../media/sensitivity-label-word.png)

<span data-ttu-id="345ea-118">이 미리보기를 활성화하고 구성한 후 사용자는 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에 대한 민감도 레이블을 추가적으로 보고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="345ea-119">예를 들어 SharePoint에서 새 팀 사이트를 만드는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-119">For example, when you create a new team site from SharePoint:</span></span>

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="345ea-121">이 미리 보기를 사용하고 레이블을 동기화</span><span class="sxs-lookup"><span data-stu-id="345ea-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="345ea-122">이 기능은 Azure AD 기능을 사용하므로 Azure AD 설명서의 지침에 따라 미리보기를 활성화하세요. [Azure Active Directory의 Office 365 그룹에 민감도 레이블 지정(미리보기)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="345ea-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="345ea-123">PowerShell 세션에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 보안 & 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="345ea-124">지침은 [Office 365 보안 및 규정 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-124">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="345ea-125">다음 명령을 실행하여 레이블을 Azure AD에 동기화하여 Office 365 그룹에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-125">Run the following commands to synchronize your labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="345ea-126">민감도 레이블을 만들거나 편집할 때 사이트 및 그룹 설정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="345ea-126">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="345ea-127">이제 사이트 및 그룹에 사용할 민감도 레이블을 만들거나 편집할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-127">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="345ea-128">미리보기를 활성화하면 민감도 레이블 마법사에서 새 페이지가 표시됩니다. **사이트 및 그룹 설정**</span><span class="sxs-lookup"><span data-stu-id="345ea-128">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="345ea-129">민감도 레이블 작성 또는 편집에 도움이 필요한 경우 [민감도 레이블 생성 및 구성](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)의 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-129">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="345ea-130">이 새 **사이트 및 그룹 설정** 페이지에서 다음과 같이 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-130">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="345ea-131">**Office 365 그룹에 연결된 팀 사이트의 개인 정보**: 기본 설정이 **공개**로 자동 선택되므로 조직의 모든 사용자가 이 레이블이 적용된 팀 사이트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-131">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="345ea-132">조직에서 승인된 구성원만 그룹의 팀 사이트에 액세스할 수 있도록 하려면 **비공개**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-132">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="345ea-133">이 옵션을 선택하면 그룹에 대해 구성할 수 있는 이전 개인 정보 설정을 대체하 고 개인 정보 보호 값을 잠가 팀 사이트 또는 그룹에서 민감도 레이블을 먼저 제거해야만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-133">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="345ea-134">민감도 레이블을 제거한 후에도 레이블의 개인 정보 설정이 유지되며 필요한 경우 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-134">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="345ea-135">**외부 사용자 액세스**: 그룹 소유자가 [그룹에 게스트를 추가](/office365/admin/create-groups/manage-guest-access-in-groups)할 수 있는지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-135">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="345ea-136">**관리되지 않는 장치**: [관리되지 않는 장치](/sharepoint/control-access-from-unmanaged-devices)의 경우 전체 액세스, 웹 전용 액세스를 허용하거나 액세스를 완벽하게 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-136">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![사이트 및 그룹 설정 탭](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="345ea-138">팀, 그룹 또는 사이트에 레이블을 적용할 때 이러한 사이트 및 그룹 설정만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-138">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="345ea-139">팀, 그룹 또는 사이트 내의 콘텐츠에는 암호화 및 콘텐츠 표시와 같은 다른 레이블 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-139">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="345ea-140">마찬가지로, 레이블을 만들고 이러한 사이트 및 그룹 설정을 켜지 않는 경우에는 사용자가 팀, 그룹 및 사이트를 만들 때 해당 레이블을 계속 사용할 수 있지만 오직 레이블 이름만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-140">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="345ea-141">레이블이 아직 게시되지 않은 경우 [레이블 정책에 추가](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)하여 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-141">If your label isn't already published, now publish it by [adding it to a label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="345ea-142">민감도 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="345ea-142">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="345ea-143">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에 사용하는 민감도 레이블 만들기, 수정 그리고 삭제는 사용자에게 레이블 정책을 게시하는데 케어 코디네이션을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-143">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="345ea-144">다음의 지침을 사용하여 모든 사용자에게 영향을 줄 수 있는 사이트 및 그룹에 대한 만들기 오류를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-144">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="345ea-145">**레이블 만들기 및 게시:**</span><span class="sxs-lookup"><span data-stu-id="345ea-145">**Creating and publishing labels:**</span></span>

<span data-ttu-id="345ea-146">민감도 레이블이 만들어지고 게시된 후 레이블이 팀, 그룹 및 사이트의 사용자에게 표시될 때까지는 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-146">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="345ea-147">다음의 단계를 사용하여 테넌트의 모든 사용자에 대한 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-147">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="345ea-148">민감도 레이블을 만들고 테넌트의 일부 사용자 계정에만 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-148">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="345ea-149">24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-149">Wait for 24 hours.</span></span>

3. <span data-ttu-id="345ea-150">24시간을 기다린 후에 1단계에서 지정한 사용자 계정 중 하나를 사용하여 1단계에서 만든 레이블이 있는 팀, Office 365 그룹 또는 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-150">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="345ea-151">3단계의 만들기 작업 중에 오류가 없으면 테넌트의 모든 사용자에게 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-151">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="345ea-152">오류가 있으면 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-152">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="345ea-153">**게시된 레이블 수정 및 삭제:**</span><span class="sxs-lookup"><span data-stu-id="345ea-153">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="345ea-154">하나 이상의 레이블 정책에 포함된 민감도 레이블을 수정하거나 삭제하는 경우, 이러한 작업의 수행은 모든 팀, 그룹 및 사이트에 대한 만들기 오류로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-154">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="345ea-155">이러한 상황을 방지하려면 다음의 지침을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-155">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="345ea-156">레이블이 포함된 모든 레이블 정책에서 민감도 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-156">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="345ea-157">48시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-157">Wait for 48 hours.</span></span>

3. <span data-ttu-id="345ea-158">48시간을 기다린 후에 팀, 그룹 또는 사이트 만들기를 시도해보고 해당 레이블이 더 이상 보이지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-158">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="345ea-159">민감도 레이블이 보이지 않는 경우에는 안전하게 레이블을 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-159">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="345ea-160">레이블이 계속 표시되면 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-160">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="345ea-161">Office 365 그룹에 민감도 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="345ea-161">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="345ea-162">이제 민감도 레이블을 Office 365 그룹에 적용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-162">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="345ea-163">Azure AD 문서로 돌아가서 다음 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-163">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="345ea-164">Azure 포털의 새 그룹에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="345ea-164">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="345ea-165">Azure 포털의 기존 그룹에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="345ea-165">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="345ea-166">[Azure 포털의 기존 그룹에서 레이블 제거](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="345ea-166">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="345ea-167">새 팀에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="345ea-167">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="345ea-168">사용자는 Microsoft Teams에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-168">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="345ea-169">사용자가 민감도 레이블을 선택할 때 개인 정보 설정이 필요에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-169">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="345ea-170">사용자가 레이블에 대해 선택한 외부 사용자 액세스 설정에 따라 조직 외부의 사용자를 팀에 추가할 수 있는지의 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-170">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="345ea-171">Teams용 민감도 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="345ea-171">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![새 팀을 만드는 경우 개인 정보 설정](../media/privacy-setting-new-team.png)

<span data-ttu-id="345ea-173">팀을 만든 후에는 모든 채널의 우측 상단 모서리에 민감도 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-173">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![민감도 레이블이 팀에 표시됩니다.](../media/privacy-setting-teams.png)

<span data-ttu-id="345ea-175">이 서비스는 Office 365 그룹 및 연결된 SharePoint 팀 사이트에 자동으로 동일한 민감도 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-175">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="345ea-176">웹용 Outlook의 새 그룹에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="345ea-176">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="345ea-177">웹용 Outlook에서 새 그룹을 만들 때 게시된 레이블에 대한 **민감도** 옵션을 선택하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-177">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![그룹 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="345ea-179">새 사이트에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="345ea-179">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="345ea-180">관리자 및 최종 사용자는 [최신 팀 사이트 및 커뮤니케이션 사이트를 만들](/sharepoint/create-site-collection) 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-180">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="345ea-181">사용자가 최신 팀 및 커뮤니케이션 사이트를 만들 때 기본적으로 민감도 레이블이 이미 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-181">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="345ea-182">사용자는 도움말 아이콘을 선택하여 레이블에 대한 더욱 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-182">Users can select the help icon to learn more about the labels.</span></span>

![사이트 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="345ea-184">사용자가 사이트로 이동할 때 레이블의 이름과 적용된 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-184">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![민감도 레이블이 적용된 사이트](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="345ea-186">SharePoint 관리 센터에서 민감도 레이블 보기</span><span class="sxs-lookup"><span data-stu-id="345ea-186">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="345ea-187">적용된 민감도 레이블을 보려면 새 SharePoint 관리 센터의 **활성 사이트** 페이지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-187">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="345ea-188">먼저 **민감도** 열을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-188">You might need to first add the **Sensitivity** column:</span></span>

![활성 사이트 페이지의 민감도 열](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="345ea-190">[새 SharePoint 관리 센터에서의 사이트 관리에 대해 자세히 알아보기](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="345ea-190">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="345ea-191">레이블의 사이트 및 그룹 설정 변경</span><span class="sxs-lookup"><span data-stu-id="345ea-191">Change site and group settings for a label</span></span>

<span data-ttu-id="345ea-192">레이블의 사이트 및 그룹 설정을 변경할 때마다 팀, 사이트, 그룹에서 새 설정을 사용할 수 있도록 다음 PowerShell 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-192">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="345ea-193">최상의 방법은 여러 팀, 그룹 또는 사이트에 레이블을 적용한 후 레이블의 사이트와 그룹 설정을 변경하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-193">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="345ea-194">다음 명령을 실행하여 Office 365 보안 & 규정 준수 센터 PowerShell에 연결한 후 민감도 레이블과 해당 Guid 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-194">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="345ea-195">사용자가 변경한 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-195">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="345ea-196">이제 Exchange Online PowerShell에 연결하여 Get-UnifiedGroup cmdlet을 실행하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-196">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="345ea-197">각 그룹에 대해 민감도 레이블을 다시 적용하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-197">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="345ea-198">민감도 레이블에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="345ea-198">Support for the sensitivity labels</span></span>

<span data-ttu-id="345ea-199">다음 앱 및 서비스에서 사이트 및 그룹 설정에 대해 구성한 민감도 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-199">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="345ea-200">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="345ea-200">SharePoint Online</span></span>
- <span data-ttu-id="345ea-201">Teams</span><span class="sxs-lookup"><span data-stu-id="345ea-201">Teams</span></span>
- <span data-ttu-id="345ea-202">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="345ea-202">Outlook on the web</span></span>
- <span data-ttu-id="345ea-203">SharePoint 관리 센터</span><span class="sxs-lookup"><span data-stu-id="345ea-203">SharePoint admin center</span></span>
- <span data-ttu-id="345ea-204">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="345ea-204">Azure AD admin center</span></span>

<span data-ttu-id="345ea-205">사이트 및 그룹 설정에 대해 구성한 민감도 레이블을 현재 사용할 수 없는 기타 앱 및 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-205">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="345ea-206">Mac용 Outlook</span><span class="sxs-lookup"><span data-stu-id="345ea-206">Outlook for the Mac</span></span>
- <span data-ttu-id="345ea-207">Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="345ea-207">Outlook mobile</span></span>
- <span data-ttu-id="345ea-208">Windows용 Outlook 데스크톱</span><span class="sxs-lookup"><span data-stu-id="345ea-208">Outlook desktop for Windows</span></span>
- <span data-ttu-id="345ea-209">양식</span><span class="sxs-lookup"><span data-stu-id="345ea-209">Forms</span></span>
- <span data-ttu-id="345ea-210">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="345ea-210">Dynamics 365</span></span>
- <span data-ttu-id="345ea-211">Yammer</span><span class="sxs-lookup"><span data-stu-id="345ea-211">Yammer</span></span>
- <span data-ttu-id="345ea-212">Stream</span><span class="sxs-lookup"><span data-stu-id="345ea-212">Stream</span></span>
- <span data-ttu-id="345ea-213">Planner</span><span class="sxs-lookup"><span data-stu-id="345ea-213">Planner</span></span>
- <span data-ttu-id="345ea-214">Project</span><span class="sxs-lookup"><span data-stu-id="345ea-214">Project</span></span>
- <span data-ttu-id="345ea-215">PowerBI</span><span class="sxs-lookup"><span data-stu-id="345ea-215">PowerBI</span></span>
- <span data-ttu-id="345ea-216">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="345ea-216">Teams admin center</span></span>
- <span data-ttu-id="345ea-217">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="345ea-217">Microsoft 365 admin center</span></span>
- <span data-ttu-id="345ea-218">Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="345ea-218">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="345ea-219">클래식 Azure AD 사이트 분류</span><span class="sxs-lookup"><span data-stu-id="345ea-219">Classic Azure AD site classification</span></span>

<span data-ttu-id="345ea-220">이 미리 보기를 사용하도록 설정하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대해 이전 분류를 더 이상 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-220">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="345ea-221">그러나 민감도 레이블을 사용하도록 변환하지 않는 한 기존 그룹 및 사이트는 여전히 이전 분류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-221">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="345ea-222">이전 분류에는 `ClassificationList` 설정에 대한 값을 정의한 Azure AD PowerShell 또는 PnP Core 라이브러리를 통해 설정하는 "최신" 사이트 분류가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-222">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="345ea-223">예를 들어 PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="345ea-223">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="345ea-224">이전 분류 방법에 대한 자세한 내용은 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-224">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="345ea-225">이전 분류를 민감도 레이블로 변환하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-225">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="345ea-226">기존 레이블 사용: 이미 게시된 기존 민감도 레이블을 편집하여 사이트 및 그룹에 대해 원하는 레이블 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-226">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="345ea-227">새 레이블 만들기: 기존 분류와 이름이 같은 새 민감도 레이블을 만들고 게시하여 사이트 및 그룹에 대해 원하는 레이블 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-227">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="345ea-228">그런 다음 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-228">Then:</span></span> 

1. <span data-ttu-id="345ea-229">이름 매핑과 함께 PowerShell을 사용하여 민감도 레이블을 기존 Office 365 그룹 및 SharePoint 사이트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-229">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="345ea-230">지침은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-230">See the next section for instructions.</span></span>

2. <span data-ttu-id="345ea-231">기존 그룹과 사이트에서 이전 분류를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-231">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="345ea-232">사용자가 아직 민감도 레이블을 지원하지 않는 앱과 서비스에서 새 그룹을 만들지 못하도록 할 수는 없지만, 반복적인 PowerShell 스크립트를 실행하여 사용자가 이전 분류로 만든 새 그룹을 찾고, 이러한 그룹을 민감도 레이블을 사용하도록 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-232">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="345ea-233">PowerShell을 사용하여 Office 365 그룹 분류를 민감도 레이블로 변환</span><span class="sxs-lookup"><span data-stu-id="345ea-233">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="345ea-234">SharePoint Online 관리 셸 버전 16.0.19418.12000 이상을 실행 중인지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-234">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="345ea-235">최신 버전을 이미 보유한 경우 4단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-235">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="345ea-236">PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행하여 모듈을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-236">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="345ea-237">Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거**로 이동하여 SharePoint Online 관리 셸을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-237">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="345ea-238">그런 다음 [다운로드 센터](https://go.microsoft.com/fwlink/p/?LinkId=255251)에서 최신 SharePoint Online 관리 셸을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-238">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="345ea-239">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한을 보유하는 회사 또는 학교 계정을 사용하여 SharePoint Online 관리 셸에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-239">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="345ea-240">자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-240">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="345ea-241">다음의 명령을 실행하여 민감도 레이블과 해당 GUID 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-241">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="345ea-242">Office 365 그룹에 적용할 민감도 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-242">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="345ea-243">다음 명령을 예로 사용하여 현재 "일반" 분류”를 포함하는 그룹 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-243">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="345ea-244">각 그룹에 새 민감도 레이블 GUID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-244">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="345ea-245">예:</span><span class="sxs-lookup"><span data-stu-id="345ea-245">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="345ea-246">민감도 레이블 활동 감사</span><span class="sxs-lookup"><span data-stu-id="345ea-246">Auditing sensitivity label activities</span></span>

<span data-ttu-id="345ea-247">누군가가 민감도 레이블로 보호된 사이트에 문서를 업로드하고 해당 문서에 사이트에 적용된 민감도 레이블보다 [높은 우선 순위](sensitivity-labels.md#label-priority-order-matters)의 레이블이 있는 경우 이 작업이 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-247">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="345ea-248">예를 들어 **일반** 레이블을 SharePoint 사이트에 적용하고 누군가가 이 사이트에 **기밀** 레이블이 지정된 문서를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-248">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="345ea-249">우선 순위가 높은 민감도 레이블은 우선 순위가 낮은 컨텐츠보다 민감도가 높은 컨텐츠를 먼저 식별하므로 이 상황은 보안상의 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-249">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="345ea-250">작업이 차단되는 것은 아니지만 감사가 진행되므로 레이블 우선 순위가 이처럼 잘못 정렬된 문서를 확인하고 필요한 경우 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-250">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="345ea-251">예를 들어 업로드된 문서를 사이트에서 삭제하거나 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-251">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="345ea-252">사이트에 적용된 민감도 레이블보다 우선 순위가 낮은 레이블이 문서에 지정되어 있다면 보안 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-252">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="345ea-253">예를 들어 **일반** 레이블이 지정된 문서가 **기밀** 레이블이 지정된 사이트에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-253">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="345ea-254">이 시나리오에서는 감사 이벤트가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-254">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="345ea-255">이 이벤트에 대한 감사 로그를 검색하려면 **파일 및 페이지 활동** 범주에서 **발견된 문서 감도 불일치**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-255">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="345ea-256">누군가가 사이트 또는 그룹에 민감도 레이블을 추가하거나 제거하는 경우에도 이러한 활동이 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-256">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="345ea-257">이러한 이벤트는 [민감도 레이블 활동](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 범주에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-257">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="345ea-258">감사 로그를 검색하기 위한 지침은 [보안 및 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-258">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="345ea-259">민감도 레이블 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="345ea-259">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="345ea-260">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 민감도 레이블에 문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="345ea-260">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="345ea-261">다음을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-261">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="345ea-262">게시 후 레이블이 보이지 않음</span><span class="sxs-lookup"><span data-stu-id="345ea-262">Labels not visible after publishing</span></span>
<span data-ttu-id="345ea-263">이 설정을 사용하도록 설정하거나 민감도 레이블의 설명을 수정한 후 팀 또는 Office 365 그룹을 만들 때 문제가 발생하는 경우 레이블 변경 내용을 저장하고 몇 시간을 기다린 후에 팀 또는 그룹을 다시 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-263">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="345ea-264">이에 대한 내용은 [민감도 레이블을 만들거나 변경한 후의 롤아웃 일정 예약](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-264">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="345ea-265">아직 SharePoint Online에서 새 민감도 레이블을 표시할 수 없는 경우 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="345ea-265">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="345ea-266">팀, 그룹 또는 SharePoint 사이트 만들기 오류</span><span class="sxs-lookup"><span data-stu-id="345ea-266">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="345ea-267">공개 미리 보기를 진행하는 동안 만들기 오류가 발생하는 경우 다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-267">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="345ea-268">모든 사용자에 대해 민감도 레이블이 필수가 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-268">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="345ea-269">[PowerShell에서 민감도 레이블 지원 활성화](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)와 동일한 지침을 사용하여 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에 대한 민감도 레이블을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-269">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="345ea-270">그러나 미리보기를 비활성화하려면 5단계에서 `$setting["EnableMIPLabels"] = "False"`을(를) 사용하여 기능을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="345ea-270">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

