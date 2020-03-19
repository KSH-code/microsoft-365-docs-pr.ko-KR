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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857182"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="4b7b1-104">Microsoft 위협 방지 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4b7b1-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="4b7b1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4b7b1-105">**Applies to:**</span></span>
- <span data-ttu-id="4b7b1-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="4b7b1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4b7b1-107">Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4b7b1-108">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b7b1-108">Licensing requirements</span></span>
<span data-ttu-id="4b7b1-109">Microsoft Threat Protection을 사용 하려면 단일 라이선스 또는 라이선스 조합이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="4b7b1-110">단일 라이선스</span><span class="sxs-lookup"><span data-stu-id="4b7b1-110">Single license</span></span>
<span data-ttu-id="4b7b1-111">다음 라이선스 *중 하나* 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="4b7b1-112">Microsoft 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="4b7b1-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="4b7b1-113">Microsoft 365 E5 보안 또는 A5 보안</span><span class="sxs-lookup"><span data-stu-id="4b7b1-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="4b7b1-114">라이선스 조합</span><span class="sxs-lookup"><span data-stu-id="4b7b1-114">Combination of licenses</span></span>
<span data-ttu-id="4b7b1-115">Office 365, *EMS (Enterprise Mobility + Security)* 및 Windows에 대해 E5 또는 A5 구독에 대해 라이선스 조합을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="4b7b1-116">라이선스 조합에는 다음 라이선스가 *모두* 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="4b7b1-117">Office 365 E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="4b7b1-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="4b7b1-118">*EMS (Enterprise Mobility + Security)* E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="4b7b1-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="4b7b1-119">Windows E5 또는 A5</span><span class="sxs-lookup"><span data-stu-id="4b7b1-119">Windows E5 or A5</span></span>

<span data-ttu-id="4b7b1-120">자세한 내용은 [Microsoft 365 Enterprise 서비스 요금제를 참조](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)하세요.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="4b7b1-121">아직 라이선스가 없습니까?</span><span class="sxs-lookup"><span data-stu-id="4b7b1-121">Don't have license yet?</span></span> [<span data-ttu-id="4b7b1-122">Microsoft 365 구독 체험 또는 구입</span><span class="sxs-lookup"><span data-stu-id="4b7b1-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="4b7b1-123">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="4b7b1-123">Check your existing  licenses</span></span>
<span data-ttu-id="4b7b1-124">Microsoft 365 관리 센터 ([admin.microsoft.com](https://admin.microsoft.com/))로 이동 하 여 기존 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="4b7b1-125">관리 센터에서 **청구** > **라이선스**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="4b7b1-126">라이선스 정보를 보려면 [AZURE AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) **청구 관리자** 또는 **전역 독자** 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="4b7b1-127">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="4b7b1-128">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b7b1-128">Browser requirements</span></span>
<span data-ttu-id="4b7b1-129">Microsoft Edge, Internet Explorer 11 또는 HTML 5와 호환 되는 웹 브라우저를 사용 하 여 microsoft 365 보안 센터의 Microsoft 위협 보호에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="4b7b1-130">Microsoft Threat Protection for US 정부 커뮤니티 클라우드 및 미국 정부 커뮤니티 클라우드 (GCC 최고) 고객</span><span class="sxs-lookup"><span data-stu-id="4b7b1-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="4b7b1-131">현재 Microsoft Threat Protection은 GCC 및 GCC High 고객에 게 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7b1-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="4b7b1-132">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4b7b1-132">Related topics</span></span>
- [<span data-ttu-id="4b7b1-133">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="4b7b1-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="4b7b1-134">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="4b7b1-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
