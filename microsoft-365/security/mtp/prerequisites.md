---
title: Microsoft 365 Defender 선행 준비
description: Microsoft 365 Defender의 라이선싱, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 자세히 알아보기
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
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930093"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="0a949-104">Microsoft 365 Defender 선행 준비</span><span class="sxs-lookup"><span data-stu-id="0a949-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0a949-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0a949-105">**Applies to:**</span></span>
- <span data-ttu-id="0a949-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a949-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0a949-107">[Microsoft 365 Defender](microsoft-threat-protection.md)프로비전 및 사용에 대한 라이선싱 및 기타 요구 사항에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="0a949-108">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a949-108">Licensing requirements</span></span>
<span data-ttu-id="0a949-109">이러한 라이선스를 사용하면 추가 비용 없이 Microsoft 365 보안 센터의 Microsoft 365 Defender 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="0a949-110">Microsoft 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="0a949-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="0a949-111">Microsoft 365 E5 보안 또는 A5 보안</span><span class="sxs-lookup"><span data-stu-id="0a949-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="0a949-112">Windows 10 Enterprise E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="0a949-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="0a949-113">EMS(Enterprise Mobility + Security) E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="0a949-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="0a949-114">Office 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="0a949-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="0a949-115">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0a949-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0a949-116">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0a949-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="0a949-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0a949-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="0a949-118">Office 365용 Defender(계획 2)</span><span class="sxs-lookup"><span data-stu-id="0a949-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="0a949-119">Office 365의 평가판 라이선스는 현재 Microsoft 365 Defender에 대한 액세스를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="0a949-120">자세한 내용은 [Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)서비스 계획을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a949-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="0a949-121">아직 라이선스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="0a949-121">Don't have license yet?</span></span> [<span data-ttu-id="0a949-122">Microsoft 365 구독 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="0a949-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="0a949-123">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="0a949-123">Check your existing  licenses</span></span>
<span data-ttu-id="0a949-124">기존 라이선스를 확인하려면 Microsoft[](https://admin.microsoft.com/)365 관리 센터(admin.microsoft.com)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="0a949-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="0a949-125">관리 센터에서 **청구** > **라이선스** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="0a949-126">라이선스 정보를 볼 수  있게 하려면  [Azure AD에서](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 청구 관리자 또는 전역 리더 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="0a949-127">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0a949-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="0a949-128">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="0a949-128">Required permissions</span></span>
<span data-ttu-id="0a949-129">Microsoft 365 Defender를 켜기 위해 Azure Active Directory의 전역 관리자 또는 보안 관리자 되어야 합니다.  </span><span class="sxs-lookup"><span data-stu-id="0a949-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="0a949-130">Microsoft 365 Defender를 사용하는 데 필요한 역할 목록과 데이터에 대한 액세스가 규제되는 방법에 대한 정보는 [Microsoft 365 Defender에](mtp-permissions.md)대한 액세스 관리에 대해 읽어보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="0a949-131">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a949-131">Browser requirements</span></span>
<span data-ttu-id="0a949-132">Microsoft Edge, Internet Explorer 11 또는 HTML 5 호환 웹 브라우저를 사용하여 Microsoft 365 보안 센터에서 Microsoft 365 Defender에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="0a949-133">미국 GCC, GCC High 및 기타 미국 정부 기관의 가용성</span><span class="sxs-lookup"><span data-stu-id="0a949-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="0a949-134">현재 Microsoft 365 Defender는 *다음을 사용할 수* 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a949-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="0a949-135">미국 GCC(정부 커뮤니티 클라우드)</span><span class="sxs-lookup"><span data-stu-id="0a949-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="0a949-136">미국 GCC(Government Community Cloud High)</span><span class="sxs-lookup"><span data-stu-id="0a949-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="0a949-137">미 국방부</span><span class="sxs-lookup"><span data-stu-id="0a949-137">US Department of Defense</span></span>
- <span data-ttu-id="0a949-138">상업용 라이선스가 있는 모든 미국 정부 기관</span><span class="sxs-lookup"><span data-stu-id="0a949-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a949-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0a949-139">Related topics</span></span>
- [<span data-ttu-id="0a949-140">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="0a949-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="0a949-141">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="0a949-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="0a949-142">액세스 및 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="0a949-142">Manage access and permissions</span></span>](mtp-permissions.md)
