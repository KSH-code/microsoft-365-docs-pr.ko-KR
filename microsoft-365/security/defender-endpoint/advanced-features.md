---
title: 끝점용 Microsoft Defender의 고급 기능 구성
description: 끝점용 Microsoft Defender에서 파일 차단과 같은 고급 기능을 켜야 합니다.
keywords: 고급 기능, 설정, 파일 차단, 자동화된 조사, 자동 해결, skype, ID에 대한 Microsoft Defender, office 365, Azure Information Protection, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ed6f6b42570a908a1f4a83d46ef5b2de0c558692
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199744"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="89805-104">끝점용 Defender의 고급 기능 구성</span><span class="sxs-lookup"><span data-stu-id="89805-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="89805-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="89805-105">**Applies to:**</span></span>
- [<span data-ttu-id="89805-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="89805-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89805-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89805-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="89805-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="89805-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89805-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="89805-110">사용하는 Microsoft 보안 제품에 따라 일부 고급 기능을 사용하여 Endpoint용 Defender를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="89805-111">고급 기능 사용</span><span class="sxs-lookup"><span data-stu-id="89805-111">Enable advanced features</span></span>

1. <span data-ttu-id="89805-112">탐색 창에서 기본 **설정** 고급 기능  >  **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="89805-113">구성할 고급 기능을 선택하고 설정 및 해제  간에 설정을 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="89805-114">기본 **설정 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-114">Click **Save preferences**.</span></span>

<span data-ttu-id="89805-115">다음 고급 기능을 사용하여 잠재적으로 악의적인 파일로부터 더 잘 보호하고 보안 조사 중에 더 나은 통찰력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="89805-116">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="89805-116">Automated investigation</span></span>

<span data-ttu-id="89805-117">이 기능을 켜서 서비스의 자동화된 조사 및 수정 기능을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="89805-118">자세한 내용은 자동화된 [조사를 참조하세요.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="89805-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="89805-119">라이브 응답</span><span class="sxs-lookup"><span data-stu-id="89805-119">Live response</span></span>

<span data-ttu-id="89805-120">적절한 권한이 있는 사용자가 디바이스에서 라이브 응답 세션을 시작할 수 있도록 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="89805-121">역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="89805-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="89805-122">서버에 대한 실시간 응답</span><span class="sxs-lookup"><span data-stu-id="89805-122">Live response for servers</span></span>
<span data-ttu-id="89805-123">적절한 사용 권한이 있는 사용자가 서버에서 라이브 응답 세션을 시작할 수 있도록 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="89805-124">역할 할당에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="89805-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="89805-125">라이브 응답 부호 없는 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="89805-125">Live response unsigned script execution</span></span>

<span data-ttu-id="89805-126">이 기능을 사용하도록 설정하면 라이브 응답 세션에서 부호 없는 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="89805-127">수정된 경고 자동 해결</span><span class="sxs-lookup"><span data-stu-id="89805-127">Autoresolve remediated alerts</span></span>

<span data-ttu-id="89805-128">Windows 10 버전 1809 이상에서 만든 테넌트의 경우 자동화된 분석 결과 상태가 "위협 없음" 또는 "수정"인 경고를 해결하도록 기본적으로 자동화된 조사 및 수정 기능이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-128">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="89805-129">경고를 자동으로 해결하지 못하게 하려는 경우 기능을 수동으로 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-129">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="89805-130">해당 버전 이전에 만든 테넌트의 경우 고급 기능 페이지에서 이 기능을 수동으로 [켜야](https://securitycenter.windows.com/preferences2/integration) 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-130">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="89805-131">자동 해결 작업의 결과는 장치에서 발견된 활성 경고를 기반으로 하는 장치 위험 수준 계산에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-131">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="89805-132">보안 운영 분석가가 경고의 상태를 수동으로 "진행 중" 또는 "해결"으로 설정하면 자동 확인 기능이 덮어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-132">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="89805-133">파일 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="89805-133">Allow or block file</span></span>

<span data-ttu-id="89805-134">차단은 조직에서 다음 요구 사항을 충족하는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-134">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="89805-135">Microsoft Defender 바이러스 백신을 활성 맬웨어 방지 솔루션으로 사용</span><span class="sxs-lookup"><span data-stu-id="89805-135">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="89805-136">클라우드 기반 보호 기능이 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-136">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="89805-137">이 기능을 사용하면 네트워크에서 잠재적으로 악의적인 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-137">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="89805-138">파일을 차단하면 조직의 장치에서 파일을 읽거나 쓰거나 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-138">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="89805-139">파일 허용 **또는 차단을** 설정하려면</span><span class="sxs-lookup"><span data-stu-id="89805-139">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="89805-140">탐색 창에서 설정 고급 **기능** 파일 허용 또는  >    >  **차단을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-140">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="89805-141">설정과 끄기 **간에 설정을** **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-141">Toggle the setting between **On** and **Off**.</span></span>

    ![파일 차단 기능에 대한 고급 설정 이미지](images/atp-preferences-setup.png)

1. <span data-ttu-id="89805-143">페이지 **아래쪽의** 기본 설정 저장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-143">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="89805-144">이 기능을 켜면 파일 [](respond-file-alerts.md#allow-or-block-file) 프로필 페이지의  표시기 추가 탭을 통해 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-144">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="89805-145">사용자 지정 네트워크 표시기</span><span class="sxs-lookup"><span data-stu-id="89805-145">Custom network indicators</span></span>

<span data-ttu-id="89805-146">이 기능을 켜면 IP 주소, 도메인 또는 URL에 대한 표시기를 만들어 사용자 지정 표시기 목록에 따라 허용 또는 차단할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-146">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="89805-147">이 기능을 사용하려면 장치에서 Windows 10 버전 1709 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-147">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="89805-148">또한 맬웨어 방지 플랫폼의 차단 모드 및 버전 4.18.1906.3 이상에서도 네트워크 보호 기능을 사용할 수 [있습니다. KB 4052623을](https://go.microsoft.com/fwlink/?linkid=2099834)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89805-148">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="89805-149">자세한 내용은 [지표 관리를 참조하세요.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="89805-149">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="89805-150">네트워크 보호는 끝점 데이터용 Defender에 대해 선택한 위치 밖에 있을 수 있는 위치에서 요청을 처리하는 신뢰도 서비스를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-150">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="show-user-details"></a><span data-ttu-id="89805-151">사용자 세부 정보 표시</span><span class="sxs-lookup"><span data-stu-id="89805-151">Show user details</span></span>

<span data-ttu-id="89805-152">Azure Active Directory에 저장된 사용자 세부 정보를 볼 수 있도록 이 기능을 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="89805-152">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="89805-153">세부 정보에는 사용자 계정 엔터티를 조사할 때 사용자의 사진, 이름, 직위 및 부서 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-153">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="89805-154">다음 보기에서 사용자 계정 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-154">You can find user account information in the following views:</span></span>

- <span data-ttu-id="89805-155">보안 운영 대시보드</span><span class="sxs-lookup"><span data-stu-id="89805-155">Security operations dashboard</span></span>
- <span data-ttu-id="89805-156">경고 큐</span><span class="sxs-lookup"><span data-stu-id="89805-156">Alert queue</span></span>
- <span data-ttu-id="89805-157">장치 세부 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="89805-157">Device details page</span></span>

<span data-ttu-id="89805-158">자세한 내용은 사용자 계정 [조사를 참조하세요.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="89805-158">For more information, see [Investigate a user account](investigate-user.md).</span></span>

## <a name="skype-for-business-integration"></a><span data-ttu-id="89805-159">비즈니스용 Skype 통합</span><span class="sxs-lookup"><span data-stu-id="89805-159">Skype for Business integration</span></span>

<span data-ttu-id="89805-160">비즈니스용 Skype 통합을 사용하도록 설정하면 비즈니스용 Skype, 전자 메일 또는 전화를 사용하여 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-160">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="89805-161">이는 사용자와 통신하고 위험을 완화해야 하는 경우 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-161">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="89805-162">장치가 네트워크에서 격리되는 경우 Outlook 및 Skype 통신을 사용하도록 선택할 수 있는 팝업이 있습니다. 그러면 네트워크에서 연결이 끊어진 동안 사용자에게 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-162">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="89805-163">이 설정은 장치가 고리 모드에 있는 경우 Skype 및 Outlook 통신에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-163">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="azure-advanced-threat-protection-integration"></a><span data-ttu-id="89805-164">Azure Advanced Threat Protection 통합</span><span class="sxs-lookup"><span data-stu-id="89805-164">Azure Advanced Threat Protection integration</span></span>

<span data-ttu-id="89805-165">Azure Advanced Threat Protection과의 통합을 통해 다른 Microsoft ID 보안 제품으로 직접 피벗할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-165">The integration with Azure Advanced Threat Protection allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="89805-166">Azure Advanced Threat Protection은 손상된 계정 및 관련 리소스에 대한 추가 정보를 사용하여 조사를 강화합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-166">Azure Advanced Threat Protection augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="89805-167">이 기능을 사용하도록 설정하면 식별 시점에서 네트워크를 통해 피벗하여 장치 기반 조사 기능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-167">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="89805-168">이 기능을 사용하려면 적절한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-168">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="89805-169">Office 365 위협 인텔리전스 연결</span><span class="sxs-lookup"><span data-stu-id="89805-169">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="89805-170">이 기능은 활성 Office 365 E5 또는 위협 인텔리전스 추가 기능이 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-170">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="89805-171">자세한 내용은 Office 365 Enterprise E5 제품 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89805-171">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="89805-172">이 기능을 켜면 Office 365 Advanced Threat Protection의 데이터를 Microsoft Defender 보안 센터에 통합하여 Office 365 사서함 및 Windows 장치에서 포괄적인 보안 조사를 실시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-172">When you turn this feature on, you'll be able to incorporate data from Office 365 Advanced Threat Protection into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="89805-173">이 기능을 사용하려면 적절한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-173">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="89805-174">Office 365 위협 인텔리전스에서 상황에 맞는 장치 통합을 받으하려면 보안 및 준수 대시보드에서 끝점에 대한 Defender 설정을 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-174">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="89805-175">자세한 내용은 위협 조사 및 [응답을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)</span><span class="sxs-lookup"><span data-stu-id="89805-175">For more information, see [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts"></a><span data-ttu-id="89805-176">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="89805-176">Microsoft Threat Experts</span></span>

<span data-ttu-id="89805-177">Microsoft Threat Expert 구성 요소 2개 중 대상 공격 알림은 일반 공급 중입니다.</span><span class="sxs-lookup"><span data-stu-id="89805-177">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="89805-178">전문가 요구 시 기능은 여전히 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="89805-178">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="89805-179">미리 보기를 신청하고 응용 프로그램이 승인된 경우 전문가 요구 시 기능만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-179">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="89805-180">Endpoint 포털의 경고 대시보드에 대한 Defender를 통해 Microsoft 위협 전문가로부터 대상 공격 알림을 받을 수 있으며, 구성하는 경우 전자 메일을 통해 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-180">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="89805-181">Endpoint용 Defender의 Microsoft Threat Experts 기능은 Enterprise Mobility + Security에 대한 E5 [라이선스로 사용할 수 있습니다.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)</span><span class="sxs-lookup"><span data-stu-id="89805-181">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="89805-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89805-182">Microsoft Cloud App Security</span></span>

<span data-ttu-id="89805-183">이 설정을 사용하도록 설정하면 끝점용 Defender 신호가 Microsoft Cloud App Security로 전달되어 클라우드 응용 프로그램 사용 현황에 대한 더 깊은 가시성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-183">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="89805-184">전달된 데이터는 Cloud App Security 데이터와 동일한 위치에 저장 및 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-184">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="89805-185">이 기능은 Windows 10 버전 1709(OS 빌드 16299.1085 및 [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10을 실행하는 장치에서 [Enterprise Mobility + Security에](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) 대한 E5 라이선스로 사용할 수 있습니다. 버전 1803(OS 빌드 17134.704( [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, 버전 1809(OS 빌드 17763.379 및 [KB4489899)](https://support.microsoft.com/help/4489899)이상 Windows 10 버전.</span><span class="sxs-lookup"><span data-stu-id="89805-185">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="azure-information-protection"></a><span data-ttu-id="89805-186">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="89805-186">Azure Information Protection</span></span>

<span data-ttu-id="89805-187">이 설정을 켜면 신호를 Azure Information Protection으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-187">Turning on this setting allows signals to be forwarded to Azure Information Protection.</span></span> <span data-ttu-id="89805-188">이 기능을 사용하면 데이터 소유자와 관리자가 온보더된 디바이스의 보호된 데이터와 장치 위험 등급을 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-188">It gives data owners and administrators visibility into protected data on onboarded devices and device risk ratings.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="89805-189">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="89805-189">Microsoft Secure Score</span></span>

<span data-ttu-id="89805-190">끝점용 Microsoft Defender 신호를 Microsoft 365 보안 센터의 Microsoft 보안 점수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-190">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="89805-191">이 기능을 켜면 Microsoft 보안 점수가 장치의 보안 상태와 관련한 가시성을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-191">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="89805-192">전달된 데이터는 Microsoft 보안 점수 데이터와 동일한 위치에 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-192">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="89805-193">Microsoft Defender for Identity 포털에서 끝점에 대한 Microsoft Defender 통합 사용</span><span class="sxs-lookup"><span data-stu-id="89805-193">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="89805-194">Id에 대한 Microsoft Defender에서 상황에 맞는 장치 통합을 받으기 위해 Microsoft Defender for Identity 포털에서 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-194">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="89805-195">전역 관리자 또는 보안 관리자 역할로 ID 포털에 Microsoft [Defender에](https://portal.atp.azure.com/) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-195">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="89805-196">인스턴스 **만들기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-196">Click **Create your instance**.</span></span>

3. <span data-ttu-id="89805-197">통합 설정을 **으로 전환하고** 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89805-197">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="89805-198">두 포털에서 통합 단계를 완료한 후 장치 세부 정보 또는 사용자 세부 정보 페이지에서 관련 알림을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-198">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="microsoft-intune-connection"></a><span data-ttu-id="89805-199">Microsoft Intune 연결</span><span class="sxs-lookup"><span data-stu-id="89805-199">Microsoft Intune connection</span></span>

<span data-ttu-id="89805-200">끝점용 Defender를 [Microsoft Intune과](https://docs.microsoft.com/intune/what-is-intune) 통합하여 장치 위험 기반 조건부 액세스를 사용하도록 [설정할 수 있습니다.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="89805-200">Defender for Endpoint can be integrated with [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) to [enable device risk-based conditional access](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="89805-201">이 [기능을 켜면](configure-conditional-access.md)끝점 장치 정보에 대한 Defender를 Intune과 공유하여 정책 적용을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-201">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89805-202">이 기능을 사용하려면 Intune 및 Endpoint용 Defender에서 통합을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-202">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="89805-203">특정 단계에 대한 자세한 내용은 [Configure Conditional Access in Defender for Endpoint을 참조하세요.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="89805-203">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="89805-204">이 기능은 다음이 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-204">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="89805-205">Enterprise Mobility + Security E3 및 Windows E5(또는 Microsoft 365 Enterprise E5)에 대한 사용이 허가된 테넌트</span><span class="sxs-lookup"><span data-stu-id="89805-205">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="89805-206">Intune에서 관리하는 Windows 10 장치 [Azure AD에](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)가입된 활성 Microsoft Intune 환경.</span><span class="sxs-lookup"><span data-stu-id="89805-206">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="89805-207">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="89805-207">Conditional Access policy</span></span>

<span data-ttu-id="89805-208">Intune 통합을 사용하도록 설정하면 Intune에서 클래식 CA(조건부 액세스) 정책을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="89805-208">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="89805-209">이 클래식 CA 정책은 상황 보고서를 Intune으로 설정하기 위한 전제입니다.</span><span class="sxs-lookup"><span data-stu-id="89805-209">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="89805-210">삭제하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-210">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="89805-211">Intune에서 만든 클래식 CA 정책은 [](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)끝점을 구성하는 데 사용되는 최신 조건부 액세스 정책과는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="89805-211">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>

## <a name="preview-features"></a><span data-ttu-id="89805-212">미리 보기 기능</span><span class="sxs-lookup"><span data-stu-id="89805-212">Preview features</span></span>

<span data-ttu-id="89805-213">Endpoint용 Defender 미리 보기 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-213">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="89805-214">예정된 기능에 액세스할 수 있습니다. 기능은 일반적으로 사용 가능하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-214">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="89805-215">Microsoft 준수 센터와 끝점 경고 공유</span><span class="sxs-lookup"><span data-stu-id="89805-215">Share endpoint alerts with Microsoft Compliance Center</span></span>

<span data-ttu-id="89805-216">끝점 보안 경고 및 해당 평가 상태를 Microsoft 규정 준수 센터에 전달하여 경고를 통해 내부자 위험 관리 정책을 향상하고 내부 위험을 발생시키는 위험을 해결한 후 손상을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89805-216">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="89805-217">전달된 데이터는 처리되고 Office 365 데이터와 동일한 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-217">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="89805-218">내부자 위험 [](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) 관리 설정에서 보안 정책 위반 표시기를 구성한 후 끝점용 Defender 경고는 해당 사용자의 내부자 위험 관리와 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="89805-218">After configuring the [Security policy violation indicators](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89805-219">관련 항목</span><span class="sxs-lookup"><span data-stu-id="89805-219">Related topics</span></span>

- [<span data-ttu-id="89805-220">데이터 보존 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="89805-220">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="89805-221">경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="89805-221">Configure alert notifications</span></span>](configure-email-notifications.md)
