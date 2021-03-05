---
title: Microsoft 365 Defender 선행 준비
description: Microsoft 365 Defender의 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 자세히 알아보시다.
keywords: 요구 사항, 선행 조건, 하드웨어, 소프트웨어, 브라우저, MTP, M365, 라이선스, E5, A5, EMS, 구매
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: afa5cd42545eddafb1d0ec1a6d88eb0903e07820
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454554"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="1d5cb-104">Microsoft 365 Defender 선행 준비</span><span class="sxs-lookup"><span data-stu-id="1d5cb-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1d5cb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1d5cb-105">**Applies to:**</span></span>
- <span data-ttu-id="1d5cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d5cb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1d5cb-107">[Microsoft 365 Defender](microsoft-threat-protection.md)프로비전 및 사용에 대한 라이선스 및 기타 요구 사항에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1d5cb-108">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d5cb-108">Licensing requirements</span></span>
<span data-ttu-id="1d5cb-109">이러한 라이선스를 사용하면 추가 비용 없이 Microsoft 365 보안 센터의 Microsoft 365 Defender 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="1d5cb-110">Microsoft 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1d5cb-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1d5cb-111">Microsoft 365 E5 보안 또는 A5 보안</span><span class="sxs-lookup"><span data-stu-id="1d5cb-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="1d5cb-112">Windows 10 Enterprise E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1d5cb-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="1d5cb-113">EMS(Enterprise Mobility + Security) E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1d5cb-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="1d5cb-114">Office 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="1d5cb-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1d5cb-115">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d5cb-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1d5cb-116">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d5cb-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="1d5cb-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1d5cb-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1d5cb-118">Office 365용 Defender(계획 2)</span><span class="sxs-lookup"><span data-stu-id="1d5cb-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="1d5cb-119">자세한 내용은 [Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)서비스 요금제 를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="1d5cb-120">아직 라이선스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="1d5cb-120">Don't have license yet?</span></span> [<span data-ttu-id="1d5cb-121">Microsoft 365 구독 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="1d5cb-121">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="1d5cb-122">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="1d5cb-122">Check your existing  licenses</span></span>
<span data-ttu-id="1d5cb-123">Microsoft 365 관리[센터(admin.microsoft.com](https://admin.microsoft.com/))로 이동하여 기존 라이선스를 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="1d5cb-124">관리 센터에서 **청구** > **라이선스** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="1d5cb-125">라이선스 정보를 볼 수  있게 하려면  [Azure AD에서](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 청구 관리자 또는 전역 리더 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="1d5cb-126">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="1d5cb-127">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1d5cb-127">Required permissions</span></span>
<span data-ttu-id="1d5cb-128">Microsoft 365 Defender를 켜기 위해 Azure Active Directory에서 전역 관리자 또는 보안 관리자 되어야 합니다.  </span><span class="sxs-lookup"><span data-stu-id="1d5cb-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="1d5cb-129">Microsoft 365 Defender를 사용하는 데 필요한 역할 목록과 데이터에 대한 액세스가 규제되는 방법에 대한 정보는 [Microsoft 365 Defender에](mtp-permissions.md)대한 액세스 관리에 대해 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="1d5cb-130">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d5cb-130">Browser requirements</span></span>
<span data-ttu-id="1d5cb-131">Microsoft Edge, Internet Explorer 11 또는 HTML 5 호환 웹 브라우저를 사용하여 Microsoft 365 보안 센터에서 Microsoft 365 Defender에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="1d5cb-132">미국 GCC, GCC High 및 기타 미국 정부 기관의 가용성</span><span class="sxs-lookup"><span data-stu-id="1d5cb-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="1d5cb-133">현재 Microsoft 365 Defender는 *다음을 사용할 수* 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="1d5cb-134">미국 GCC(정부 커뮤니티 클라우드)</span><span class="sxs-lookup"><span data-stu-id="1d5cb-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="1d5cb-135">미국 GCC(Government Community Cloud High)</span><span class="sxs-lookup"><span data-stu-id="1d5cb-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="1d5cb-136">미 국방부</span><span class="sxs-lookup"><span data-stu-id="1d5cb-136">US Department of Defense</span></span>
- <span data-ttu-id="1d5cb-137">상업용 라이선스가 있는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="1d5cb-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d5cb-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1d5cb-138">Related topics</span></span>
- [<span data-ttu-id="1d5cb-139">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="1d5cb-139">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1d5cb-140">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="1d5cb-140">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="1d5cb-141">액세스 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="1d5cb-141">Manage access and permissions</span></span>](mtp-permissions.md)
