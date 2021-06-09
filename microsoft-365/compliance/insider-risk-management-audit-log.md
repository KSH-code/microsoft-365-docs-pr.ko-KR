---
title: 내부자 위험 관리 감사 로그
description: 내부자 위험 관리 감사 로그에 대해 Microsoft 365
keywords: Microsoft 365, 내부 위험 관리, 위험 관리, 규정 준수
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820281"
---
# <a name="insider-risk-management-audit-log"></a><span data-ttu-id="20576-104">내부자 위험 관리 감사 로그</span><span class="sxs-lookup"><span data-stu-id="20576-104">Insider risk management audit log</span></span>

<span data-ttu-id="20576-105">내부자 위험 관리 감사 로그를 사용하면 내부자 위험 관리 기능에 대해 수행된 작업에 대한 정보를 계속 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-105">The insider risk management audit log enables you to stay informed on the actions that were taken on insider risk management features.</span></span> <span data-ttu-id="20576-106">이 로그를 사용하면 하나 이상의 내부자 위험 관리 역할 그룹에 할당된 사용자가 수행한 작업을 독립적으로 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-106">This log allows independent review of the actions taken by users assigned to one or more insider risk management role groups.</span></span> <span data-ttu-id="20576-107">내부자 위험 관리 감사 로그는 조직에서 자동으로 사용하도록 설정되며 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-107">The insider risk management audit log is automatically enabled in your organization and cannot be disabled.</span></span>

![내부자 위험 관리 감사 로그](../media/insider-risk-audit-log.png)

<span data-ttu-id="20576-109">감사 로그는 모니터링된 활동이 발생할 때마다 자동으로 즉시 업데이트되며 로그는 180일(약 6개월) 동안 활동에 대한 정보를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="20576-109">The audit log is automatically and immediately updated whenever monitored activities occur and the log retains information about the activity for 180 days (about six months).</span></span> <span data-ttu-id="20576-110">180일이 지난 후 활동의 데이터는 로그에서 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="20576-110">After 180 days, the data for the activity is permanently deleted from the log.</span></span>

<span data-ttu-id="20576-111">활동 모니터링에 포함된 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-111">Areas included in activity monitoring include:</span></span>

- <span data-ttu-id="20576-112">정책</span><span class="sxs-lookup"><span data-stu-id="20576-112">Policies</span></span>
- <span data-ttu-id="20576-113">사례</span><span class="sxs-lookup"><span data-stu-id="20576-113">Cases</span></span>
- <span data-ttu-id="20576-114">경고</span><span class="sxs-lookup"><span data-stu-id="20576-114">Alerts</span></span>
- <span data-ttu-id="20576-115">설정</span><span class="sxs-lookup"><span data-stu-id="20576-115">Settings</span></span>
- <span data-ttu-id="20576-116">사용자</span><span class="sxs-lookup"><span data-stu-id="20576-116">Users</span></span>
- <span data-ttu-id="20576-117">알림 템플릿</span><span class="sxs-lookup"><span data-stu-id="20576-117">Notice templates</span></span>

<span data-ttu-id="20576-118">감사 로그에서 데이터를 보고 내보내기하려면 사용자를 내부자 위험 관리 또는 내부자 위험 관리 감사자 역할 그룹에 *할당해야* 합니다. </span><span class="sxs-lookup"><span data-stu-id="20576-118">To view and export data from the audit log, users must be assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups.</span></span> <span data-ttu-id="20576-119">내부자 위험 관리 역할 그룹에 대한 자세한 내용은 내부자 위험 관리 1단계: 사용 권한 사용 [시작을 참조합니다.](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)</span><span class="sxs-lookup"><span data-stu-id="20576-119">To learn more about insider risk management role groups, see [Getting started with insider risk management Step 1: Enabling permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management).</span></span>

>[!NOTE]
><span data-ttu-id="20576-120">내부자 위험 관리 감사 로그는 Microsoft 365 감사 로그와 연결되지 않습니다. 이러한 로그는 독립적인 감사 시스템으로, 별도의 활동에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="20576-120">The insider risk management audit log isn't associated with the Microsoft 365 audit log, they are independent auditing systems and capture information on separate activities.</span></span> <span data-ttu-id="20576-121">감사를 Microsoft 365 내부자 위험 관리 내의 활동 감사에는 영향을주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-121">Disabling Microsoft 365 auditing doesn't impact activity auditing within insider risk management.</span></span>

## <a name="view-activity-in-the-insider-risk-audit-log"></a><span data-ttu-id="20576-122">내부자 위험 감사 로그에서 활동 보기</span><span class="sxs-lookup"><span data-stu-id="20576-122">View activity in the insider risk audit log</span></span>

<span data-ttu-id="20576-123">내부자 위험 관리에 대해 모니터링되는 기능 활동을 확인하려면 모든 내부자 위험 관리 탭의 오른쪽 위에 있는 내부자 위험 감사 로그 링크를 탐색하고 선택합니다.  기본적으로 내부자 위험 관리 활동에 대해 표시되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-123">To view feature activity monitored for insider risk management, navigate to, and select the **Insider risk audit log** link in the top-right area of any insider risk management tab. By default, you'll see the following information displayed for insider risk management activities:</span></span>

