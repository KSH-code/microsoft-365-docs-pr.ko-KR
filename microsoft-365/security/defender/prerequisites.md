---
title: Microsoft 365 Defender 선행 준비
description: Defender의 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 Microsoft 365 정보
keywords: 요구 사항, 선행 조건, 하드웨어, 소프트웨어, 브라우저, Microsoft 365 Defender, M365, 라이선스, E5, A5, EMS, 구매
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f3fd597181d73c1768057ea7740ab111e5af2068
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689160"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="27c06-104">Microsoft 365 Defender 선행 준비</span><span class="sxs-lookup"><span data-stu-id="27c06-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27c06-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="27c06-105">**Applies to:**</span></span>
- <span data-ttu-id="27c06-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27c06-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="27c06-107">Defender를 프로비전하고 사용하는 라이선싱 [및 기타 요구 사항에 대해 Microsoft 365.](microsoft-365-defender.md)</span><span class="sxs-lookup"><span data-stu-id="27c06-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="27c06-108">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="27c06-108">Licensing requirements</span></span>
<span data-ttu-id="27c06-109">이러한 라이선스를 사용하면 추가 비용 없이 Microsoft 365 보안 센터의 Microsoft 365 Defender 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="27c06-110">Microsoft 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="27c06-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="27c06-111">Microsoft 365 E3 추가 Microsoft 365 E5 Security 있는 경우</span><span class="sxs-lookup"><span data-stu-id="27c06-111">Microsoft 365 E3 with the Microsoft 365 E5 Security add-on</span></span>
- <span data-ttu-id="27c06-112">Microsoft 365 A3 및 Microsoft 365 A5 보안 추가 기능</span><span class="sxs-lookup"><span data-stu-id="27c06-112">Microsoft 365 A3 with the Microsoft 365 A5 Security add-on</span></span>
- <span data-ttu-id="27c06-113">Windows 10 Enterprise E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="27c06-113">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="27c06-114">Enterprise Mobility + Security(EMS) E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="27c06-114">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="27c06-115">Office 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="27c06-115">Office 365 E5 or A5</span></span>
- <span data-ttu-id="27c06-116">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="27c06-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="27c06-117">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="27c06-117">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="27c06-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="27c06-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="27c06-119">Office 365용 Defender(플랜 2)</span><span class="sxs-lookup"><span data-stu-id="27c06-119">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="27c06-120">자세한 내용은 서비스 [Microsoft 365 Enterprise 를 참조하십시오.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="27c06-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="27c06-121">아직 라이선스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="27c06-121">Don't have license yet?</span></span> [<span data-ttu-id="27c06-122">Microsoft 365 구독 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="27c06-122">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="27c06-123">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="27c06-123">Check your existing  licenses</span></span>
<span data-ttu-id="27c06-124">기존 라이선스를 Microsoft 365 관리[](https://admin.microsoft.com/)센터(admin.microsoft.com)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="27c06-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="27c06-125">관리 센터에서 **청구** > **라이선스** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="27c06-126">라이선스 정보를 볼 수  있게 하려면  [Azure AD에서](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 청구 관리자 또는 전역 리더 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="27c06-127">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="27c06-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="27c06-128">필수 권한</span><span class="sxs-lookup"><span data-stu-id="27c06-128">Required permissions</span></span>
<span data-ttu-id="27c06-129">Defender를  켜기 위해  전역 관리자 또는 Azure Active Directory 관리자 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="27c06-130">Microsoft 365 Defender를 사용하는 데 필요한 역할 목록과 데이터에 대한 액세스가 규제되는 방법에 대한 정보는 Microsoft 365 Defender에 대한 액세스 [관리에 대해 읽어 보아야 합니다.](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="27c06-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="27c06-131">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="27c06-131">Browser requirements</span></span>
<span data-ttu-id="27c06-132">Microsoft 365, Microsoft 365, Internet Explorer Microsoft Edge 11 또는 HTML 5 호환 웹 브라우저를 사용하여 Microsoft 365 보안 센터에서 Internet Explorer Defender에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="27c06-133">US GCC, GCC High 및 기타 미국 정부 기관의 가용성</span><span class="sxs-lookup"><span data-stu-id="27c06-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="27c06-134">현재 다음 Microsoft 365 Defender를 *사용할 수* 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="27c06-135">US 정부 커뮤니티 클라우드(GCC)</span><span class="sxs-lookup"><span data-stu-id="27c06-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="27c06-136">US 정부 커뮤니티 클라우드 High(GCC High)</span><span class="sxs-lookup"><span data-stu-id="27c06-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="27c06-137">미 국방부</span><span class="sxs-lookup"><span data-stu-id="27c06-137">US Department of Defense</span></span>
- <span data-ttu-id="27c06-138">상업용 라이선스가 있는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="27c06-138">All US government institutions with commercial licenses</span></span>


<span data-ttu-id="27c06-139">현재 Microsoft Defender for Office 365 통합 Microsoft 365 Defend Office 365 er 기능에 통합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27c06-139">Currently, the Microsoft Defender for Office 365 integration into the unified Microsoft 365 Defender features are not available to customers in the following Office 365 datacenter locations:</span></span>

- <span data-ttu-id="27c06-140">브라질</span><span class="sxs-lookup"><span data-stu-id="27c06-140">Brazil</span></span> 
- <span data-ttu-id="27c06-141">독일</span><span class="sxs-lookup"><span data-stu-id="27c06-141">Germany</span></span> 
- <span data-ttu-id="27c06-142">노르웨이</span><span class="sxs-lookup"><span data-stu-id="27c06-142">Norway</span></span> 
- <span data-ttu-id="27c06-143">싱가포르</span><span class="sxs-lookup"><span data-stu-id="27c06-143">Singapore</span></span> 
- <span data-ttu-id="27c06-144">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="27c06-144">South Africa</span></span>
- <span data-ttu-id="27c06-145">스위스</span><span class="sxs-lookup"><span data-stu-id="27c06-145">Switzerland</span></span> 
- <span data-ttu-id="27c06-146">아랍에미리트</span><span class="sxs-lookup"><span data-stu-id="27c06-146">United Arab Emirates</span></span> 


## <a name="related-topics"></a><span data-ttu-id="27c06-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="27c06-147">Related topics</span></span>
- [<span data-ttu-id="27c06-148">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="27c06-148">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="27c06-149">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="27c06-149">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="27c06-150">액세스 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="27c06-150">Manage access and permissions</span></span>](m365d-permissions.md)
