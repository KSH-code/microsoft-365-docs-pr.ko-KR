---
title: 최신 릴리스에 대한 광범위한 배포 예제
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 최신 릴리스를 배포하는 조직에서 Windows 10과 Microsoft 365 앱용 채널을 사용하는 방법입니다.
ms.openlocfilehash: 46f36a7bd26ef190aca2a63fdaa993e420988b30
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200127"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a><span data-ttu-id="49f25-103">최신 릴리스에 대한 광범위한 배포 예제</span><span class="sxs-lookup"><span data-stu-id="49f25-103">Example of broad deployment for the latest releases</span></span>

<span data-ttu-id="49f25-104">이 채널 구성 예제는 비즈니스 우선순위에 맞게 최신 릴리스를 빠르게 배포하는 조직을 위한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-104">This channel configuration example is for an organization that uses rapid deployment of the latest releases to fit these business priorities:</span></span>

- <span data-ttu-id="49f25-105">Microsoft 앱과 서비스로 비즈니스 연속성을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-105">Ensure business continuity with Microsoft apps and services.</span></span>
- <span data-ttu-id="49f25-106">Microsoft의 최신 기능과 픽스로 장치, 서비스 및 데이터 보안을 최대화합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-106">Maximize device, service, and data security with the latest features and fixes from Microsoft.</span></span>
- <span data-ttu-id="49f25-107">Microsoft에서 제공하는 최신 기능을 사용하여 사용자 생산성을 최대화합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-107">Maximize user productivity with the latest features from Microsoft.</span></span>

<span data-ttu-id="49f25-108">이러한 목표는 광범위한 배포 이전에 기능적 유효성 검사를 위해 빠른 프로덕션 배포와 사용자와 장치의 대표 하위 집합을 통한 조기 심사 간의 균형을 찾는 IT 작업으로 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-108">These goals translate to the IT task of finding the balance between rapid production deployment and early vetting with a representative subset of users and devices to validate functionally before broad deployment.</span></span>

<span data-ttu-id="49f25-109">이 예제에서 조직은 유럽, 아프리카, 아시아 및 아메리카의 전 세계 건물에 5,000명의 직원을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-109">Our example organization has 5,000 employees in buildings across the world in Europe, Africa, Asia, and the Americas.</span></span> <span data-ttu-id="49f25-110">직원의 70%는 Microsoft 365 E3를 사용하고 나머지 조직은 Microsoft 365 E5를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-110">70% of the employees use Microsoft 365 E3 and the rest of the organization uses Microsoft 365 E5.</span></span>

>[!Note]
><span data-ttu-id="49f25-111">이 예제는 다양한 유형과 규모의 조직에 사용할 수 있는 배포 단계와 그룹을 사용하는 방법을 보여 주도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-111">This example is designed to show you how you can use deployment stages and groups, which can work for organizations of many types and sizes.</span></span>
>

<span data-ttu-id="49f25-112">이 조직의 IT 인프라:</span><span class="sxs-lookup"><span data-stu-id="49f25-112">This organization's IT infrastructure:</span></span> 

- <span data-ttu-id="49f25-113">대부분 Windows, Microsoft 365 앱 Microsoft 클라우드 서비스가 설치 기반의 60%로 동질적입니다. </span><span class="sxs-lookup"><span data-stu-id="49f25-113">Is largely homogeneous, with Windows, Microsoft 365 Apps, and Microsoft cloud services comprising 60% of the installed base.</span></span> <span data-ttu-id="49f25-114">IT 인프라를 단순화하고 간소화하기 위해 집중적으로 다년간 노력을 기울인 끝에 몇 가지 레거시 시스템이 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-114">A few legacy systems remain after an intensive, multi-year effort to simplify and streamline the IT infrastructure.</span></span>
- <span data-ttu-id="49f25-115">풍부한 경험이 있는 직원이 관리하고 Microsoft의 릴리스를 따라 사용자와 장치의 생산성과 보안을 유지하는 업무를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-115">Is maintained by highly experienced staff and tasked with keeping users and their devices productive and secure by following Microsoft’s lead in their releases.</span></span>

