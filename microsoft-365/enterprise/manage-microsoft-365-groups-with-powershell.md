---
title: PowerShell을 Microsoft 365 그룹 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: 이 문서에서는 PowerShell에서 Microsoft 365 관리 작업을 수행하는 방법을 설명합니다.
ms.openlocfilehash: 22bf4d1f3187746483d8d904378e675562a62142
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730561"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="e7e51-103">PowerShell을 Microsoft 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="e7e51-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="e7e51-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="e7e51-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e7e51-105">이 문서에서는 Microsoft PowerShell에서 그룹에 대한 일반적인 관리 작업을 수행하는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="e7e51-106">또한 그룹에 대한 PowerShell cmdlet을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="e7e51-107">사이트 관리에 대한 자세한 SharePoint [PowerShell을](/sharepoint/manage-team-and-communication-sites-in-powershell)사용하여 SharePoint 온라인 사이트 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7e51-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="e7e51-108">사용자 그룹 Microsoft 365 지침 링크</span><span class="sxs-lookup"><span data-stu-id="e7e51-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="e7e51-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e51-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="e7e51-110">사용자가 [조직에서 그룹을 만들거나 편집할 Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)조직의 사용 지침에 대한 링크를 표시하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="e7e51-111">예를 들어 그룹 이름에 특정 접두사나 접미사 추가가 필요한 경우</span><span class="sxs-lookup"><span data-stu-id="e7e51-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="e7e51-112">Azure AD(Azure Active Directory) PowerShell을 사용하여 사용자에게 조직의 조직 사용 지침을 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="e7e51-113">그룹 [Azure Active Directory 구성하기 위한 cmdlet을](/azure/active-directory/enterprise-users/groups-settings-cmdlets) 확인하고 디렉터리 수준에서 설정  만들기의 단계에 따라 사용 지침 하이퍼링크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="e7e51-114">AAD cmdlet을 실행하고 나면 사용자가 그룹에서 그룹을 만들거나 편집할 때 지침에 대한 링크가 Outlook.</span><span class="sxs-lookup"><span data-stu-id="e7e51-114">Once you run the AAD cmdlet, users will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![사용 지침 링크를 사용하여 새 그룹 만들기](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![그룹 사용 지침을 클릭하여 조직의 그룹 Office 365 확인](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="e7e51-117">사용자가 그룹으로 보내기 허용 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7e51-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="e7e51-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e51-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="e7e51-119">그룹에서 "다른 Microsoft 365 보내기"를 사용하도록 설정하려면 [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) 및 [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlet을 사용하여 이를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="e7e51-120">이 설정을 사용하도록 설정하면 Microsoft 365 사용자가 웹에서 Outlook 또는 Outlook 사용하여 전자 메일을 보내고 전자 메일 그룹에 회신할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="e7e51-121">사용자는 그룹으로 이동하여 새 전자 메일을 만들고 "다른 사람으로 보내기" 필드를 그룹의 전자 메일 주소로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="e7e51-122">(관리 센터에서 이 작업을 Exchange[있습니다.](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)</span><span class="sxs-lookup"><span data-stu-id="e7e51-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="e7e51-123">다음 스크립트를 사용하여 업데이트할 그룹의 별칭과 사용 권한을 부여할 사용자의 별칭으로 바랜 다음 스크립트를 *\<GroupAlias\>* *\<UserAlias\>* 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7e51-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="e7e51-124">[커넥트 실행하기 위해 Exchange Online PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="e7e51-125">cmdlet이 실행되면 사용자는 보낸 사람 필드에 그룹 전자 메일 주소를 추가하여 Outlook Outlook 또는 웹에서 그룹으로 보내기 위해 웹에서 사이트로 이동하거나 그룹으로 보낼 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e7e51-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="e7e51-126">조직에서 Microsoft 365 그룹에 대한 분류 만들기</span><span class="sxs-lookup"><span data-stu-id="e7e51-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="e7e51-127">조직의 사용자가 그룹을 만들 때 설정할 수 있는 민감도 레이블을 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="e7e51-128">그룹을 분류하려는 경우 이전 그룹 분류 기능 대신 민감도 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="e7e51-129">민감도 레이블 사용에 대한 자세한 내용은 민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint [사이트를 참조하세요.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="e7e51-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7e51-130">현재 분류 레이블을 사용하는 경우 민감도 레이블을 사용하도록 설정하면 그룹을 만드는 사용자가 더 이상 해당 레이블을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="e7e51-131">이전 그룹 분류 기능을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="e7e51-132">조직의 사용자가 그룹을 만들 때 설정할 수 있는 분류를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="e7e51-133">예를 들어 사용자가 만든 그룹에 대해 "표준", "비밀" 및 "최고 비밀"을 설정하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="e7e51-134">그룹 분류는 기본적으로 설정되지 않습니다. 사용자가 그룹 분류를 설정하려면 그룹 분류를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="e7e51-135">PowerShell을 Azure Active Directory 사용하여 사용자가 Microsoft 365 그룹에 대한 조직의 사용 지침을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="e7e51-136">그룹 [Azure Active Directory 구성하기 위한 Azure Active Directory cmdlet을](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) 확인하고 디렉터리 수준에서  설정 만들기의 단계에 따라 Microsoft 365 그룹에 대한 분류를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="e7e51-137">각 분류에 설명을 연결하려면 Settings 특성  *ClassificationDescriptions를* 사용하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="e7e51-138">여기서 Classification은 ClassificationList의 문자열과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="e7e51-139">예제:</span><span class="sxs-lookup"><span data-stu-id="e7e51-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="e7e51-140">위의 Azure Active Directory cmdlet을 실행하여 분류를 설정한 후 특정 그룹에 대한 분류를 설정하려는 경우 [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="e7e51-141">또는 분류를 사용하여 새 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="e7e51-142">PowerShell 사용에 대한 자세한 내용은 [PowerShell을](/powershell/exchange/exchange-online-powershell) Exchange Online 커넥트 [Exchange Online PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 사용하여 Exchange Online 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="e7e51-143">이러한 설정을 사용하도록 설정하면 그룹 소유자는 웹 및 웹 페이지의 Outlook 드롭다운 메뉴에서 분류를 선택하고 Outlook 편집 페이지에서 저장할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![그룹 Microsoft 365 선택](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="e7e51-145">전체 Microsoft 365 그룹 숨기기</span><span class="sxs-lookup"><span data-stu-id="e7e51-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="e7e51-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e51-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="e7e51-147">GAL(전체 주소 Microsoft 365) 및 조직의 기타 목록에 그룹이 나타나는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="e7e51-148">예를 들어 주소 목록에 표시하지 않는 법률 부서 그룹이 있는 경우 해당 그룹이 GAL에 나타나지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="e7e51-149">다음 Set-Unified 그룹 cmdlet을 실행하여 주소 목록에서 그룹을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="e7e51-150">내부 사용자만 그룹으로 메시지를 Microsoft 365 허용</span><span class="sxs-lookup"><span data-stu-id="e7e51-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="e7e51-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e51-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="e7e51-152">다른 조직의 사용자가 Microsoft 365 그룹으로 전자 메일을 보내지 못하게 하려는 경우 해당 그룹의 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="e7e51-153">내부 사용자만 그룹에 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="e7e51-154">외부 사용자가 해당 그룹에 메시지를 보내면 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="e7e51-155">Set-UnifiedGroup cmdlet을 실행하여 이 설정을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="e7e51-156">메일 그룹에 메일 Microsoft 365 추가</span><span class="sxs-lookup"><span data-stu-id="e7e51-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="e7e51-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e51-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="e7e51-158">보낸 사람이 Microsoft 365 그룹으로 전자 메일을 보내면 메일Tip을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="e7e51-159">그룹 Set-Unified 실행하여 그룹에 메일Tip을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="e7e51-160">메일Tip과 함께 메일Tip에 대한 추가 언어를 지정하는 MailTipTranslations를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="e7e51-161">스페인어 번역을 사용하려는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="e7e51-162">그룹의 표시 이름 Microsoft 365 변경</span><span class="sxs-lookup"><span data-stu-id="e7e51-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="e7e51-163">표시 이름은 그룹의 이름을 Microsoft 365 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="e7e51-164">이 이름은 Exchange 관리 센터 또는 exchange 관리 센터에서 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="e7e51-165">다음 명령을 실행하여 그룹의 표시 이름을 편집하거나 기존 Microsoft 365 그룹에 표시 이름을 할당할 Set-UnifiedGroup 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="e7e51-166">사용자에 대한 Microsoft 365 그룹의 기본 Outlook 또는 비공개로 변경</span><span class="sxs-lookup"><span data-stu-id="e7e51-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="e7e51-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e7e51-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="e7e51-168">Microsoft 365 그룹의 Outlook 기본적으로 비공개로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="e7e51-169">조직에서 기본적으로 Microsoft 365 그룹을 공개로 만들거나 다시 비공개로 만들 수 있도록 하려는 경우 다음 PowerShell cmdlet 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="e7e51-170">비공개로 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="e7e51-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="e7e51-171">설정을 확인하면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="e7e51-172">자세한 내용은 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) 및 [Get-OrganizationConfig를 참조합니다.](/powershell/module/exchange/get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="e7e51-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="e7e51-173">Microsoft 365 그룹 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e7e51-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="e7e51-174">다음 cmdlet은 그룹에서 사용할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="e7e51-175">**cmdlet 이름**</span><span class="sxs-lookup"><span data-stu-id="e7e51-175">**Cmdlet name**</span></span>|<span data-ttu-id="e7e51-176">**설명**</span><span class="sxs-lookup"><span data-stu-id="e7e51-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e7e51-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="e7e51-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="e7e51-178">이 cmdlet을 사용하여 기존 Microsoft 365 그룹을 조회하고 그룹 개체의 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="e7e51-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="e7e51-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="e7e51-180">Group에서 특정 속성 Microsoft 365 업데이트</span><span class="sxs-lookup"><span data-stu-id="e7e51-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="e7e51-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="e7e51-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="e7e51-182">새 그룹 Microsoft 365 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="e7e51-183">이 cmdlet은 최소한의 매개 변수 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="e7e51-184">확장 속성의 값을 설정하기 위해 새 Set-UnifiedGroup 다음에 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="e7e51-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="e7e51-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="e7e51-186">기존 그룹 Microsoft 365 삭제</span><span class="sxs-lookup"><span data-stu-id="e7e51-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="e7e51-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="e7e51-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="e7e51-188">그룹 구성원 자격 및 소유자 정보 Microsoft 365 검색</span><span class="sxs-lookup"><span data-stu-id="e7e51-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="e7e51-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="e7e51-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="e7e51-190">기존 그룹의 구성원, 소유자 및 구독자 Microsoft 365 추가</span><span class="sxs-lookup"><span data-stu-id="e7e51-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="e7e51-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="e7e51-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="e7e51-192">기존 그룹에서 소유자 및 Microsoft 365 제거</span><span class="sxs-lookup"><span data-stu-id="e7e51-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="e7e51-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="e7e51-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="e7e51-194">계정과 연결된 사용자 사진에 대한 정보를 보는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="e7e51-195">사용자 사진이 Active Directory에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="e7e51-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="e7e51-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="e7e51-197">사용자 사진을 계정과 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="e7e51-198">사용자 사진이 Active Directory에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e51-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="e7e51-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="e7e51-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="e7e51-200">그룹에서 사진 Microsoft 365 제거</span><span class="sxs-lookup"><span data-stu-id="e7e51-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="e7e51-201">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e7e51-201">Related topics</span></span>

[<span data-ttu-id="e7e51-202">메일 그룹을 Microsoft 365 업그레이드</span><span class="sxs-lookup"><span data-stu-id="e7e51-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="e7e51-203">Microsoft 365 그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="e7e51-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="e7e51-204">그룹에 대한 게스트 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="e7e51-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="e7e51-205">정적 그룹 구성원을 동적 인으로 변경</span><span class="sxs-lookup"><span data-stu-id="e7e51-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)
