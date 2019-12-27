---
title: Microsoft 위협 방지 필수 구성 요소
description: Microsoft 위협 방지의 라이선싱, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.
keywords: 요구 사항, 필수 구성 요소, 하드웨어, 소프트웨어, 브라우저, MTP, M365, 라이선스
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 2175ca328678e271056ae75d1bcbb7dc70a2198d
ms.sourcegitcommit: 5b0a2e11c86c00e6e6b534f8b0a19962d1bb2805
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/27/2019
ms.locfileid: "40881969"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="21499-104">Microsoft 위협 방지 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="21499-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="21499-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="21499-105">**Applies to:**</span></span>
- <span data-ttu-id="21499-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="21499-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="21499-107">라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정을 사용하여 Microsoft 365 보안을 실행하고 사용하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="21499-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="21499-108">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="21499-108">Licensing requirements</span></span>
<span data-ttu-id="21499-109">Microsoft 365 보안을 사용하려면 다음 라이선스 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21499-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="21499-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="21499-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="21499-111">Office 365 E5, Enterprise Mobility + Security E5 및 Windows E5</span><span class="sxs-lookup"><span data-stu-id="21499-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="21499-112">[Microsoft 365 Enterprise 페이지](https://www.microsoft.com/en-us/microsoft-365/enterprise)에서 이 라이선스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21499-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="21499-113">기존 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="21499-113">Check your existing  licenses</span></span>
<span data-ttu-id="21499-114">기존 라이선스를 보려면 [admin.microsoft.com](https://admin.microsoft.com/)에서 Microsoft 365 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="21499-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="21499-115">관리 센터에서 **청구** > **라이선스**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="21499-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="21499-116">라이선스 정보를 보려면 Azure AD에서청구 관리자 또는 전역 독자[역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21499-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="21499-117">액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="21499-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="21499-118">브라우저 요구 사항</span><span class="sxs-lookup"><span data-stu-id="21499-118">Browser requirements</span></span>
<span data-ttu-id="21499-119">Microsoft 365 보안 센터에 대한 액세스는 브라우저를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="21499-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="21499-120">Internet Explorer 및 Microsoft Edge가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="21499-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="21499-121">모든 HTML5 호환 브라우저도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="21499-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="21499-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="21499-122">Related topics</span></span>
- [<span data-ttu-id="21499-123">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="21499-123">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="21499-124">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="21499-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)