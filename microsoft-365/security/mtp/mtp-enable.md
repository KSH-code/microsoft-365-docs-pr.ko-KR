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
ms.openlocfilehash: 394fceffb96350b7702c5eef4a8138b3eb53f714
ms.sourcegitcommit: 997f6227f33c3683ade9672e881d09216df22ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44016077"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b84c3-104">Microsoft Threat Protection 사용 설정</span><span class="sxs-lookup"><span data-stu-id="b84c3-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="b84c3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b84c3-105">**Applies to:**</span></span>
- <span data-ttu-id="b84c3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b84c3-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b84c3-107">Microsoft Threat Protection은 Microsoft Defender의 ATP(Advanced Threat Protection), Office 365 ATP, Microsoft Cloud App Security, Azure ATP에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b84c3-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="b84c3-109">최적의 보호를 위해 Microsoft 위협 보호를 얻으려면 해당 하는 모든 지원 서비스를 네트워크에 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="b84c3-110">자세한 내용은 [지원 되는 서비스 배포에 대 한 내용을 참조](deploy-supported-services.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="b84c3-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b84c3-111">라이선스 자격 및 필요한 권한 확인</span><span class="sxs-lookup"><span data-stu-id="b84c3-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="b84c3-112">Microsoft 365 E5, E5 Security, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합이 지원 되는 서비스에 대 한 액세스를 제공 하 고, 추가 라이선스 비용 없이 Microsoft 365 보안 센터에서 Microsoft Threat Protection을 사용할 수 통해.</span><span class="sxs-lookup"><span data-stu-id="b84c3-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="b84c3-113">라이선스 정보에 대 한 자세한 내용은 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.</span><span class="sxs-lookup"><span data-stu-id="b84c3-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="b84c3-114">역할 확인</span><span class="sxs-lookup"><span data-stu-id="b84c3-114">Check your role</span></span>
<span data-ttu-id="b84c3-115">Microsoft Threat Protection을 켜려면 **전역 관리자** 이거나 Azure Active Directory의 **보안 관리자** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="b84c3-116">Azure AD에서 역할 보기</span><span class="sxs-lookup"><span data-stu-id="b84c3-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="b84c3-117">서비스 사용 시작</span><span class="sxs-lookup"><span data-stu-id="b84c3-117">Start using the service</span></span>

<span data-ttu-id="b84c3-118">Microsoft Threat Protection은 다양 한 통합 서비스에서 데이터를 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="b84c3-119">새 정보를 식별 하 고 중앙 집중식 응답 워크플로를 수행할 수 있도록 중앙에서 데이터를 처리 및 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="b84c3-120">통합 서비스와 연결 된 기존 배포, 설정 또는 데이터에 영향을 주지 않고이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-120">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="b84c3-121">서비스를 설정 하기 전에 Microsoft 365 보안 센터 ([security.microsoft.com](https://security.microsoft.com))는 탐색 창에서 **인시던트**, **작업 센터** **또는 검색** 을 선택할 때 microsoft 위협 보호 시작 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-121">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="b84c3-122">이러한 탐색 옵션은 Microsoft Threat Protection을 사용할 수 없는 경우에는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-122">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="b84c3-123">![Microsoft](../../media/mtp-welcome.png)
*보안 센터 365의* microsoft threat protection 시작 페이지에서 microsoft threat protection이 설정 되지 않은 경우 표시 되는 microsoft threat protection 환영 페이지 이미지</span><span class="sxs-lookup"><span data-stu-id="b84c3-123">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="b84c3-124">Microsoft Threat Protection을 설정 하려면 환영 페이지에서 프로세스를 완료 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-124">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="b84c3-125">탐색 창에서[security.microsoft.com/settings](https://security.microsoft.com/settings)( **설정** )에 액세스 하 고 **microsoft threat Protection**을 선택 하 여 microsoft threat protection을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-125">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="b84c3-126">탐색 창에 **설정이** 표시 되지 않거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-126">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>       

### <a name="select-data-center-location"></a><span data-ttu-id="b84c3-127">데이터 센터 위치 선택</span><span class="sxs-lookup"><span data-stu-id="b84c3-127">Select data center location</span></span>
<span data-ttu-id="b84c3-128">Microsoft Defender ATP가 조직에 프로비전된 경우 [Microsoft Defender ATP 데이터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 위해 선택한 것과 동일한 데이터 센터 위치에 데이터가 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-128">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b84c3-129">Microsoft Defender ATP가 없는 경우 Microsoft Threat Protection를 위한 새로운 데이터 센터 위치를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-129">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="b84c3-130">서비스 간에 데이터를 공유 하 고 집계 하기 전에 동의를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-130">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b84c3-131">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-131">Confirm that the service is on</span></span>
<span data-ttu-id="b84c3-132">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-132">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b84c3-133">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="b84c3-133">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b84c3-134">[자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="b84c3-134">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b84c3-135">[고급 구하기](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="b84c3-135">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="b84c3-136">![Microsoft threat protection 기능이](../../media/mtp-on.png)
있는 microsoft 365 보안 센터 탐색 창 이미지*문제 관리 및 기타 microsoft threat protection 기능을 가진 microsoft 365 보안 센터*</span><span class="sxs-lookup"><span data-stu-id="b84c3-136">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="b84c3-137">Azure ATP 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="b84c3-137">Getting Azure ATP data</span></span>
<span data-ttu-id="b84c3-138">Azure ATP 데이터를 Microsoft Threat Protection 기능과 공유하려면 Microsoft Cloud App Security 및 Azure ATP 통합이 사용하도록 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b84c3-138">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="b84c3-139">이 통합에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="b84c3-139">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="b84c3-140">Microsoft Threat Protection 해제</span><span class="sxs-lookup"><span data-stu-id="b84c3-140">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="b84c3-141">Microsoft Threat Protection 사용을 중지하려면 Microsoft 365 보안 센터에서 **설정** > **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-141">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b84c3-142">**Microsoft Threat Protection 사용**을 선택 취소하고 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-142">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="b84c3-143">해당 기능은 Microsoft 365 보안 센터에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-143">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b84c3-144">지원 받기</span><span class="sxs-lookup"><span data-stu-id="b84c3-144">Get assistance</span></span>

<span data-ttu-id="b84c3-145">Microsoft 지원 요원은 테 넌 트에 서비스 및 관련 리소스를 구축 하거나 프로 비전 해제 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-145">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b84c3-146">도움이 필요 하면 Microsoft 365 보안 센터에서 **도움말 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-146">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b84c3-147">지원 센터에 문의 하는 경우 Microsoft Threat Protection을 언급 합니다.</span><span class="sxs-lookup"><span data-stu-id="b84c3-147">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b84c3-148">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b84c3-148">Related topics</span></span>

- [<span data-ttu-id="b84c3-149">Microsoft Threat Protection 개요</span><span class="sxs-lookup"><span data-stu-id="b84c3-149">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b84c3-150">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b84c3-150">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b84c3-151">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="b84c3-151">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="b84c3-152">Microsoft Defender ATP 개요</span><span class="sxs-lookup"><span data-stu-id="b84c3-152">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b84c3-153">Office 365 ATP 개요</span><span class="sxs-lookup"><span data-stu-id="b84c3-153">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b84c3-154">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="b84c3-154">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b84c3-155">Azure ATP 개요</span><span class="sxs-lookup"><span data-stu-id="b84c3-155">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b84c3-156">Microsoft Defender ATP 데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="b84c3-156">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
