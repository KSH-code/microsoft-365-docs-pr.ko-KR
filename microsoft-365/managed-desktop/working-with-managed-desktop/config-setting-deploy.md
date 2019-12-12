---
title: Microsoft Managed Desktop에서 구성 가능한 설정 배포
description: Microsoft Managed Desktop에서 구성 가능한 설정 변경 내용을 배포 하 고 추적 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962245"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="a86bb-104">구성 가능한 설정 배포 및 추적-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a86bb-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a86bb-105">설정 범주를 변경 하 고 배포를 준비 했으면 배포 상태 페이지에서 그룹에 대 한 설정을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="a86bb-106">이 페이지에는 구성 가능한 각 설정에 대 한 요약이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="a86bb-107">설정 범주를 열면 설정을 그룹에 배포 하 고 해당 배포의 진행 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="a86bb-108">배포 상태</span><span class="sxs-lookup"><span data-stu-id="a86bb-108">Deployment statuses</span></span> 

<span data-ttu-id="a86bb-109">각 배포에 대해 표시 되는 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="a86bb-110">상태</span><span class="sxs-lookup"><span data-stu-id="a86bb-110">Status</span></span>  | <span data-ttu-id="a86bb-111">설명</span><span class="sxs-lookup"><span data-stu-id="a86bb-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="a86bb-112">배포</span><span class="sxs-lookup"><span data-stu-id="a86bb-112">Deploy</span></span> | <span data-ttu-id="a86bb-113">변경 내용이이 그룹에 배포 되기를 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="a86bb-114">진행 중</span><span class="sxs-lookup"><span data-stu-id="a86bb-114">In progress</span></span> | <span data-ttu-id="a86bb-115">변경 내용이이 그룹의 활성 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="a86bb-116">작업이</span><span class="sxs-lookup"><span data-stu-id="a86bb-116">Complete</span></span> | <span data-ttu-id="a86bb-117">이 그룹의 모든 활성 장치에서 변경 내용이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="a86bb-118">Failed</span><span class="sxs-lookup"><span data-stu-id="a86bb-118">Failed</span></span> | <span data-ttu-id="a86bb-119">그룹의 활성 장치 중 10%에서 변경이 실패 하 여 배포가 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="a86bb-120">배포 문제를 해결 하기 위해 Microsoft Managed Desktop 작업을 사용 하 여 지원 요청이 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="a86bb-121">되돌아갑니다</span><span class="sxs-lookup"><span data-stu-id="a86bb-121">Reverted</span></span> | <span data-ttu-id="a86bb-122">변경 내용이 모든 배포 그룹에 성공적으로 배포 된 마지막 변경 내용으로 되돌아갔습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="a86bb-123">변경 내용 배포</span><span class="sxs-lookup"><span data-stu-id="a86bb-123">Deploy changes</span></span>

<span data-ttu-id="a86bb-124">이 지침에서는 바탕 화면 배경 그림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="a86bb-125">배포를 단계적으로 완료 한 후 배포 상태 페이지에서 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="a86bb-126">**변경 내용을 배포 하려면**</span><span class="sxs-lookup"><span data-stu-id="a86bb-126">**To deploy changes**</span></span>

1. <span data-ttu-id="a86bb-127">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="a86bb-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a86bb-128">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a86bb-129">**배포 상태** 작업 영역에서 배포할 설정을 선택 하 고 배포할 미리 구성 된 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="a86bb-130">배포 **를 선택 하** 여 배치 그룹 중 하나에 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="a86bb-131">![배포 상태 작업 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-131">![Deployment status workspace.</span></span> <span data-ttu-id="a86bb-132">오른쪽의 신뢰할 수 있는 사이트 창입니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-132">Trusted sites pane on the right.</span></span> <span data-ttu-id="a86bb-133">배포 그룹 섹션에는 배포 그룹, 장치 및 상태의 세 가지 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-133">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="a86bb-134">상태 열에서 "배포"가 강조 표시 됩니다.](images/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="a86bb-134">In the status column, "deploy" is highlighted.](images/1deployedit.png)</span></span>
<span data-ttu-id="a86bb-135">Test, First, Fast, 폭넓은 순서로 배포 그룹에 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-135">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="a86bb-136">각 그룹에서 변경 내용이 완료 되 면 상태가 **완료**로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-136">When changes complete in each group, the status changes to **Complete**.</span></span>

![업데이트, 버전, 테스트, 처음, 빠르게, 광범위 한 열이 포함 된 배포 상태 작업 영역입니다.](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="a86bb-139">배포 되돌리기</span><span class="sxs-lookup"><span data-stu-id="a86bb-139">Revert deployment</span></span>

<span data-ttu-id="a86bb-140">변경 내용을 배포한 후에는 **배포 상태**를 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-140">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="a86bb-141">**진행** 중이거나 **완료**된 변경 내용을 되돌리면 현재 배포가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-141">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="a86bb-142">이 설정은 모든 그룹에 배포 된 마지막 버전으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-142">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="a86bb-143">예를 들어 데스크톱 배경 그림을 사용 하 여 변경 내용을 되돌리는 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-143">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="a86bb-144">**변경 내용을 되돌리려면**</span><span class="sxs-lookup"><span data-stu-id="a86bb-144">**To revert a change**</span></span>
1. <span data-ttu-id="a86bb-145">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="a86bb-145">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a86bb-146">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-146">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a86bb-147">**배포 상태** 작업 영역에서 되돌리려는 설정을 선택 하 고 되돌릴 미리 구성 된 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-147">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="a86bb-148">**이 변경 내용을 되돌릴 필요가 있습니까?** 에서 **배포 되돌리기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a86bb-148">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![배포 상태 작업 영역입니다.](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="a86bb-152">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a86bb-152">Additional resources</span></span>
- [<span data-ttu-id="a86bb-153">구성 가능한 설정 개요</span><span class="sxs-lookup"><span data-stu-id="a86bb-153">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="a86bb-154">구성 가능한 설정 참조</span><span class="sxs-lookup"><span data-stu-id="a86bb-154">Configurable settings reference</span></span>](config-setting-ref.md) 