## <a name="deployment-and-update-stages"></a><span data-ttu-id="49f25-116">배포 및 업데이트 단계</span><span class="sxs-lookup"><span data-stu-id="49f25-116">Deployment and update stages</span></span>

<span data-ttu-id="49f25-117">이 예제에서 조직은 최신 릴리스의 빠른 배포 목표에 따라 2단계 배포 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-117">Based on rapid deployment goals of the latest release, this example organization uses a two-step deployment process.</span></span>

1. <span data-ttu-id="49f25-118">**미리 보기 또는 파일럿 배포 사용:** 얼리어답터, IT 담당자, 대표 구성의 사용자 및 교육 담당자를 확인하고 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-118">**Use a preview or pilot deployment:** Validate and iterate with early adopters, IT staff, users with representative configurations, and training staff.</span></span> 

   <span data-ttu-id="49f25-119">얼리어답터, IT 담당자, 대표 구성의 사용자는 새 기능이 조직의 나머지 부분에 배포되기 전에 다른 앱과 장치에서 기능의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-119">The early adopters, IT staff, users with representative configurations can validate functionality with other apps and on devices before the new features roll out to the rest of the organization.</span></span>

   <span data-ttu-id="49f25-120">변경 관리자는 광범위한 배포 전에 새로운 기능을 미리 살펴보고 메시징과 배포를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-120">Change managers have an early peek at the new features before widespread rollout and can plan messaging and rollout.</span></span>

   <span data-ttu-id="49f25-121">교육 담당자는 광범위하게 배포하기 전에 새 내부 교육 과정을 계획하거나 새로운 기능에 대해 기존 교육 과정을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-121">Training staff can plan new internal courses or update existing courses for the new features before widespread rollout.</span></span>

2. <span data-ttu-id="49f25-122">**프로덕션 배포:** 지역, 부서 또는 기타 배포 방법별로 나머지 모든 사용자에게 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-122">**Production deployment:** Roll out to all remaining users by region, department, or other deployment method.</span></span>

## <a name="deployment-configuration-for-windows-10"></a><span data-ttu-id="49f25-123">Windows 10용 배포 구성</span><span class="sxs-lookup"><span data-stu-id="49f25-123">Deployment configuration for Windows 10</span></span>

<span data-ttu-id="49f25-124">전반적인 목표는 대표 사용자 그룹과 사용자의 장치 그룹에 의한 릴리스 미리 보기 채널 변경 사항의 유효성을 확인한 후 최신 반기 채널 릴리스를 광범위하게 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-124">The overall goal is to perform a broad deployment of the latest Semi-Annual Channel release after validation of Release Preview Channel changes by a group of representative users and their devices.</span></span>

