---
title: 제어된 폴더 액세스로 파일을 암호화하지 않는 랜섬웨어로부터 중요한 폴더 보호
description: 기본 폴더의 파일은 악성 앱에 의해 변경되지 못하게 보호할 수 있습니다. 랜섬웨어가 파일을 암호화하지 못하게 합니다.
keywords: 제어된 폴더 액세스, windows 10, windows defender, 랜섬웨어, 보호, 파일, 폴더
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: cd662dc130adc37b3bf8bd06839242ccc9a49f8e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185972"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="04bf2-105">제어된 폴더 액세스로 중요한 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="04bf2-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04bf2-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="04bf2-106">**Applies to:**</span></span>
- [<span data-ttu-id="04bf2-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="04bf2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="04bf2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04bf2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="04bf2-109">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="04bf2-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="04bf2-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="04bf2-111">제어된 폴더 액세스란?</span><span class="sxs-lookup"><span data-stu-id="04bf2-111">What is controlled folder access?</span></span>

<span data-ttu-id="04bf2-112">제어된 폴더 액세스는 랜섬웨어와 같은 악성 앱 및 위협으로부터 중요한 데이터를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="04bf2-113">제어된 폴더 액세스는 알려진 신뢰할 수 있는 앱 목록에서 앱을 확인하여 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="04bf2-114">Windows Server 2019 및 Windows 10 클라이언트에서 지원되는 제어된 폴더 액세스는 Windows 보안 앱, Microsoft Endpoint Configuration Manager 또는 Intune(관리되는 디바이스의 경우)을 사용하여 으로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="04bf2-115">스크립팅 엔진은 신뢰할 수 없습니다. 제어된 보호된 폴더에 대한 액세스를 허용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="04bf2-116">예를 들어 인증서 및 파일 표시기를 사용하여 허용하는 경우에도 PowerShell은 제어된 폴더 액세스에서 [신뢰되지 않습니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="04bf2-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="04bf2-117">제어된 폴더 액세스는 제어된 폴더 액세스 이벤트에 대한 자세한 보고를 제공하고 일반적인 경고 조사 시나리오의 일부로 차단하는 [끝점용 Microsoft Defender와](microsoft-defender-endpoint.md)가장 [잘 작동합니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="04bf2-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="04bf2-118">제어된 폴더 액세스 블록은 경고 큐에 [경고를 생성하지 않습니다.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="04bf2-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="04bf2-119">그러나 고급 헌팅을 사용하는 동안 또는 [](investigate-machines.md)사용자 지정 검색 [](advanced-hunting-overview.md)규칙과 함께 장치 타임라인 보기에서 제어된 폴더 액세스 블록에 대한 정보를 볼 [수 있습니다.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="04bf2-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="04bf2-120">제어된 폴더 액세스는 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="04bf2-120">How does controlled folder access work?</span></span>

<span data-ttu-id="04bf2-121">제어된 폴더 액세스는 신뢰할 수 있는 앱이 보호된 폴더에 액세스할 수만 있도록 허용하여 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="04bf2-122">보호된 폴더는 제어된 폴더 액세스를 구성할 때 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="04bf2-123">일반적으로 일반적으로 문서, 그림, 다운로드 등에서 사용되는 폴더와 같이 일반적으로 사용되는 폴더는 제어된 폴더 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="04bf2-124">제어된 폴더 액세스는 신뢰할 수 있는 앱 목록에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="04bf2-125">신뢰할 수 있는 소프트웨어 목록에 포함된 앱은 예상대로 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="04bf2-126">목록에 포함되지 않은 앱은 보호된 폴더 내부의 파일을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="04bf2-127">앱이 보전 및 신뢰도에 따라 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="04bf2-128">조직 전체에서 매우 만연하며 악의적인 것으로 간주되는 동작을 표시하지 않은 앱은 신뢰할 수 있는 앱으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="04bf2-129">이러한 앱은 목록에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="04bf2-130">Configuration Manager 또는 Intune을 사용하여 앱을 신뢰할 수 있는 목록에 수동으로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="04bf2-131">앱에 대한 [](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) 파일 표시기 추가와 같은 추가 작업은 보안 센터 콘솔에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="04bf2-132">제어된 폴더 액세스가 중요한 이유</span><span class="sxs-lookup"><span data-stu-id="04bf2-132">Why controlled folder access is important</span></span>

<span data-ttu-id="04bf2-133">제어된 폴더 액세스는 랜섬웨어로부터 문서 및 정보를 보호하는 데 [특히 유용합니다.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="04bf2-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="04bf2-134">랜섬웨어 공격에서 파일은 암호화되고 인질로 보호될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="04bf2-135">제어된 폴더 액세스가 적용된 경우 앱이 보호된 폴더의 파일을 변경하려고 시도한 컴퓨터에 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="04bf2-136">회사 세부 [정보 및 연락처](customize-attack-surface-reduction.md#customize-the-notification) 정보로 알림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="04bf2-137">또한 규칙을 개별적으로 사용하도록 설정하여 기능이 모니터링하는 기술을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="04bf2-138">보호된 [폴더에는](#review-controlled-folder-access-events-in-windows-event-viewer) 일반적인 시스템 폴더(부팅 섹터 포함)가 포함되고 폴더를 더 추가할 [수 있습니다.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="04bf2-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="04bf2-139">앱에서 보호된 [폴더에](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) 대한 액세스 권한을 부여하도록 허용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="04bf2-140">감사 모드를 [사용하여](audit-windows-defender.md) 제어된 폴더 액세스가 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="04bf2-141">또한 Windows Defender 테스트 demo.wd.microsoft.com 웹 사이트를 방문하여 기능이 작동하는지 확인하고 작동 방법을 확인할 수 있습니다. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="04bf2-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="04bf2-142">제어된 폴더 액세스는 다음 버전의 Windows에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="04bf2-143">[Windows 10 버전 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="04bf2-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="04bf2-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="04bf2-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="04bf2-145">Windows 시스템 폴더는 기본적으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="04bf2-146">Windows 시스템 폴더는 기본적으로 몇 가지 다른 폴더와 함께 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="04bf2-147">추가 폴더를 보호된 폴더로 구성할 수는 있지만 기본적으로 보호되는 Windows 시스템 폴더는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="04bf2-148">제어된 폴더 액세스에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="04bf2-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="04bf2-149">제어된 폴더 액세스에는 Microsoft Defender 바이러스 백신 실시간 보호를 [사용하도록 설정해야 합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="04bf2-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="04bf2-150">Microsoft Defender 보안 센터에서 제어된 폴더 액세스 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="04bf2-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="04bf2-151">Endpoint용 Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 [차단합니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="04bf2-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="04bf2-152">고급 헌팅을 사용하여 Microsoft Defender에서 끝점 데이터를 [쿼리할 수 있습니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="04bf2-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="04bf2-153">감사 모드를 사용하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 제어된 폴더 액세스 설정이 사용하도록 설정된 경우 환경에 어떤 영향을 주는지 볼 수 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="04bf2-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="04bf2-154">쿼리 예제:</span><span class="sxs-lookup"><span data-stu-id="04bf2-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="04bf2-155">Windows 이벤트 뷰어에서 제어된 폴더 액세스 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="04bf2-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="04bf2-156">Windows 이벤트 로그를 검토하여 제어된 폴더 액세스가 앱을 차단(또는 감사)할 때 생성되는 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="04bf2-157">평가 [패키지를](https://aka.ms/mp7z2w) 다운로드하고  디바이스에서cfa-events.xml쉽게 액세스할 수 있는 위치에 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="04bf2-158">시작 **메뉴에** 이벤트 뷰어를 입력하여 Windows 이벤트 뷰어를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="04bf2-159">왼쪽 패널의 **동작에서** 사용자 지정 보기 **가져오기... 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="04bf2-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="04bf2-160">추출한 위치로 *이동하여cfa-events.xml* 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="04bf2-161">또는 [XML을 직접 복사합니다.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="04bf2-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="04bf2-162">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-162">Select **OK**.</span></span>

<span data-ttu-id="04bf2-163">다음 표에는 제어된 폴더 액세스와 관련된 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="04bf2-164">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="04bf2-164">Event ID</span></span> | <span data-ttu-id="04bf2-165">설명</span><span class="sxs-lookup"><span data-stu-id="04bf2-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="04bf2-166">5007</span><span class="sxs-lookup"><span data-stu-id="04bf2-166">5007</span></span> | <span data-ttu-id="04bf2-167">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="04bf2-167">Event when settings are changed</span></span> |
|<span data-ttu-id="04bf2-168">1124</span><span class="sxs-lookup"><span data-stu-id="04bf2-168">1124</span></span> | <span data-ttu-id="04bf2-169">감사된 제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="04bf2-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="04bf2-170">1123</span><span class="sxs-lookup"><span data-stu-id="04bf2-170">1123</span></span> | <span data-ttu-id="04bf2-171">차단된 제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="04bf2-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="04bf2-172">보호된 폴더 목록 보기 또는 변경</span><span class="sxs-lookup"><span data-stu-id="04bf2-172">View or change the list of protected folders</span></span>

<span data-ttu-id="04bf2-173">Windows 보안 앱을 사용하여 제어된 폴더 액세스로 보호되는 폴더 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="04bf2-174">Windows 10 디바이스에서 Windows 보안 앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="04bf2-175">바이러스 **& 보호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="04bf2-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="04bf2-176">**랜섬웨어 보호에서** **랜섬웨어** 보호 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="04bf2-177">제어된 폴더 액세스가 꺼져 있는 경우 이를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="04bf2-178">보호된 **폴더를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="04bf2-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="04bf2-179">다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="04bf2-180">폴더를 추가하려면 **+ 보호된 폴더 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="04bf2-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="04bf2-181">폴더를 제거하려면 폴더를 선택하고 제거 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="04bf2-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="04bf2-182">[Windows 시스템 폴더는](#windows-system-folders-are-protected-by-default) 기본적으로 보호되어 있으며 목록에서 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04bf2-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="04bf2-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04bf2-183">See also</span></span>

- [<span data-ttu-id="04bf2-184">제어된 폴더 액세스 평가</span><span class="sxs-lookup"><span data-stu-id="04bf2-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="04bf2-185">제어된 폴더 액세스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="04bf2-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="04bf2-186">더 많은 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="04bf2-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
