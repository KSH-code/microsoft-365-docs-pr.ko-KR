---
title: 앱 정책 만들기
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱 정책을 만듭니다.
ms.openlocfilehash: 17417d7fac80f2763edbbaa8dbb2c8be16e47371
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420425"
---
# <a name="create-app-policies"></a><span data-ttu-id="8160b-103">앱 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8160b-103">Create app policies</span></span>

><span data-ttu-id="8160b-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="8160b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8160b-105">비정상적인 앱 동작을 감지하고 경고를 생성하는 기본 제공 기능 집합과 함께 Microsoft 앱 거버넌스의 앱 정책은 다음을 수행할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="8160b-106">앱 거버넌스가 자동 또는 수동 수정을 위해 앱 동작을 경고할 수 있는 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="8160b-107">조직에 대한 앱 준수 정책을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="8160b-108">사용자 지정할 수 있는 제공된 템플릿에서 앱 정책을 만들거나 사용자 지정 앱 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="8160b-109">새 앱 정책을 만들려면 **Microsoft 365 준수 센터 > 앱 보호 및 거버넌스 > 개요 페이지 > 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App protection & governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="8160b-110">앱 사용용으로 디자인된 템플릿을 사용하여 새 앱 정책을 만들려면 **앱 사용 정책 만들기** 아래에서 **정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="8160b-111">앱 사용 권한용으로 디자인된 템플릿을 사용하여 새 앱 정책을 만들려면 **사용 권한 정책 만들기** 에서 **정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="8160b-112">앱 인증 또는 사용자 지정 정책에 대한 새 앱 정책을 만들려면 **새 항목 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="8160b-113">앱 정책 템플릿</span><span class="sxs-lookup"><span data-stu-id="8160b-113">App policy templates</span></span>

<span data-ttu-id="8160b-114">앱 정책 템플릿을 기반으로 새 앱 정책을 만들려면 **앱 정책 템플릿 선택 페이지** 에서 앱 템플릿 범주를 선택하고 템플릿의 이름을 선택한 다음 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="8160b-115">앱 거버넌스에는 세 가지 범주의 앱 정책 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="8160b-116">앱 사용자 및 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="8160b-116">App users and data access</span></span>

<span data-ttu-id="8160b-117">앱 거버넌스에는 앱 사용에 대한 경고를 생성하는 이러한 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="8160b-118">서식 파일 이름</span><span class="sxs-lookup"><span data-stu-id="8160b-118">Template name</span></span> | <span data-ttu-id="8160b-119">설명</span><span class="sxs-lookup"><span data-stu-id="8160b-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="8160b-120">많은 양의 데이터 액세스 권한이 있는 새 앱</span><span class="sxs-lookup"><span data-stu-id="8160b-120">New app with a high volume of data access</span></span> | <span data-ttu-id="8160b-121">해당 데이터 패턴을 예상할 수 있도록 대용량 데이터 액세스 권한이 있는 최근 등록된 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="8160b-122">기본적으로 이 정책은 지난 7일 동안 등록되었으며 해당 기간 동안 1GB 이상의 데이터 액세스 권한이 있는 모든 앱에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="8160b-123">이 정책은 더 많은 조건 및 작업으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="8160b-124">앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8160b-124">App Permissions</span></span>

<span data-ttu-id="8160b-125">앱 거버넌스에는 앱 사용 권한에 대한 경고를 생성하는 이러한 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="8160b-126">서식 파일 이름</span><span class="sxs-lookup"><span data-stu-id="8160b-126">Template name</span></span> | <span data-ttu-id="8160b-127">설명</span><span class="sxs-lookup"><span data-stu-id="8160b-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="8160b-128">과도한 권한이 있는 앱</span><span class="sxs-lookup"><span data-stu-id="8160b-128">Overprivileged apps</span></span> | <span data-ttu-id="8160b-129">잠재적인 사용 권한 감소에 대한 기회를 식별하기 위해 해당 앱에서 사용하는 것보다 권한이 더 많은 모든 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="8160b-130">기본적으로 이 정책은 90일 동안 사용되지 않는 경우 과도한 권한 보유로 표시된 모든 앱에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="8160b-131">이 기간 필터는 더 많은 조건 및 작업으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="8160b-132">높은 권한이 있는 새 앱</span><span class="sxs-lookup"><span data-stu-id="8160b-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="8160b-133">추가 조사가 필요할 수 있는 잠재적으로 큰 공간을 차지하는 앱을 식별하도록 사용 권한이 높은 모든 새 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="8160b-134">기본적으로 이 정책은 높은 사용 권한이 있는 지난 7일 동안 등록된 모든 앱에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="8160b-135">앱 인증</span><span class="sxs-lookup"><span data-stu-id="8160b-135">App certification</span></span>

