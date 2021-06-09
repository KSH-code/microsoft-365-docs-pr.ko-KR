---
title: 구성 가능한 설정 배포를 Microsoft Managed Desktop
description: 구성 가능한 설정 변경 내용을 배포하고 추적할 수 Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104537"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="6a6f2-104">구성 가능한 설정 배포 및 추적 - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="6a6f2-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="6a6f2-105">설정 범주를 변경하고 배포를 단계별로 변경한 후 배포 상태 페이지에서는 그룹에 설정을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="6a6f2-106">이 페이지에는 구성 가능한 각 설정에 대한 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="6a6f2-107">설정 범주를 열면 그룹에 설정을 배포하고 이러한 배포의 진행률을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="6a6f2-108">배포 상태</span><span class="sxs-lookup"><span data-stu-id="6a6f2-108">Deployment statuses</span></span> 

<span data-ttu-id="6a6f2-109">다음은 각 배포에 대해 확인할 수 있는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="6a6f2-110">상태</span><span class="sxs-lookup"><span data-stu-id="6a6f2-110">Status</span></span>  | <span data-ttu-id="6a6f2-111">설명</span><span class="sxs-lookup"><span data-stu-id="6a6f2-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="6a6f2-112">배포</span><span class="sxs-lookup"><span data-stu-id="6a6f2-112">Deploy</span></span> | <span data-ttu-id="6a6f2-113">변경이 이 그룹에 배포 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="6a6f2-114">진행 중</span><span class="sxs-lookup"><span data-stu-id="6a6f2-114">In progress</span></span> | <span data-ttu-id="6a6f2-115">이 그룹의 활성 장치에 변경이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="6a6f2-116">전체</span><span class="sxs-lookup"><span data-stu-id="6a6f2-116">Complete</span></span> | <span data-ttu-id="6a6f2-117">이 그룹의 모든 활성 장치에서 변경이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="6a6f2-118">실패</span><span class="sxs-lookup"><span data-stu-id="6a6f2-118">Failed</span></span> | <span data-ttu-id="6a6f2-119">그룹의 활성 장치의 10%에서 변경이 실패하여 배포가 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="6a6f2-120">배포 문제를 해결하기 위한 Microsoft Managed Desktop 지원 요청이 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="6a6f2-121">되전</span><span class="sxs-lookup"><span data-stu-id="6a6f2-121">Reverted</span></span> | <span data-ttu-id="6a6f2-122">변경된 변경은 모든 배포 그룹에 성공적으로 배포된 마지막 변경으로 되 고쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="6a6f2-123">변경 내용 배포</span><span class="sxs-lookup"><span data-stu-id="6a6f2-123">Deploy changes</span></span>

<span data-ttu-id="6a6f2-124">이 지침에서는 바탕 화면 배경 그림을 보여 준다고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="6a6f2-125">배포를 구성한 후 배포 상태 페이지에서 변경 내용을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="6a6f2-126">**변경 내용을 배포하는 경우**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-126">**To deploy changes**</span></span>

1. <span data-ttu-id="6a6f2-127">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="6a6f2-128">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="6a6f2-129">배포 **상태** 작업 영역에서 배포할 설정을 선택한 다음 배포할 단계적 배포를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="6a6f2-130">배포 **그룹** 중 하나에 변경을 배포하려면 배포를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="6a6f2-131">주황색 주의 아이콘은 배포에 사용할 수 있는 이전 그룹이 있습니다. 순서대로 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="6a6f2-132">테스트, 첫 번째, 빠르기, 광범위 순서대로 배포 그룹에 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="6a6f2-133">각 그룹에서 변경이 완료되면 상태가 완료로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="6a6f2-134">배포 되버리기</span><span class="sxs-lookup"><span data-stu-id="6a6f2-134">Revert deployment</span></span>

<span data-ttu-id="6a6f2-135">변경을 배포한 후 배포 상태 에서 **되전할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="6a6f2-136">진행 중 또는 완료인  변경을 되전하면 현재 배포가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="6a6f2-137">이 설정은 모든 그룹에 배포된 마지막 버전으로 되버됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="6a6f2-138">예를 들어 데스크톱 배경 그림을 사용하여 변경을 되전하는 단계를 보여 주겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="6a6f2-139">**변경을 되버리기 위해**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-139">**To revert a change**</span></span>
1. <span data-ttu-id="6a6f2-140">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="6a6f2-141">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="6a6f2-142">배포 **상태** 작업 영역에서 되전할 설정을 선택한 다음 되전할 단계적 배포를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a6f2-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="6a6f2-143">이 **변경을 되전해야 하나요?** 에서 배포 **되전을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6a6f2-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="6a6f2-144">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="6a6f2-144">Additional resources</span></span>
- [<span data-ttu-id="6a6f2-145">구성 가능한 설정 개요</span><span class="sxs-lookup"><span data-stu-id="6a6f2-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="6a6f2-146">구성 가능한 설정 참조</span><span class="sxs-lookup"><span data-stu-id="6a6f2-146">Configurable settings reference</span></span>](config-setting-ref.md) 