- <span data-ttu-id="20576-124">**활동:** 사용자가 내부자 위험 관리 솔루션 내에서 취한 활동에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-124">**Activity:** A description of the activity taken within the insider risk management solution by a user.</span></span>
- <span data-ttu-id="20576-125">**범주:** 활동이 수행된 영역 또는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-125">**Category:** The area or item where the activity was performed.</span></span> <span data-ttu-id="20576-126">예를 들어 정책 변경 활동이 수행된 경우 *정책이* 범주로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20576-126">For example, you'll see *Policies* as the category when policy change activities were performed.</span></span>
- <span data-ttu-id="20576-127">**수행되는 활동:** 활동을 수행한 사용자의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-127">**Activity performed by:** The user name of the user that performed the activity.</span></span>
- <span data-ttu-id="20576-128">**날짜:** 활동이 수행된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-128">**Date:** The date and time the activity was performed.</span></span> <span data-ttu-id="20576-129">날짜 및 시간은 조직의 로컬 날짜와 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-129">The date and time are the local date and time for your organization.</span></span>

<span data-ttu-id="20576-130">기록된 활동에 대한 자세한 내용을 확인하려면 활동을 선택하여 활동 세부 정보 창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="20576-130">For more information about a logged activity, select the activity to display the activity details pane.</span></span> <span data-ttu-id="20576-131">이 창에는 활동에 대한 추가 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="20576-131">This pane includes additional information about the activity.</span></span>

## <a name="columns-and-filtering"></a><span data-ttu-id="20576-132">열 및 필터링</span><span class="sxs-lookup"><span data-stu-id="20576-132">Columns and filtering</span></span>

<span data-ttu-id="20576-133">감사자는 기록된 활동을 보다 쉽게 검토할 수 있도록 내부자 위험 감사 로그에서 **필터링이 지원됩니다.**</span><span class="sxs-lookup"><span data-stu-id="20576-133">To make it easier for auditors to review logged activity, filtering is supported in the **Insider risk audit log**.</span></span> <span data-ttu-id="20576-134">기본 필터링의 경우 큐 열을 보기에 추가하여 파일 및 메시지에 서로 다른 피벗을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-134">For basic filtering, queue columns are available to add to the view to provide different pivots on the files and messages.</span></span> <span data-ttu-id="20576-135">필드에서 수행한 **범주,** 날짜 범위 및 **활동별로 활동을 필터링할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-135">You can filter activities by the **Category, Date range,** and **Activity performed by** fields.</span></span>

<span data-ttu-id="20576-136">활동 큐에 대한 열 머리 제목을 추가하거나 제거하려면 열 사용자 지정 컨트롤을 **사용하여** 열 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20576-136">To add or remove column headings for the activity queue, use the **Customize columns** control and select from the column options.</span></span> <span data-ttu-id="20576-137">이러한 열은 내부자 위험  감사 로그에서 지원되는 일반적인 조건에 매핑되어 있으며 이 문서의 뒷부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-137">These columns map to common conditions supported in the **Insider risk audit log** and are listed later in this article.</span></span>

## <a name="audit-log-export"></a><span data-ttu-id="20576-138">감사 로그 내보내기</span><span class="sxs-lookup"><span data-stu-id="20576-138">Audit log export</span></span>

<span data-ttu-id="20576-139">*내부자* 위험 관리 또는  내부자 위험 관리 감사자 역할 그룹에 할당된 사용자는 내부자 위험 감사 로그 페이지에서 내보내기  를 선택하여 감사 로그의 모든 활동을 .csv(콤보로 구분된 값) 파일로 내보낼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-139">Users assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups can export all activity in the audit log to a .csv (comma-separated values) file by selecting **Export** on the **Insider risk audit log** page.</span></span> <span data-ttu-id="20576-140">활동에 따라 활동에 대한 일부 필드가 활동에 적용되지 않을 수 있으며 이러한 필드는 내보낼 파일에 비어 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20576-140">Depending on the activity, some fields for an activity may not be applicable to the activity and these fields will appear as blank in the exported file.</span></span>

<span data-ttu-id="20576-141">파일에는 다음 필드에 대한 활동 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20576-141">The file contains activity information for the following fields:</span></span>

