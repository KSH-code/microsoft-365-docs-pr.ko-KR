---
title: SharePoint, OneDrive 및 Microsoft Teams에 대해 안전한 첨부 파일 설정
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 관리자는 검색된 파일에 대한 알림을 설정하는 금고, SharePoint, OneDrive 및 Microsoft Teams 설정하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083095"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="becb8-103">SharePoint, OneDrive 및 Microsoft Teams에 대해 안전한 첨부 파일 설정</span><span class="sxs-lookup"><span data-stu-id="becb8-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="becb8-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="becb8-104">**Applies to**</span></span>
- [<span data-ttu-id="becb8-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="becb8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="becb8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="becb8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="becb8-107">Microsoft Defender for Office 365 for SharePoint, OneDrive 및 Microsoft Teams 악의적인 파일을 공유하지 못하게 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="becb8-108">자세한 내용은 금고, SharePoint 및 OneDrive 첨부 [Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="becb8-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="becb8-109">이 문서에는 SharePoint, 파일 및 금고 첨부 파일을 사용하도록 설정하고 구성하는 OneDrive 단계가 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="becb8-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="becb8-110">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="becb8-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="becb8-111"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="becb8-112">첨부 파일 금고 **직접 이동하기 위해 를** 를 니다. <https://security.microsoft.com/safeattachmentv2></span><span class="sxs-lookup"><span data-stu-id="becb8-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="becb8-113">금고, SharePoint, OneDrive 및 Microsoft Teams에 대한 첨부 파일을 설정하려면 Microsoft 365 Defender 포털에서 **조직** 관리 또는 보안 관리자  역할 그룹의 구성원 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="becb8-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="becb8-114">자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="becb8-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="becb8-115">SharePoint Online PowerShell을 사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지하려면 [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) Azure AD에서 전역 관리자 또는 SharePoint 관리자 역할의 구성원이 되어야 합니다. [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)</span><span class="sxs-lookup"><span data-stu-id="becb8-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="becb8-116">조직에 대해 감사 로깅이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="becb8-117">자세한 내용은 [감사 로그 검색 설정 및 해제](../../compliance/turn-audit-log-search-on-or-off.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="becb8-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="becb8-118">설정이 적용되는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="becb8-119">1단계: Microsoft 365 Defender 포털을 사용하여 금고, SharePoint, OneDrive 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="becb8-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="becb8-120">Microsoft 365 Defender 포털에서 정책 &  \>  \>  정책 \> **섹션에서 금고 로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="becb8-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="becb8-121">첨부 **금고 페이지에서** 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="becb8-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="becb8-122">전역 **설정** 플라이아웃이 나타나면 파일 보호 섹션으로 **SharePoint,** OneDrive 및 Microsoft Teams 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="becb8-123">Office 365, **SharePoint,** OneDrive 및 Microsoft Teams 금고에 대한 Defender 켜기 토글을 오른쪽 토글로 이동하여 SharePoint, OneDrive 및 ![ ](../../media/scc-toggle-on.png) Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="becb8-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="becb8-124">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="becb8-125">PowerShell Exchange Online 사용하여 금고 OneDrive, SharePoint 및 SharePoint 첨부 파일을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="becb8-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="becb8-126">PowerShell을 사용하여 금고, SharePoint, OneDrive 및 Microsoft Teams [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) 연결하고 Exchange Online 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="becb8-127">구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="becb8-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="becb8-128">2단계: (권장) SharePoint Online PowerShell을 사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지</span><span class="sxs-lookup"><span data-stu-id="becb8-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="becb8-129">기본적으로 금고 사용자는 SharePoint, 파일 및 파일에 대한 첨부 파일에서 검색된 악성 파일을 열거나 이동, 복사 또는 SharePoint <sup>\*</sup> 수 OneDrive Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="becb8-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="becb8-130">그러나 악성 파일을 삭제하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="becb8-131"><sup>\*</sup> 사용자가 액세스 **관리로 이동하면** **공유 옵션을** 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="becb8-132">사용자가 악성 파일을 다운로드하지 못하게 SharePoint [Online PowerShell에 연결하고 다음](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="becb8-133">**참고:**</span><span class="sxs-lookup"><span data-stu-id="becb8-133">**Notes**:</span></span>

- <span data-ttu-id="becb8-134">이 설정은 사용자와 관리자 모두에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="becb8-135">사람들은 여전히 악성 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-135">People can still delete malicious files.</span></span>

<span data-ttu-id="becb8-136">구문과 매개 변수에 대한 자세한 내용은 [Set-SPOTenant 를 참조하십시오.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="becb8-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="becb8-137">3단계(권장) Microsoft 365 Defender 포털을 사용하여 검색된 파일에 대한 경고 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="becb8-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="becb8-138">첨부 파일에서 악의적인 파일을 감지하는 금고 첨부 파일을 SharePoint OneDrive 관리자에게 알리는 Microsoft Teams 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="becb8-139">경고에 대한 자세한 내용은 Microsoft 365 Defender 포털에서 활동 [경고 만들기를 참조합니다.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="becb8-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="becb8-140">Microsoft 365 Defender 포털에서 정책 정책 & **경고** \> **정책으로 이동하거나 을 를** 열 수 <https://security.microsoft.com/alertpolicies> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="becb8-141">경고 **정책 페이지에서** 새 경고 **정책 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="becb8-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="becb8-142">새 **경고 정책 마법사가** 플라이아웃에서 열립니다. 경고 **이름 지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="becb8-143">**이름:** 고유하고 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="becb8-144">예를 들어 라이브러리의 악성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="becb8-145">**설명:** 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="becb8-146">예를 들어 SharePoint Online, OneDrive 또는 파일에서 악성 파일이 검색되면 관리자에게 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="becb8-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="becb8-147">**심각도:** **드롭다운 목록에서 낮음,** 중간 또는 높음을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="becb8-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="becb8-148">**범주:** 드롭다운 **목록에서** 위협 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="becb8-149">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="becb8-150">경고 **설정 만들기 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="becb8-151">**어떤 것을 경고하고 싶나요?** 섹션 \> **활동은** \> 드롭다운 **목록에서** 파일에서 검색된 맬웨어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="becb8-152">**경고를 트리거하는** 방법 섹션: 활동이 선택한 규칙과 일치할 때마다 **기본값을 그대로** 떠 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="becb8-153">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="becb8-154">받는 **사람 설정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="becb8-155">전자 **메일 알림 보내기가 선택되어 있는지** 확인</span><span class="sxs-lookup"><span data-stu-id="becb8-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="becb8-156">전자 메일 받는 사람 **상자에서** 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="becb8-157">**일별 알림 제한:** 기본값 제한 **없음을 선택된 그대로** 떠습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="becb8-158">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="becb8-159">설정 **검토 페이지에서** 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="becb8-160">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="becb8-161">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="becb8-162">정책을 **바로** 켜시겠습니까? 섹션에서 기본값 **Yes, turn it on right away selected(기본값 예, 바로 켜기)를 선택된 것으로 떠났습니다.**</span><span class="sxs-lookup"><span data-stu-id="becb8-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="becb8-163">완료되면 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="becb8-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="becb8-164">보안 및 & PowerShell을 사용하여 검색된 파일에 대한 경고 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="becb8-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="becb8-165">PowerShell을 사용하여 이전 섹션에 설명된 동일한 경고 정책을 만들 경우 보안 & 준수 센터 [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 연결하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="becb8-166">**참고:** 기본 _심각도 값은_ Low입니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="becb8-167">Medium 또는 High를 지정하기 위해 _명령에 Severity_ 매개 변수와 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="becb8-168">구문과 매개 변수에 대한 자세한 내용은 [New-ActivityAlert 를 참조하십시오.](/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="becb8-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="becb8-169">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="becb8-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="becb8-170">금고, OneDrive 및 Microsoft Teams SharePoint 첨부 파일이 설정되어 있는지 확인 Microsoft Teams 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="becb8-171">Microsoft 365 Defender 포털에서 정책 & **규칙** 위협 정책 섹션금고 첨부 \>  \>  \> **파일,** 전역 설정 을 선택하고 Office 365,  OneDrive 및 Microsoft Teams SharePoint 설정에 대한 Office 365에 대한 Defender 켜기 Microsoft Teams 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="becb8-172">PowerShell을 Exchange Online 다음 명령을 실행하여 속성 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="becb8-173">구문과 매개 변수에 대한 자세한 내용은 [Get-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="becb8-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="becb8-174">사용자가 악성 파일을 다운로드하지 못하게 차단하는지 확인하려면 SharePoint Online PowerShell을 열고 다음 명령을 실행하여 속성 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="becb8-175">구문과 매개 변수에 대한 자세한 내용은 [Get-SPOTenant 를 참조하십시오.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="becb8-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="becb8-176">검색된 파일에 대해 경고 정책을 성공적으로 구성한지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="becb8-177">Microsoft 365 Defender 포털에서 정책 & 규칙  경고 정책으로 이동하여 경고 정책을 선택하고 설정을 \>  \> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="becb8-178">Microsoft 365 Defender 포털 PowerShell에서 경고 정책의 이름으로 바꾸고 다음 명령을 실행하고 속성 값을 \<AlertPolicyName\> 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="becb8-179">구문과 매개 변수에 대한 자세한 내용은 [Get-ActivityAlert 를 참조하십시오.](/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="becb8-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="becb8-180">위협 [방지 상태 보고서를](view-email-security-reports.md#threat-protection-status-report) 사용하여 검색된 파일에 대한 정보를 SharePoint, OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="becb8-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="becb8-181">특히 다음을 사용하여 데이터 보기: 콘텐츠 맬웨어 **\> 보기를 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb8-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
