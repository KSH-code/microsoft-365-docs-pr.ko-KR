---
title: 보안 Microsoft 365 센터에서 Microsoft 365 켜기
description: Defender를 사용하도록 Microsoft 365 보안 인시던트 및 대응 통합을 시작하는 방법을 배워야 합니다.
keywords: 시작, Microsoft 365 Defender, Microsoft 365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지 사용
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3d7564b5d509190c8c8e799c541bb0ca583097f1
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636233"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="fc017-104">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="fc017-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fc017-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fc017-105">**Applies to:**</span></span>
- <span data-ttu-id="fc017-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc017-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fc017-107">[Microsoft 365 Defender는](microsoft-365-defender.md) 끝점용 Microsoft Defender, Office 365, Microsoft Cloud App Security 및 ID용 Microsoft Defender에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="fc017-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="fc017-109">Microsoft 365 필요한 권한이 있는 적격 고객이 보안 센터를 방문하면 defender가 Microsoft 365 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="fc017-110">이 문서를 읽고 다양한 선행 요구와 Defender가 프로비전되는 Microsoft 365 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="fc017-111">라이선스 자격 및 필요한 사용 권한 확인</span><span class="sxs-lookup"><span data-stu-id="fc017-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="fc017-112">일반적으로 Microsoft 365 보안 제품에 대한 라이선스는 추가 라이선스 비용 없이 Microsoft 365 보안 센터에서 Microsoft 365 Defender를 사용할 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="fc017-113">지원되는 모든 서비스에 대한 액세스를 Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합을 구입하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="fc017-114">라이선스에 대한 자세한 내용은 라이선스 [요구 사항을 참조하세요.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="fc017-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="fc017-115">역할 확인</span><span class="sxs-lookup"><span data-stu-id="fc017-115">Check your role</span></span>

<span data-ttu-id="fc017-116">Defender를  켜기 위해  전역 관리자 또는 Azure Active Directory 관리자 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="fc017-117">Azure AD에서 역할 보기</span><span class="sxs-lookup"><span data-stu-id="fc017-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="fc017-118">지원되는 서비스</span><span class="sxs-lookup"><span data-stu-id="fc017-118">Supported services</span></span>

<span data-ttu-id="fc017-119">Microsoft 365 Defender는 이미 배포한 다양한 지원 서비스에서 데이터를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="fc017-120">새 인사이트를 식별하고 중앙 집중식 응답 워크플로를 사용할 수 있도록 데이터를 중앙에서 처리 및 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="fc017-121">이 작업에서는 통합 서비스와 연결된 기존 배포, 설정 또는 데이터에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="fc017-122">Defender를 가장 잘 보호하고 최적화하기 Microsoft 365 지원되는 모든 서비스를 네트워크에 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="fc017-123">자세한 내용은 [지원되는 서비스 배포를 참조하십시오.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="fc017-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="fc017-124">서비스에 온보드</span><span class="sxs-lookup"><span data-stu-id="fc017-124">Onboard to the service</span></span>
<span data-ttu-id="fc017-125">Defender를 Microsoft 365 온보딩하는 것은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="fc017-126">탐색 메뉴에서 인시던트Microsoft 365 헌팅, 작업 센터 또는 위협 분석과 같은 모든 Defender 항목을 선택하여 온보딩 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-126">From the navigation menu, select any Microsoft 365 Defender items, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="fc017-127">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="fc017-127">Data center location</span></span>

<span data-ttu-id="fc017-128">Microsoft 365 Defender는 끝점용 Microsoft Defender에서 사용하는 동일한 위치에 데이터를 [저장하고 처리합니다.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="fc017-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="fc017-129">끝점용 Microsoft Defender가 없는 경우 활성 데이터 센터 보안 서비스의 위치에 따라 새 데이터 센터 Microsoft 365 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="fc017-130">선택한 데이터 센터 위치가 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="fc017-131">다른 **데이터** 센터 위치의 Microsoft 365 Defender 프로비전에 대해 Microsoft 지원에 문의하려면 Microsoft 365 필요하세요?를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="fc017-132">끝점용 Microsoft Defender는 Azure Defender를 통해 켜져 있는 경우 유럽 연합(EU) 데이터 센터에서 자동으로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="fc017-133">Microsoft 365 Defender는 이러한 방식으로 끝점에 대한 Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="fc017-134">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-134">Confirm that the service is on</span></span>

<span data-ttu-id="fc017-135">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="fc017-136">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="fc017-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="fc017-137">경고 큐</span><span class="sxs-lookup"><span data-stu-id="fc017-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="fc017-138">[자동화 조사 및 대응](m365d-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="fc017-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="fc017-139">[고급 헌팅](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="fc017-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="fc017-140">위협 분석</span><span class="sxs-lookup"><span data-stu-id="fc017-140">Threat analytics</span></span>

<span data-ttu-id="fc017-141">![인시던트 관리 Microsoft 365 기타 보안 센터와 함께 Microsoft 365 Defender 기능이 있는 Microsoft 365 보안 센터 탐색 창의 Microsoft 365 ](../../media/overview-incident.png)
 *이미지*</span><span class="sxs-lookup"><span data-stu-id="fc017-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="fc017-142">ID 데이터에 대한 Microsoft Defender 다운로드</span><span class="sxs-lookup"><span data-stu-id="fc017-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="fc017-143">사용자와 통합을 Microsoft Cloud App Security 한 번 이상 로그인해야 Microsoft Cloud App Security 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="fc017-144">지원 받기</span><span class="sxs-lookup"><span data-stu-id="fc017-144">Get assistance</span></span>

<span data-ttu-id="fc017-145">Defender를 켜는 데 대한 가장 일반적으로 Microsoft 365 [FAQ를 읽으면 합니다.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="fc017-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="fc017-146">Microsoft 지원 직원은 테넌트에서 서비스 및 관련 리소스를 프로비전하거나 프로비전을 프로비전하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="fc017-147">도움을 **요청하려면** 보안 센터에서 도움이 Microsoft 365 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="fc017-148">지원에 문의할 때 Defender에 Microsoft 365 언급합니다.</span><span class="sxs-lookup"><span data-stu-id="fc017-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc017-149">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fc017-149">Related topics</span></span>

- [<span data-ttu-id="fc017-150">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="fc017-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="fc017-151">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fc017-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="fc017-152">지원 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="fc017-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="fc017-153">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="fc017-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="fc017-154">끝점용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="fc017-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="fc017-155">Defender for Office 365 개요</span><span class="sxs-lookup"><span data-stu-id="fc017-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="fc017-156">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="fc017-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="fc017-157">Microsoft Defender for Identity 개요</span><span class="sxs-lookup"><span data-stu-id="fc017-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="fc017-158">끝점 데이터 저장소용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fc017-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