- <span data-ttu-id="20576-142">**수행되는 활동:** 항목 값을 수정하는 사용자의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-142">**Activity performed by:** The user name of the user modifying an item value.</span></span> <span data-ttu-id="20576-143">여기에 나열된 사용자는 내부자 위험 관리, 내부자 위험 관리 관리자, 내부자 위험 관리 분석가, 내부자 위험 관리 조사자 등 역할 내부자 위험 관리 역할 그룹 중 하나 이상에 *할당됩니다.* [](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)</span><span class="sxs-lookup"><span data-stu-id="20576-143">Users listed here were assigned to one or more of the following role [insider risk management role groups](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management): *Insider Risk Management*, *Insider Risk Management Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*.</span></span> <span data-ttu-id="20576-144">각 역할 그룹에는 내부자 위험 기능을 관리하기 위한 사용 권한 수준이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="20576-144">Each role group has different permission levels for managing insider risk features.</span></span>
- <span data-ttu-id="20576-145">**활동:** 항목에 대한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-145">**Activity:** The activity taken on an item.</span></span> <span data-ttu-id="20576-146">값은 *보기, 삭제, 추가, 편집된 정책, 사례, 사용자,* 경고 *및 설정.*</span><span class="sxs-lookup"><span data-stu-id="20576-146">Values are *Viewed, Deleted, Added, Edited policy, Case, User, Alert,* and *Settings.*</span></span>
- <span data-ttu-id="20576-147">**추가된** 개체: 사용자, 파일 형식 또는 도메인과 같이 활동 중에 추가된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-147">**Added**: Objects that were added during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="20576-148">**경고 볼륨:** 내부자 위험 관리 설정에 정의된 경고 볼륨 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-148">**Alert volume**: The level of alert volume defined in insider risk management settings.</span></span>
- <span data-ttu-id="20576-149">**Amount**: 현재 선택한 정책에 대한 사용자 지정 표시기 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-149">**Amount**: The currently selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="20576-150">**자산 ID:** 활동이 수행된 우선 순위 실제 자산의 자산 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-150">**Asset ID**: The asset ID of the priority physical asset the activity was performed on.</span></span>
- <span data-ttu-id="20576-151">**범주:** 수정된 항목의 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-151">**Category:** The category of the item modified.</span></span> <span data-ttu-id="20576-152">값은 *정책, 사례, 사용자, 알림,* 설정 및 *알림 템플릿입니다.*</span><span class="sxs-lookup"><span data-stu-id="20576-152">Values are *Policies, Cases, Users, Alerts, Settings,* and *Notice templates.*</span></span>
- <span data-ttu-id="20576-153">**날짜:** 조직의 로컬 날짜 및 시간으로 나열된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-153">**Date:** Date and time, listed in your organization's local date and time.</span></span>
- <span data-ttu-id="20576-154">**설명:** 사용자가 작업할 개체(예: 정책 또는 우선 순위 사용자 그룹)에 대한 설명 입력입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-154">**Description**: The description input by the user for the object being acted on (such as a policy or a priority user group).</span></span>
- <span data-ttu-id="20576-155">**DLP 정책:** 내부자 위험 관리 정책에 포함을 트리거하기 위해 선택된 DLP(데이터 손실 방지) 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-155">**DLP policy**: The data loss prevention (DLP) policy selected to trigger inclusion in an insider risk management policy.</span></span>
- <span data-ttu-id="20576-156">**표시기:** 활동이 수행된 내부자 위험 설정의 표시기(예: 표시기 추가 또는 제거)입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-156">**Indicator**: The indicator in the within insider risk settings that the activity was performed on (such as adding or removing an indicator).</span></span>
- <span data-ttu-id="20576-157">**알림 서식** 파일: 활동이 수행된 알림 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-157">**Notice template**: The notice template the activity was performed on.</span></span>
- <span data-ttu-id="20576-158">**일 수:** 내부자 위험 설정에 정의된 정책 활성화 창입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-158">**Number of days**: The policy activation window defined in insider risk settings.</span></span>
- <span data-ttu-id="20576-159">**파일 수:** 내부자 위험 관리 설정에 정의된 파일 볼륨 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-159">**Number of files**: The file volume limit defined in insider risk management settings.</span></span>
- <span data-ttu-id="20576-160">**정책 템플릿:** 표시기가 속해 있는 정책 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-160">**Policy template**: The policy template that the indicators acted on belongs to.</span></span>
- <span data-ttu-id="20576-161">**이전 금액:** 정책에 대해 이전에 선택한 사용자 지정 표시기 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-161">**Previous amount**: The previously selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="20576-162">**우선 순위 사용자 그룹:** 활동이 수행된 우선 순위 사용자 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-162">**Priority user group**: The priority user group the activity was performed on.</span></span>
- <span data-ttu-id="20576-163">**제거됨:** 사용자, 파일 형식 또는 도메인과 같이 활동 중에 제거된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-163">**Removed**: Objects that were removed during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="20576-164">**보낸 사람**: 활동이 수행된 알림 서식 파일의 보낸 사람 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-164">**Sender**: The sender field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="20576-165">**대상 정책:** 활동이 수행된 정책입니다(예: 사용자를 추가하거나 사용자에서 제거).</span><span class="sxs-lookup"><span data-stu-id="20576-165">**Target policy**: The policy the activity was performed on (such as adding a user to or removing a user from).</span></span>
- <span data-ttu-id="20576-166">**서식 파일 메시지 본문:** 활동이 수행된 알림 서식 파일 메시지 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-166">**Template message body**: The message body of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="20576-167">**서식 파일 제목:** 활동이 수행된 알림 서식 파일의 제목 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-167">**Template subject**: The subject field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="20576-168">**사용자:** 활동이 수행된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="20576-168">**User:** User the activity was performed on.</span></span>
