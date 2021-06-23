---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Plan 2용 Microsoft Defender에서 사용자 태그를 사용하여 특정 사용자 그룹을 식별하는 Office 365 있습니다. 태그 필터링은 Microsoft Defender의 경고, 보고서 및 조사에서 사용할 수 있으며, Office 365 사용자를 빠르게 식별할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083119"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="eefce-104">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="eefce-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="eefce-105">사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="eefce-106">릴리스 일정에 대한 자세한 내용은 Microsoft 365 [로드맵을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="eefce-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="eefce-107">사용자 태그는 에 대한 Microsoft [Defender의](defender-for-office-365.md)특정 사용자 그룹의 식별자 Office 365.</span><span class="sxs-lookup"><span data-stu-id="eefce-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="eefce-108">사용자 태그에는 다음 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-108">There are two types of user tags:</span></span>

- <span data-ttu-id="eefce-109">**시스템 태그:** 현재 [우선](../../admin/setup/priority-accounts.md) 순위 계정은 시스템 태그의 유일한 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="eefce-110">**사용자 지정 태그:** 이러한 사용자 태그를 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="eefce-111">조직에 Office 365 계획 2에 대한 Defender가 있는 경우(구독 또는 추가 기능으로 포함) 우선 순위 계정 태그를 사용하는 것 외에도 사용자 지정 사용자 태그를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="eefce-112">현재 사서함 사용자에게만 사용자 태그를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="eefce-113">사용자에게 시스템 태그 또는 사용자 지정 태그를 적용한 후 경고, 보고서 및 조사에서 이러한 태그를 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="eefce-114">경고</span><span class="sxs-lookup"><span data-stu-id="eefce-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="eefce-115">사용자 지정 경고 정책</span><span class="sxs-lookup"><span data-stu-id="eefce-115">Custom alert policies</span></span>](../../compliance/alert-policies.md#viewing-alerts)
- [<span data-ttu-id="eefce-116">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="eefce-116">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="eefce-117">전자 메일 엔터티 페이지</span><span class="sxs-lookup"><span data-stu-id="eefce-117">Email entity page</span></span>](mdo-email-entity-page.md#other-innovations)
- [<span data-ttu-id="eefce-118">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="eefce-118">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="eefce-119">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="eefce-119">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="eefce-120">우선 순위 계정의 경우 [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) EAC(Exchange 관리 센터)의 우선 순위 계정 보고서에 전자 메일 문제를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-120">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="eefce-121">이 문서에서는 사이트 포털에서 사용자 태그를 구성하는 Microsoft 365 Defender 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-121">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="eefce-122">사용자 태그를 관리하는 Microsoft 365 Defender cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-122">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="eefce-123">사용자 태그가 영향력이 큰 사용자 계정을 보호하는 데 도움이 되는 전략의 일부인 방법을 자세한 내용은 에서 우선 순위 계정에 [대한 보안 권장 사항을 Microsoft 365.](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="eefce-123">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eefce-124">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="eefce-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eefce-125"><https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-125">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="eefce-126">사용자 태그 페이지로 직접 **이동하기** 위해 를 를 <https://security.microsoft.com/securitysettings/userTags> 니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-126">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="eefce-127">이 문서의 절차를 수행하려면 Microsoft 365 Defender 포털에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-127">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="eefce-128">사용자 태그를 만들고 수정하고 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-128">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="eefce-129">기존 사용자 태그에서 구성원을 추가 및 제거하려면 **조직** **관리,** 보안 관리자 또는 보안 운영자 역할 그룹의 **구성원이** 되거나,</span><span class="sxs-lookup"><span data-stu-id="eefce-129">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="eefce-130">사용자 태그에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-130">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="eefce-131">자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eefce-131">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="eefce-132">Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한 및 Microsoft 365 Defender 포털의  다른 기능에 대한 사용 권한이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eefce-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="eefce-133">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eefce-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="eefce-134">사용자 태그 관리는 태그 판독기 및 **태그** 관리자 **역할에 의해** 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="eefce-135">또한 사용자 계정에서 우선 순위 계정을 관리하고 모니터링할 Microsoft 365 관리 센터.</span><span class="sxs-lookup"><span data-stu-id="eefce-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="eefce-136">자세한 내용은 우선 순위 [계정 관리 및 모니터링을 참조하세요.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="eefce-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="eefce-137">권한 있는 계정(관리자 계정)의 보안에 대한 자세한 내용은 이 [항목을 참조하세요.](/azure/architecture/framework/security/critical-impact-accounts) </span><span class="sxs-lookup"><span data-stu-id="eefce-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="eefce-138">Microsoft 365 Defender 포털을 사용하여 사용자 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="eefce-138">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="eefce-139">Microsoft 365 Defender 포털에서 설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="eefce-139">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="eefce-140">사용자 **태그 페이지에서** 태그 만들기 ![ 아이콘 태그 ](../../media/m365-cc-sc-create-icon.png) **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eefce-140">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="eefce-141">태그 **만들기 마법사가** 새 플라이아웃에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-141">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="eefce-142">태그 **정의 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-142">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="eefce-143">**이름:** 태그를 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-143">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="eefce-144">이 값은 표시하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-144">This is the value that you'll see and use.</span></span> <span data-ttu-id="eefce-145">태그를 만든 후 태그 이름을 다시 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-145">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="eefce-146">**설명:** 태그에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-146">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="eefce-147">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="eefce-148">구성원 **할당 페이지에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-148">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="eefce-149">구성원 ![ 추가 아이콘 구성원 ](../../media/m365-cc-sc-create-icon.png) **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eefce-149">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="eefce-150">플라이아웃이 나타나면 다음 단계에 따라 개별 사용자 또는 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-150">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="eefce-151">상자를 클릭하고 목록을 스크롤하여 사용자 또는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-151">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="eefce-152">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자 또는 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-152">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="eefce-153">값을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-153">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="eefce-154">개별 항목을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="eefce-154">To remove individual entries, click</span></span> ![항목 제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="eefce-156">상자의 항목 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-156">next to the entry in the box.</span></span>
     - <span data-ttu-id="eefce-157">모든 항목을 제거하려면 상자 아래의 선택한 nn 사용자 및 nn 그룹 항목에서 항목 ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **제거** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-157">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="eefce-158">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-158">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="eefce-159">구성원 할당 **페이지에서** 항목 옆에 있는 삭제 아이콘을 클릭하여 항목을 ![ 제거할 수도 ](../../media/m365-cc-sc-delete-icon.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-159">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="eefce-160">가져오기 **를** 클릭하여 사용자 또는 그룹의 전자 메일 주소가 포함된 텍스트 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-160">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="eefce-161">텍스트 파일에 한 줄에 항목이 하나씩 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="eefce-161">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="eefce-162">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="eefce-163">태그 **검토** 페이지가 나타나면 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-163">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="eefce-164">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-164">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="eefce-165">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-165">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="eefce-166">완료되면 제출을 **클릭하고** 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eefce-166">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="eefce-167">Microsoft 365 Defender 포털을 사용하여 사용자 태그 보기</span><span class="sxs-lookup"><span data-stu-id="eefce-167">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="eefce-168">Microsoft 365 Defender 포털에서 설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="eefce-168">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="eefce-169">사용자 **태그 페이지에는** 사용자 태그 목록에 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-169">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="eefce-170">**Tag**: 사용자 태그의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-170">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="eefce-171">여기에는 기본 제공 우선 순위 계정 **시스템 태그가** 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-171">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="eefce-172">**적용된 구성원** 수</span><span class="sxs-lookup"><span data-stu-id="eefce-172">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="eefce-173">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="eefce-173">**Last modified**</span></span>
   - <span data-ttu-id="eefce-174">**만든 날짜**</span><span class="sxs-lookup"><span data-stu-id="eefce-174">**Created on**</span></span>

3. <span data-ttu-id="eefce-175">이름을 클릭하여 사용자 태그를 선택하면 세부 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-175">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="eefce-176">Microsoft 365 Defender 포털을 사용하여 사용자 태그 수정</span><span class="sxs-lookup"><span data-stu-id="eefce-176">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="eefce-177">Microsoft 365 Defender 포털에서 설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="eefce-177">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="eefce-178">사용자 **태그 페이지에서** 목록에서 사용자 태그를 선택한 다음 태그 아이콘 편집 태그 ![ ](../../media/m365-cc-sc-edit-icon.png) **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eefce-178">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="eefce-179">나타나는 세부 정보 플라이아웃에서 이 문서 앞부분의 Microsoft 365 Defender [](#use-the-microsoft-365-defender-portal-to-create-user-tags) 포털을 사용하여 사용자 태그 만들기 섹션에 설명된 대로 동일한 마법사 및 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-179">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="eefce-180">**참고:**</span><span class="sxs-lookup"><span data-stu-id="eefce-180">**Notes**:</span></span>

   - <span data-ttu-id="eefce-181">태그 **정의 페이지는** 기본 제공 우선  순위 계정 시스템 태그에 사용할 수 없습니다. 따라서 이 태그의 이름을 바꾸거나 설명을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-181">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="eefce-182">사용자 지정 태그의 이름을 바꿀 수 없지만 설명을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-182">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="eefce-183">사용자 Microsoft 365 Defender 포털을 사용하여 사용자 태그 제거</span><span class="sxs-lookup"><span data-stu-id="eefce-183">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="eefce-184">기본 제공 우선 순위 계정 시스템 태그는 **제거할** 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eefce-184">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="eefce-185">Microsoft 365 Defender 포털에서 설정 전자 메일  & \>  \> **사용자 태그로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="eefce-185">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="eefce-186">사용자 **태그 페이지에서** 목록에서 사용자 태그를 선택한 다음 태그 삭제 ![ 아이콘 삭제 태그 ](../../media/m365-cc-sc-delete-icon.png) **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eefce-186">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="eefce-187">나타나는 확인 대화 상자에서 경고를 읽은 다음 **예, 제거를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eefce-187">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
