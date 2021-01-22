---
title: Microsoft 365 보안 센터에서 Microsoft 365 Defender 켜기
description: Microsoft 365 Defender를 사용하도록 설정하고 보안 인시던트 및 대응 통합을 시작하는 방법을 자세히 알아보고
keywords: 시작, MTP 사용, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930225"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="4c147-104">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="4c147-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4c147-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4c147-105">**Applies to:**</span></span>
- <span data-ttu-id="4c147-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c147-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4c147-107">[Microsoft 365 Defender는](microsoft-threat-protection.md) 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="4c147-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="4c147-109">필요한 권한이 있는 적격 고객이 Microsoft 365 보안 센터를 방문하면 Microsoft 365 Defender가 자동으로 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="4c147-110">이 문서를 읽고 다양한 선행 및 Microsoft 365 Defender가 프로비전된 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="4c147-111">라이선스 자격 및 필요한 사용 권한 확인</span><span class="sxs-lookup"><span data-stu-id="4c147-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="4c147-112">Microsoft 365 보안 제품에 대한 라이선스는 일반적으로 추가 라이선스 비용 없이 Microsoft 365 보안 센터에서 Microsoft 365 Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="4c147-113">Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 지원되는 모든 서비스에 대한 액세스를 제공하는 유효한 라이선스 조합을 다운로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="4c147-114">라이선스에 대한 자세한 내용은 라이선스 요구 [사항을 참조하세요.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="4c147-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="4c147-115">역할 확인</span><span class="sxs-lookup"><span data-stu-id="4c147-115">Check your role</span></span>

<span data-ttu-id="4c147-116">Microsoft 365 Defender를 켜기 위해 Azure Active Directory의 전역 관리자 또는 보안 관리자 되어야 합니다.  </span><span class="sxs-lookup"><span data-stu-id="4c147-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="4c147-117">Azure AD에서 역할 보기</span><span class="sxs-lookup"><span data-stu-id="4c147-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="4c147-118">지원되는 서비스</span><span class="sxs-lookup"><span data-stu-id="4c147-118">Supported services</span></span>

<span data-ttu-id="4c147-119">Microsoft 365 Defender는 이미 배포한 다양한 지원 서비스에서 데이터를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="4c147-120">새 인사이트를 식별하고 중앙 집중식 응답 워크플로를 사용할 수 있도록 데이터를 중앙에서 처리 및 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="4c147-121">이 작업에서는 기존 배포, 설정 또는 통합 서비스와 연결된 데이터에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="4c147-122">최상의 보호를 얻고 Microsoft 365 Defender를 최적화하기 위해 네트워크에서 지원되는 모든 서비스를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="4c147-123">자세한 내용은 [지원되는 서비스 배포에 대해 읽어보아야 합니다.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="4c147-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="4c147-124">서비스를 시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4c147-124">Before starting the service</span></span>

<span data-ttu-id="4c147-125">서비스를 켜기 전에 탐색 창에서 인시던트, 관리[센터 또는](https://security.microsoft.com)헌팅을 선택하면 Microsoft 365 보안 센터(security.microsoft.com)에 Microsoft 365 Defender 설정 페이지가 표시됩니다.  </span><span class="sxs-lookup"><span data-stu-id="4c147-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="4c147-126">Microsoft 365 Defender를 사용할 수 없는 경우 이러한 탐색 항목이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="4c147-127">![Microsoft 365 Defender가 Microsoft 365 보안 센터에서 Microsoft 365 Defender 설정에 설정되어 있지 않은 경우 ](../../media/mtp-enable/mtp-settings.png)
 *표시되는 Microsoft 365 Defender* 설정 페이지의 이미지</span><span class="sxs-lookup"><span data-stu-id="4c147-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="4c147-128">서비스 시작</span><span class="sxs-lookup"><span data-stu-id="4c147-128">Starting the service</span></span>

<span data-ttu-id="4c147-129">Microsoft 365 Defender를 켜기 위해 **Microsoft 365 Defender** 켜기만 선택하고 변경을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="4c147-130">탐색 창에서 설정(security.microsoft.com/settings)을 선택한 다음 **Microsoft 365 Defender를** 선택하여 이 옵션에 액세스할 수 있습니다.  [](https://security.microsoft.com/settings)</span><span class="sxs-lookup"><span data-stu-id="4c147-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="4c147-131">탐색 창에 설정이 표시되거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="4c147-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="4c147-132">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="4c147-132">Data center location</span></span>

<span data-ttu-id="4c147-133">Microsoft 365 Defender는 끝점용 Microsoft Defender에서 사용하는 동일한 위치에 [데이터를 저장하고 처리합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="4c147-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="4c147-134">끝점용 Microsoft Defender가 없는 경우 활성 Microsoft 365 보안 서비스의 위치에 따라 새 데이터 센터 위치가 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="4c147-135">선택한 데이터 센터 위치가 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="4c147-136">도움이 **필요하세요?** Microsoft 365 보안 센터에서 다른 데이터 센터 위치에서 Microsoft 365 Defender 프로비전에 대해 Microsoft 지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="4c147-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="4c147-137">끝점용 Microsoft Defender는 Azure Defender를 통해 켜져 있는 경우 유럽 연합(EU) 데이터 센터에서 자동으로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="4c147-138">Microsoft 365 Defender는 이 방식으로 끝점에 대한 Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="4c147-139">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-139">Confirm that the service is on</span></span>

<span data-ttu-id="4c147-140">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="4c147-141">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="4c147-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="4c147-142">[자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="4c147-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="4c147-143">[고급 헌팅](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="4c147-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="4c147-144">![Microsoft 365 Defender가 있는 Microsoft 365 보안 센터 탐색 창의 이미지는 인시던트 관리 및 ](../../media/mtp-enable/mtp-on.png)
 *기타 Microsoft 365 Defender* 기능이 있는 Microsoft 365 보안 센터 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="4c147-145">ID에 대한 Microsoft Defender 데이터 다운로드</span><span class="sxs-lookup"><span data-stu-id="4c147-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="4c147-146">Id용 Microsoft Defender 데이터를 Microsoft 365 Defender와 공유하기 위해 Microsoft Cloud App Security 및 ID용 Microsoft Defender 통합이 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="4c147-147">[이 통합에 대해 자세히 알아보습니다.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="4c147-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="4c147-148">지원 받기</span><span class="sxs-lookup"><span data-stu-id="4c147-148">Get assistance</span></span>

<span data-ttu-id="4c147-149">Microsoft 365 Defender 켜기와 관련한 가장 일반적으로 묻는 질문에 대한 답변을 얻습니다. [FAQ를 읽어 보아야 합니다.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="4c147-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="4c147-150">Microsoft 지원 직원은 테넌트에서 서비스 및 관련 리소스를 프로비전하거나 프로비전을 프로비전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="4c147-151">도움이 필요하면  Microsoft 365 보안 센터에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="4c147-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="4c147-152">지원에 문의할 때 Microsoft 365 Defender를 언급합니다.</span><span class="sxs-lookup"><span data-stu-id="4c147-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c147-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4c147-153">Related topics</span></span>

- [<span data-ttu-id="4c147-154">자주 묻는 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="4c147-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="4c147-155">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4c147-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="4c147-156">지원 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="4c147-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="4c147-157">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="4c147-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="4c147-158">끝점용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="4c147-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="4c147-159">Office 365용 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="4c147-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="4c147-160">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="4c147-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="4c147-161">Id용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="4c147-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="4c147-162">끝점 데이터 저장소용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4c147-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