<span data-ttu-id="8160b-136">앱 거버넌스에는 앱 인증에 대한 경고를 생성하는 이러한 템플릿이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="8160b-137">서식 파일 이름</span><span class="sxs-lookup"><span data-stu-id="8160b-137">Template name</span></span> | <span data-ttu-id="8160b-138">설명</span><span class="sxs-lookup"><span data-stu-id="8160b-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="8160b-139">인증되지 않은 새 앱</span><span class="sxs-lookup"><span data-stu-id="8160b-139">New uncertified app</span></span> | <span data-ttu-id="8160b-140">테넌트에서 예상되도록 앱 인증 프로세스를 거치지 않은 새 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="8160b-141">기본적으로 이 정책은 지난 7일 동안 등록되어 인증되지 않은 모든 앱에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="8160b-142">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="8160b-142">Custom app policies</span></span>

<span data-ttu-id="8160b-143">기본 제공 템플릿 중 하나에서 아직 수행하지 않은 작업을 수행해야 하는 경우 사용자 지정 앱 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="8160b-144">새 사용자 지정 앱 정책을 만들려면 먼저 **정책** 페이지에서 **새 항목 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="8160b-145">**앱 정책 템플릿 선택 페이지** 에서 **사용자 지정** 범주, **사용자 지정 정책** 템플릿을 선택한 다음 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="8160b-146">**이름 및 설명** 페이지에서 다음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="8160b-147">정책 이름</span><span class="sxs-lookup"><span data-stu-id="8160b-147">Policy Name</span></span>

- <span data-ttu-id="8160b-148">정책 설명</span><span class="sxs-lookup"><span data-stu-id="8160b-148">Policy Description</span></span>

- <span data-ttu-id="8160b-149">이 정책에서 생성된 경고의 심각도를 설정하는 정책 심각도를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="8160b-150">High</span><span class="sxs-lookup"><span data-stu-id="8160b-150">High</span></span>
  - <span data-ttu-id="8160b-151">Medium</span><span class="sxs-lookup"><span data-stu-id="8160b-151">Medium</span></span>
  - <span data-ttu-id="8160b-152">낮음</span><span class="sxs-lookup"><span data-stu-id="8160b-152">Low</span></span>

<span data-ttu-id="8160b-153">**정책 설정 및 조건 선택** 페이지에서 **이 정책이 적용할 수 있는 앱** 에 대해 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="8160b-154">모든 앱</span><span class="sxs-lookup"><span data-stu-id="8160b-154">All Apps</span></span>
- <span data-ttu-id="8160b-155">특정 앱 선택</span><span class="sxs-lookup"><span data-stu-id="8160b-155">Choose specific apps</span></span>

  <span data-ttu-id="8160b-156">창을 통해 하나 이상의 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="8160b-157">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-157">Select **Add**.</span></span>

<span data-ttu-id="8160b-158">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-158">Select **Next**.</span></span>

<span data-ttu-id="8160b-159">**정책 설정 및 조건 선택** 페이지에서 **정책에 대한 새 조건 설정** 을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="8160b-160">**규칙 만들기** 창을 사용하여 새 규칙의 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="8160b-161">**조건 추가** 를 선택하고 조건 목록에서 선택한 다음 조건 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="8160b-162">여러 조건을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-162">You can add multiple conditions.</span></span>

