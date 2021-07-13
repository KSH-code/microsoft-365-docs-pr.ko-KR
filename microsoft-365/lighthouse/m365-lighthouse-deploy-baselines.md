---
title: 기본 Microsoft 365 Lighthouse 배포
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스를 사용하는 MSP(관리 서비스 공급자)의 Microsoft 365 Lighthouse 기준을 배포하는 Microsoft 365 Lighthouse 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395366"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="e4a12-103">기본 Microsoft 365 Lighthouse 배포</span><span class="sxs-lookup"><span data-stu-id="e4a12-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="e4a12-104">이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e4a12-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="e4a12-105">조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="e4a12-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="e4a12-106">Microsoft 365 Lighthouse 기준을 사용하면 표준 관리되는 테넌트 구성을 배포하여 테넌트 사용자, 장치 및 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="e4a12-107">기본 기본 구성은 다음 6개 기본 Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="e4a12-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="e4a12-108">관리자에게 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="e4a12-108">Require MFA for admins</span></span>
- <span data-ttu-id="e4a12-109">최종 사용자에 대해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="e4a12-109">Require MFA for end users</span></span>
- <span data-ttu-id="e4a12-110">레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="e4a12-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="e4a12-111">장치에서 장치 등록 Microsoft Endpoint Manager – Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="e4a12-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="e4a12-112">장치용 Defender 바이러스 백신 Windows 구성</span><span class="sxs-lookup"><span data-stu-id="e4a12-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="e4a12-113">디바이스에 대한 Windows 정책 구성</span><span class="sxs-lookup"><span data-stu-id="e4a12-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e4a12-114">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="e4a12-114">Before you begin</span></span>

<span data-ttu-id="e4a12-115">사용자 및 고객 테넌트가 요구 사항에 나열된 요구 사항을 [충족하는지](m365-lighthouse-requirements.md)Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="e4a12-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="e4a12-116">기본 기준에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="e4a12-116">Learn more about the default baseline</span></span>

<span data-ttu-id="e4a12-117">왼쪽 **탐색 창에서** 기준을 선택하여 기준 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="e4a12-118">기본 기준이 기본 테넌트 그룹(모든 테넌트)에 이미 추가된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="e4a12-119">기본 기준 구성을 확인하려면  기준 보기를 선택하여 기본 기준 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="e4a12-120">구성은 배포 단계로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="e4a12-121">배포 세부 정보 및 사용자 영향을 확인하려면 배포 단계를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Default baseline page.>.":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="e4a12-123">기준 구성 배포</span><span class="sxs-lookup"><span data-stu-id="e4a12-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="e4a12-124">왼쪽 탐색 페이지에서 테넌트 를 선택하여 온보드 테넌트 목록을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e4a12-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="e4a12-125">기준 구성을 배포할 테넌트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="e4a12-126">배포 **계획 탭을** 선택하여 테넌트의 배포 계획에 추가된 기준의 모든 배포 단계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="e4a12-127">배포 단계를 선택하여 배포 단계 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="e4a12-128">**적용을** 선택하여 선택한 배포 단계를 테넌트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="e4a12-129">배포 단계에 "이 작업을 수행하려면 수동 단계가 필요합니다."가 표시되면 배포 단계가 올바르게 적용될 수 있도록 수동 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a12-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="e4a12-130">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="e4a12-130">Related content</span></span>

<span data-ttu-id="e4a12-131">[기준을 사용하여](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) 표준 테넌트 구성 배포 개요(문서)</span><span class="sxs-lookup"><span data-stu-id="e4a12-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="e4a12-132">[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="e4a12-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>