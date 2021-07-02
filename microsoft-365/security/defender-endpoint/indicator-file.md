---
title: 파일에 대한 지표 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시에 대한 표시기를 만들 수 있습니다.
keywords: 파일, 해시, 관리, 허용, 차단, 차단, 정리, 악성, 파일 해시, ip 주소, URL, 도메인
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256918"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="83275-104">파일에 대한 지표 만들기</span><span class="sxs-lookup"><span data-stu-id="83275-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83275-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="83275-105">**Applies to:**</span></span>
- [<span data-ttu-id="83275-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="83275-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="83275-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83275-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="83275-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="83275-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="83275-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="83275-110">잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="83275-111">잠재적으로 악의적인 PE(이식 가능한 실행 파일) 파일을 알고 있는 경우 해당 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="83275-112">이 작업을 수행하면 조직의 장치에서 읽고 쓰거나 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="83275-113">파일에 대한 표시기를 만드는 방법에는 다음 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="83275-114">설정 페이지를 통해 표시기를 만들어</span><span class="sxs-lookup"><span data-stu-id="83275-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="83275-115">파일 세부 정보 페이지에서 표시기 추가 단추를 사용하여 상황 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="83275-116">표시기 API를 통해 [표시기를 만들어](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="83275-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="83275-117">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="83275-117">Before you begin</span></span>

<span data-ttu-id="83275-118">파일에 대한 표시기를 만들기 전에 다음과 같은 선행 방법을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="83275-119">이 기능은 조직에서 활성  Microsoft Defender 바이러스 백신 클라우드 기반 보호를 사용하도록 설정된 경우 **사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="83275-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="83275-120">자세한 내용은 클라우드 기반 보호 [관리를 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="83275-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="83275-121">맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="83275-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="83275-122">월별 [플랫폼 및 엔진 버전 참조](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="83275-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="83275-123">2019년 Windows 10 버전 1703 이상, Windows Server 2016 장치에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="83275-124">파일 차단을 시작하려면 먼저 파일 차단에서 "차단 또는 [허용"](advanced-features.md) 기능을 켜야 설정.</span><span class="sxs-lookup"><span data-stu-id="83275-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="83275-125">이 기능은 의심되는 맬웨어(또는 악성 파일)가 웹에서 다운로드되지 않도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="83275-126">현재 이식 가능한 PE(실행 파일) 파일(예: 파일 및 .exe 포함).dll 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="83275-127">적용 범위는 시간이 지날 때 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="83275-128">설정 페이지에서 파일에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="83275-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="83275-129">탐색 창에서 **표시기 설정 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83275-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="83275-130">파일 **해시 탭을**   선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="83275-131">표시기 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83275-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="83275-132">다음 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-132">Specify the following details:</span></span>
    - <span data-ttu-id="83275-133">Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="83275-134">작업 - 수행될 작업을 지정하고 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="83275-135">범위 - 장치 그룹의 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="83275-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="83275-136">요약 탭에서 세부 정보를 검토한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="83275-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="83275-137">파일 세부 정보 페이지에서 상황 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="83275-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="83275-138">파일에 대한 응답 [](respond-file-alerts.md)작업을 수행할 때의 옵션 중 하나는 파일에 대한 표시기를   추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83275-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="83275-139">파일에 대한 표시기 해시를 추가할 때 조직의 장치가 파일을 실행하려고 할 때마다 경고를 발생하고 파일을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="83275-140">표시기에서 자동으로 차단되는 파일은 파일의 알림 센터에 표시되지 않지만 경고 큐에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="83275-141">일반적으로 파일 블록은 몇 분 이내에 적용 및 제거되지만 30분까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="83275-142">적용 유형과 대상이 동일한 충돌하는 파일 IoC 정책이 있는 경우 보다 안전한 해시 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="83275-143">SHA-256 파일 해시 IoC 정책은 SHA-1 파일 해시 IoC 정책을 통해 이기며, 해시 유형이 동일한 파일을 정의하는 경우 MD5 파일 해시 IoC 정책에서 이기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="83275-144">이는 장치 그룹에 관계없이 항상 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="83275-145">다른 모든 경우 적용 대상이 동일한 충돌하는 파일 IoC 정책이 모든 장치 및 디바이스 그룹에 적용될 경우 디바이스 그룹의 정책이 이기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="83275-146">EnableFileHashComputation 그룹 정책을 사용하지 않도록 설정하면 IoC 파일의 차단 정확도가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="83275-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="83275-147">그러나 사용하도록 `EnableFileHashComputation` 설정하면 장치 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83275-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="83275-148">예를 들어 네트워크 공유에서 로컬 장치(특히 VPN 연결을 통해)에 큰 파일을 복사하면 장치 성능에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="83275-149">EnableFileHashComputation 그룹 정책에 대한 자세한 내용은 [Defender CSP를 참조하세요.](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="83275-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="83275-150">정책 충돌 처리</span><span class="sxs-lookup"><span data-stu-id="83275-150">Policy conflict handling</span></span>  

<span data-ttu-id="83275-151">Cert 및 File IoC 정책 처리 충돌은 다음 순서를 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="83275-152">응용 프로그램 제어 및 AppLocker에서 모드 정책/정책을 Windows Defender 파일을 허용하지 않는 경우 **차단**</span><span class="sxs-lookup"><span data-stu-id="83275-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="83275-153">그 외 제외에서 파일을 Microsoft Defender 바이러스 백신 다음 **허용**</span><span class="sxs-lookup"><span data-stu-id="83275-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="83275-154">그렇지 않은 경우 파일이 차단되거나 파일 IoC에 의해 경고된 경우 **차단/경고**</span><span class="sxs-lookup"><span data-stu-id="83275-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="83275-155">파일을 허용 파일 IoC 정책에서 허용하는 경우  허용</span><span class="sxs-lookup"><span data-stu-id="83275-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="83275-156">다른 경우 파일이 ASR 규칙, CFA, AV, SmartScreen, Block에 의해 **차단된 경우**</span><span class="sxs-lookup"><span data-stu-id="83275-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="83275-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span><span class="sxs-lookup"><span data-stu-id="83275-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="83275-158">적용 유형과 대상이 동일한 충돌하는 파일 IoC 정책이 있는 경우 더 안전한(더 긴) 해시 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="83275-159">예를 들어 두 해시 유형이 동일한 파일을 정의하는 경우 SHA-256 파일 해시 IoC 정책이 MD5 파일 해시 IoC 정책에서 이기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="83275-160">위협 및 취약성 관리 응용 프로그램 차단 기능은 적용을 위해 IoC 파일을 사용하며 위의 충돌 처리 순서를 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83275-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="83275-161">예제</span><span class="sxs-lookup"><span data-stu-id="83275-161">Examples</span></span>

|<span data-ttu-id="83275-162">구성 요소</span><span class="sxs-lookup"><span data-stu-id="83275-162">Component</span></span> |<span data-ttu-id="83275-163">구성 요소 적용</span><span class="sxs-lookup"><span data-stu-id="83275-163">Component enforcement</span></span> |<span data-ttu-id="83275-164">파일 표시기 동작</span><span class="sxs-lookup"><span data-stu-id="83275-164">File indicator Action</span></span> |<span data-ttu-id="83275-165">결과</span><span class="sxs-lookup"><span data-stu-id="83275-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="83275-166">공격 표면 축소 파일 경로 제외</span><span class="sxs-lookup"><span data-stu-id="83275-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="83275-167">허용</span><span class="sxs-lookup"><span data-stu-id="83275-167">Allow</span></span> |<span data-ttu-id="83275-168">차단</span><span class="sxs-lookup"><span data-stu-id="83275-168">Block</span></span> |<span data-ttu-id="83275-169">차단</span><span class="sxs-lookup"><span data-stu-id="83275-169">Block</span></span>
|<span data-ttu-id="83275-170">공격 표면 감소 규칙</span><span class="sxs-lookup"><span data-stu-id="83275-170">Attack surface reduction rule</span></span> |<span data-ttu-id="83275-171">차단</span><span class="sxs-lookup"><span data-stu-id="83275-171">Block</span></span> |<span data-ttu-id="83275-172">허용</span><span class="sxs-lookup"><span data-stu-id="83275-172">Allow</span></span> |<span data-ttu-id="83275-173">허용</span><span class="sxs-lookup"><span data-stu-id="83275-173">Allow</span></span>
|<span data-ttu-id="83275-174">Windows Defender 응용 프로그램 제어</span><span class="sxs-lookup"><span data-stu-id="83275-174">Windows Defender Application Control</span></span> |<span data-ttu-id="83275-175">허용</span><span class="sxs-lookup"><span data-stu-id="83275-175">Allow</span></span> |<span data-ttu-id="83275-176">차단</span><span class="sxs-lookup"><span data-stu-id="83275-176">Block</span></span> |<span data-ttu-id="83275-177">허용</span><span class="sxs-lookup"><span data-stu-id="83275-177">Allow</span></span> |
|<span data-ttu-id="83275-178">Windows Defender 응용 프로그램 제어</span><span class="sxs-lookup"><span data-stu-id="83275-178">Windows Defender Application Control</span></span> |<span data-ttu-id="83275-179">차단</span><span class="sxs-lookup"><span data-stu-id="83275-179">Block</span></span> |<span data-ttu-id="83275-180">허용</span><span class="sxs-lookup"><span data-stu-id="83275-180">Allow</span></span> |<span data-ttu-id="83275-181">차단</span><span class="sxs-lookup"><span data-stu-id="83275-181">Block</span></span>
|<span data-ttu-id="83275-182">Microsoft Defender 바이러스 백신 제외</span><span class="sxs-lookup"><span data-stu-id="83275-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="83275-183">허용</span><span class="sxs-lookup"><span data-stu-id="83275-183">Allow</span></span> |<span data-ttu-id="83275-184">차단</span><span class="sxs-lookup"><span data-stu-id="83275-184">Block</span></span> |<span data-ttu-id="83275-185">허용</span><span class="sxs-lookup"><span data-stu-id="83275-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="83275-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83275-186">See also</span></span>

- [<span data-ttu-id="83275-187">지표 만들기</span><span class="sxs-lookup"><span data-stu-id="83275-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="83275-188">IP 및 URL/도메인에 대한 지표 만들기</span><span class="sxs-lookup"><span data-stu-id="83275-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="83275-189">인증서를 기반으로 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="83275-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="83275-190">지표 관리</span><span class="sxs-lookup"><span data-stu-id="83275-190">Manage indicators</span></span>](indicator-manage.md)
