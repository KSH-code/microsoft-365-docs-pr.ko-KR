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
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209250"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="a2aad-104">Microsoft Threat Protection 사용 설정</span><span class="sxs-lookup"><span data-stu-id="a2aad-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="a2aad-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a2aad-105">**Applies to:**</span></span>
- <span data-ttu-id="a2aad-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a2aad-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a2aad-107">Microsoft Threat Protection은 Microsoft Defender의 ATP(Advanced Threat Protection), Office 365 ATP, Microsoft Cloud App Security, Azure ATP에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="a2aad-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="a2aad-109">최적의 보호를 위해 Microsoft 위협 보호를 얻으려면 해당 하는 모든 지원 서비스를 네트워크에 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="a2aad-110">자세한 내용은 [지원 되는 서비스 배포에 대 한 내용을 참조](deploy-supported-services.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="a2aad-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="a2aad-111">라이선스 자격 및 필요한 권한 확인</span><span class="sxs-lookup"><span data-stu-id="a2aad-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="a2aad-112">Microsoft 365 E5, E5 Security, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합이 지원 되는 서비스에 대 한 액세스를 제공 하 고, 추가 라이선스 비용 없이 Microsoft 365 보안 센터에서 Microsoft Threat Protection을 사용할 수 통해.</span><span class="sxs-lookup"><span data-stu-id="a2aad-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="a2aad-113">라이선스 정보에 대 한 자세한 내용은 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.</span><span class="sxs-lookup"><span data-stu-id="a2aad-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="a2aad-114">역할 확인</span><span class="sxs-lookup"><span data-stu-id="a2aad-114">Check your role</span></span>
<span data-ttu-id="a2aad-115">Microsoft Threat Protection을 켜려면 **전역 관리자** 이거나 Azure Active Directory의 **보안 관리자** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="a2aad-116">Azure AD에서 역할 보기</span><span class="sxs-lookup"><span data-stu-id="a2aad-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="a2aad-117">서비스 사용 시작</span><span class="sxs-lookup"><span data-stu-id="a2aad-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="a2aad-118">시작 시 12 일, 2020 Microsoft는 [라이선스 요구](prerequisites.md#licensing-requirements) 에 따라 최적화 된 새 환경을 점진적으로 배포 하 고 Microsoft Threat Protection을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-118">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="a2aad-119">이 기간 중 몇 주 동안 일부 고객은 포털 환경에 대 한 변경 내용을 확인 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="a2aad-120">새로운 환경에 대 한 정보는이 문서의 **새로운 환경** 으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="a2aad-121">Microsoft Threat Protection은 다양 한 통합 서비스에서 데이터를 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="a2aad-122">새 정보를 식별 하 고 중앙 집중식 응답 워크플로를 수행할 수 있도록 중앙에서 데이터를 처리 및 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="a2aad-123">통합 서비스와 연결 된 기존 배포, 설정 또는 데이터에 영향을 주지 않고이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="a2aad-124">서비스를 설정 하기 전에 Microsoft 365 보안 센터 ([security.microsoft.com](https://security.microsoft.com))는 탐색 창에서 **인시던트**, **작업 센터** **또는 검색** 을 선택할 때 microsoft 위협 보호 시작 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="a2aad-125">이러한 탐색 옵션은 Microsoft Threat Protection을 사용할 수 없는 경우에는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="a2aad-126">![Microsoft ](../../media/mtp-welcome.png)
 *보안 센터 365의* microsoft threat protection 시작 페이지에서 microsoft threat protection이 설정 되지 않은 경우 표시 되는 microsoft threat protection 환영 페이지 이미지</span><span class="sxs-lookup"><span data-stu-id="a2aad-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="a2aad-127">Microsoft Threat Protection을 설정 하려면 환영 페이지에서 프로세스를 완료 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="a2aad-128">탐색 창에서[security.microsoft.com/settings](https://security.microsoft.com/settings)( **설정** )에 액세스 하 고 **microsoft threat Protection**을 선택 하 여 microsoft threat protection을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="a2aad-129">탐색 창에 **설정이** 표시 되지 않거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="a2aad-130">데이터 센터 위치 선택</span><span class="sxs-lookup"><span data-stu-id="a2aad-130">Select data center location</span></span>
<span data-ttu-id="a2aad-131">Microsoft Defender ATP가 조직에 프로비전된 경우 [Microsoft Defender ATP 데이터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 위해 선택한 것과 동일한 데이터 센터 위치에 데이터가 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="a2aad-132">Microsoft Defender ATP가 없는 경우 Microsoft Threat Protection를 위한 새로운 데이터 센터 위치를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="a2aad-133">서비스 간에 데이터를 공유 하 고 집계 하기 전에 동의를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="a2aad-134">**새로운 환경:** 5 월 12 일, 2020, 고객이 이러한 환경에 대 한 변경 내용을 점차적으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-134">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="a2aad-135">새 환경을 사용 하는 사용자의 경우 서비스에서는 기존 Microsoft 365 보안 서비스를 기반으로 집계 된 데이터에 대해 최적의 데이터 센터 위치를 자동으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="a2aad-136">선택한 데이터 센터 위치가 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="a2aad-137">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-137">Confirm that the service is on</span></span>
<span data-ttu-id="a2aad-138">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="a2aad-139">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="a2aad-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="a2aad-140">[자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="a2aad-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="a2aad-141">[고급 구하기](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="a2aad-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="a2aad-142">![Microsoft Threat Protection 기능이 있는 Microsoft 365 보안 센터 탐색 창 이미지 ](../../media/mtp-on.png)
 *문제 관리 및 기타 Microsoft threat protection 기능을 가진 microsoft 365 보안 센터*</span><span class="sxs-lookup"><span data-stu-id="a2aad-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="a2aad-143">Azure ATP 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="a2aad-143">Getting Azure ATP data</span></span>
<span data-ttu-id="a2aad-144">Azure ATP 데이터를 Microsoft Threat Protection 기능과 공유하려면 Microsoft Cloud App Security 및 Azure ATP 통합이 사용하도록 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a2aad-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="a2aad-145">이 통합에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a2aad-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="a2aad-146">Microsoft Threat Protection 해제</span><span class="sxs-lookup"><span data-stu-id="a2aad-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="a2aad-147">Microsoft Threat Protection 사용을 중지하려면 Microsoft 365 보안 센터에서 **설정** > **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="a2aad-148">**Microsoft Threat Protection 사용**을 선택 취소하고 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="a2aad-149">해당 기능은 Microsoft 365 보안 센터에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="a2aad-150">지원 받기</span><span class="sxs-lookup"><span data-stu-id="a2aad-150">Get assistance</span></span>

<span data-ttu-id="a2aad-151">Microsoft 지원 요원은 테 넌 트에 서비스 및 관련 리소스를 구축 하거나 프로 비전 해제 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="a2aad-152">도움이 필요 하면 Microsoft 365 보안 센터에서 **도움말 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="a2aad-153">지원 센터에 문의 하는 경우 Microsoft Threat Protection을 언급 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2aad-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2aad-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a2aad-154">Related topics</span></span>

- [<span data-ttu-id="a2aad-155">Microsoft Threat Protection 개요</span><span class="sxs-lookup"><span data-stu-id="a2aad-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="a2aad-156">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a2aad-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="a2aad-157">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="a2aad-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="a2aad-158">Microsoft Defender ATP 개요</span><span class="sxs-lookup"><span data-stu-id="a2aad-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="a2aad-159">Office 365 ATP 개요</span><span class="sxs-lookup"><span data-stu-id="a2aad-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="a2aad-160">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="a2aad-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="a2aad-161">Azure ATP 개요</span><span class="sxs-lookup"><span data-stu-id="a2aad-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="a2aad-162">Microsoft Defender ATP 데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="a2aad-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)