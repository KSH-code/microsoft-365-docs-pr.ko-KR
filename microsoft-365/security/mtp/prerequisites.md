---
title: Microsoft 위협 방지 필수 구성 요소
description: Microsoft 위협 방지의 라이선싱, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.
keywords: 요구 사항, 필수 구성 요소, 하드웨어, 소프트웨어, 브라우저, MTP, M365, 라이선스
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
ms.openlocfilehash: d3f24e8615f5b11b0853d7f1e36b49eb0cf2424f
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661924"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="d1e74-104">Microsoft 위협 방지 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d1e74-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="d1e74-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d1e74-105">**Applies to:**</span></span>
- <span data-ttu-id="d1e74-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="d1e74-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d1e74-107">Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d1e74-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d1e74-108">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1e74-108">Licensing requirements</span></span>
<span data-ttu-id="d1e74-109">Microsoft Threat Protection을 사용 하려면 다음 라이선스 또는 라이선스 조합 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e74-109">To use Microsoft Threat Protection, you need one of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="d1e74-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d1e74-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="d1e74-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="d1e74-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="d1e74-112">Office 365 E5, Enterprise Mobility + Security E5 및 Windows E5</span><span class="sxs-lookup"><span data-stu-id="d1e74-112">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

[<span data-ttu-id="d1e74-113">Microsoft 365 Enterprise 서비스 계획 보기</span><span class="sxs-lookup"><span data-stu-id="d1e74-113">View Microsoft 365 Enterprise service plans</span></span>](https://www.microsoft.com/en-us/licensing/product-licensing/microsoft-365-enterprise)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="d1e74-114">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="d1e74-114">Check your existing  licenses</span></span>
<span data-ttu-id="d1e74-115">Microsoft 365 관리 센터 ([admin.microsoft.com](https://admin.microsoft.com/))로 이동 하 여 기존 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e74-115">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="d1e74-116">관리 센터에서 **청구** > **라이선스**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e74-116">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="d1e74-117">라이선스 정보를 보려면 [AZURE AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) **청구 관리자** 또는 **전역 독자** 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e74-117">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="d1e74-118">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="d1e74-118">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="d1e74-119">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1e74-119">Browser requirements</span></span>
<span data-ttu-id="d1e74-120">Microsoft Edge, Internet Explorer 11 또는 HTML 5와 호환 되는 웹 브라우저를 사용 하 여 microsoft 365 보안 센터의 Microsoft 위협 보호에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e74-120">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1e74-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d1e74-121">Related topics</span></span>
- [<span data-ttu-id="d1e74-122">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="d1e74-122">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d1e74-123">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="d1e74-123">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)