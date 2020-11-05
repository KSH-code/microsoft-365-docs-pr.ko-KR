---
title: Microsoft 365 보안 센터에서 Microsoft 365 Defender 켜기
description: Microsoft 365 Defender를 사용 하도록 설정 하 고 보안 인시던트 및 응답의 통합을 시작 하는 방법을 알아봅니다.
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920505"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="9a577-104">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="9a577-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a577-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9a577-105">**Applies to:**</span></span>
- <span data-ttu-id="9a577-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a577-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9a577-107">[Microsoft 365 Defender](microsoft-threat-protection.md) 는 끝점, microsoft Defender for Office 365, Microsoft Cloud App Security 및 microsoft Defender for Identity에 주요 기능을 통합 하 여 문제 대응 프로세스를 함께 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="9a577-108">이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="9a577-109">Microsoft 365 Defender는 필요한 권한이 있는 적합 한 고객이 Microsoft 365 보안 센터에 방문 하면 자동으로 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="9a577-110">이 문서를 읽으면 다양 한 필수 구성 요소와 Microsoft 365 Defender가 구축 되는 방식을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="9a577-111">라이선스 자격 및 필요한 권한 확인</span><span class="sxs-lookup"><span data-stu-id="9a577-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="9a577-112">Microsoft 365 보안 제품에 대 한 라이선스는 일반적으로 추가 라이선스 비용 없이 microsoft 365 보안 센터에서 Microsoft 365 Defender를 사용 하는 통해입니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="9a577-113">Microsoft 365 E5, E5 Security, A5 또는 A5 보안 라이선스를 가져오거나 지원 되는 모든 서비스에 대 한 액세스를 제공 하는 유효한 라이선스 조합을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="9a577-114">라이선스 정보에 대 한 자세한 내용은 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.</span><span class="sxs-lookup"><span data-stu-id="9a577-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="9a577-115">역할 확인</span><span class="sxs-lookup"><span data-stu-id="9a577-115">Check your role</span></span>
<span data-ttu-id="9a577-116">Microsoft 365 Defender를 켜려면 **전역 관리자** 이거나 Azure Active Directory의 **보안 관리자** 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="9a577-117">Azure AD에서 역할 보기</span><span class="sxs-lookup"><span data-stu-id="9a577-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="9a577-118">지원 되는 서비스</span><span class="sxs-lookup"><span data-stu-id="9a577-118">Supported services</span></span>
<span data-ttu-id="9a577-119">Microsoft 365 Defender는 이미 배포 된 다양 한 지원 서비스에서 데이터를 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="9a577-120">새 정보를 식별 하 고 중앙 집중식 응답 워크플로를 수행할 수 있도록 중앙에서 데이터를 처리 및 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="9a577-121">통합 서비스와 연결 된 기존 배포, 설정 또는 데이터에 영향을 주지 않고이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="9a577-122">최적의 보호를 위해 Microsoft 365 Defender를 최적화 하려면 적용 가능한 모든 지원 서비스를 네트워크에 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="9a577-123">자세한 내용은 [지원 되는 서비스 배포에 대 한 내용을 참조](deploy-supported-services.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="9a577-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="9a577-124">서비스를 시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="9a577-124">Before starting the service</span></span>
<span data-ttu-id="9a577-125">서비스를 설정 하기 전에 Microsoft 365 보안 센터 ( [security.microsoft.com](https://security.microsoft.com))는 탐색 창에서 **인시던트** , **작업 센터** **또는 검색** 을 선택할 때 microsoft 365 Defender 설정 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-125">Before you turn on the service, the Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents** , **Action center** , or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="9a577-126">이러한 탐색 항목은 Microsoft 365 Defender를 사용할 수 없는 경우에는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="9a577-127">![Microsoft 365 ](../../media/mtp-enable/mtp-settings.png)
 *보안 센터 365의 Microsoft 365 defender settings* on에 설정 되어 있지 않은 경우 표시 되는 microsoft 365 defender settings 페이지 이미지</span><span class="sxs-lookup"><span data-stu-id="9a577-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="9a577-128">서비스 시작</span><span class="sxs-lookup"><span data-stu-id="9a577-128">Starting the service</span></span>
<span data-ttu-id="9a577-129">Microsoft 365 Defender를 켜려면 **microsoft 365 defender를 켠** 후 변경 사항을 적용 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="9a577-130">탐색 창에서 **설정** ( [security.microsoft.com/settings](https://security.microsoft.com/settings))을 선택 하 고 **microsoft 365 Defender** 를 선택 하 여이 옵션에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-130">You can also access this option by selecting **Settings** ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="9a577-131">탐색 창에 **설정이** 표시 되지 않거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="9a577-132">데이터 센터 위치</span><span class="sxs-lookup"><span data-stu-id="9a577-132">Data center location</span></span>
<span data-ttu-id="9a577-133">Microsoft 365 Defender는 [Microsoft Defender For Endpoint에서 사용 하는 것과 동일한 위치](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)에 데이터를 저장 하 고 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="9a577-134">Microsoft Defender for Endpoint를 사용 하지 않는 경우에는 활성 Microsoft 365 보안 서비스의 위치에 따라 새 데이터 센터 위치가 자동으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="9a577-135">선택한 데이터 센터 위치가 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="9a577-136">Microsoft 기술 지원 서비스에 문의 하 여 microsoft 365 Defender를 다른 데이터 센터 위치에 프로 비전 하는 방법에 대 한 자세한 내용은 마이크로소프트 365 보안 센터를 **참조** 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a577-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="9a577-137">끝점에 대 한 Microsoft Defender Azure Defender를 통해 켜면 EU (유럽 연합) 데이터 센터를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="9a577-138">Microsoft 365 Defender는이 방식으로 끝점에 대 한 Defender를 프로 비전 한 고객을 위해 동일한 EU 데이터 센터를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="9a577-139">서비스가 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-139">Confirm that the service is on</span></span>
<span data-ttu-id="9a577-140">서비스를 프로비전하면 다음이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="9a577-141">인시던트 관리</span><span class="sxs-lookup"><span data-stu-id="9a577-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="9a577-142">[자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터</span><span class="sxs-lookup"><span data-stu-id="9a577-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="9a577-143">[고급 구하기](advanced-hunting-overview.md) 기능</span><span class="sxs-lookup"><span data-stu-id="9a577-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="9a577-144">![Microsoft 365 Defender features이 포함 된 마이크로소프트 365 보안 센터 탐색 창 이미지 microsoft ](../../media/mtp-enable/mtp-on.png)
 *365 보안 센터 (문제 관리 및 기타 Microsoft 365 Defender 기능 포함* )</span><span class="sxs-lookup"><span data-stu-id="9a577-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="9a577-145">Id 데이터에 대 한 Microsoft Defender 가져오기</span><span class="sxs-lookup"><span data-stu-id="9a577-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="9a577-146">Microsoft 365 Defender를 사용 하 여 Id 데이터에 대 한 Microsoft Defender를 공유 하려면 Microsoft Cloud App Security 및 Microsoft Defender for Identity 통합용을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="9a577-147">이 통합에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="9a577-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a><span data-ttu-id="9a577-148">Microsoft 365 Defender 끄기</span><span class="sxs-lookup"><span data-stu-id="9a577-148">Turn off Microsoft 365 Defender</span></span>
<span data-ttu-id="9a577-149">Microsoft 365 Defender 사용을 중지 하려면 **Settings**  >  microsoft 365 보안 센터에서 **microsoft 365 Defender**  >  **옵트인/옵트아웃** 설정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-149">To stop using Microsoft 365 Defender, go to **Settings** > **Microsoft 365 Defender** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9a577-150">**Microsoft 365 Defender 사용** 을 선택 취소 하 고 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-150">Unselect **Turn on Microsoft 365 Defender** and apply the changes.</span></span>

<span data-ttu-id="9a577-151">해당 기능은 Microsoft 365 보안 센터에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="9a577-152">지원 받기</span><span class="sxs-lookup"><span data-stu-id="9a577-152">Get assistance</span></span>

<span data-ttu-id="9a577-153">Microsoft 365 Defender를 켜는 방법에 대 한 가장 일반적인 질문과 대답을 보려면 [FAQ를 참조](mtp-enable-faq.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="9a577-153">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="9a577-154">Microsoft 지원 요원은 테 넌 트에 서비스 및 관련 리소스를 구축 하거나 프로 비전 해제 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="9a577-155">도움이 필요 하면 Microsoft 365 보안 센터에서 **도움말 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9a577-156">지원 센터에 문의 하는 경우 Microsoft 365 Defender를 언급 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a577-156">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a577-157">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9a577-157">Related topics</span></span>

- [<span data-ttu-id="9a577-158">자주 묻는 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="9a577-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="9a577-159">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9a577-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="9a577-160">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="9a577-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="9a577-161">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="9a577-161">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="9a577-162">끝점에 대 한 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="9a577-162">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="9a577-163">Defender for Office 365 개요</span><span class="sxs-lookup"><span data-stu-id="9a577-163">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="9a577-164">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="9a577-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="9a577-165">Id에 대 한 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="9a577-165">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="9a577-166">Microsoft Defender for Endpoint data 저장소</span><span class="sxs-lookup"><span data-stu-id="9a577-166">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
