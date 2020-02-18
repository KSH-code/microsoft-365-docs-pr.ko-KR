---
title: Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용
f1.keywords:
- NOCSH
ms.author: krowley
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
ms.openlocfilehash: 297ccd3e17f6c5a747e18a46747e6f2c23311df0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069828"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="27561-103">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="27561-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="27561-104">[Microsoft 365 준수 센터](https://protection.office.com/)에서 민감도 레이블을 만들 때 이제 레이블을 Microsoft Teams, Office 365 그룹 그리고 SharePoint 사이트에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="27561-105">사용자는 정책을 레이블과 연결하여 다음을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="27561-106">공개/비공개 설정</span><span class="sxs-lookup"><span data-stu-id="27561-106">Public/private settings</span></span>
- <span data-ttu-id="27561-107">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="27561-107">Guest access</span></span>
- <span data-ttu-id="27561-108">관리되지 않는 장치에서 액세스</span><span class="sxs-lookup"><span data-stu-id="27561-108">Access from unmanaged devices</span></span>

<span data-ttu-id="27561-109">팀 또는 그룹에 레이블을 적용하는 경우 레이블은 자동으로 연결된 SharePoint 팀 사이트로 적용되고 그 반대로 적용되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="27561-110">사용자는 이제 또한 SharePoint 및 OneDrive에서 Office 파일에 민감도 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-110">You can now also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="27561-111">자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-111">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="27561-112">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 공개 미리 보기에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="27561-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="27561-113">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 민감도 레이블은 테넌트에 점진적으로 배포되고 있으며 최종 출시 전에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="27561-114">이 공개 미리 보기는 Office 365 Content Delivery Network(CDNs)에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="27561-115">개요</span><span class="sxs-lookup"><span data-stu-id="27561-115">Overview</span></span>

<span data-ttu-id="27561-116">민감도 레이블을 게시할 때 Office 365의 사용자는 같은 레이블 목록에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="27561-117">이 이미지들은 다음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-117">These images show:</span></span>

- <span data-ttu-id="27561-118">SharePoint에서 새 팀 사이트를 만들 때 목록이 표시되는 방식</span><span class="sxs-lookup"><span data-stu-id="27561-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="27561-119">Word에서 목록을 볼 때</span><span class="sxs-lookup"><span data-stu-id="27561-119">When you view the list in Word</span></span>

<span data-ttu-id="27561-120">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="27561-120">For example:</span></span>

![SharePoint에서 팀 사이트를 만들 때의 민감도 레이블](../media/sensitivity-label-new-team-site.png)

![Word 데스크톱 앱에 표시되는 민감도 레이블](../media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a><span data-ttu-id="27561-123">이 미리 보기를 사용</span><span class="sxs-lookup"><span data-stu-id="27561-123">Enable this preview</span></span>

<span data-ttu-id="27561-124">사용자는 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트를 사용하여 이 민감도 레이블의 미리 보기를 사용하도록 설정하려면 [그래프용 Azure Directory PowerShell(AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)(모듈 이름 **AzureADPreview**)의 미리 보기 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-124">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

- <span data-ttu-id="27561-125">이전에 Azure AD PowerShell 모듈의 어떠한 버전도 설치하지 않은 경우 [Azure AD 모듈 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)를 참조하고 지침에 따라 공개 미리 보기 릴리스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-125">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="27561-126">AzureAD(Azure AD PowerShell 모듈)의 2.0 일반 가용성 버전을 설치한 경우에는 PowerShell 세션에서 `Uninstall-Module AzureAD`를 실행하여 제거를 하고 `Install-Module AzureADPreview`를 실행하여 미리 보기 버전을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-126">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="27561-127">미리 보기 버전을 이미 설치한 경우에는 `Install-Module AzureADPreview`를 실행하여 이 모듈의 최신 버전인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-127">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="27561-128">이제 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에서 민감도 레이블의 미리 보기를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-128">You're now ready to enable the preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

1. <span data-ttu-id="27561-129">PowerShell 세션에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 Azure Active Directory에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-129">In a PowerShell session, using a work or school account that has global admin privileges, connect to Azure Active Directory.</span></span> <span data-ttu-id="27561-130">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-130">For example, run:</span></span>
    
    ```powershell
    Connect-AzureAD
    ````
    
    <span data-ttu-id="27561-131">자세한 지침은 [Azure AD에 연결](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-131">For full instructions, see [Connect to Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span></span>

2. <span data-ttu-id="27561-132">다음의 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-132">Run the following commands:</span></span>
    
    ```powershell
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
    
    > [!NOTE]
    > <span data-ttu-id="27561-133">이 미리 보기를 사용하도록 설정하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대해 이전의 분류를 더 이상 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-133">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="27561-134">[Azure AD 사이트 분류](/sharepoint/dev/solution-guidance/modern-experience-site-classification)($setting ["ClassificationList"])를 사용한 경우 기존 그룹과 사이트에서는 여전히 이전의 분류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-134">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="27561-135">새 분류를 표시하려면 전환을 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-135">To display the new classifications, convert them.</span></span> <span data-ttu-id="27561-136">전환하는 방법에 대한 내용은 [클래식 Azure AD 사이트 분류를 사용한 경우](#if-you-used-classic-azure-ad-site-classification)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-136">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

3. <span data-ttu-id="27561-137">동일한 PowerShell 세션에서 이제 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 보안 & 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-137">In the same PowerShell session, now connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="27561-138">지침은 [Office 365 보안 및 규정 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-138">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

4. <span data-ttu-id="27561-139">다음 명령을 실행하여 레이블을 Azure AD에 동기화하여 Office 365 그룹에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-139">Run the following commands to synchronize your labels to Azure AD, so that they can used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="27561-140">민감도 레이블을 만들거나 편집할 때 사이트 및 그룹 설정을 지정</span><span class="sxs-lookup"><span data-stu-id="27561-140">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="27561-141">미리 보기를 사용하도록 설정한 후 다음 단계를 사용하여 민감도 레이블을 만들거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-141">After you enable the preview, use the following steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="27561-142">레이블이 이미 정의되어 있는 경우에도 새 민감도 레이블이 사이트 및 그룹과 작동하려면 다음의 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-142">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="27561-143">이러한 설정에 대한 변경은 동기화하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-143">Changes to these settings might take up to 24 hours to synchronize.</span></span>

1. <span data-ttu-id="27561-144">Microsoft 365 규정 준수 센터에서 **분류** > **민감도 레이블**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-144">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="27561-145">**레이블 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-145">Select **Create a label**.</span></span> <span data-ttu-id="27561-146">이미 레이블이 있으면 다음 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="27561-146">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="27561-147">원하는 옵션을 선택한 다음 **사이트 및 그룹 설정** 탭에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-147">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>
    
    - <span data-ttu-id="27561-148">개인 정보(공개/비공개): 비공개는 조직에서 승인된 구성원만 그룹 내부의 내용을 볼 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-148">Privacy (Public/Private): Private means that only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="27561-149">조직의 그 외의 사람은 그룹 내부의 내용을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-149">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="27561-150">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="27561-150">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="27561-151">게스트 액세스: 사용자는 그룹에 게스트를 추가할 수 있는지를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-151">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="27561-152">Office 365 그룹에서의 게스트 액세스 관리에 대해 알아보세요</span><span class="sxs-lookup"><span data-stu-id="27561-152">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="27561-153">관리되지 않는 장치: 이 설정을 사용하면 Intune에서 하이브리드 AD에 참가하지 않았거나 비규격인 장치에서의 SharePoint 콘텐츠로의 액세스를 차단하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-153">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="27561-154">관리되지 않는 장치를 선택하는 경우 Azure AD로 이동하여 정책 설정을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-154">If you select Unmanaged devices, you must go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="27561-155">관련 정보는 [관리되지 않는 장치에서 액세스 제어](/sharepoint/control-access-from-unmanaged-devices)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-155">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>
    
    ![사이트 및 그룹 설정 탭](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="27561-157">팀, 그룹 또는 사이트에 레이블을 적용하는 경우에는 사이트 및 그룹 설정만 적용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-157">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="27561-158">암호화 및 콘텐츠 표시와 같은 다른 설정은 팀, 그룹 또는 사이트 내의 모든 콘텐츠에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-158">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="27561-159">마찬가지로, 레이블을 만들고 사이트 및 그룹 설정을 켜지 않는 경우에는 사용자가 팀, 그룹 및 사이트를 만들 때 해당 레이블을 계속 사용할 수 있지만 설정을 적용하지 않고 분류를 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-159">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it will classify without applying any settings.</span></span>

[<span data-ttu-id="27561-160">민감도 레이블 게시에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="27561-160">Learn more about publishing sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a><span data-ttu-id="27561-161">민감도 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="27561-161">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="27561-162">Microsoft Teams, Office 365 그룹 및 SharePoint 사이트에 사용하는 민감도 레이블 만들기, 수정 그리고 삭제는 사용자에게 레이블 정책을 게시하는데 케어 코디네이션을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-162">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="27561-163">다음의 지침을 사용하여 모든 사용자에게 영향을 줄 수 있는 사이트 및 그룹에 대한 만들기 오류를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-163">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="27561-164">**레이블 만들기 및 게시:**</span><span class="sxs-lookup"><span data-stu-id="27561-164">**Creating and publishing labels:**</span></span>

<span data-ttu-id="27561-165">민감도 레이블이 만들어지고 게시된 후 레이블이 팀, 그룹 및 사이트의 사용자에게 표시될 때까지는 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-165">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="27561-166">다음의 단계를 사용하여 테넌트의 모든 사용자에 대한 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-166">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="27561-167">민감도 레이블을 만들고 테넌트의 일부 사용자 계정에만 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-167">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="27561-168">24시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="27561-168">Wait for 24 hours.</span></span>

3. <span data-ttu-id="27561-169">24시간을 기다린 후에 1단계에서 지정한 사용자 계정 중 하나를 사용하여 1단계에서 만든 레이블이 있는 팀, Office 365 그룹 또는 SharePoint 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27561-169">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="27561-170">3단계의 만들기 작업 중에 오류가 없으면 테넌트의 모든 사용자에게 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-170">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="27561-171">오류가 있으면 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-171">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="27561-172">**게시된 레이블 수정 및 삭제:**</span><span class="sxs-lookup"><span data-stu-id="27561-172">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="27561-173">하나 이상의 레이블 정책에 포함된 민감도 레이블을 수정하거나 삭제하는 경우, 이러한 작업의 수행은 모든 팀, 그룹 및 사이트에 대한 만들기 오류로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-173">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="27561-174">이러한 상황을 방지하려면 다음의 지침을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-174">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="27561-175">레이블이 포함된 모든 레이블 정책에서 민감도 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-175">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="27561-176">48시간을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="27561-176">Wait for 48 hours.</span></span>

3. <span data-ttu-id="27561-177">48시간을 기다린 후에 팀, 그룹 또는 사이트 만들기를 시도해보고 해당 레이블이 더 이상 보이지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-177">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="27561-178">민감도 레이블이 보이지 않는 경우에는 안전하게 레이블을 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-178">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="27561-179">레이블이 계속 표시되면 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-179">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="27561-180">민감도 레이블 배포 문제 해결</span><span class="sxs-lookup"><span data-stu-id="27561-180">Troubleshoot sensitivity label deployment</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="27561-181">게시 후 레이블이 보이지 않음</span><span class="sxs-lookup"><span data-stu-id="27561-181">Labels not visible after publishing</span></span>
<span data-ttu-id="27561-182">이 설정을 사용하도록 설정하거나 민감도 레이블의 설명을 수정한 후 팀 또는 Office 365 그룹을 만들 때 문제가 발생하는 경우 레이블을 저장하고 몇 시간을 기다린 후에 팀 또는 그룹을 다시 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="27561-182">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, save the label, wait a few hours, and then try to create the team or group again.</span></span> <span data-ttu-id="27561-183">이에 대한 내용은 [민감도 레이블을 만들거나 변경한 후의 롤아웃 일정 예약](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-183">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="27561-184">아직 SharePoint Online에서 새 민감도 레이블을 표시할 수 없는 경우 [Microsoft 지원 센터](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-184">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="27561-185">팀, 그룹 또는 SharePoint 사이트 만들기 오류</span><span class="sxs-lookup"><span data-stu-id="27561-185">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="27561-186">공개 미리 보기를 진행하는 동안 만들기 오류가 발생하는 경우 다음과 같은 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-186">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="27561-187">모든 사용자에 대해 민감도 레이블이 필수가 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-187">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="27561-188">이 페이지의 [이 미리 보기를 사용](#enable-this-preview) 섹션에서와 동일한 지침을 사용하여 Microsoft Teams, Office 365 그룹 및 SharePoint 사이트의 민감도 레이블을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-188">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from the [Enable this preview](#enable-this-preview) section on this page.</span></span> <span data-ttu-id="27561-189">그러나 미리 보기를 사용하지 않도록 설정하려면 회선 `$setting["EnableMIPLabels"] = "True"`을 검색하고 **True**값을 **False**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-189">However, to disable the preview, search for the line `$setting["EnableMIPLabels"] = "True"`, and change the **True** value to **False**.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="27561-190">새 팀에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="27561-190">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="27561-191">사용자는 Microsoft Teams에서 새 팀을 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-191">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="27561-192">사용자가 민감도 레이블을 선택할 때 개인 정보 설정이 필요에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-192">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="27561-193">사용자가 레이블에 대해 선택한 게스트 액세스 설정에 따라 조직 외부의 사용자를 팀에 추가할 수 있는지의 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-193">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="27561-194">Teams용 민감도 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="27561-194">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![새 팀을 만드는 경우 개인 정보 설정](../media/privacy-setting-new-team.png)

<span data-ttu-id="27561-196">팀을 만든 후에는 모든 채널의 우측 상단 모서리에 민감도 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-196">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![민감도 레이블이 팀에 표시됩니다.](../media/privacy-setting-teams.png)

<span data-ttu-id="27561-198">이 서비스는 Office 365 그룹 및 연결된 SharePoint 팀 사이트에 자동으로 동일한 민감도 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-198">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="27561-199">새 그룹에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="27561-199">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="27561-200">웹용 Outlook에서 새 **민감도** 상자에는 게시된 레이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-200">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="27561-201">사용자가 추가 정보를 원하는 경우 도움말 아이콘을 클릭하여 사용 가능한 레이블과 관련 정책에 대한 세부 정보를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-201">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![그룹 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="27561-203">새 사이트에 민감도 레이블을 적용</span><span class="sxs-lookup"><span data-stu-id="27561-203">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="27561-204">관리자 및 최종 사용자는 최신 팀 사이트 및 커뮤니케이션 사이트를 만들 때 민감도 레이블을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-204">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="27561-205">새 SharePoint 관리 센터에서 사이트 만드는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="27561-205">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="27561-206">사용자가 최신 팀 및 커뮤니케이션 사이트를 만들 때 기본적으로 민감도 레이블이 이미 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-206">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="27561-207">사용자는 도움말 아이콘을 선택하여 레이블에 대한 더욱 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-207">Users can select the help icon to learn more about the labels.</span></span>

![사이트 만들기 및 민감도 아래의 옵션 선택](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="27561-209">사용자가 사이트로 이동할 때 레이블의 이름과 적용된 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-209">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![민감도 레이블이 적용된 사이트](../media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="27561-211">SharePoint 관리 센터에서 민감도 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="27561-211">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="27561-212">레이블을 보고 편집하려면 새 SharePoint 관리 센터의 활성 사이트 페이지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-212">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![활성 사이트 페이지의 민감도 열](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="27561-214">[새 SharePoint 관리 센터에서의 사이트 관리에 대해 자세히 알아보기](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="27561-214">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="27561-215">레이블의 사이트 및 그룹 설정 변경</span><span class="sxs-lookup"><span data-stu-id="27561-215">Change site and group settings for a label</span></span>

<span data-ttu-id="27561-216">레이블의 사이트 및 그룹 설정을 변경할 때마다 팀, 사이트, 그룹에서 새 설정을 사용할 수 있도록 다음 PowerShell 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-216">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="27561-217">최상의 방법은 여러 팀, 그룹 또는 사이트에 레이블을 적용한 후 레이블의 사이트와 그룹 설정을 변경하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27561-217">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="27561-218">다음 명령을 실행하여 Office 365 보안 & 규정 준수 센터 PowerShell에 연결한 후 민감도 레이블과 해당 Guid 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27561-218">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="27561-219">사용자가 변경한 레이블의 GUID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="27561-219">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="27561-220">이제 Exchange Online PowerShell에 연결하여 Get-UnifiedGroup cmdlet을 실행하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-220">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="27561-221">각 그룹에 대해 민감도 레이블을 다시 적용하고 예제 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" 대신에 레이블 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-221">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="27561-222">새 민감도 레이블에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="27561-222">Support for the new sensitivity labels</span></span>

<span data-ttu-id="27561-223">다음의 앱과 서비스는 이 미리 보기에서 민감도 레이블을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-223">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="27561-224">Microsoft 365 규정 준수 센터</span><span class="sxs-lookup"><span data-stu-id="27561-224">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="27561-225">SharePoint</span><span class="sxs-lookup"><span data-stu-id="27561-225">SharePoint</span></span>
- <span data-ttu-id="27561-226">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="27561-226">Outlook on the web</span></span>
- <span data-ttu-id="27561-227">Teams</span><span class="sxs-lookup"><span data-stu-id="27561-227">Teams</span></span>
- <span data-ttu-id="27561-228">SharePoint 관리 센터</span><span class="sxs-lookup"><span data-stu-id="27561-228">SharePoint admin center</span></span>
- <span data-ttu-id="27561-229">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="27561-229">Azure AD admin center</span></span>

<span data-ttu-id="27561-230">다음과 같은 앱과 서비스를 사용하여 새 민감도 레이블이 있는 Office 365 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-230">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="27561-231">Mac용 Outlook</span><span class="sxs-lookup"><span data-stu-id="27561-231">Outlook for the Mac</span></span>
- <span data-ttu-id="27561-232">Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="27561-232">Outlook mobile</span></span>  
- <span data-ttu-id="27561-233">Windows용 Outlook 데스크톱</span><span class="sxs-lookup"><span data-stu-id="27561-233">Outlook desktop for Windows</span></span>
- <span data-ttu-id="27561-234">양식</span><span class="sxs-lookup"><span data-stu-id="27561-234">Forms</span></span>  
- <span data-ttu-id="27561-235">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="27561-235">Dynamics 365</span></span>  
- <span data-ttu-id="27561-236">Yammer</span><span class="sxs-lookup"><span data-stu-id="27561-236">Yammer</span></span>  
- <span data-ttu-id="27561-237">Stream</span><span class="sxs-lookup"><span data-stu-id="27561-237">Stream</span></span>  
- <span data-ttu-id="27561-238">Planner</span><span class="sxs-lookup"><span data-stu-id="27561-238">Planner</span></span>  
- <span data-ttu-id="27561-239">Project</span><span class="sxs-lookup"><span data-stu-id="27561-239">Project</span></span>  
- <span data-ttu-id="27561-240">PowerBI</span><span class="sxs-lookup"><span data-stu-id="27561-240">PowerBI</span></span>  
- <span data-ttu-id="27561-241">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="27561-241">Teams admin center</span></span>  
- <span data-ttu-id="27561-242">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="27561-242">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="27561-243">Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="27561-243">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="27561-244">클래식 Azure AD 사이트 분류를 사용한 경우</span><span class="sxs-lookup"><span data-stu-id="27561-244">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="27561-245">이 미리 보기를 사용하도록 설정하면 Office 365에서 새 그룹 및 SharePoint 사이트에 대해 이전의 분류를 더 이상 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-245">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="27561-246">그러나 기존의 그룹과 사이트는 이전 분류를 변환하지 않는 한 계속 표시를 합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-246">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="27561-247">이전 분류에는 `ClassificationList` 설정에 대한 값을 정의한 Azure AD PowerShell 또는 PnP Core 라이브러리를 통해 설정하는 "최신" 사이트 분류가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-247">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="27561-248">예를 들어 PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="27561-248">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="27561-249">이전 분류 방법에 대한 자세한 내용은 [SharePoint "최신" 사이트 분류](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-249">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="27561-250">현재의 배포에 따라 이전의 분류를 새 분류로 변환하기 위한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-250">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="27561-251">파일 및 전자 메일에 대해 민감도 레이블(통합 Microsoft 정보 보호 레이블)을 전혀 사용하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="27561-251">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="27561-252">다음의 작업을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-252">We recommend that you:</span></span>

1. <span data-ttu-id="27561-253">Microsoft 365 준수 센터에서 기존의 분류와 이름이 같은 새 민감도 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27561-253">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="27561-254">PowerShell을 사용하여 새 레이블을 이름 매핑을 사용하여 기존의 Office 365 그룹 및 SharePoint 사이트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-254">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="27561-255">이전의 분류를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-255">Delete the old classifications.</span></span>

<span data-ttu-id="27561-256">새 민감도 레이블을 지원하는 앱 및 서비스에서 해당 항목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-256">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="27561-257">새 레이블과 같이 새 팀, 그룹 및 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27561-257">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="27561-258">사용자는 새 레이블을 지원하지 않는 앱 및 서비스에서 계속해서 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-258">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="27561-259">그러나 사용자는 이 그룹에 레이블을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-259">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="27561-260">PowerShell을 사용하여 이 그룹에 새 민감도 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-260">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="27561-261">사용자는 이전의 분류를 유지할 수 있지만 PowerShell을 사용하여 이러한 그룹에 새 민감도 레이블을 적용할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-261">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="27561-262">새 민감도 레이블을 지원하는 앱 및 서비스가 새 레이블과 함께 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="27561-262">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="27561-263">사용자는 새 레이블을 지원하지 않는 앱 및 서비스에서 그룹을 만들 때 분류를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-263">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="27561-264">파일 및 전자 메일에 대해 민감도 레이블(통합 Microsoft 정보 보호 레이블)을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="27561-264">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="27561-265">이 미리 보기를 사용하도록 설정하는 즉시 Microsoft 365 준수 센터의 각 레이블로 이동하여 사이트 및 그룹에 원하는 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-265">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="27561-266">사용자는 사이트 및 그룹에 대해 사용할 수 있는 기존 레이블을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27561-266">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="27561-267">Office 365 그룹의 레이블을 변경하기 전에 SharePoint Online 관리 셸을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-267">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="27561-268">새 레이블을 적용하기 전에 최신 SharePoint Online 관리 셸을 실행하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-268">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="27561-269">이미 최신 버전을 사용하고 있는 경우 [새 민감도 레이블로 Office 365 그룹의 레이블 변경 ](#relabel-office-365-groups-with-new-sensitivity-labels)을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27561-269">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="27561-270">미리 보기를 위한 SharePoint Online 관리 셸을 준비하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-270">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="27561-271">이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거**로 이동하여 "SharePoint Online 관리 셸"을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-271">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="27561-272">웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-272">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="27561-273">언어를 선택한 다음 **다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-273">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="27561-274">X64 및 x86 .msi 파일 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-274">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="27561-275">64비트 버전의 Windows를 실행하는 경우 x64 파일을 혹은 32비트 버전을 실행하는 경우 x86 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-275">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="27561-276">버전을 모르는 경우에는 [어떠한 Windows 운영 체제 버전을 실행 중인가요?](https://support.microsoft.com/help/13443/windows-which-operating-system)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-276">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="27561-277">파일을 다운로드한 후 실행을 하고 설정 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="27561-277">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="27561-278">새 민감도 레이블로 Office 365 그룹의 레이블을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-278">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="27561-279">최신 버전의 SharePoint Online 관리 셸을 사용 하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-279">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="27561-280">이에 대한 지침은 [Office 365 그룹의 레이블을 변경하기 전에 SharePoint Online 관리 셸을 준비](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-280">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="27561-281">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한을 보유하는 회사 또는 학교 계정을 사용하여 SharePoint Online 관리 셸에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-281">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="27561-282">자세한 방법은 [SharePoint Online 관리 셸 시작](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27561-282">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="27561-283">다음의 명령을 실행하여 민감도 레이블과 해당 GUID 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27561-283">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="27561-284">덮어쓸 레이블의 GUID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-284">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="27561-285">예를 들면 "일반" 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="27561-285">For example, the "General" label.</span></span>

5. <span data-ttu-id="27561-286">다음의 명령을 사용하여 "일반" 분류를 포함하는 그룹의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27561-286">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="27561-287">이 명령을 실행하는 경우 Exchange Online PowerShell에 연결하고 Get-unifiedGroup cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-287">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="27561-288">각 그룹에 새 민감도 레이블 GUID를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27561-288">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
