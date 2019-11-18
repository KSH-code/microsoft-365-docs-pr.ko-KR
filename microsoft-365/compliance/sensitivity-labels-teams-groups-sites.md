---
title: Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블 사용 (공개 미리 보기)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 레이블을 적용할 수 있습니다.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687171"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="4af80-103">Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블 사용 (공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="4af80-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="4af80-104">[Microsoft 365 준수 센터](https://protection.office.com/)에서 민감도 레이블을 만들 때는 이제 microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 해당 우편물을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="4af80-105">다음과 같이 레이블에 정책을 연결 하 여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="4af80-106">공용/개인 설정</span><span class="sxs-lookup"><span data-stu-id="4af80-106">Public/private settings</span></span>
- <span data-ttu-id="4af80-107">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="4af80-107">Guest access</span></span>
- <span data-ttu-id="4af80-108">관리 되지 않는 장치에서 액세스</span><span class="sxs-lookup"><span data-stu-id="4af80-108">Access from unmanaged devices</span></span>

<span data-ttu-id="4af80-109">팀 또는 그룹에 레이블을 적용 하면 연결 된 SharePoint 팀 사이트 및 기타 방식으로 레이블이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="4af80-110">이제 SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="4af80-111">[자세한 정보](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="4af80-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="4af80-112">Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 대 한 공개 미리 보기</span><span class="sxs-lookup"><span data-stu-id="4af80-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="4af80-113">Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 대 한 민감도 레이블은 테 넌 트에 점진적으로 롤아웃 되며 최종 릴리스 전에 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

## <a name="overview"></a><span data-ttu-id="4af80-114">개요</span><span class="sxs-lookup"><span data-stu-id="4af80-114">Overview</span></span>

<span data-ttu-id="4af80-115">민감도 레이블을 게시할 때 Office 365의 사용자에 게 동일한 레이블 목록에 대 한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-115">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="4af80-116">표시 되는 이미지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-116">These images show:</span></span>

- <span data-ttu-id="4af80-117">SharePoint에서 새 팀 사이트를 만들 때 목록이 표시 되는 방식</span><span class="sxs-lookup"><span data-stu-id="4af80-117">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="4af80-118">Word에서 목록을 볼 때</span><span class="sxs-lookup"><span data-stu-id="4af80-118">When you view the list in Word</span></span>

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](media/sensitivity-label-new-team-site.png)

![Word 데스크톱 앱에 표시 되는 민감도 레이블](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="4af80-121">Azure PowerShell을 사용 하 여이 미리 보기 사용</span><span class="sxs-lookup"><span data-stu-id="4af80-121">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="4af80-122">Azure PowerShell을 사용 하 여 Azure에 전역 관리자로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-122">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="4af80-123">자세한 내용은 [Azure PowerShell을 사용 하 여 로그인](/powershell/azure/authenticate-azureps)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4af80-123">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4af80-124">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-124">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="4af80-125">이 미리 보기를 사용 하도록 설정 하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대 한 이전 분류를 더 이상 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-125">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="4af80-126">[AZURE AD 사이트 분류](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting ["ClassificationList"])를 사용 하는 경우 기존 그룹 및 사이트에서 이전 분류를 계속 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-126">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="4af80-127">새 분류를 표시 하려면 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-127">To display the new classifications, convert them.</span></span> <span data-ttu-id="4af80-128">이를 변환 하는 방법에 대 한 자세한 내용은 [클래식 AZURE AD 사이트 분류를 사용 하는지](#if-you-used-classic-azure-ad-site-classification)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4af80-128">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span>

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a><span data-ttu-id="4af80-129">민감도 레이블을 만들 때 사이트 및 그룹 설정 설정</span><span class="sxs-lookup"><span data-stu-id="4af80-129">Set site and group settings when you create sensitivity labels</span></span>

<span data-ttu-id="4af80-130">미리 보기를 사용 하도록 설정한 후에는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-130">After you enable the preview, follow these steps:</span></span>

1. <span data-ttu-id="4af80-131">Microsoft 365 준수 센터에서 **분류** > **민감도 레이블을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-131">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="4af80-132">**레이블 만들기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-132">Select **Create a label**.</span></span>

3. <span data-ttu-id="4af80-133">원하는 옵션을 선택 하 고 **사이트 및 그룹 설정** 탭에서 다음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-133">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="4af80-134">개인 정보 보호 (공개/개인): 비공개 란 조직에서 승인 된 구성원만이 그룹 내의 내용을 볼 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-134">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="4af80-135">조직의 다른 사용자가 그룹의 내용을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-135">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="4af80-136">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4af80-136">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="4af80-137">게스트 액세스: 게스트를 그룹에 추가할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-137">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="4af80-138">Office 365 그룹에서 게스트 액세스 관리에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4af80-138">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="4af80-139">관리 되지 않는 장치:이 설정을 사용 하면 Intune에서 하이브리드 AD가 연결 되어 있지 않거나 호환 되지 않는 장치에서 SharePoint 콘텐츠에 대 한 액세스를 차단 하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-139">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="4af80-140">관리 되지 않는 장치를 선택 하는 경우에는 Azure AD로 이동 하 여 정책 설정을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-140">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="4af80-141">자세한 내용은 [관리 되지 않는 장치에서의 액세스 제어](/sharepoint/control-access-from-unmanaged-devices)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4af80-141">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![사이트 및 그룹 설정 탭](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="4af80-143">팀, 그룹 또는 사이트에 레이블을 적용 하는 경우에만 사이트 및 그룹 설정만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-143">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="4af80-144">암호화 및 콘텐츠 표시와 같은 다른 설정은 팀, 그룹 또는 사이트 내의 모든 콘텐츠에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-144">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="4af80-145">마찬가지로 레이블을 만들고 사이트 및 그룹 설정을 사용 하지 않는 경우에도 사용자가 팀, 그룹 및 사이트를 만들 때도 레이블을 사용할 수 있지만 사용자가이를 적용할 때 어떤 작업을 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-145">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="4af80-146">민감도 레이블을 게시 하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="4af80-146">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="4af80-147">새 팀에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="4af80-147">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="4af80-148">사용자는 Microsoft 팀에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-148">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="4af80-149">민감도 수준을 선택 하면 개인 정보 설정이 필요에 따라 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-149">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="4af80-150">레이블에 대해 선택한 게스트 액세스 설정에 따라 사용자가 조직 외부의 사용자를 팀에 추가할 수 있거나 추가 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-150">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![새 팀을 만들 때의 개인 정보 설정](media/privacy-setting-new-team.png)

<span data-ttu-id="4af80-152">팀을 만든 후에는 민감도 레이블이 모든 채널의 오른쪽 위 모서리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-152">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![팀에 민감도 레이블이 표시 됩니다.](media/privacy-setting-teams.png)

<span data-ttu-id="4af80-154">이 서비스는 Office 365 그룹 및 연결 된 SharePoint 팀 사이트에 동일한 민감도 레이블을 자동으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-154">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="4af80-155">새 그룹에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="4af80-155">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="4af80-156">웹용 Outlook에서 새 **우편물 종류** 상자에는 게시 된 레이블이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-156">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="4af80-157">사용자가 추가 정보를 원하는 경우 도움말 아이콘을 클릭 하 여 사용 가능한 레이블과 연결 된 정책에 대 한 세부 정보를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-157">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![그룹 만들기 및 민감도에서 옵션 선택](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="4af80-159">새 사이트에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="4af80-159">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="4af80-160">관리자 및 최종 사용자가 최신 팀 사이트 및 통신 사이트를 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-160">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="4af80-161">새 SharePoint 관리 센터에서 사이트를 만드는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-161">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="4af80-162">사용자가 최신 팀 및 커뮤니케이션 사이트를 만들 때 우편물 종류 레이블은 기본적으로 이미 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-162">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="4af80-163">사용자가 도움말 아이콘을 선택 하 여 레이블에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-163">Users can select the help icon to learn more about the labels.</span></span>

![사이트 만들기 및 민감도에서 옵션 선택](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="4af80-165">사용자가 사이트를 탐색할 때 레이블 이름 및 적용 된 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-165">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![민감도 레이블이 적용 된 사이트](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="4af80-167">SharePoint 관리 센터에서 민감도 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="4af80-167">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="4af80-168">레이블을 보고 편집 하려면 새 SharePoint 관리 센터에서 활성 사이트 페이지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-168">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![활성 사이트 페이지의 민감도 열](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="4af80-170">[새 SharePoint 관리 센터에서 사이트를 관리 하는 방법에 대해 자세히 알아보세요](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4af80-170">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="4af80-171">레이블에 대 한 사이트 및 그룹 설정 변경</span><span class="sxs-lookup"><span data-stu-id="4af80-171">Change site and group settings for a label</span></span>

<span data-ttu-id="4af80-172">여러 팀, 그룹 또는 사이트에 레이블을 적용 한 후에는 설정을 변경 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-172">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="4af80-173">변경을 수행 해야 하는 경우 Azure AD PowerShell 스크립트를 사용 하 여 업데이트를 수동으로 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-173">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="4af80-174">이 메서드를 사용 하면 모든 기존 팀, 사이트 및 그룹이 새 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-174">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="4af80-175">새 민감도 레이블 지원</span><span class="sxs-lookup"><span data-stu-id="4af80-175">Support for the new sensitivity labels</span></span>

<span data-ttu-id="4af80-176">다음 앱 및 서비스는이 미리 보기에서 민감도 레이블을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-176">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="4af80-177">Microsoft 365 규정 준수 센터</span><span class="sxs-lookup"><span data-stu-id="4af80-177">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="4af80-178">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4af80-178">SharePoint</span></span>
- <span data-ttu-id="4af80-179">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="4af80-179">Outlook on the web</span></span>
- <span data-ttu-id="4af80-180">Teams</span><span class="sxs-lookup"><span data-stu-id="4af80-180">Teams</span></span>
- <span data-ttu-id="4af80-181">SharePoint 관리 센터</span><span class="sxs-lookup"><span data-stu-id="4af80-181">SharePoint admin center</span></span>
- <span data-ttu-id="4af80-182">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="4af80-182">Azure AD admin center</span></span>

<span data-ttu-id="4af80-183">다음 앱 및 서비스를 사용 하 여 새 민감도 레이블로 Office 365 그룹을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-183">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="4af80-184">Mac 용 Outlook</span><span class="sxs-lookup"><span data-stu-id="4af80-184">Outlook for the Mac</span></span>
- <span data-ttu-id="4af80-185">Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="4af80-185">Outlook mobile</span></span>  
- <span data-ttu-id="4af80-186">Windows 용 Outlook 데스크톱</span><span class="sxs-lookup"><span data-stu-id="4af80-186">Outlook desktop for Windows</span></span>
- <span data-ttu-id="4af80-187">양식</span><span class="sxs-lookup"><span data-stu-id="4af80-187">Forms</span></span>  
- <span data-ttu-id="4af80-188">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4af80-188">Dynamics 365</span></span>  
- <span data-ttu-id="4af80-189">Yammer</span><span class="sxs-lookup"><span data-stu-id="4af80-189">Yammer</span></span>  
- <span data-ttu-id="4af80-190">Stream</span><span class="sxs-lookup"><span data-stu-id="4af80-190">Stream</span></span>  
- <span data-ttu-id="4af80-191">Planner</span><span class="sxs-lookup"><span data-stu-id="4af80-191">Planner</span></span>  
- <span data-ttu-id="4af80-192">Project</span><span class="sxs-lookup"><span data-stu-id="4af80-192">Project</span></span>  
- <span data-ttu-id="4af80-193">PowerBI</span><span class="sxs-lookup"><span data-stu-id="4af80-193">PowerBI</span></span>  
- <span data-ttu-id="4af80-194">팀 관리 센터</span><span class="sxs-lookup"><span data-stu-id="4af80-194">Teams admin center</span></span>  
- <span data-ttu-id="4af80-195">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="4af80-195">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="4af80-196">Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="4af80-196">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="4af80-197">클래식 Azure AD 사이트 분류를 사용한 경우</span><span class="sxs-lookup"><span data-stu-id="4af80-197">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="4af80-198">이 미리 보기를 사용 하도록 설정 하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대 한 이전 분류를 더 이상 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-198">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="4af80-199">그러나 기존 그룹과 사이트는 변환 하지 않는 한 이전 분류를 계속 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-199">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="4af80-200">이전 분류에는 설정 값 `ClassificationList` 을 정의 하는 Azure AD PowerShell 또는 PnP 핵심 라이브러리를 통해 설정한 "최신" 사이트 분류가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-200">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="4af80-201">예를 들어 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4af80-201">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="4af80-202">이전 분류 방법에 대 한 자세한 내용은 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4af80-202">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="4af80-203">현재 배포에 따라 이전 분류를 새 분류로 변환 하는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-203">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="4af80-204">파일 및 전자 메일에 대해 민감도 레이블 (통합 Microsoft Information Protection 레이블)을 사용 하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="4af80-204">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="4af80-205">따라서 다음 작업이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-205">We recommend that you:</span></span>

1. <span data-ttu-id="4af80-206">Microsoft 365 준수 센터에서 기존 분류와 이름이 같은 새 민감도 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-206">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="4af80-207">PowerShell을 사용 하 여 새 레이블을 이름 매핑을 사용 하 여 기존 Office 365 그룹 및 SharePoint 사이트에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-207">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="4af80-208">이전 분류를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-208">Delete the old classifications.</span></span>

<span data-ttu-id="4af80-209">새 민감도 레이블을 지 원하는 앱 및 서비스에서 해당 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-209">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="4af80-210">새 레이블을 사용 하 여 팀, 그룹 및 사이트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-210">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="4af80-211">사용자는 새 레이블을 지원 하지 않는 앱 및 서비스에서 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-211">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="4af80-212">그러나 사용자는 이러한 그룹에 레이블을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-212">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="4af80-213">PowerShell을 사용 하 여 이러한 그룹에 새 민감도 레이블을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-213">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="4af80-214">이전 분류를 유지할 수 있습니다. 그러나 PowerShell을 사용 하 여 이러한 그룹에 새 민감도 레이블을 적용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-214">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="4af80-215">새 민감도 레이블을 지 원하는 앱 및 서비스가 새 레이블로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-215">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="4af80-216">사용자가 새 레이블을 지원 하지 않는 앱 및 서비스에서 그룹을 만들 때는 분류를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-216">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="4af80-217">파일 및 전자 메일에 민감도 레이블 (통합 Microsoft Information Protection labels)을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4af80-217">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="4af80-218">이 미리 보기를 사용 하도록 설정 하는 즉시 Microsoft 365 준수 센터의 각 레이블로 이동 하 여 사이트 및 그룹에 대해 원하는 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-218">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="4af80-219">사용자는 사이트 및 그룹에 사용할 수 있는 기존 레이블을 확인 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-219">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="4af80-220">Office 365 그룹을 relabel 하기 전에 SharePoint Online 관리 셸 준비</span><span class="sxs-lookup"><span data-stu-id="4af80-220">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="4af80-221">새 레이블을 적용 하기 전에 최신 SharePoint Online 관리 셸을 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-221">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="4af80-222">최신 버전을 이미 사용 하 고 있는 경우 [Relabel Office 365 그룹을 새 민감도 레이블로](#relabel-office-365-groups-with-new-sensitivity-labels)이동 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-222">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="4af80-223">미리 보기에 대해 SharePoint Online 관리 셸을 준비 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-223">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="4af80-224">이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 "SharePoint Online 관리 셸"을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-224">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="4af80-225">웹 브라우저에서 다운로드 센터 페이지로 이동 하 [여 최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-225">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="4af80-226">언어를 선택 하 고 **다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-226">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="4af80-227">X64 파일과 x86 .msi 파일 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-227">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="4af80-228">64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-228">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="4af80-229">알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system)을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4af80-229">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="4af80-230">파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-230">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="4af80-231">새 민감도 레이블이 있는 Relabel Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="4af80-231">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="4af80-232">최신 버전의 SharePoint Online 관리 셸을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-232">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="4af80-233">자세한 내용은 [Office 365 그룹을 relabel 하기 전에 SharePoint Online 관리 셸 준비](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4af80-233">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="4af80-234">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint Online 관리 셸에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-234">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="4af80-235">자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4af80-235">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="4af80-236">다음 명령을 실행 하 여 민감도 레이블 및 해당 Guid의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-236">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="4af80-237">덮어쓸 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-237">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="4af80-238">예를 들면 "일반" 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-238">For example, the "General" label.</span></span>

5. <span data-ttu-id="4af80-239">다음 명령을 사용 하 여 "General" 분류를 포함 하는 그룹 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-239">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="4af80-240">이 명령을 실행 하면 Exchange Online PowerShell에 연결 하 여 Remove-unifiedgroup cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-240">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="4af80-241">각 그룹에 대해 새 민감도 레이블 GUID를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af80-241">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
