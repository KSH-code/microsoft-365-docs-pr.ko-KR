---
title: Microsoft 365 Lighthouse 목록 개요
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
description: 테넌트 목록을 사용하는 MSP(관리 Microsoft 365 Lighthouse 공급자)의 경우 테넌트 목록에 대해 자세히 알아보면 됩니다.
ms.openlocfilehash: 05c6bf6c1b9529d05fac04c2d5c43802280cfbc9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395337"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a><span data-ttu-id="8586d-103">Microsoft 365 Lighthouse 목록 개요</span><span class="sxs-lookup"><span data-stu-id="8586d-103">Microsoft 365 Lighthouse tenant list overview</span></span>

> [!NOTE]
> <span data-ttu-id="8586d-104">이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="8586d-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="8586d-105">조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="8586d-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="8586d-106">Microsoft 365 Lighthouse 테넌트 목록은 테넌트에 대한 상대적인 테넌트 온보더링 상태를 포함하여 계약을 체결한 다른 테넌트에 대한 Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="8586d-106">The Microsoft 365 Lighthouse tenant list provides insights into the different tenants you have a contract with, including tenant onboarding status relative to Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="8586d-107">또한 테넌트 목록에 태그를 지정하여 테넌트 전체에 다양한 필터를 Microsoft 365 Lighthouse, 드릴다운하여 특정 테넌트 및 배포 계획의 상태에 대해 자세히 알아보는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-107">The tenant list also lets you tag tenants to provide different filters throughout Microsoft 365 Lighthouse, and drill down to learn more about a given tenant and the status of their deployment plan.</span></span>

<span data-ttu-id="8586d-108">테넌트가 Microsoft 365 Lighthouse [](m365-lighthouse-requirements.md)요구 사항을 충족하면 해당 상태가 테넌트 목록에 **활성으로** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-108">After your tenants meet the [Microsoft 365 Lighthouse onboarding requirements](m365-lighthouse-requirements.md), their status will show as **Active** in the tenant list.</span></span>

<span data-ttu-id="8586d-109">Microsoft 365 Lighthouse 테넌트 목록에 액세스하려면 왼쪽  탐색 창에서 테넌트를 선택하여 테넌트 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-109">To access the tenant list in Microsoft 365 Lighthouse, select **Tenants** in the left navigation pane to open the Tenants page.</span></span>

## <a name="tenant-status"></a><span data-ttu-id="8586d-110">테넌트 상태</span><span class="sxs-lookup"><span data-stu-id="8586d-110">Tenant status</span></span>

<span data-ttu-id="8586d-111">다음 표에는 다양한 상태 메시지와 그 의미가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-111">The following table shows the different status messages and their meaning.</span></span><br><br>

| <span data-ttu-id="8586d-112">상태 메시지</span><span class="sxs-lookup"><span data-stu-id="8586d-112">Status message</span></span> | <span data-ttu-id="8586d-113">설명</span><span class="sxs-lookup"><span data-stu-id="8586d-113">Description</span></span> |
|--|--|
| <span data-ttu-id="8586d-114">활성</span><span class="sxs-lookup"><span data-stu-id="8586d-114">Active</span></span> | <span data-ttu-id="8586d-115">온보더링 및 데이터 흐름이 시작된 경우</span><span class="sxs-lookup"><span data-stu-id="8586d-115">Onboarding and data flow has started.</span></span> |
| <span data-ttu-id="8586d-116">In process</span><span class="sxs-lookup"><span data-stu-id="8586d-116">In process</span></span> | <span data-ttu-id="8586d-117">테넌트가 검색되지만 완전히 온보드된 것은 아니며 검색된 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-117">Tenant discovered, but not fully onboarded.</span></span> |
| <span data-ttu-id="8586d-118">부적임, DAP</span><span class="sxs-lookup"><span data-stu-id="8586d-118">Ineligible, DAP</span></span> | <span data-ttu-id="8586d-119">DAP(위임된 관리자 권한) 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-119">Delegated Admin Privileges (DAP) setup is required.</span></span> |
| <span data-ttu-id="8586d-120">부적정, 사용자 수</span><span class="sxs-lookup"><span data-stu-id="8586d-120">Ineligible, user count</span></span> | <span data-ttu-id="8586d-121">테넌트에 허용되는 것보다 많은 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-121">Tenant has more users than allowed.</span></span> |
| <span data-ttu-id="8586d-122">부적임, 라이선스</span><span class="sxs-lookup"><span data-stu-id="8586d-122">Ineligible, license</span></span> | <span data-ttu-id="8586d-123">테넌트에는 필수 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-123">Tenant does not have required license.</span></span> |
| <span data-ttu-id="8586d-124">비활성</span><span class="sxs-lookup"><span data-stu-id="8586d-124">Inactive</span></span> | <span data-ttu-id="8586d-125">테넌트가 더 이상 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-125">Tenant is no longer active.</span></span> |

<span data-ttu-id="8586d-126">테넌트의 비활성화가 완료되면 비활성화 프로세스를 완료하는 동안 테넌트에 Microsoft 365 Lighthouse 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-126">Once you inactivate a tenant, you can't take action on the tenant while Microsoft 365 Lighthouse completes the inactivation process.</span></span> <span data-ttu-id="8586d-127">비활성화가 완료될 때 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-127">It may take up to 48 hours for inactivation to complete.</span></span>

<span data-ttu-id="8586d-128">테넌트를 다시 활성화하기로 결정한 경우 데이터가 다시 그려지기까지 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-128">If you decide to reactivate a tenant, it may take up to 48 hours for data to reappear.</span></span>

## <a name="tenant-tags"></a><span data-ttu-id="8586d-129">테넌트 태그</span><span class="sxs-lookup"><span data-stu-id="8586d-129">Tenant tags</span></span>

<span data-ttu-id="8586d-130">고객 테넌트에 사용자 지정 레이블을 사용하여 고객 테넌트에 태그를 Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="8586d-130">You can tag your customer tenants with a custom label within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="8586d-131">이러한 태그를 사용하여 테넌트를 구성할 수 있으며 관련 고객 테넌트 집합에 사용할 수 있는 기존 보기 및 정보를 쉽게 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-131">These tags can be used to organize your tenants and can also help you easily filter the existing views and insights available to relevant sets of customer tenants.</span></span> <span data-ttu-id="8586d-132">테넌트 페이지에서 태그와 태그가 할당된 테넌트도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8586d-132">You can also manage your tags and which tenants they're assigned to from the Tenants page.</span></span>

## <a name="related-content"></a><span data-ttu-id="8586d-133">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8586d-133">Related content</span></span>

<span data-ttu-id="8586d-134">[요구 사항](m365-lighthouse-requirements.md) Microsoft 365 Lighthouse(문서)</span><span class="sxs-lookup"><span data-stu-id="8586d-134">[Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (article)</span></span>\
<span data-ttu-id="8586d-135">[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="8586d-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>