---
title: Microsoft 365 보안 센터에서 Microsoft Threat Protection 사용 설정
description: Microsoft Threat Protection를 사용하도록 설정하고 보안 인시던트 및 대응 통합을 시작하는 방법을 알아봅니다.
keywords: 시작, MTP, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필수 사용 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235217"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="e903d-104">Microsoft Threat Protection 사용 설정</span><span class="sxs-lookup"><span data-stu-id="e903d-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="e903d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e903d-105">**Applies to:**</span></span>
- <span data-ttu-id="e903d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e903d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="e903d-107">Microsoft Threat Protection은 Microsoft Defender의 ATP(Advanced Threat Protection), Office 365 ATP, Microsoft Cloud App Security, Azure ATP에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="e903d-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="e903d-109">라이선스 자격 및 필요한 권한 확인</span><span class="sxs-lookup"><span data-stu-id="e903d-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="e903d-110">Microsoft 365 E5, Microsoft 365 E5 보안 또는이에 해당 하는 라이선스 조합이 있는 고객은 Microsoft Threat Protection을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="e903d-111">자세한 내용은 [라이선스 요구 사항 읽기](prerequisites.md#licensing-requirements)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e903d-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="e903d-112">Microsoft Threat Protection을 켜려면 **전역 관리자** 이거나 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 의 **보안 관리자** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="e903d-113">서비스 사용 시작</span><span class="sxs-lookup"><span data-stu-id="e903d-113">Start using the service</span></span>
<span data-ttu-id="e903d-114">Microsoft Threat Protection은 다양 한 통합 서비스에서 데이터를 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="e903d-115">새 정보를 식별 하 고 중앙 집중식 응답 워크플로를 수행할 수 있도록 중앙에서 데이터를 처리 및 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="e903d-116">서비스를 설정 하기 전에 Microsoft 365 보안 센터 ([security.microsoft.com](https://security.microsoft.com))에 탐색 창에 **인시던트** 및 **작업 센터** 옵션이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="e903d-117">![Microsoft threat protection 기능이](../../media/mtp-off.png)
없는 microsoft 365 보안 센터 탐색 창 이미지 microsoft*threat protection이 해제 된 microsoft 365 보안 센터*</span><span class="sxs-lookup"><span data-stu-id="e903d-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="e903d-118">Microsoft Threat Protection을 설정 하려면 탐색 창에서 **설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="e903d-119">**[설정 페이지](https://security.microsoft.com/settings)** 에서 **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="e903d-120">탐색 창에 **설정이** 표시 되지 않거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="e903d-121">데이터 센터 위치 선택</span><span class="sxs-lookup"><span data-stu-id="e903d-121">Select data center location</span></span>
<span data-ttu-id="e903d-122">Microsoft Defender ATP가 조직에 프로비전된 경우 [Microsoft Defender ATP 데이터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 위해 선택한 것과 동일한 데이터 센터 위치에 데이터가 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="e903d-123">Microsoft Defender ATP가 없는 경우 Microsoft Threat Protection를 위한 새로운 데이터 센터 위치를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="e903d-124">서비스 간에 데이터를 공유 하 고 집계 하기 전에 동의를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="e903d-125">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-125">Confirm that the service is on</span></span>
<span data-ttu-id="e903d-126">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="e903d-127">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="e903d-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="e903d-128">[자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="e903d-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="e903d-129">기존 **헌팅** 페이지에 대한 [고급 헌팅](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="e903d-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="e903d-130">![Microsoft threat protection 기능이](../../media/mtp-on.png)
있는 microsoft 365 보안 센터 탐색 창 이미지*문제 관리 및 기타 microsoft threat protection 기능을 가진 microsoft 365 보안 센터*</span><span class="sxs-lookup"><span data-stu-id="e903d-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="e903d-131">Azure ATP 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="e903d-131">Getting Azure ATP data</span></span>
<span data-ttu-id="e903d-132">Azure ATP 데이터를 Microsoft Threat Protection 기능과 공유하려면 Microsoft Cloud App Security 및 Azure ATP 통합이 사용하도록 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e903d-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="e903d-133">이 통합에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="e903d-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="e903d-134">Microsoft Threat Protection 해제</span><span class="sxs-lookup"><span data-stu-id="e903d-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="e903d-135">Microsoft Threat Protection 사용을 중지하려면 Microsoft 365 보안 센터에서 **설정** > **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="e903d-136">**Microsoft Threat Protection 사용**을 선택 취소하고 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="e903d-137">데이터가 영구적으로 삭제 되 고 해당 기능이 Microsoft 365 보안 센터에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="e903d-138">지원 받기</span><span class="sxs-lookup"><span data-stu-id="e903d-138">Get assistance</span></span>

<span data-ttu-id="e903d-139">Microsoft 지원 요원은 테 넌 트에 서비스 및 관련 리소스를 구축 하거나 프로 비전 해제 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="e903d-140">도움이 필요 하면 Microsoft 365 보안 센터에서 **도움말 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="e903d-141">지원 센터에 문의 하는 경우 Microsoft Threat Protection을 언급 합니다.</span><span class="sxs-lookup"><span data-stu-id="e903d-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e903d-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e903d-142">Related topics</span></span>

- [<span data-ttu-id="e903d-143">Microsoft Threat Protection 개요</span><span class="sxs-lookup"><span data-stu-id="e903d-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="e903d-144">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e903d-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="e903d-145">Microsoft Defender ATP 개요</span><span class="sxs-lookup"><span data-stu-id="e903d-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="e903d-146">Office 365 ATP 개요</span><span class="sxs-lookup"><span data-stu-id="e903d-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="e903d-147">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="e903d-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="e903d-148">Azure ATP 개요</span><span class="sxs-lookup"><span data-stu-id="e903d-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="e903d-149">Microsoft Defender ATP 데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="e903d-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
