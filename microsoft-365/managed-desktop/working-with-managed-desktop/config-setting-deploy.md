---
title: Microsoft Managed Desktop에서 구성 가능한 설정 배포
description: Microsoft Managed Desktop에서 구성 가능한 설정 변경 내용을 배포 하 고 추적 합니다.
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414173"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="959e9-104">구성 가능한 설정 배포 및 추적-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="959e9-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="959e9-105">설정 범주를 변경 하 고 배포를 준비 했으면 배포 상태에 대 한 배포 진행률을 배포 하 고 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-105">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status.</span></span> <span data-ttu-id="959e9-106">이 페이지에는 구성 가능한 각 설정에 대 한 요약이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="959e9-107">각 배포 및 해당 세부 정보를 확인 하려면 설정 범주를 열고 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-107">Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="959e9-108">배포 상태</span><span class="sxs-lookup"><span data-stu-id="959e9-108">Deployment statuses</span></span> 

<span data-ttu-id="959e9-109">각 배포에 대해 볼 수 있는 동상입니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="959e9-110">상태</span><span class="sxs-lookup"><span data-stu-id="959e9-110">Status</span></span>  | <span data-ttu-id="959e9-111">설명</span><span class="sxs-lookup"><span data-stu-id="959e9-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="959e9-112">배포</span><span class="sxs-lookup"><span data-stu-id="959e9-112">Deploy</span></span> | <span data-ttu-id="959e9-113">변경 내용이이 링으로 배포 되기를 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="959e9-114">진행 중</span><span class="sxs-lookup"><span data-stu-id="959e9-114">In progress</span></span> | <span data-ttu-id="959e9-115">변경 내용이이 링의 활성 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-115">The change is being applied to active devices in this ring.</span></span> 
<span data-ttu-id="959e9-116">작업이</span><span class="sxs-lookup"><span data-stu-id="959e9-116">Complete</span></span> | <span data-ttu-id="959e9-117">이 링의 모든 활성 장치에서 변경 내용이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-117">The change completed on all active devices in this ring.</span></span> 
<span data-ttu-id="959e9-118">Failed</span><span class="sxs-lookup"><span data-stu-id="959e9-118">Failed</span></span> | <span data-ttu-id="959e9-119">링에서 활성 장치의 10%가 변경 되지 않아 배포가 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-119">The change failed on a 10 percent of active devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="959e9-120">배포 문제를 해결 하기 위해 Microsoft Managed Desktop 작업을 사용 하 여 지원 요청이 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="959e9-121">되돌아갑니다</span><span class="sxs-lookup"><span data-stu-id="959e9-121">Reverted</span></span> | <span data-ttu-id="959e9-122">모든 배포 링에 성공적으로 배포 된 마지막 변경 내용으로 변경 내용을 되돌렸습니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="959e9-123">변경 내용 배포</span><span class="sxs-lookup"><span data-stu-id="959e9-123">Deploy changes</span></span>

<span data-ttu-id="959e9-124">이 지침에서는 바탕 화면 배경 그림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="959e9-125">배포를 단계적으로 완료 한 후 배포 상태에서 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-125">After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="959e9-126">**변경 내용을 배포 하려면**</span><span class="sxs-lookup"><span data-stu-id="959e9-126">**To deploy changes**</span></span>

1. <span data-ttu-id="959e9-127">[Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="959e9-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="959e9-128">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="959e9-129">**배포 상태** 작업 영역에서 배포할 설정을 선택 하 고 배포할 미리 구성 된 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="959e9-130">배포 \*\*\*\* 를 선택 하 여 배치 링 중 하나에 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![구성 가능한 설정 배포 상태 개요](images/deploy-cs-overview.png)

<span data-ttu-id="959e9-132">Microsoft Managed Desktop은 Test, First, Fast, 폭넓은 순서로 배포 링에 배포할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="959e9-133">각 링에서 변경이 완료 되 면 상태가 **완료**로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![구성 가능한 설정 배포 완료](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="959e9-135">배포 되돌리기</span><span class="sxs-lookup"><span data-stu-id="959e9-135">Revert deployment</span></span>

<span data-ttu-id="959e9-136">이 지침에서는 바탕 화면 배경 그림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="959e9-137">변경 내용을 배포한 후에는 **배포 상태**를 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-137">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="959e9-138">**진행** 중이거나 **완료**된 변경 내용을 되돌리면 현재 배포가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-138">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="959e9-139">이 설정은 모든 링에 배포 된 마지막 버전으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-139">The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="959e9-140">**변경 내용을 되돌리려면**</span><span class="sxs-lookup"><span data-stu-id="959e9-140">**To revert a change**</span></span>
1. <span data-ttu-id="959e9-141">[Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="959e9-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="959e9-142">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="959e9-143">**배포 상태** 작업 영역에서 되돌리려는 설정을 선택 하 고 되돌릴 미리 구성 된 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="959e9-144">**이 변경 내용을 되돌릴 필요성**에서 **배포 되돌리기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="959e9-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![구성 가능한 설정 배포 되돌리기](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="959e9-146">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="959e9-146">Additional resources</span></span>
- [<span data-ttu-id="959e9-147">구성 가능한 설정 개요</span><span class="sxs-lookup"><span data-stu-id="959e9-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="959e9-148">구성 가능한 설정 참조</span><span class="sxs-lookup"><span data-stu-id="959e9-148">Configurable settings reference</span></span>](config-setting-ref.md) 