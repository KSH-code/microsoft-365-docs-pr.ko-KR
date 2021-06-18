---
title: 보안 Microsoft 365 Defender 센터에서 Microsoft 365 켜기
description: 보안 인시던트와 Microsoft 365 Defender 통합을 시작하는 방법을 배워야 합니다.
keywords: 시작, Microsoft 365 Defender, Microsoft 365 Defender, M365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지
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
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007612"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="822f0-104">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="822f0-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="822f0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="822f0-105">**Applies to:**</span></span>
- <span data-ttu-id="822f0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="822f0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="822f0-107">[Microsoft 365 Defender](microsoft-365-defender.md) Microsoft Defender for Endpoint, microsoft Defender for Office 365, Microsoft Cloud App Security 및 Id용 Microsoft Defender에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="822f0-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="822f0-109">Microsoft 365 Defender 권한이 있는 적격 고객이 보안 센터를 방문하면 Microsoft 365 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="822f0-110">이 문서를 읽고 다양한 선행 준비와 프로비전 Microsoft 365 Defender 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="822f0-111">라이선스 자격 및 필요한 사용 권한 확인</span><span class="sxs-lookup"><span data-stu-id="822f0-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="822f0-112">일반적으로 Microsoft 365 보안 제품에 대한 라이선스를 사용하면 추가 라이선스 비용 없이 Microsoft 365 Defender Microsoft 365 보안 센터에서 라이선스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="822f0-113">지원되는 모든 서비스에 대한 액세스를 Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합을 구입하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="822f0-114">라이선스에 대한 자세한 내용은 라이선스 [요구 사항을 참조하세요.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="822f0-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="822f0-115">역할 확인</span><span class="sxs-lookup"><span data-stu-id="822f0-115">Check your role</span></span>

<span data-ttu-id="822f0-116">전역 관리자  또는 보안  관리자 Azure Active Directory 설정해야 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="822f0-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="822f0-117">Azure AD에서 역할 보기</span><span class="sxs-lookup"><span data-stu-id="822f0-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="822f0-118">지원되는 서비스</span><span class="sxs-lookup"><span data-stu-id="822f0-118">Supported services</span></span>

<span data-ttu-id="822f0-119">Microsoft 365 Defender 이미 배포한 다양한 지원 서비스의 데이터를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="822f0-120">새 인사이트를 식별하고 중앙 집중식 응답 워크플로를 사용할 수 있도록 데이터를 중앙에서 처리 및 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="822f0-121">이 작업에서는 통합 서비스와 연결된 기존 배포, 설정 또는 데이터에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="822f0-122">최상의 보호를 적용하고 최적화하기 Microsoft 365 Defender 지원되는 모든 서비스를 네트워크에 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="822f0-123">자세한 내용은 [지원되는 서비스 배포를 참조하십시오.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="822f0-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="822f0-124">서비스에 온보드</span><span class="sxs-lookup"><span data-stu-id="822f0-124">Onboard to the service</span></span>
<span data-ttu-id="822f0-125">온보드를 Microsoft 365 Defender 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="822f0-126">탐색 메뉴에서 인시던트 및 경고, &, 알림 센터 또는  **위협** 분석과 **같은** 항목을 선택하여 온보더링 프로세스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-126">From the navigation menu, select any item, such as **Incidents & alerts**, **Hunting**, **Action center**, or **Threat analytics** to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="822f0-127">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="822f0-127">Data center location</span></span>

<span data-ttu-id="822f0-128">Microsoft 365 Defender Microsoft [Defender for Endpoint에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)사용하는 동일한 위치에 데이터를 저장하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="822f0-129">끝점용 Microsoft Defender가 없는 경우 활성 데이터 센터 보안 서비스의 위치에 따라 새 데이터 센터 Microsoft 365 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="822f0-130">선택한 데이터 센터 위치가 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="822f0-131">다른 **데이터** 센터 위치의 프로비저닝 Microsoft 365 Microsoft 지원에 문의하려면 Microsoft 365 Defender 센터에서 도움이 필요하세요?를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="822f0-132">과거에는 Azure Defender를 통해 켜져 있는 경우 끝점용 Microsoft Defender가 EU(유럽 연합) 데이터 센터에서 자동으로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="822f0-133">Microsoft 365 Defender 이 방식으로 끝점에 대해 Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="822f0-134">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-134">Confirm that the service is on</span></span>

<span data-ttu-id="822f0-135">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="822f0-136">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="822f0-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="822f0-137">경고 큐</span><span class="sxs-lookup"><span data-stu-id="822f0-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="822f0-138">[자동화 조사 및 대응](m365d-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="822f0-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="822f0-139">[고급 헌팅](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="822f0-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="822f0-140">위협 분석</span><span class="sxs-lookup"><span data-stu-id="822f0-140">Threat analytics</span></span>

<span data-ttu-id="822f0-141">![인시던트 관리 Microsoft 365 기타 보안 센터와 함께 Microsoft 365 Defender 기능을 Microsoft 365 보안 센터의 Microsoft 365 Defender ](../../media/overview-incident.png)
 *창 이미지*</span><span class="sxs-lookup"><span data-stu-id="822f0-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="822f0-142">ID 데이터에 대한 Microsoft Defender 다운로드</span><span class="sxs-lookup"><span data-stu-id="822f0-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="822f0-143">사용자와 통합을 Microsoft Cloud App Security 한 번 이상 로그인해야 Microsoft Cloud App Security 합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="822f0-144">지원 받기</span><span class="sxs-lookup"><span data-stu-id="822f0-144">Get assistance</span></span>

<span data-ttu-id="822f0-145">이 기능을 켜는 데 대한 가장 일반적으로 묻는 질문에 대한 답변을 Microsoft 365 Defender [FAQ를 읽어 보아야 합니다.](m365d-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="822f0-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="822f0-146">Microsoft 지원 직원은 테넌트에서 서비스 및 관련 리소스를 프로비전하거나 프로비전을 프로비전하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="822f0-147">도움을 **요청하려면** 보안 센터에서 도움이 Microsoft 365 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="822f0-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="822f0-148">지원에 문의할 때 지원에 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="822f0-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="822f0-149">관련 항목</span><span class="sxs-lookup"><span data-stu-id="822f0-149">Related topics</span></span>

- [<span data-ttu-id="822f0-150">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="822f0-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="822f0-151">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="822f0-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="822f0-152">지원 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="822f0-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="822f0-153">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="822f0-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="822f0-154">끝점용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="822f0-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="822f0-155">Defender for Office 365 개요</span><span class="sxs-lookup"><span data-stu-id="822f0-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="822f0-156">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="822f0-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="822f0-157">Microsoft Defender for Identity 개요</span><span class="sxs-lookup"><span data-stu-id="822f0-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="822f0-158">끝점 데이터 저장소용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="822f0-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
