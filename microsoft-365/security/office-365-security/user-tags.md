---
title: Microsoft Defender for Office 365의 사용자 태그
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for Office 365 계획 2에서 사용자 태그를 사용하여 특정 사용자 그룹을 식별하는 방법을 배울 수 있습니다. 태그 필터링은 Microsoft Defender for Office 365의 경고, 보고서 및 조사에서 사용할 수 있으며, 태그가 지정된 사용자를 빠르게 식별할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c439dcb91831475bc10da4a01d0fa29e7aae359
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632205"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8d8be-104">Microsoft Defender for Office 365의 사용자 태그</span><span class="sxs-lookup"><span data-stu-id="8d8be-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="8d8be-105">사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="8d8be-106">릴리스 일정에 대한 자세한 내용은 [Microsoft 365 로드맵 을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="8d8be-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="8d8be-107">사용자 태그는 [Office 365용 Microsoft Defender의](defender-for-office-365.md)특정 사용자 그룹에 대한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="8d8be-108">사용자 태그에는 다음 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-108">There are two types of user tags:</span></span>

- <span data-ttu-id="8d8be-109">**시스템 태그:** 현재 [우선](../../admin/setup/priority-accounts.md) 순위 계정은 시스템 태그의 유일한 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="8d8be-110">**사용자 지정 태그:** 이러한 사용자 태그를 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="8d8be-111">조직에 Office 365 계획 2용 Defender가 있는 경우(구독 또는 추가 기능으로 포함) 우선 순위 계정 태그를 사용하는 것 외에도 사용자 지정 사용자 태그를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="8d8be-112">현재 사서함 사용자에게만 사용자 태그를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="8d8be-113">사용자에게 시스템 태그 또는 사용자 지정 태그를 적용한 후 경고, 보고서 및 조사에서 이러한 태그를 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="8d8be-114">보안 및 준수 & 알림</span><span class="sxs-lookup"><span data-stu-id="8d8be-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="8d8be-115">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="8d8be-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="8d8be-116">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="8d8be-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="8d8be-117">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="8d8be-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="8d8be-118">우선 순위 계정의 경우 [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) EAC(Exchange 관리 센터)의 우선 순위 계정 보고서에 대한 전자 메일 문제를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="8d8be-119">이 문서에서는 보안 및 준수 센터에서 사용자 태그를 & 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="8d8be-120">보안 및 준수 센터에는 사용자 태그를 & cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="8d8be-121">사용자 태그가 영향력이 큰 사용자 계정을 보호하는 데 도움이 되는 전략의 일부인 방법을 자세한 내용은 [Microsoft 365의](security-recommendations-for-priority-accounts.md)우선 순위 계정에 대한 보안 권장 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d8be-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8d8be-122">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8d8be-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8d8be-123"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8d8be-124">사용자 태그 페이지로 직접 **이동하기** 위해 를 를 <https://protection.office.com/userTags> 니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-124">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="8d8be-125">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8d8be-126">사용자 태그를 만들고 수정하고 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8d8be-127">기존 사용자 태그에서 구성원을 추가 및 제거하려면 **조직** **관리,** 보안 관리자 또는 보안 운영자 역할 그룹의 **구성원이** 되거나,</span><span class="sxs-lookup"><span data-stu-id="8d8be-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="8d8be-128">사용자 태그에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8d8be-129">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d8be-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="8d8be-130">**참고**:</span><span class="sxs-lookup"><span data-stu-id="8d8be-130">**Notes**:</span></span>

  - <span data-ttu-id="8d8be-131">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-131">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8d8be-132">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d8be-132">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8d8be-133">사용자 태그 관리는 태그 판독기 및 **태그** 관리자 **역할에 의해** 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-133">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="8d8be-134">Microsoft 365 관리 센터에서 우선 순위 계정을 관리하고 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-134">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8d8be-135">자세한 내용은 우선 순위 [계정 관리 및 모니터링을 참조하세요.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="8d8be-135">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="8d8be-136">권한 있는 계정(관리자 계정)의 보안에 대한 자세한 내용은 이 [항목을 참조하세요.](/azure/architecture/framework/security/critical-impact-accounts) </span><span class="sxs-lookup"><span data-stu-id="8d8be-136">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="8d8be-137">보안 및 준수 & 사용하여 사용자 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="8d8be-137">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="8d8be-138">보안 및 & 센터에서 **위협** 관리 \> **사용자 태그로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-138">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8d8be-139">열 **수 있는 사용자 태그** 페이지에서 태그 **만들기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-139">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="8d8be-140">태그 **만들기 마법사가** 새 플라이아웃에서 열립니다. 태그 **정의 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-140">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="8d8be-141">**이름:** 태그를 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="8d8be-142">이 값은 표시하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-142">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="8d8be-143">**설명:** 태그에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-143">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="8d8be-144">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8d8be-145">사용자 **할당 페이지에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-145">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="8d8be-146">사용자 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-146">Click **Add users**.</span></span> <span data-ttu-id="8d8be-147">플라이아웃이 나타나면 다음 단계에 따라 개별 사용자 또는 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-147">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="8d8be-148">상자를 클릭하고 목록을 스크롤하여 사용자 또는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-148">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="8d8be-149">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자 또는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-149">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="8d8be-150">값을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-150">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="8d8be-151">상자에서 개별 항목을 제거하려면  상자의 사용자 또는 그룹에서 제거 아이콘 ![ ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-151">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="8d8be-152">상자 아래의 목록에서 기존 항목을 제거하려면 항목 **제거** ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-152">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="8d8be-153">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-153">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="8d8be-154">가져오기 **를** 클릭하여 사용자 또는 그룹의 전자 메일 주소가 포함된 텍스트 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-154">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="8d8be-155">텍스트 파일에 한 줄에 항목이 하나씩 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8d8be-155">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="8d8be-156">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8d8be-157">태그 **검토 페이지에서** 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-157">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="8d8be-158">특정 섹션에서 **편집을** 클릭하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-158">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="8d8be-159">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="8d8be-160">보안 및 준수 & 사용하여 사용자 태그 보기</span><span class="sxs-lookup"><span data-stu-id="8d8be-160">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="8d8be-161">보안 및 & 센터에서 **위협** 관리 \> **사용자 태그로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-161">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8d8be-162">열 **수 있는 사용자** 태그 페이지에서 보하려는 사용자 태그를 선택합니다(확인란을 클릭하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="8d8be-162">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="8d8be-163">나타나는 읽기 전용 세부 정보 플라이아웃에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-163">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="8d8be-164">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-164">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="8d8be-165">보안 및 준수 & 사용하여 사용자 태그 수정</span><span class="sxs-lookup"><span data-stu-id="8d8be-165">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="8d8be-166">보안 및 & 센터에서 **위협** 관리 \> **사용자 태그로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-166">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8d8be-167">열 **수 있는 사용자** 태그 페이지에서 보하려는 사용자 태그를 선택한 다음 태그 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-167">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="8d8be-168">정책 마법사가 태그  편집 플라이아웃에서 열립니다. **다음을** 클릭하여 설정을 검토하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-168">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="8d8be-169">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-169">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="8d8be-170">보안 및 준수 & 사용하여 사용자 태그 제거</span><span class="sxs-lookup"><span data-stu-id="8d8be-170">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="8d8be-171">**참고:** 기본 제공 우선 순위 계정 태그는 제거할 **수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-171">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="8d8be-172">보안 및 & 센터에서 **위협** 관리 \> **사용자 태그로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d8be-172">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8d8be-173">열 **수 있는 사용자** 태그 페이지에서 제거할 사용자 태그를 선택하고 태그 삭제를 클릭한 다음 **예,** 나타나는 경고에서 제거를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d8be-173">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>