---
title: PowerShell을 사용하여 Microsoft 365 그룹 관리
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
description: 이 문서에서는 PowerShell에서 Microsoft 365 그룹에 대한 일반 관리 작업을 수행하는 방법을 설명합니다.
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830618"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="fc94b-103">PowerShell을 사용하여 Microsoft 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="fc94b-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="fc94b-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="fc94b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fc94b-105">이 문서에서는 Microsoft PowerShell에서 그룹에 대한 일반 관리 작업을 수행하는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="fc94b-106">또한 그룹에 대한 PowerShell cmdlet을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="fc94b-107">SharePoint 사이트 관리에 대한 자세한 내용은 [PowerShell을 사용하여 SharePoint Online 사이트 관리를 참조하세요.](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="fc94b-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="fc94b-108">Microsoft 365 그룹 사용 지침 링크</span><span class="sxs-lookup"><span data-stu-id="fc94b-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="fc94b-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="fc94b-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="fc94b-110">사용자가 [Outlook에서](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)그룹을 만들거나 편집할 때 조직의 사용 지침에 대한 링크를 표시하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="fc94b-111">예를 들어 그룹 이름에 특정 접두사나 접미사를 추가해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fc94b-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="fc94b-112">Azure AD(Azure Active Directory) PowerShell을 사용하여 Microsoft 365 그룹에 대한 조직의 사용 지침을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="fc94b-113">그룹 설정을 구성하기 위한 [Azure Active Directory cmdlet을](https://go.microsoft.com/fwlink/?LinkID=827484)  확인하고 디렉터리 수준에서 설정 만들기의 단계에 따라 사용 지침 하이퍼링크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="fc94b-114">AAD cmdlet을 실행하면 Outlook에서 그룹을 만들거나 편집할 때 지침에 대한 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![사용 지침 링크를 사용하여 새 그룹 만들기](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![그룹 사용 지침을 클릭하여 조직 Office 365 그룹 지침 확인](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="fc94b-117">사용자가 Microsoft 365 그룹으로 보내기 허용</span><span class="sxs-lookup"><span data-stu-id="fc94b-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="fc94b-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="fc94b-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="fc94b-119">Microsoft 365 그룹에서 "다른 사람으로 보내기"를 사용하도록 설정하려면 [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) 및 [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlet을 사용하여 이를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="fc94b-120">이 설정을 사용하면 Microsoft 365 그룹 사용자는 웹용 Outlook 또는 Outlook을 사용하여 Microsoft 365 그룹으로 전자 메일을 보내고 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="fc94b-121">사용자는 그룹으로 이동하여 새 전자 메일을 만들고 "다른 사람으로 보내기" 필드를 그룹의 전자 메일 주소로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="fc94b-122">(Exchange[관리 센터에서](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)이 작업을 할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="fc94b-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="fc94b-123">다음 스크립트를 사용하여 업데이트할 그룹의 별칭과 사용 권한을 부여할 사용자의 별칭으로 바랜 다음 스크립트를 *\<GroupAlias\>* *\<UserAlias\>* 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc94b-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="fc94b-124">[Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 연결하여 이 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="fc94b-125">cmdlet이 실행되면 사용자는 보낸 사람 필드에 그룹 전자 메일 주소를 추가하여 웹에서 Outlook 또는 Outlook으로 이동하여 그룹으로 보낼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="fc94b-126">조직에서 Microsoft 365 그룹에 대한 분류 만들기</span><span class="sxs-lookup"><span data-stu-id="fc94b-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="fc94b-127">조직의 사용자가 Microsoft 365 그룹을 만들 때 설정할 수 있는 민감도 레이블을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="fc94b-128">그룹을 분류하려는 경우 이전 그룹 분류 기능 대신 민감도 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="fc94b-129">민감도 레이블 사용에 대한 자세한 내용은 민감도 레이블을 사용하여 [Microsoft Teams, Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)그룹 및 SharePoint 사이트의 콘텐츠를 보호하세요.</span><span class="sxs-lookup"><span data-stu-id="fc94b-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc94b-130">현재 분류 레이블을 사용하는 경우 민감도 레이블을 사용하도록 설정하면 그룹을 만드는 사용자가 더 이상 해당 레이블을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="fc94b-131">이전 그룹 분류 기능을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="fc94b-132">조직의 사용자가 Microsoft 365 그룹을 만들 때 설정할 수 있는 분류를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="fc94b-133">예를 들어 사용자가 만든 그룹에 대해 "표준", "비밀" 및 "최고 비밀"을 설정하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="fc94b-134">그룹 분류는 기본적으로 설정되지 않습니다. 사용자가 그룹 분류를 설정하려면 그룹 분류를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="fc94b-135">Azure Active Directory PowerShell을 사용하여 Microsoft 365 그룹에 대한 조직의 사용 지침을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="fc94b-136">그룹 설정을 구성하기 위한 [Azure Active Directory cmdlet을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)  확인하고 디렉터리 수준에서 설정 만들기의 단계에 따라 Microsoft 365 그룹에 대한 분류를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="fc94b-137">각 분류에 설명을 연결하기 위해  *ClassificationDescriptions* 설정 특성을 사용하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="fc94b-138">여기서 분류는 ClassificationList의 문자열과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="fc94b-139">예제:</span><span class="sxs-lookup"><span data-stu-id="fc94b-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="fc94b-140">위의 Azure Active Directory cmdlet을 실행하여 분류를 설정한 후 특정 그룹에 대한 분류를 설정하려는 경우 [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="fc94b-141">또는 분류를 사용하여 새 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="fc94b-142">Exchange [Online에서 PowerShell을](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) 사용하고 [Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 연결하여 Exchange Online PowerShell 사용에 대한 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc94b-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="fc94b-143">이러한 설정을 사용하도록 설정하면 그룹 소유자는 웹에서 Outlook 및 Outlook의 드롭다운 메뉴에서 분류를 선택하고 그룹 편집 페이지에서 저장할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Microsoft 365 그룹 분류 선택](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="fc94b-145">전체 주소 목록에서 Microsoft 365 그룹을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="fc94b-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fc94b-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fc94b-147">조직의 GAL(전체 주소 목록) 및 기타 목록에 Microsoft 365 그룹을 표시하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="fc94b-148">예를 들어 주소 목록에 표시하지 않는 법률 부서 그룹이 있는 경우 해당 그룹이 GAL에 나타나지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="fc94b-149">Set-Unified 그룹 cmdlet을 실행하여 주소 목록에서 그룹을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="fc94b-150">내부 사용자만 Microsoft 365 그룹에 메시지를 보낼 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="fc94b-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="fc94b-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fc94b-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fc94b-152">다른 조직의 사용자가 Microsoft 365 그룹에 전자 메일을 보내지 못하게 하려는 경우 해당 그룹의 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="fc94b-153">내부 사용자만 그룹에 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="fc94b-154">외부 사용자가 해당 그룹에 메시지를 보내면 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="fc94b-155">다음 Set-UnifiedGroup cmdlet을 실행하여 이 설정을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="fc94b-156">Microsoft 365 그룹에 메일Tips 추가</span><span class="sxs-lookup"><span data-stu-id="fc94b-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="fc94b-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fc94b-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fc94b-158">보낸 사람이 Microsoft 365 그룹에 전자 메일을 보내고자 할 때마다 메일Tip을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="fc94b-159">Set-Unified 그룹 cmdlet을 실행하여 그룹에 메일Tip을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="fc94b-160">메일Tip과 함께 메일Tip에 대한 추가 언어를 지정하는 MailTipTranslations를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="fc94b-161">스페인어 번역을 사용하려는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="fc94b-162">Microsoft 365 그룹의 표시 이름 변경</span><span class="sxs-lookup"><span data-stu-id="fc94b-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="fc94b-163">표시 이름은 Microsoft 365 그룹의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="fc94b-164">Exchange 관리 센터 또는 Microsoft 365 관리 센터에서 이 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="fc94b-165">다음 명령을 실행하여 그룹의 표시 이름을 편집하거나 기존 Microsoft 365 그룹에 표시 이름을 Set-UnifiedGroup 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="fc94b-166">Outlook용 Microsoft 365 그룹의 기본 설정 변경</span><span class="sxs-lookup"><span data-stu-id="fc94b-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="fc94b-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fc94b-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fc94b-168">Outlook의 Microsoft 365 그룹은 기본적으로 비공개로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="fc94b-169">조직에서 Microsoft 365 그룹을 기본적으로 공용(또는 비공개로)으로 만들 수 있도록 하려는 경우 다음 PowerShell cmdlet 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="fc94b-170">비공개로 설정:</span><span class="sxs-lookup"><span data-stu-id="fc94b-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="fc94b-171">설정을 확인하면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="fc94b-172">자세한 내용은 [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) 및 [Get-OrganizationConfig를 참조합니다.](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="fc94b-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="fc94b-173">Microsoft 365 그룹 cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc94b-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="fc94b-174">다음 cmdlet은 Microsoft 365 그룹과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="fc94b-175">**cmdlet 이름**</span><span class="sxs-lookup"><span data-stu-id="fc94b-175">**Cmdlet name**</span></span>|<span data-ttu-id="fc94b-176">**설명**</span><span class="sxs-lookup"><span data-stu-id="fc94b-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fc94b-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="fc94b-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="fc94b-178">이 cmdlet을 사용하여 기존 Microsoft 365 그룹을 조회하고 그룹 개체의 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="fc94b-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="fc94b-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="fc94b-180">특정 Microsoft 365 그룹의 속성 업데이트</span><span class="sxs-lookup"><span data-stu-id="fc94b-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fc94b-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="fc94b-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="fc94b-182">새 Microsoft 365 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="fc94b-183">이 cmdlet은 최소한의 매개 변수 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="fc94b-184">확장 속성에 대한 값을 설정하는 Set-UnifiedGroup 그룹을 만들고 나면 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="fc94b-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="fc94b-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="fc94b-186">기존 Microsoft 365 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="fc94b-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fc94b-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="fc94b-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="fc94b-188">Microsoft 365 그룹에 대한 구성원 및 소유자 정보 검색</span><span class="sxs-lookup"><span data-stu-id="fc94b-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fc94b-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="fc94b-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="fc94b-190">기존 Microsoft 365 그룹에 구성원, 소유자 및 구독자 추가</span><span class="sxs-lookup"><span data-stu-id="fc94b-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="fc94b-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="fc94b-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="fc94b-192">기존 Microsoft 365 그룹에서 소유자 및 구성원 제거</span><span class="sxs-lookup"><span data-stu-id="fc94b-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fc94b-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="fc94b-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="fc94b-194">계정과 연결된 사용자 사진에 대한 정보를 보는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="fc94b-195">사용자 사진이 Active Directory에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="fc94b-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="fc94b-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="fc94b-197">사용자 사진을 계정과 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="fc94b-198">사용자 사진이 Active Directory에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc94b-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="fc94b-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="fc94b-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="fc94b-200">Microsoft 365 그룹의 사진 제거</span><span class="sxs-lookup"><span data-stu-id="fc94b-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="fc94b-201">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fc94b-201">Related topics</span></span>

[<span data-ttu-id="fc94b-202">메일 그룹을 Microsoft 365 그룹으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="fc94b-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="fc94b-203">Microsoft 365 그룹을 만들 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="fc94b-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="fc94b-204">Microsoft 365 그룹에 대한 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="fc94b-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="fc94b-205">정적 그룹 구성원을 동적 인으로 변경</span><span class="sxs-lookup"><span data-stu-id="fc94b-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
