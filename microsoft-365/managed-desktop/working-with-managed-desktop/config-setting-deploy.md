---
title: Microsoft Managed Desktop에서 구성 가능한 설정 배포
description: Microsoft Managed Desktop에서 구성 가능한 설정 변경 내용을 배포 하 고 추적 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5b6a2756514e94cb4f96141d6e7c9f6f2a6dd7ff
ms.sourcegitcommit: a4657a499967751d4c2dfc6cd1904258ab8be193
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37040811"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="0cfb5-104">구성 가능한 설정 배포 및 추적-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0cfb5-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="0cfb5-105">설정 범주를 변경 하 고 배포를 준비 했으면 배포 상태 페이지에서 그룹에 대 한 설정을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="0cfb5-106">이 페이지에는 구성 가능한 각 설정에 대 한 요약이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="0cfb5-107">설정 범주를 열면 설정을 그룹에 배포 하 고 해당 배포의 진행 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="0cfb5-108">배포 상태</span><span class="sxs-lookup"><span data-stu-id="0cfb5-108">Deployment statuses</span></span> 

<span data-ttu-id="0cfb5-109">각 배포에 대해 표시 되는 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="0cfb5-110">상태</span><span class="sxs-lookup"><span data-stu-id="0cfb5-110">Status</span></span>  | <span data-ttu-id="0cfb5-111">설명</span><span class="sxs-lookup"><span data-stu-id="0cfb5-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="0cfb5-112">배포</span><span class="sxs-lookup"><span data-stu-id="0cfb5-112">Deploy</span></span> | <span data-ttu-id="0cfb5-113">변경 내용이이 그룹에 배포 되기를 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="0cfb5-114">진행 중</span><span class="sxs-lookup"><span data-stu-id="0cfb5-114">In progress</span></span> | <span data-ttu-id="0cfb5-115">변경 내용이이 그룹의 활성 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="0cfb5-116">작업이</span><span class="sxs-lookup"><span data-stu-id="0cfb5-116">Complete</span></span> | <span data-ttu-id="0cfb5-117">이 그룹의 모든 활성 장치에서 변경 내용이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="0cfb5-118">Failed</span><span class="sxs-lookup"><span data-stu-id="0cfb5-118">Failed</span></span> | <span data-ttu-id="0cfb5-119">그룹의 활성 장치 중 10%에서 변경이 실패 하 여 배포가 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="0cfb5-120">배포 문제를 해결 하기 위해 Microsoft Managed Desktop 작업을 사용 하 여 지원 요청이 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="0cfb5-121">되돌아갑니다</span><span class="sxs-lookup"><span data-stu-id="0cfb5-121">Reverted</span></span> | <span data-ttu-id="0cfb5-122">변경 내용이 모든 배포 그룹에 성공적으로 배포 된 마지막 변경 내용으로 되돌아갔습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="0cfb5-123">변경 내용 배포</span><span class="sxs-lookup"><span data-stu-id="0cfb5-123">Deploy changes</span></span>

<span data-ttu-id="0cfb5-124">이 지침에서는 바탕 화면 배경 그림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="0cfb5-125">배포를 단계적으로 완료 한 후 배포 상태 페이지에서 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="0cfb5-126">**변경 내용을 배포 하려면**</span><span class="sxs-lookup"><span data-stu-id="0cfb5-126">**To deploy changes**</span></span>

1. <span data-ttu-id="0cfb5-127">[Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="0cfb5-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="0cfb5-128">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="0cfb5-129">**배포 상태** 작업 영역에서 배포할 설정을 선택 하 고 배포할 미리 구성 된 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="0cfb5-130">배포 **를 선택 하** 여 배치 그룹 중 하나에 변경 내용을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="0cfb5-131">![구성 가능한 설정 배포 상태](images/1deployedit.png) 개요 Microsoft Managed Desktop은 Test, First, Fast, 폭넓은 순서로 배포 그룹에 배포할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-131">![Configurable settings deployment status overview](images/1deployedit.png) Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="0cfb5-132">각 그룹에서 변경 내용이 완료 되 면 상태가 **완료**로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-132">When changes complete in each group, the status changes to **Complete**.</span></span>

![구성 가능한 설정 배포 완료](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="0cfb5-134">배포 되돌리기</span><span class="sxs-lookup"><span data-stu-id="0cfb5-134">Revert deployment</span></span>

<span data-ttu-id="0cfb5-135">변경 내용을 배포한 후에는 **배포 상태**를 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="0cfb5-136">**진행** 중이거나 **완료**된 변경 내용을 되돌리면 현재 배포가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="0cfb5-137">이 설정은 모든 그룹에 배포 된 마지막 버전으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="0cfb5-138">예를 들어 데스크톱 배경 그림을 사용 하 여 변경 내용을 되돌리는 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="0cfb5-139">**변경 내용을 되돌리려면**</span><span class="sxs-lookup"><span data-stu-id="0cfb5-139">**To revert a change**</span></span>
1. <span data-ttu-id="0cfb5-140">[Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="0cfb5-140">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="0cfb5-141">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-141">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="0cfb5-142">**배포 상태** 작업 영역에서 되돌리려는 설정을 선택 하 고 되돌릴 미리 구성 된 배포를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="0cfb5-143">**이 변경 내용을 되돌릴 필요성**에서 **배포 되돌리기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-143">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![구성 가능한 설정 배포 되돌리기](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="0cfb5-145">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="0cfb5-145">Additional resources</span></span>
- [<span data-ttu-id="0cfb5-146">구성 가능한 설정 개요</span><span class="sxs-lookup"><span data-stu-id="0cfb5-146">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="0cfb5-147">구성 가능한 설정 참조</span><span class="sxs-lookup"><span data-stu-id="0cfb5-147">Configurable settings reference</span></span>](config-setting-ref.md) 
