---
title: Microsoft 위협 방지 필수 구성 요소
description: Microsoft 위협 방지의 라이선싱, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.
keywords: 요구 사항, 필수 구성 요소, 하드웨어, 소프트웨어, 브라우저, MTP, M365, license, E5, A5, EMS, purchase
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280537"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="1ce6f-104">Microsoft 위협 방지 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1ce6f-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="1ce6f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1ce6f-105">**Applies to:**</span></span>
- <span data-ttu-id="1ce6f-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="1ce6f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1ce6f-107">Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1ce6f-108">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ce6f-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="1ce6f-109">시작 시 12 일, 2020 Microsoft는 라이선스 요구에 따라 최적화 된 새 환경을 점진적으로 배포 하 고 [Microsoft Threat Protection을 설정](mtp-enable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="1ce6f-110">이 기간 중 몇 주 동안 일부 고객은 포털 환경에 대 한 변경 내용을 확인 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="1ce6f-111">새로운 환경에 대 한 정보는이 문서의 **새로운 환경** 으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="1ce6f-112">Microsoft Threat Protection을 사용 하려면 단일 라이선스 또는 라이선스 조합이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="1ce6f-113">이러한 라이선스 또는 라이선스 조합은 추가 비용 없이 Microsoft Threat Protection 기능에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="1ce6f-114">단일 라이선스</span><span class="sxs-lookup"><span data-stu-id="1ce6f-114">Single license</span></span>
<span data-ttu-id="1ce6f-115">다음 라이선스 *중 하나* 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="1ce6f-116">Microsoft 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1ce6f-117">Microsoft 365 E5 보안 또는 A5 보안</span><span class="sxs-lookup"><span data-stu-id="1ce6f-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="1ce6f-118">라이선스 조합</span><span class="sxs-lookup"><span data-stu-id="1ce6f-118">Combination of licenses</span></span>
<span data-ttu-id="1ce6f-119">Office 365, *EMS (Enterprise Mobility + Security)* 및 Windows에 대해 E5 또는 A5 구독에 대해 라이선스 조합을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="1ce6f-120">라이선스 조합에는 다음 라이선스가 *모두* 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="1ce6f-121">Office 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1ce6f-122">*EMS (Enterprise Mobility + Security)* E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="1ce6f-123">Windows 10 Enterprise E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="1ce6f-124">자세한 내용은 [Microsoft 365 Enterprise 서비스 요금제를 참조](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)하세요.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="1ce6f-125">아직 라이선스가 없습니까?</span><span class="sxs-lookup"><span data-stu-id="1ce6f-125">Don't have license yet?</span></span> [<span data-ttu-id="1ce6f-126">Microsoft 365 구독 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="1ce6f-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="1ce6f-127">**새로운 환경:** 5 월 12 일, 2020, 고객이 이러한 환경에 대 한 변경 내용을 점차적으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="1ce6f-128">이러한 새로운 환경을 사용 하는 경우 Microsoft Threat Protection을 설정 하는 옵션은 다음 라이선스를 가진 *모든* 고객에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="1ce6f-129">Microsoft 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1ce6f-130">Microsoft 365 E5 보안 또는 A5 보안</span><span class="sxs-lookup"><span data-stu-id="1ce6f-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="1ce6f-131">Windows 10 Enterprise E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="1ce6f-132">EMS (Enterprise Mobility + Security) E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="1ce6f-133">Office 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1ce6f-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1ce6f-134">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1ce6f-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="1ce6f-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1ce6f-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="1ce6f-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1ce6f-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="1ce6f-137">Office 365 Advanced Threat Protection (계획 2)</span><span class="sxs-lookup"><span data-stu-id="1ce6f-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="1ce6f-138">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="1ce6f-138">Check your existing  licenses</span></span>
<span data-ttu-id="1ce6f-139">Microsoft 365 관리 센터 ([admin.microsoft.com](https://admin.microsoft.com/))로 이동 하 여 기존 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="1ce6f-140">관리 센터에서 **청구** > **라이선스**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="1ce6f-141">라이선스 정보를 보려면 [AZURE AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) **청구 관리자** 또는 **전역 독자** 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="1ce6f-142">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="1ce6f-143">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ce6f-143">Browser requirements</span></span>
<span data-ttu-id="1ce6f-144">Microsoft Edge, Internet Explorer 11 또는 HTML 5와 호환 되는 웹 브라우저를 사용 하 여 microsoft 365 보안 센터의 Microsoft 위협 보호에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce6f-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="1ce6f-145">미국 GCC, GCC 최고 및 기타 미국 정부 기관에 대 한 가용성</span><span class="sxs-lookup"><span data-stu-id="1ce6f-145">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="1ce6f-146">현재 다음과 같은 경우에는 Microsoft Threat Protection을 사용할 수 *없습니다* .</span><span class="sxs-lookup"><span data-stu-id="1ce6f-146">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="1ce6f-147">미국 정부 커뮤니티 클라우드 (GCC)</span><span class="sxs-lookup"><span data-stu-id="1ce6f-147">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="1ce6f-148">미국 정부 커뮤니티 클라우드 높음 (GCC 높음)</span><span class="sxs-lookup"><span data-stu-id="1ce6f-148">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="1ce6f-149">미국 방어 부서</span><span class="sxs-lookup"><span data-stu-id="1ce6f-149">US Department of Defense</span></span>
- <span data-ttu-id="1ce6f-150">상업적 라이선스를 포함 하는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="1ce6f-150">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ce6f-151">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1ce6f-151">Related topics</span></span>
- [<span data-ttu-id="1ce6f-152">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="1ce6f-152">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1ce6f-153">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="1ce6f-153">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