<span data-ttu-id="49f25-125">Windows 10 배포 방법 및 전략에 대한 자세한 내용은 [Windows 10 배포](https://docs.microsoft.com/windows/deployment/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49f25-125">See [Windows 10 deployment](https://docs.microsoft.com/windows/deployment/) for more information on Windows 10 deployment methods and strategies.</span></span>

| <span data-ttu-id="49f25-126">단계</span><span class="sxs-lookup"><span data-stu-id="49f25-126">Stage</span></span> | <span data-ttu-id="49f25-127">채널</span><span class="sxs-lookup"><span data-stu-id="49f25-127">Channel</span></span> | <span data-ttu-id="49f25-128">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="49f25-128">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="49f25-129">파일럿</span><span class="sxs-lookup"><span data-stu-id="49f25-129">Pilot</span></span> |  <span data-ttu-id="49f25-130">**릴리스 미리 보기**</span><span class="sxs-lookup"><span data-stu-id="49f25-130">**Release Preview Channel**</span></span>  <ul><li><span data-ttu-id="49f25-131">목적: 대표 장치와 구성(언어, 타사 앱)에 대한 유효성 검사를 위해 IT 담당자와 얼리어답터에게 기능 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="49f25-131">Purpose: Deployment of feature updates to IT staff and early adopters for validation on representative devices and configurations (languages, 3rd party apps).</span></span> </li><li> <span data-ttu-id="49f25-132">상태: 상업적 고객에게 완전히 호환되고 지원되며 귀하의 지원 계약에 불리하게 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-132">State: Fully compliant and supported for commercial customers and it does not count against your support agreements.</span></span> </li></ul> | <span data-ttu-id="49f25-133">**Win10ReleasePreviewChannel**(예제 이름)</span><span class="sxs-lookup"><span data-stu-id="49f25-133">**Win10ReleasePreviewChannel** (example name)</span></span> <br><br> <span data-ttu-id="49f25-134">구성원은 다음을 포함하는 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-134">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="49f25-135">부서와 위치에 관계없는 Windows 마니아</span><span class="sxs-lookup"><span data-stu-id="49f25-135">Windows enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="49f25-136">유효성 검사가 필요한 구성이 있는 직원</span><span class="sxs-lookup"><span data-stu-id="49f25-136">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="49f25-137">IT 관리자 및 IT 배포 담당자</span><span class="sxs-lookup"><span data-stu-id="49f25-137">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="49f25-138">변경 관리자</span><span class="sxs-lookup"><span data-stu-id="49f25-138">Change managers</span></span> </li><li> <span data-ttu-id="49f25-139">내부 교육 담당자</span><span class="sxs-lookup"><span data-stu-id="49f25-139">Internal training staff</span></span> </li></ul> |
| <span data-ttu-id="49f25-140">프로덕션</span><span class="sxs-lookup"><span data-stu-id="49f25-140">Production</span></span> |  <span data-ttu-id="49f25-141">**반기 채널**</span><span class="sxs-lookup"><span data-stu-id="49f25-141">**Semi-Annual Channel**</span></span>  <ul><li><span data-ttu-id="49f25-142">목적: 조직의 나머지 부분에 최신 기능 업데이트의 광범위한 배포</span><span class="sxs-lookup"><span data-stu-id="49f25-142">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="49f25-143">상태: 완전히 호환되고 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-143">State: Fully compliant and supported.</span></span> </li></ul> | <span data-ttu-id="49f25-144">**Win10SemiAnnualChannel**(예제 이름)</span><span class="sxs-lookup"><span data-stu-id="49f25-144">**Win10SemiAnnualChannel** (example name)</span></span> <br><br> <span data-ttu-id="49f25-145">구성원은 Win10ReleasePreviewChannel 그룹에 속하지 않은 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-145">Members are all users that are not in the Win10ReleasePreviewChannel group.</span></span> |
||||

<span data-ttu-id="49f25-146">이 조직은 Windows Update 또는 Windows Server Update Services와 같은 반기 채널 릴리스를 배포할 때와 같은 방식으로 릴리스 미리 보기 채널 페이로드를 배포하는 모범 사례를 사용하며 두 채널 업데이트에 대해 동일한 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-146">This organization uses the best practice of deploying the Release Preview Channel payload in the same way as they deploy Semi-Annual Channel releases, such as Windows Update or Windows Server Update Services, and that they apply the same policies for both channel updates.</span></span>

<span data-ttu-id="49f25-147">진행 중인 업데이트 프로세스:</span><span class="sxs-lookup"><span data-stu-id="49f25-147">Ongoing updates process:</span></span>

1. <span data-ttu-id="49f25-148">릴리스 미리 보기 채널 변경 내용이 Win10ReleasePreviewChannel(예제 이름) 배포 그룹에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-148">Release Preview Channel changes are deployed to the Win10ReleasePreviewChannel (example name) deployment group.</span></span>
2. <span data-ttu-id="49f25-149">Win10ReleasePreviewChannel 그룹 구성원은 릴리즈 미리 보기 채널 변경 내용이 작동함을 IT 배포 담당자에게 확인해 줍니다. 이들은 Microsoft에 피드백을 제공하고 추가 유효성 검사를 위해 다음 릴리스 미리 보기 채널 변경 내용을 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-149">Win10ReleasePreviewChannel group members confirm that Release Preview Channel changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Release Preview Channel changes for additional validation.</span></span>
3. <span data-ttu-id="49f25-150">반기 채널 기능 변경 내용이 Win10SemiAnnualChannel 배포 그룹에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-150">Semi-Annual Channel feature changes are deployed to the Win10SemiAnnualChannel deployment group.</span></span> 

>[!Note]
><span data-ttu-id="49f25-151">반기 채널을 사용하는 것이 좋지만, IT 부서는 관리 도구를 활용하여 조직 내에서 최신 반기 채널 릴리스를 배포할 시기를 결정한 다음 단계별로 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-151">While the Semi-Annual Channel is the recommended channel, your IT department should utilize their management tools and determine when to deploy the latest Semi-Annual Channel release within their organization and then roll it out in waves.</span></span>
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a><span data-ttu-id="49f25-152">Microsoft 365 앱에 대한 배포 구성</span><span class="sxs-lookup"><span data-stu-id="49f25-152">Deployment configuration for Microsoft 365 Apps</span></span>

<span data-ttu-id="49f25-153">전반적인 목표는 대표 사용자 그룹과 사용자의 장치 그룹에 의한 현재 채널(미리 보기) 변경 사항의 유효성을 확인한 후 현재 채널(미리 보기) 릴리스를 광범위하게 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-153">The overall goal is to perform a broad deployment of the latest Current Channel release after validation of Current Channel (Preview) changes by a group of representative users.</span></span>

<span data-ttu-id="49f25-154">Microsoft 365 앱 배포 방법 및 전략에 대한 자세한 내용은 [Microsoft 365 앱 배포](https://docs.microsoft.com/deployoffice/plan-office-365-proplus)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49f25-154">See [Microsoft 365 Apps deployment](https://docs.microsoft.com/deployoffice/plan-office-365-proplus) for more information on Microsoft 365 Apps deployment methods and strategies.</span></span>

| <span data-ttu-id="49f25-155">단계</span><span class="sxs-lookup"><span data-stu-id="49f25-155">Stage</span></span> | <span data-ttu-id="49f25-156">채널</span><span class="sxs-lookup"><span data-stu-id="49f25-156">Channel</span></span> | <span data-ttu-id="49f25-157">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="49f25-157">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="49f25-158">파일럿</span><span class="sxs-lookup"><span data-stu-id="49f25-158">Pilot</span></span> |  <span data-ttu-id="49f25-159">**현재 채널(미리 보기)**</span><span class="sxs-lookup"><span data-stu-id="49f25-159">**Current Channel (Preview)**</span></span> <ul><li> <span data-ttu-id="49f25-160">목적: {대표 사용자 그룹에 새로운 Microsoft 365 앱 기능 살짝 살펴보기 제공} 현재 기능(미리 보기) 사용자를 대상으로 테스트하고 프로덕션 준비가 완료되는 즉시 기능 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="49f25-160">Purpose: {give a group of representative users a sneak peek of new Microsoft 365 Apps features} Deployment of feature updates as soon as they are tested with Current Channel (Preview) users and are production-ready.</span></span> </li><li> <span data-ttu-id="49f25-161">상태: 완전히 호환되고 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-161">State: Fully compliant and supported.</span></span></li><li> <span data-ttu-id="49f25-162">빈도: 매월 2~3번 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-162">How often: Updates 2-3 times each month.</span></span> </li></ul> | <span data-ttu-id="49f25-163">**AppsCurrentChannelPreview**(예제 이름)</span><span class="sxs-lookup"><span data-stu-id="49f25-163">**AppsCurrentChannelPreview** (example name)</span></span> <br><br> <span data-ttu-id="49f25-164">구성원은 다음을 포함하는 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-164">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="49f25-165">부서와 위치에 관계없는 Office 앱 마니아</span><span class="sxs-lookup"><span data-stu-id="49f25-165">Office apps enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="49f25-166">유효성 검사가 필요한 구성이 있는 직원</span><span class="sxs-lookup"><span data-stu-id="49f25-166">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="49f25-167">IT 관리자 및 IT 배포 담당자</span><span class="sxs-lookup"><span data-stu-id="49f25-167">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="49f25-168">변경 관리자</span><span class="sxs-lookup"><span data-stu-id="49f25-168">Change managers</span></span> </li><li> <span data-ttu-id="49f25-169">내부 교육 담당자</span><span class="sxs-lookup"><span data-stu-id="49f25-169">Internal training staff</span></span> </li></ul>|
| <span data-ttu-id="49f25-170">프로덕션</span><span class="sxs-lookup"><span data-stu-id="49f25-170">Production</span></span> | <span data-ttu-id="49f25-171">**현재 채널**</span><span class="sxs-lookup"><span data-stu-id="49f25-171">**Current Channel**</span></span> <ul><li> <span data-ttu-id="49f25-172">목적: 조직의 나머지 부분에 최신 기능 업데이트의 광범위한 배포</span><span class="sxs-lookup"><span data-stu-id="49f25-172">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="49f25-173">상태: 완전히 호환되고 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-173">State: Fully compliant and supported.</span></span> </li></ul> |  <span data-ttu-id="49f25-174">**AppsCurrentChannel**(예제 이름)</span><span class="sxs-lookup"><span data-stu-id="49f25-174">**AppsCurrentChannel** (example name)</span></span> <br><br> <span data-ttu-id="49f25-175">구성원은 AppsCurrentChannelPreview 그룹에 속하지 않은 모든 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-175">Members are all users that are not in the AppsCurrentChannelPreview group.</span></span> |
|||

<span data-ttu-id="49f25-176">진행 중인 업데이트 프로세스:</span><span class="sxs-lookup"><span data-stu-id="49f25-176">Ongoing updates process:</span></span>

1. <span data-ttu-id="49f25-177">현재 채널(미리 보기) 변경 내용이 AppsCurrentChannelPreview 배포 그룹에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-177">Current Channel (Preview) changes are deployed to the AppsCurrentChannelPreview deployment group.</span></span>
2. <span data-ttu-id="49f25-178">AppsCurrentChannelPreview 그룹 구성원은 현재 채널(미리 보기) 변경 내용이 작동함을 IT 배포 담당자에게 확인해 줍니다. 이들은 Microsoft에 피드백을 제공하고 추가 유효성 검사를 위해 다음 릴리스 미리 보기 채널 변경 내용을 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-178">AppsCurrentChannelPreview group members confirm that Current Channel (Preview) changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Current Channel (Preview) release for additional validation.</span></span>
3. <span data-ttu-id="49f25-179">현재 채널 변경 내용이 AppsCurrentChannel 배포 그룹에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-179">Current Channel changes are deployed to the AppsCurrentChannel deployment group.</span></span> 

## <a name="visual-summary"></a><span data-ttu-id="49f25-180">시각적 요약</span><span class="sxs-lookup"><span data-stu-id="49f25-180">Visual summary</span></span>

<span data-ttu-id="49f25-181">다음은 이 예제 조직에서 사용하는 제품, 해당 채널 및 배포 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="49f25-181">Here are the products, their channels, and the deployment groups used by this example organization.</span></span> 

![최신 릴리스의 광범위한 배포를 위한 배포 그룹](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a><span data-ttu-id="49f25-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49f25-183">See also</span></span>

[<span data-ttu-id="49f25-184">배포 및 업데이트 채널 예제 구성</span><span class="sxs-lookup"><span data-stu-id="49f25-184">Deployment and update channel example configurations</span></span>](deploy-update-channels-examples.md)

[<span data-ttu-id="49f25-185">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="49f25-185">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="49f25-186">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="49f25-186">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
