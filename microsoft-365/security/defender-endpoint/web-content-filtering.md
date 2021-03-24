---
title: 웹 콘텐츠 필터링
description: Microsoft Defender ATP의 웹 콘텐츠 필터링을 사용하여 해당 콘텐츠 범주에 따라 웹 사이트에 대한 액세스를 추적하고 규제합니다.
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 모니터링, 보고서, 카드, 도메인 목록, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071759"
---
# <a name="web-content-filtering"></a><span data-ttu-id="83413-104">웹 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="83413-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83413-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="83413-105">**Applies to:**</span></span>
- [<span data-ttu-id="83413-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="83413-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="83413-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83413-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="83413-108">**웹 콘텐츠 필터링이 현재 공개 미리 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="83413-109">이 미리 보기 버전은 서비스 수준 계약 없이 제공하며 프로덕션 워크로드에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="83413-110">일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="83413-111">자세한 내용은 끝점 미리 보기 [기능용 Microsoft Defender를 참조하세요.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="83413-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="83413-112">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="83413-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83413-113">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="83413-114">웹 콘텐츠 필터링은 [](web-protection-overview.md) 끝점용 Microsoft Defender의 웹 보호 기능의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="83413-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="83413-115">이를 통해 조직은 해당 콘텐츠 범주에 따라 웹 사이트에 대한 액세스를 추적하고 규제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="83413-116">이러한 웹 사이트 중 상당수는 악의적이지 않은 경우 규정 준수 규정, 대역폭 사용량 또는 기타 문제로 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="83413-117">특정 범주를 차단하도록 장치 그룹 전체에서 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="83413-118">범주를 차단하면 지정된 장치 그룹 내의 사용자가 해당 범주와 연결된 URL에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="83413-119">차단되지 않은 범주에 대해 URL이 자동으로 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="83413-120">사용자는 중단 없이 URL에 액세스할 수 있으며 액세스 통계를 수집하여 보다 사용자 지정 정책 결정을 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="83413-121">사용자가 보고 있는 페이지의 요소가 차단된 리소스를 호출하는 경우 차단 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="83413-122">웹 콘텐츠 필터링은 Microsoft Edge(Microsoft Edge) 및 네트워크 보호(Chrome, Firefox, Brave 및 Opera)에서 Windows Defender 블록이 있는 주요 웹 브라우저에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="83413-123">브라우저 지원에 대한 자세한 내용은 prerequisites 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83413-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="83413-124">이점 요약:</span><span class="sxs-lookup"><span data-stu-id="83413-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="83413-125">사용자가 차단된 범주의 웹 사이트에 액세스하지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="83413-126">끝점 역할 기반 액세스 제어 설정에 대해 [Microsoft Defender에](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac) 정의된 장치 그룹을 사용하여 사용자 그룹에 정책을 편리하게 배포</span><span class="sxs-lookup"><span data-stu-id="83413-126">Conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="83413-127">실제 블록 및 웹 사용 현황에 대한 가시성을 사용하여 동일한 중앙 위치에 있는 웹 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="83413-127">Access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="83413-128">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="83413-128">User experience</span></span>

<span data-ttu-id="83413-129">지원되는 제3자 브라우저에 대한 차단 환경은 차단된 연결을 사용자에게 알리는 시스템 수준 알림을 제공하는 네트워크 보호를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> 

<span data-ttu-id="83413-130">보다 친숙한 브라우저 내 환경을 위해 Microsoft Edge를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-130">For a more user-friendly in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83413-131">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="83413-131">Prerequisites</span></span>

<span data-ttu-id="83413-132">이 기능을 사용해 보기 전에 다음 요구 사항이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="83413-133">Windows 10 Enterprise E5 라이선스 또는 Microsoft 365 E3 + Microsoft 365 E5 보안 추가 기능</span><span class="sxs-lookup"><span data-stu-id="83413-133">Windows 10 Enterprise E5 license OR Microsoft 365 E3 + Microsoft 365 E5 Security add-on.</span></span>
- <span data-ttu-id="83413-134">Microsoft Defender 보안 센터 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="83413-134">Access to Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="83413-135">최신 MoCAMP 업데이트를 통해 Windows 10 1주년 업데이트(버전 1607) 이상을 실행하는 장치.</span><span class="sxs-lookup"><span data-stu-id="83413-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

<span data-ttu-id="83413-136">SmartScreen을 Windows Defender 경우 네트워크 보호가 차단을 인계합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-136">If Windows Defender SmartScreen isn't turned on, Network Protection will take over the blocking.</span></span> <span data-ttu-id="83413-137">디바이스에서 [네트워크 보호를](enable-network-protection.md) 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-137">It requires [enabling Network Protection](enable-network-protection.md) on the device.</span></span> <span data-ttu-id="83413-138">Chrome, Firefox, Brave 및 Opera는 현재 이 기능이 활성화된 제3자 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="83413-138">Chrome, Firefox, Brave, and Opera are currently 3rd party browsers in which this feature is enabled.</span></span>

## <a name="data-handling"></a><span data-ttu-id="83413-139">데이터 처리</span><span class="sxs-lookup"><span data-stu-id="83413-139">Data handling</span></span>

<span data-ttu-id="83413-140">Microsoft Defender for Endpoint 데이터 처리 설정의 일부로 사용하기로 선택한 [지역을 따를 것입니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="83413-140">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy).</span></span> <span data-ttu-id="83413-141">데이터가 데이터 센터에서 나가지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-141">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="83413-142">또한 데이터 공급자를 포함하여 모든 타사와 귀하의 데이터가 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-142">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="83413-143">웹 콘텐츠 필터링 켜기</span><span class="sxs-lookup"><span data-stu-id="83413-143">Turn on web content filtering</span></span>

<span data-ttu-id="83413-144">왼쪽 탐색 메뉴에서 설정 > 고급 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-144">From the left-hand navigation menu, select **Settings > General > Advanced Features**.</span></span> <span data-ttu-id="83413-145">웹 콘텐츠 필터링 항목이 표시될 때까지 아래로 **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-145">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="83413-146">토글을 **켜기 및** 저장 기본 **설정으로 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-146">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="83413-147">웹 콘텐츠 필터링 정책 구성</span><span class="sxs-lookup"><span data-stu-id="83413-147">Configure web content filtering policies</span></span>

<span data-ttu-id="83413-148">웹 콘텐츠 필터링 정책은 어떤 장치 그룹에서 차단되는 사이트 범주를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-148">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="83413-149">정책을 관리하려면 웹 콘텐츠 필터링 **> 규칙 > 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-149">To manage the policies, go to **Settings > Rules > Web content filtering**.</span></span>

<span data-ttu-id="83413-150">필터를 사용하여 차단된 특정 범주를 포함하거나 특정 장치 그룹에 적용되는 정책을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-150">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="83413-151">정책 만들기</span><span class="sxs-lookup"><span data-stu-id="83413-151">Create a policy</span></span>

<span data-ttu-id="83413-152">새 정책을 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="83413-152">To add a new policy:</span></span>

1. <span data-ttu-id="83413-153">설정 **에서** 웹 콘텐츠 필터링 페이지에서 **정책** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-153">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>
2. <span data-ttu-id="83413-154">이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-154">Specify a name.</span></span>
3. <span data-ttu-id="83413-155">차단할 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-155">Select the categories to block.</span></span> <span data-ttu-id="83413-156">확장 아이콘을 사용하여 각 상위 범주를 완전히 확장하고 특정 웹 콘텐츠 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-156">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>
4. <span data-ttu-id="83413-157">정책 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-157">Specify the policy scope.</span></span> <span data-ttu-id="83413-158">정책을 적용할 위치를 지정하려면 장치 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-158">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="83413-159">선택한 디바이스 그룹의 디바이스만 선택한 범주의 웹 사이트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-159">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>
5. <span data-ttu-id="83413-160">요약을 검토하고 정책을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-160">Review the summary and save the policy.</span></span> <span data-ttu-id="83413-161">선택한 장치에 정책 새로 고침을 적용하는 데 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-161">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

<span data-ttu-id="83413-162">팁: 장치 그룹에서 범주를 선택하지 않고 정책을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-162">Tip: You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="83413-163">이 작업은 차단 정책을 만들기 전에 사용자 동작을 이해하는 데 도움이 되는 감사 전용 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-163">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="83413-164">정책을 제거하거나 장치 그룹을 동시에 변경하는 경우 정책 배포가 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-164">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="83413-165">"분류되지 않은" 범주를 차단하면 예기치 않게 원치 않는 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-165">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="83413-166">특정 웹 사이트 허용</span><span class="sxs-lookup"><span data-stu-id="83413-166">Allow specific websites</span></span>

<span data-ttu-id="83413-167">웹 콘텐츠 필터링에서 차단된 범주를 정의하여 사용자 지정 표시기 정책을 만들어 단일 사이트를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-167">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="83413-168">사용자 지정 표시기 정책은 해당 디바이스 그룹에 적용될 때 웹 콘텐츠 필터링 정책을 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-168">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="83413-169">설정 표시기   >    >  **URL/도메인** 항목 추가로 이동하여 Microsoft Defender 보안 센터에서 사용자 지정  >  **표시기 만들기**</span><span class="sxs-lookup"><span data-stu-id="83413-169">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**</span></span>
2. <span data-ttu-id="83413-170">사이트의 도메인 입력</span><span class="sxs-lookup"><span data-stu-id="83413-170">Enter the domain of the site</span></span>
3. <span data-ttu-id="83413-171">정책 작업을 허용으로 **설정**</span><span class="sxs-lookup"><span data-stu-id="83413-171">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="83413-172">부정확성 보고</span><span class="sxs-lookup"><span data-stu-id="83413-172">Reporting inaccuracies</span></span>

<span data-ttu-id="83413-173">잘못 분류된 도메인이 발견되는 경우 웹 콘텐츠 필터링 보고서 페이지에서 부정확한 정보를 직접 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-173">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="83413-174">이 기능은 새로운 Microsoft 365 보안 센터(security.microsoft.com)에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-174">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="83413-175">부정확한 내용을 보고하려면 보고서 > 웹 보호 > 도메인의 웹 콘텐츠 필터링 > **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-175">To report an inaccuracy, navigate to **Reports > Web protection > Web Content Filtering Details > Domains**.</span></span> <span data-ttu-id="83413-176">웹 콘텐츠 필터링 보고서의 도메인 탭에는 각 도메인 옆에 타원이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-176">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="83413-177">이 타원 위에 마우스를 대고 **부정확성 보고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-177">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="83413-178">우선 순위를 선택하고 다시 분류할 수 있는 범주와 같은 추가 세부 정보를 추가할 수 있는 패널이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="83413-178">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="83413-179">양식을 완성한 후 제출 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83413-179">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="83413-180">팀에서 업무일 1일 이내에 요청을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-180">Our team will review the request within one business day.</span></span> <span data-ttu-id="83413-181">즉각적인 차단 해제를 위해 사용자 지정 허용 [표시기를 만드시다.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="83413-181">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="83413-182">웹 콘텐츠 필터링 카드 및 세부 정보</span><span class="sxs-lookup"><span data-stu-id="83413-182">Web content filtering cards and details</span></span>

<span data-ttu-id="83413-183">웹 **> 필터링** 및 웹 위협 방지에 대한 정보가 있는 카드를 표시하려면 보고서 웹 보호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-183">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="83413-184">다음 카드는 웹 콘텐츠 필터링에 대한 요약 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-184">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="83413-185">범주별 웹 활동</span><span class="sxs-lookup"><span data-stu-id="83413-185">Web activity by category</span></span>

<span data-ttu-id="83413-186">이 카드에는 액세스 시도 횟수가 가장 크게 증가하거나 감소한 상위 웹 콘텐츠 범주가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-186">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="83413-187">지난 30일, 3개월 또는 6개월 동안 조직의 웹 활동 패턴이 대대적으로 변경된 내용을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-187">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="83413-188">범주 이름을 선택하여 자세한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-188">Select a category name to view more information.</span></span>

<span data-ttu-id="83413-189">이 기능을 처음 30일 동안 사용하면 조직에 이 정보를 표시할 데이터가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-189">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![범주 카드별 웹 활동 이미지](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="83413-191">웹 콘텐츠 필터링 요약 카드</span><span class="sxs-lookup"><span data-stu-id="83413-191">Web content filtering  summary card</span></span>

<span data-ttu-id="83413-192">이 카드는 여러 상위 웹 콘텐츠 범주에 대해 차단된 액세스 시도의 분포를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-192">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="83413-193">특정 상위 웹 범주에 대한 자세한 정보를 표시하려면 색 막대 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-193">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![웹 콘텐츠 필터링 요약 카드의 이미지](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="83413-195">웹 활동 요약 카드</span><span class="sxs-lookup"><span data-stu-id="83413-195">Web activity summary card</span></span>

<span data-ttu-id="83413-196">이 카드에는 모든 URL의 웹 콘텐츠에 대한 총 요청 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-196">This card displays the total number of requests for web content in all URLs.</span></span>

![웹 활동 요약 카드의 이미지](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="83413-198">카드 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="83413-198">View card details</span></span>

<span data-ttu-id="83413-199">카드의 차트에서 표 행이나 색이 있는 막대를 선택하여 각 카드에 대한 보고서 세부 정보에 액세스할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="83413-199">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="83413-200">각 카드의 보고서 세부 정보 페이지에는 웹 콘텐츠 범주, 웹 사이트 도메인 및 장치 그룹에 대한 광범위한 통계 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-200">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![웹 보호 보고서 세부 정보 이미지](images/web-protection-report-details.png)

- <span data-ttu-id="83413-202">**웹 범주:** 조직에서 액세스 시도가 시도된 웹 콘텐츠 범주를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-202">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="83413-203">요약 플라이아웃을 열기 위해 특정 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-203">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="83413-204">**도메인:** 조직에서 액세스되거나 차단된 웹 도메인을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-204">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="83413-205">해당 도메인에 대한 자세한 정보를 확인하려면 특정 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-205">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="83413-206">**장치 그룹:** 조직에서 웹 활동을 생성한 모든 장치 그룹을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-206">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="83413-207">페이지 왼쪽 위에 있는 시간 범위 필터를 사용하여 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-207">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="83413-208">정보를 필터링하거나 열을 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-208">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="83413-209">선택한 항목에 대한 추가 정보가 있는 플라이아웃 창을 열기 위해 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83413-209">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="83413-210">오류 및 문제</span><span class="sxs-lookup"><span data-stu-id="83413-210">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="83413-211">이 미리 보기의 제한 사항 및 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="83413-211">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="83413-212">장치의 OS 구성이 Server(Systeminfo > OS 구성)인 > Microsoft Edge만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-212">Only Microsoft Edge is supported if your device's OS configuration is Server (cmd > Systeminfo > OS Configuration).</span></span> <span data-ttu-id="83413-213">네트워크 보호는 지원되는 제3자 브라우저에서 트래픽을 보호하는 서버 장치의 검사 모드에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-213">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="83413-214">미지정 장치에는 보고서에 잘못된 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83413-214">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="83413-215">Report details > Device groups pivot, you may see a row with a blank Device Group field.</span><span class="sxs-lookup"><span data-stu-id="83413-215">In the Report details > Device groups pivot, you may see a row with a blank Device Group field.</span></span> <span data-ttu-id="83413-216">이 그룹에는 지정한 그룹에 들어가기 전에 지정되지 않은 장치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-216">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="83413-217">이 행에 대한 보고서에 장치 또는 액세스 수가 정확한 수를 포함하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83413-217">The report for this row may not contain an accurate count of devices or access counts.</span></span>

## <a name="related-topics"></a><span data-ttu-id="83413-218">관련 항목</span><span class="sxs-lookup"><span data-stu-id="83413-218">Related topics</span></span>

- [<span data-ttu-id="83413-219">웹 보호 개요</span><span class="sxs-lookup"><span data-stu-id="83413-219">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="83413-220">웹 위협 방지</span><span class="sxs-lookup"><span data-stu-id="83413-220">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="83413-221">웹 보안 모니터링</span><span class="sxs-lookup"><span data-stu-id="83413-221">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="83413-222">웹 위협에 대응</span><span class="sxs-lookup"><span data-stu-id="83413-222">Respond to web threats</span></span>](web-protection-response.md)
