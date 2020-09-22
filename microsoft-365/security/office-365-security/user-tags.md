---
title: 사용자 태그
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
description: 관리자는 Oiffce 365 ATP 계획 2에서 사용자 태그를 사용 하 여 특정 사용자 그룹을 식별 하는 방법을 배울 수 있습니다. 태그 필터링은 태그가 지정 된 사용자를 빠르게 식별 하기 위해 Office 365 ATP에서 경고, 보고서 및 조사를 통해 사용할 수 있습니다.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210033"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="f8e73-104">Microsoft 보안 센터의 사용자 태그</span><span class="sxs-lookup"><span data-stu-id="f8e73-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="f8e73-105">사용자 태그는 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md)에서 특정 사용자 그룹의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="f8e73-106">[우선 순위 계정은](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 사용자 태그의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="f8e73-107">조직에 Office 365 ATP 계획 2 (구독 또는 추가 기능에 포함)가 있는 경우 우선 순위 계정 태그를 사용 하는 것 외에 사용자 지정 사용자 태그를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="f8e73-108">특정 사용자에 게 태그를 적용 한 후에는 경고, 보고서 및 조사에서 해당 태그를 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="f8e73-109">보안 & 준수 센터의 알림</span><span class="sxs-lookup"><span data-stu-id="f8e73-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="f8e73-110">위협 탐색기 및 실시간 검색</span><span class="sxs-lookup"><span data-stu-id="f8e73-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="f8e73-111">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="f8e73-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="f8e73-112">캠페인 보기</span><span class="sxs-lookup"><span data-stu-id="f8e73-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="f8e73-113">이 문서에서는 보안 센터에서 사용자 태그를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8e73-114">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="f8e73-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f8e73-115">보안 센터를 엽니다 <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="f8e73-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="f8e73-116">**사용자 태그** 페이지로 직접 이동 하려면를 엽니다 <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="f8e73-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="f8e73-117">사용자 태그를 만들거나 수정 하거나 제거 하려면 보안 & 준수 센터에서 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="f8e73-118">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8e73-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f8e73-119">Microsoft 365 관리 센터에서 우선 순위 계정을 관리 하 고 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f8e73-120">자세한 내용은 [우선 순위 계정 관리 및 모니터링](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8e73-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="f8e73-121">보안 센터를 사용 하 여 사용자 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="f8e73-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="f8e73-122">보안 센터에서 **설정** \> **전자 메일 & 공동 작업** \> **사용자 태그로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="f8e73-123">**사용자 태그** 페이지가 열리면 **태그 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="f8e73-124">새 플라이 아웃에서 **태그 만들기** 마법사가 열립니다. **태그 정의** 페이지에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="f8e73-125">**이름**: 태그에 대해 설명 하는 고유한 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="f8e73-126">이 값을 보고 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="f8e73-127">**설명**: 태그에 대 한 설명을 입력 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="f8e73-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="f8e73-128">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f8e73-129">**사서함 할당** 페이지에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="f8e73-130">**사서함 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="f8e73-131">즉시 표시 되는 다음 단계를 수행 하 여 개별 사용자 또는 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="f8e73-132">상자를 클릭 하 고 목록을 스크롤하여 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="f8e73-133">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 사용자 또는 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="f8e73-134">값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="f8e73-135">상자에서 개별 항목을 제거 하려면 상자에서 **Remove** ![ ](../../media/scc-remove-icon.png) 사용자 또는 그룹에 대 한 제거 아이콘 제거를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="f8e73-136">상자 아래 목록에서 기존 항목을 제거 하려면 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="f8e73-137">작업이 완료 되 면 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="f8e73-138">**가져오기를** 클릭 하 여 사용자 또는 그룹의 전자 메일 주소가 포함 된 텍스트 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="f8e73-139">텍스트 파일에 줄당 한 개의 항목이 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="f8e73-140">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f8e73-141">**태그 검토** 페이지에서 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="f8e73-142">변경 작업을 수행 하려면 특정 섹션에서 **편집** 을 클릭 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="f8e73-143">작업이 완료 되 면 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="f8e73-144">보안 센터를 사용 하 여 사용자 태그 보기</span><span class="sxs-lookup"><span data-stu-id="f8e73-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="f8e73-145">보안 센터에서 **설정** \> **전자 메일 & 공동 작업** \> **사용자 태그로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="f8e73-146">**사용자 태그** 페이지가 열리면 보려는 사용자 태그를 선택 합니다 (확인란을 클릭 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="f8e73-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="f8e73-147">읽기 전용 세부 정보가 표시 되 면 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="f8e73-148">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="f8e73-149">보안 센터를 사용 하 여 사용자 태그 수정</span><span class="sxs-lookup"><span data-stu-id="f8e73-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="f8e73-150">보안 센터에서 **설정** \> **전자 메일 & 공동 작업** \> **사용자 태그로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="f8e73-151">**사용자 태그** 페이지가 열리면 보려는 사용자 태그를 선택 하 고 **태그 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="f8e73-152">**편집 태그** 에서 즉시 정책 마법사가 열립니다. **다음** 을 클릭 하 여 설정을 검토 하 고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="f8e73-153">작업이 완료 되 면 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="f8e73-154">보안 센터를 사용 하 여 사용자 태그 제거</span><span class="sxs-lookup"><span data-stu-id="f8e73-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="f8e73-155">**참고**: 기본 제공 **우선 순위 계정** 태그는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="f8e73-156">보안 센터에서 **설정** \> **전자 메일 & 공동 작업** \> **사용자 태그로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="f8e73-157">**사용자 태그** 페이지가 열리면 제거할 사용자 태그를 선택 하 고 **태그 삭제**를 클릭 한 다음 표시 되는 경고에서 **예, 제거** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e73-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