<span data-ttu-id="8160b-163">다음은 사용자 지정 앱 정책에 사용할 수 있는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="8160b-164">조건</span><span class="sxs-lookup"><span data-stu-id="8160b-164">Condition</span></span> | <span data-ttu-id="8160b-165">조건 값 수락됨</span><span class="sxs-lookup"><span data-stu-id="8160b-165">Condition values accepted</span></span> | <span data-ttu-id="8160b-166">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8160b-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="8160b-167">앱 등록 기간</span><span class="sxs-lookup"><span data-stu-id="8160b-167">App registration age</span></span> | <span data-ttu-id="8160b-168">지난 X일 이내</span><span class="sxs-lookup"><span data-stu-id="8160b-168">Within last X days</span></span> |  |
| <span data-ttu-id="8160b-169">앱 인증</span><span class="sxs-lookup"><span data-stu-id="8160b-169">App certification</span></span> | <span data-ttu-id="8160b-170">기본 규정 준수, MCAS 규정 준수 또는 해당 없음</span><span class="sxs-lookup"><span data-stu-id="8160b-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="8160b-171">Microsoft 365 인증</span><span class="sxs-lookup"><span data-stu-id="8160b-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="8160b-172">게시자 검증</span><span class="sxs-lookup"><span data-stu-id="8160b-172">Publisher verification</span></span> | <span data-ttu-id="8160b-173">예 또는 아니요</span><span class="sxs-lookup"><span data-stu-id="8160b-173">Yes or No</span></span> | [<span data-ttu-id="8160b-174">게시자 확인</span><span class="sxs-lookup"><span data-stu-id="8160b-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="8160b-175">응용 프로그램 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8160b-175">Application Permission</span></span> | <span data-ttu-id="8160b-176">목록에서 하나 이상의 API 권한 선택</span><span class="sxs-lookup"><span data-stu-id="8160b-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="8160b-177">Microsoft Graph 권한 참조</span><span class="sxs-lookup"><span data-stu-id="8160b-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="8160b-178">위임된 권한</span><span class="sxs-lookup"><span data-stu-id="8160b-178">Delegated Permission</span></span> | <span data-ttu-id="8160b-179">목록에서 하나 이상의 API 권한 선택</span><span class="sxs-lookup"><span data-stu-id="8160b-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="8160b-180">Microsoft Graph 권한 참조</span><span class="sxs-lookup"><span data-stu-id="8160b-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="8160b-181">높은 권한</span><span class="sxs-lookup"><span data-stu-id="8160b-181">High privilege</span></span> | <span data-ttu-id="8160b-182">예 또는 아니요</span><span class="sxs-lookup"><span data-stu-id="8160b-182">Yes or No</span></span> | <span data-ttu-id="8160b-183">MCAS에서 사용하는 동일한 논리를 기반으로 하는 내부 지정입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="8160b-184">과도한 권한이 있는 앱</span><span class="sxs-lookup"><span data-stu-id="8160b-184">Overprivileged app</span></span> | <span data-ttu-id="8160b-185">예 또는 아니요</span><span class="sxs-lookup"><span data-stu-id="8160b-185">Yes or No</span></span> | <span data-ttu-id="8160b-186">해당 앱에서 사용하는 것보다 더 많은 권한이 부여된 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="8160b-187">앱 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="8160b-187">App data access</span></span> | <span data-ttu-id="8160b-188">시간당 XGB 데이터 액세스보다 큼</span><span class="sxs-lookup"><span data-stu-id="8160b-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="8160b-189">앱 데이터 액세스 추세</span><span class="sxs-lookup"><span data-stu-id="8160b-189">App data access trend</span></span> | <span data-ttu-id="8160b-190">지난 7일 간의 데이터 사용량 X% 증가</span><span class="sxs-lookup"><span data-stu-id="8160b-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="8160b-191">앱 API 액세스</span><span class="sxs-lookup"><span data-stu-id="8160b-191">App API Access</span></span> | <span data-ttu-id="8160b-192">시간당 X API 호출보다 큼</span><span class="sxs-lookup"><span data-stu-id="8160b-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="8160b-193">앱 API 액세스 추세</span><span class="sxs-lookup"><span data-stu-id="8160b-193">App API Access trend</span></span> | <span data-ttu-id="8160b-194">지난 7일 동안 API 호출 증가 비율은 X%입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="8160b-195">동의한 사용자</span><span class="sxs-lookup"><span data-stu-id="8160b-195">Users consented</span></span> | <span data-ttu-id="8160b-196">(초과 또는 미만) X 동의한 사용자</span><span class="sxs-lookup"><span data-stu-id="8160b-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="8160b-197">우선 순위 사용자 동의</span><span class="sxs-lookup"><span data-stu-id="8160b-197">Priority user consented</span></span> | <span data-ttu-id="8160b-198">예 또는 아니요</span><span class="sxs-lookup"><span data-stu-id="8160b-198">Yes or No</span></span> | <span data-ttu-id="8160b-199">[우선 순위 계정](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="8160b-200">앱에 동의한 사용자</span><span class="sxs-lookup"><span data-stu-id="8160b-200">App consented by</span></span> | <span data-ttu-id="8160b-201">목록에서 사용자 선택</span><span class="sxs-lookup"><span data-stu-id="8160b-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="8160b-202">사용자의 역할 동의</span><span class="sxs-lookup"><span data-stu-id="8160b-202">Consenting user’s role</span></span> | <span data-ttu-id="8160b-203">Teams 관리자, 디렉터리 읽기 권한자, 보안 읽기 권한자, 준수 관리자, 보안 관리자, 기술 지원팀 관리자, SharePoint 관리자, Exchange 관리자, 전역 읽기 권한자, 전역 관리자, 준수 데이터 관리자, 사용자 관리자, 서비스 지원 관리자 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="8160b-204">여러 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="8160b-205">할당된 멤버가 있는 모든 Azure AD 역할을 이 목록에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="8160b-206">액세스된 워크로드</span><span class="sxs-lookup"><span data-stu-id="8160b-206">Workload accessed</span></span> | <span data-ttu-id="8160b-207">OneDrive 및/또는 SharePoint 및/또는 Exchange</span><span class="sxs-lookup"><span data-stu-id="8160b-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="8160b-208">여러 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="8160b-209">오류율</span><span class="sxs-lookup"><span data-stu-id="8160b-209">Error rate</span></span> | <span data-ttu-id="8160b-210">오류율이 지난 7일 동안 X%보다 크며, 여기서 X는 관리자가 정의한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="8160b-211">이 앱 정책을 적용하려면 지정된 모든 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="8160b-212">조건 지정이 완료되면 **저장** 을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="8160b-213">**정책 작업 정의** 페이지에서 이 정책을 기반으로 하는 경고가 생성될 때 앱 거버넌스에서 앱을 사용하지 않도록 설정하려면 **앱 사용 안 함** 을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="8160b-214">**정책 상태 정의** 페이지에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="8160b-215">**감사 모드**: 정책이 평가되지만 구성된 작업은 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="8160b-216">감사 모드 정책은 정책 목록에 **감사** 상태로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="8160b-217">**활성**: 정책이 평가되고 구성된 작업이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="8160b-218">**비활성**: 정책이 평가되지 않으며 구성된 작업이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="8160b-219">새 앱 정책 테스트 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="8160b-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="8160b-220">이제 앱 정책이 만들어졌으므로 **정책** 페이지에서 모니터링하여 테스트 중에 예상되는 활성 경고 수 및 총 경고를 등록하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![강조 표시된 정책이 있는 Microsoft 365 준수 센터의 MAPG 정책 요약 페이지](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="8160b-222">경고 수가 예기치 않게 낮은 값인 경우 앱 정책의 설정을 편집하여 상태를 설정하기 전에 올바르게 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="8160b-223">다음은 새 정책을 만들고 테스트한 다음 활성화하는 프로세스의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="8160b-224">심각도, 앱, 조건 및 작업을 초기 값으로 설정하고 상태를 **감사 모드** 로 설정하여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="8160b-225">생성된 경고와 같은 예상 동작을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="8160b-226">동작이 필요하지 않은 경우 필요에 따라 정책 앱, 조건 및 작업 설정을 편집하고 2단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="8160b-227">동작이 필요한 경우 정책을 편집하고 상태를 **활성** 으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![앱 정책 만들기 워크플로](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="8160b-229">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8160b-229">Next step</span></span>

[<span data-ttu-id="8160b-230">앱 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8160b-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
