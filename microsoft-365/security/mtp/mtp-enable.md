---
title: Microsoft 365 보안 센터에서 Microsoft Threat Protection 사용 설정
description: Microsoft Threat Protection를 사용하도록 설정하고 보안 인시던트 및 대응 통합을 시작하는 방법을 알아봅니다.
keywords: 시작하기, MTP, Microsoft Threat Protection, M365, 보안, 데이터 위치
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808453"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="da2bc-104">Microsoft Threat Protection 사용 설정</span><span class="sxs-lookup"><span data-stu-id="da2bc-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="da2bc-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="da2bc-105">**Applies to:**</span></span>
- <span data-ttu-id="da2bc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="da2bc-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="da2bc-107">Microsoft Threat Protection은 Microsoft Defender의 ATP(Advanced Threat Protection), Office 365 ATP, Microsoft Cloud App Security, Azure ATP에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="da2bc-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-your-eligibility"></a><span data-ttu-id="da2bc-109">자격 확인</span><span class="sxs-lookup"><span data-stu-id="da2bc-109">Check your eligibility</span></span>
<span data-ttu-id="da2bc-110">Microsoft 365 E5 또는 이와 동등한 라이선스가 있는 고객은 Microsoft Threat Protection을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="da2bc-111">자세한 내용은 [라이선스 요구 사항 읽기](prerequisites.md#licensing-requirements)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da2bc-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="da2bc-112">서비스 사용 시작</span><span class="sxs-lookup"><span data-stu-id="da2bc-112">Start using the service</span></span>
<span data-ttu-id="da2bc-113">Microsoft Threat Protection 서비스를 사용하도록 설정하면 다양한 통합된 서비스에서 데이터를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-113">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="da2bc-114">데이터는 중앙에서 처리되고 저장되어 새 정보를 식별하고 중앙 집중식 대응 워크플로를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-114">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="da2bc-115">서비스를 사용하도록 설정하기 전에 Microsoft 365 보안 센터([security.microsoft.com](https://security.microsoft.com))는 메뉴에 **인시던트**와 **알림 센터** 옵션을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-115">Before you turn the service on, Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="da2bc-116">![Microsoft Threat Protection 기능을 사용하지 않는 Microsoft 365 보안 센터 메뉴의 이미지](../images/mtp-off.png)
Microsoft Threat Protection이 꺼져 있는 Microsoft 365 보안 센터 \*\*</span><span class="sxs-lookup"><span data-stu-id="da2bc-116">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="da2bc-117">Microsoft Threat Protection 서비스 사용을 설정하려면 Microsoft 365 보안 센터에서 **설정** > **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-117">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="da2bc-118">이 작업을 수행하려면 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)에서 전역 관리자 또는 보안 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-118">You will need to be a global administrator or a security administrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to perform this task.</span></span>

<span data-ttu-id="da2bc-119">Microsoft Defender ATP가 조직에 프로비전된 경우 [Microsoft Defender ATP 데이터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 위해 선택한 것과 동일한 데이터 센터 위치에 데이터가 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="da2bc-120">Microsoft Defender ATP가 없는 경우 Microsoft Threat Protection를 위한 새로운 데이터 센터 위치를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="da2bc-121">서비스와 집계된 데이터가 공유되기 전에 동의를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="da2bc-122">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-122">Confirm that the service is on</span></span>
<span data-ttu-id="da2bc-123">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="da2bc-124">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="da2bc-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="da2bc-125">[자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="da2bc-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="da2bc-126">기존 **헌팅** 페이지에 대한 [고급 헌팅](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="da2bc-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="da2bc-127">![Microsoft Threat Protection 기능을 사용하는 Microsoft 365 보안 센터 메뉴의 이미지](../images/mtp-on.png)
*인시던트 관리와 Microsoft Threat Protection 기능이 있는 Microsoft 365 보안 센터*</span><span class="sxs-lookup"><span data-stu-id="da2bc-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="da2bc-128">Azure ATP 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="da2bc-128">Getting Azure ATP data</span></span>
<span data-ttu-id="da2bc-129">Azure ATP 데이터를 Microsoft Threat Protection 기능과 공유하려면 Microsoft Cloud App Security 및 Azure ATP 통합이 사용하도록 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="da2bc-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="da2bc-130">이 통합에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="da2bc-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="da2bc-131">Microsoft Threat Protection 해제</span><span class="sxs-lookup"><span data-stu-id="da2bc-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="da2bc-132">Microsoft Threat Protection 사용을 중지하려면 Microsoft 365 보안 센터에서 **설정** > **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="da2bc-133">**Microsoft Threat Protection 사용**을 선택 취소하고 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="da2bc-134">데이터가 영구적으로 삭제되고 해당 기능이 Microsoft 365 보안 센터에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-134">Data will be permanently deleted and corresponding features will be removed from Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="da2bc-135">지원 받기</span><span class="sxs-lookup"><span data-stu-id="da2bc-135">Get assistance</span></span>

<span data-ttu-id="da2bc-136">Microsoft 직원은 테넌트의 서비스 및 관련 리소스를 프로비저닝하거나 프로비전 해제하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2bc-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="da2bc-137">도움이 필요한 경우 [프리미어 지원에 문의](https://go.microsoft.com/fwlink/?LinkID=733758)하세요.</span><span class="sxs-lookup"><span data-stu-id="da2bc-137">For assistance, [contact premier support](https://go.microsoft.com/fwlink/?LinkID=733758).</span></span>

## <a name="related-topics"></a><span data-ttu-id="da2bc-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="da2bc-138">Related topics</span></span>

- [<span data-ttu-id="da2bc-139">Microsoft Threat Protection 개요</span><span class="sxs-lookup"><span data-stu-id="da2bc-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="da2bc-140">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="da2bc-140">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="da2bc-141">Microsoft Defender ATP 개요</span><span class="sxs-lookup"><span data-stu-id="da2bc-141">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="da2bc-142">Office 365 ATP 개요</span><span class="sxs-lookup"><span data-stu-id="da2bc-142">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="da2bc-143">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="da2bc-143">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="da2bc-144">Azure ATP 개요</span><span class="sxs-lookup"><span data-stu-id="da2bc-144">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="da2bc-145">Microsoft Defender ATP 데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="da2bc-145">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
