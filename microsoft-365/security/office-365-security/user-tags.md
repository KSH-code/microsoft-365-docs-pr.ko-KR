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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for Office 365 계획 2에서 사용자 태그를 사용 하 여 특정 사용자 그룹을 식별 하는 방법을 확인할 수 있습니다. 태그 필터링은 태그가 지정 된 사용자를 빠르게 식별 하기 위해 Microsoft Defender for Office 365의 경고, 보고서 및 조사를 통해 제공 됩니다.
ms.openlocfilehash: fcc13a04ed603712bb2a45ccaadbaf161702c502
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842883"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="130f4-104">Microsoft Defender for Office 365의 사용자 태그</span><span class="sxs-lookup"><span data-stu-id="130f4-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="130f4-105">사용자 태그 기능은 미리 보기에서 모든 사용자가 사용할 수 없으며 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="130f4-106">릴리스 일정에 대 한 자세한 내용은 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="130f4-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="130f4-107">사용자 태그는 [Defender For Office 365](office-365-atp.md)의 특정 사용자 그룹에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-107">User tags are identifiers for specific groups of users in [Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="130f4-108">사용자 태그에는 다음과 같은 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-108">There are two types of user tags:</span></span>

- <span data-ttu-id="130f4-109">**시스템 태그** : 현재 [우선 순위 계정만](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 시스템 태그 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-109">**System tags** : Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="130f4-110">**사용자 지정 태그** : 이러한 사용자 태그를 직접 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-110">**Custom tags** : You create these user tags yourself.</span></span>

<span data-ttu-id="130f4-111">조직에 Office 365 계획 2에 대 한 Defender가 있는 경우 (구독 또는 추가 기능에 포함 된 경우) priority accounts 태그를 사용 하는 것 외에 사용자 지정 사용자 태그를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="130f4-112">사용자에 게 시스템 태그나 사용자 지정 태그를 적용 한 후에는 경고, 보고서 및 조사에서 해당 태그를 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="130f4-113">보안 & 준수 센터의 알림</span><span class="sxs-lookup"><span data-stu-id="130f4-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="130f4-114">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="130f4-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="130f4-115">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="130f4-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="130f4-116">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="130f4-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="130f4-117">이 문서에서는 보안 & 준수 센터에서 사용자 태그를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="130f4-118">사용자 태그를 관리 하기 위한 보안 & 준수 센터에 cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="130f4-119">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="130f4-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="130f4-120"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="130f4-121">**사용자 태그** 페이지로 직접 이동 하려면를 엽니다 <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="130f4-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="130f4-122">**사용자 지정 사용자 태그** 를 만들거나 수정 하거나 제거 하려면 보안 & 준수 센터에서 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-122">To create, modify, or remove **custom user tags** , you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="130f4-123">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="130f4-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="130f4-124">우선 순위 계정 (시스템 태그)을 구성 하려면 [전역 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 또는 [Exchange 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="130f4-125">Microsoft 365 관리 센터에서 우선 순위 계정을 관리 하 고 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="130f4-126">자세한 내용은 [우선 순위 계정 관리 및 모니터링](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="130f4-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="130f4-127">보안 센터를 사용 하 여 사용자 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="130f4-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="130f4-128">보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="130f4-129">**사용자 태그** 페이지가 열리면 **태그 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="130f4-130">새 플라이 아웃에서 **태그 만들기** 마법사가 열립니다. **태그 정의** 페이지에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="130f4-131">**이름** : 태그에 대해 설명 하는 고유한 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-131">**Name** : Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="130f4-132">이 값을 보고 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="130f4-133">**설명** : 태그에 대 한 설명을 입력 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="130f4-133">**Description** : Enter an optional description for the tag.</span></span>

   <span data-ttu-id="130f4-134">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="130f4-135">**사서함 할당** 페이지에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="130f4-136">**사서함 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="130f4-137">즉시 표시 되는 다음 단계를 수행 하 여 개별 사용자 또는 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="130f4-138">상자를 클릭 하 고 목록을 스크롤하여 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="130f4-139">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="130f4-140">값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="130f4-141">상자에서 개별 항목을 제거 하려면 상자에서 **Remove** ![ ](../../media/scc-remove-icon.png) 사용자 또는 그룹에 대 한 제거 아이콘 제거를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="130f4-142">상자 아래 목록에서 기존 항목을 제거 하려면 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="130f4-143">작업이 완료 되 면 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="130f4-144">**가져오기를** 클릭 하 여 사용자 또는 그룹의 전자 메일 주소가 포함 된 텍스트 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="130f4-145">텍스트 파일에 줄당 한 개의 항목이 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="130f4-146">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="130f4-147">**태그 검토** 페이지에서 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="130f4-148">변경 작업을 수행 하려면 특정 섹션에서 **편집** 을 클릭 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="130f4-149">작업이 완료 되 면 **제출을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="130f4-150">보안 센터를 사용 하 여 사용자 태그 보기</span><span class="sxs-lookup"><span data-stu-id="130f4-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="130f4-151">보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="130f4-152">**사용자 태그** 페이지가 열리면 보려는 사용자 태그를 선택 합니다 (확인란을 클릭 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="130f4-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="130f4-153">읽기 전용 세부 정보가 표시 되 면 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="130f4-154">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="130f4-155">보안 센터를 사용 하 여 사용자 태그 수정</span><span class="sxs-lookup"><span data-stu-id="130f4-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="130f4-156">보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="130f4-157">**사용자 태그** 페이지가 열리면 보려는 사용자 태그를 선택 하 고 **태그 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="130f4-158">**편집 태그** 에서 즉시 정책 마법사가 열립니다. **다음** 을 클릭 하 여 설정을 검토 하 고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="130f4-159">작업이 완료 되 면 **제출을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="130f4-160">보안 센터를 사용 하 여 사용자 태그 제거</span><span class="sxs-lookup"><span data-stu-id="130f4-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="130f4-161">**참고** : 기본 제공 **우선 순위 계정** 태그는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-161">**Note** : You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="130f4-162">보안 센터에서 **위협 관리** \> **사용자 태그로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="130f4-163">**사용자 태그** 페이지가 열리면 제거할 사용자 태그를 선택 하 고 **태그 삭제** 를 클릭 한 다음 표시 되는 경고에서 **예, 제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="130f4-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag** , and then select **Yes, remove** in the warning that appears.</span></span>
