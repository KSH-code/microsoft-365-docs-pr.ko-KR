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
description: 관리자는 검색된 파일에 대한 경고를 설정하는 방법을 포함하여 SharePoint, OneDrive 및 Microsoft Teams 설정하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 07aea9551faa280cd51bda1d57f017e0a24028ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206139"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0ba28-103">SharePoint, OneDrive 및 Microsoft Teams에 대해 안전한 첨부 파일 설정</span><span class="sxs-lookup"><span data-stu-id="0ba28-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ba28-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="0ba28-104">**Applies to**</span></span>
- [<span data-ttu-id="0ba28-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="0ba28-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ba28-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ba28-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0ba28-107">Microsoft Defender for Office 365 for SharePoint, OneDrive 및 Microsoft Teams 악의적인 파일을 공유하지 못하게 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="0ba28-108">자세한 내용은 SharePoint, OneDrive 및 에 대한 안전한 첨부 [Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0ba28-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="0ba28-109">이 문서에는 보안, 설정 및 관리에 대해 안전한 첨부 SharePoint OneDrive Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ba28-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0ba28-110">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0ba28-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0ba28-111"><https://protection.office.com>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="0ba28-112">ATP 안전한 첨부 파일 페이지로 직접 **이동하기** 위해 를 를 니다. <https://protection.office.com/safeattachmentv2></span><span class="sxs-lookup"><span data-stu-id="0ba28-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="0ba28-113">SharePoint, OneDrive 및 Microsoft Teams 안전 첨부 파일을 설정하려면 보안 및 준수 센터에서 조직  관리  또는 보안 관리자 역할 그룹의 구성원 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="0ba28-114">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ba28-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0ba28-115">SharePoint Online PowerShell을 사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지하려면 [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) Azure AD에서 전역 관리자 또는 SharePoint 관리자 역할의 구성원이 되어야 합니다. [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)</span><span class="sxs-lookup"><span data-stu-id="0ba28-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="0ba28-116">조직에 대해 감사 로깅이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="0ba28-117">자세한 내용은 [감사 로그 검색 설정 및 해제](../../compliance/turn-audit-log-search-on-or-off.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ba28-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="0ba28-118">설정이 적용되는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0ba28-119">1단계: 보안 & 준수 센터를 사용하여 SharePoint, OneDrive 및 보안 준수 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ba28-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="0ba28-120">보안 및 & 센터에서 **위협** 관리 정책 ATP 안전한 첨부 파일로 \>  \> **이동하고** 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="0ba28-121">전역 **설정** 플라이아웃이 나타나면 에 대한 Office 365, SharePoint 및 OneDrive 설정으로 **Microsoft Teams** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="0ba28-122">토글을 오른쪽 토글로 이동하여 SharePoint, OneDrive 및 연결에 대한 안전 첨부 ![ ](../../media/scc-toggle-on.png) 파일을 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ba28-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="0ba28-123">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0ba28-124">PowerShell을 Exchange Online 사용하여 SharePoint, OneDrive 및 파일에 대한 안전한 첨부 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ba28-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="0ba28-125">PowerShell을 사용하여 SharePoint, OneDrive 및 Microsoft Teams 안전 첨부 파일을 설정하는 Exchange Online [PowerShell에](/powershell/exchange/connect-to-exchange-online-powershell) 연결하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="0ba28-126">구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="0ba28-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="0ba28-127">2단계: (권장) SharePoint Online PowerShell을 사용하여 사용자가 악성 파일을 다운로드하지 못하게 방지</span><span class="sxs-lookup"><span data-stu-id="0ba28-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="0ba28-128">기본적으로 사용자는 ATP에서 검색된 악성 파일을 열거나 이동, 복사 또는 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="0ba28-129">그러나 악성 파일을 삭제하고 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="0ba28-130">사용자가 악성 파일을 다운로드하지 못하게 SharePoint [Online PowerShell에 연결하고 다음](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="0ba28-131">**참고:**</span><span class="sxs-lookup"><span data-stu-id="0ba28-131">**Notes**:</span></span>

- <span data-ttu-id="0ba28-132">이 설정은 사용자와 관리자 모두에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="0ba28-133">사람들은 여전히 악성 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-133">People can still delete malicious files.</span></span>

<span data-ttu-id="0ba28-134">구문과 매개 변수에 대한 자세한 내용은 [Set-SPOTenant 를 참조하십시오.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="0ba28-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="0ba28-135">3단계(권장) 보안 & 준수 센터를 사용하여 검색된 파일에 대한 경고 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0ba28-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="0ba28-136">사용자 및 기타 관리자에게 악의적인 파일을 감지하는 경우 사용자 및 기타 관리자에게 안전한 첨부 파일을 SharePoint, OneDrive Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="0ba28-137">경고에 대한 자세한 내용은 보안 및 준수 센터에서 활동 [& 참조합니다.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0ba28-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="0ba28-138">보안 & [규정](https://protection.office.com)준수 센터에서 경고  경고 정책으로 \> **이동하거나** 을 를 열 수 <https://protection.office.com/alertpolicies> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="0ba28-139">경고 **정책 페이지에서** 새 경고 **정책 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="0ba28-140">새 **경고 정책 마법사가** 플라이아웃에서 열립니다. 경고 **이름 지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="0ba28-141">**이름:** 고유하고 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="0ba28-142">예를 들어 라이브러리의 악성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="0ba28-143">**설명:** 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="0ba28-144">예를 들어 SharePoint Online, OneDrive 또는 파일에서 악성 파일이 검색되면 관리자에게 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ba28-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="0ba28-145">**심각도**: 기본값을 낮게 **선택된** 그대로 두거나 중간 또는 **높음** 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="0ba28-146">**범주 선택:** **위협 관리 선택**.</span><span class="sxs-lookup"><span data-stu-id="0ba28-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="0ba28-147">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0ba28-148">경고 **설정 만들기 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="0ba28-149">**경고할 사항: 활동은**: **파일에서 검색된 맬웨어를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="0ba28-150">**경고를 트리거하는** 방법: 활동이 규칙과 일치할 때마다 **기본값을 그대로** 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="0ba28-151">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0ba28-152">받는 **사람 설정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="0ba28-153">**전자 메일 알림 보내기:** 이 설정이 선택되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0ba28-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="0ba28-154">전자 메일 받는 사람 **상자에서** 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="0ba28-155">**일별 알림 제한:** 기본값 제한 **없음을 선택된 그대로** 떠습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="0ba28-156">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0ba28-157">설정 **검토 페이지에서** 설정을 검토하고 모든  섹션에서 편집을 클릭하여 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="0ba28-158">정책을 **바로** 켜시겠습니까? 섹션에서 기본값 **Yes, turn it on right away selected(기본값 예, 바로 켜기)를 선택된 것으로 떠났습니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="0ba28-159">완료되면 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="0ba28-160">보안 및 & PowerShell을 사용하여 검색된 파일에 대한 경고 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0ba28-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="0ba28-161">PowerShell을 사용하여 이전 섹션에 설명된 동일한 경고 정책을 만들 경우 보안 & 준수 센터 [PowerShell에](/powershell/exchange/connect-to-scc-powershell) 연결하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="0ba28-162">**참고:** 기본 _심각도 값은_ Low입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="0ba28-163">Medium 또는 High를 지정하기 위해 _명령에 Severity_ 매개 변수와 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="0ba28-164">구문과 매개 변수에 대한 자세한 내용은 [New-ActivityAlert 를 참조하십시오.](/powershell/module/exchange/new-activityalert)</span><span class="sxs-lookup"><span data-stu-id="0ba28-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0ba28-165">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="0ba28-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="0ba28-166">SharePoint, OneDrive 및 Microsoft Teams 안전한 첨부 파일이 설정되어 있는지 확인 Microsoft Teams 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="0ba28-167">보안 & 규정 준수 [센터에서](https://protection.office.com)위협  관리 정책 \>  \> **ATP 안전한** 첨부 파일로 이동하고 전역 설정을 선택하고 Office 365, SharePoint, OneDrive 및 Microsoft Teams 설정에 대한 Office 365 에서 Defender 켜기 설정을 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ba28-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="0ba28-168">PowerShell을 Exchange Online 다음 명령을 실행하여 속성 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="0ba28-169">구문과 매개 변수에 대한 자세한 내용은 [Get-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="0ba28-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="0ba28-170">사용자가 악성 파일을 다운로드하지 못하게 차단하는지 확인하려면 SharePoint Online PowerShell을 열고 다음 명령을 실행하여 속성 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="0ba28-171">구문과 매개 변수에 대한 자세한 내용은 [Get-SPOTenant 를 참조하십시오.](/powershell/module/sharepoint-online/Set-SPOTenant)</span><span class="sxs-lookup"><span data-stu-id="0ba28-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="0ba28-172">검색된 파일에 대해 경고 정책을 성공적으로 구성한지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="0ba28-173">보안 및 & 센터에서 경고 경고  정책으로 이동하여 경고 정책을 선택하고 \>  \> 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="0ba28-174">보안 & 준수 센터 PowerShell에서 경고 정책의 이름으로 바꾸고 다음 명령을 실행하고 속성 값을 \<AlertPolicyName\> 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="0ba28-175">구문과 매개 변수에 대한 자세한 내용은 [Get-ActivityAlert 를 참조하십시오.](/powershell/module/exchange/get-activityalert)</span><span class="sxs-lookup"><span data-stu-id="0ba28-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="0ba28-176">위협 [방지 상태 보고서를](view-email-security-reports.md#threat-protection-status-report) 사용하여 검색된 파일에 대한 정보를 SharePoint, OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ba28-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="0ba28-177">특히 다음을 사용하여 데이터 보기: 콘텐츠 맬웨어 **\> 보기를 사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba28-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>