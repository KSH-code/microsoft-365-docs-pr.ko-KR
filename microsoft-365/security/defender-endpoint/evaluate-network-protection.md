---
title: 네트워크 보호 평가
description: 보호하는 일반적인 시나리오를 테스트하여 네트워크 보호가 작동하는 방법을 확인합니다.
keywords: 네트워크 보호, 악용, 악성 웹 사이트, ip, 도메인, 평가, 테스트, 데모
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ade50e85dbfcf5f59921a65d5b97bb47d21e5b12
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570927"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="04ac3-104">네트워크 보호 평가</span><span class="sxs-lookup"><span data-stu-id="04ac3-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04ac3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="04ac3-105">**Applies to:**</span></span>
- <span data-ttu-id="04ac3-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="04ac3-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>
- - [<span data-ttu-id="04ac3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04ac3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="04ac3-108">[네트워크 보호는](network-protection.md) 직원이 응용 프로그램을 사용하여 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인에 액세스하는 것을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="04ac3-109">이 문서는 기능을 사용하도록 설정하고 테스트 사이트로 안내하여 네트워크 보호를 평가하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="04ac3-110">이 평가 문서의 사이트는 악의적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="04ac3-111">악의적인 것으로 하여 특별히 만들어진 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="04ac3-112">사이트는 사용자가 악성 사이트 또는 도메인을 방문한 경우 실행되는 동작을 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="04ac3-113">Microsoft Defender Testground 웹 사이트를 방문하여 다른 보호 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방법을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="04ac3-114">감사 모드에서 네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="04ac3-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="04ac3-115">감사 모드에서 네트워크 보호를 사용하도록 설정하여 차단된 IP 주소 및 도메인을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="04ac3-116">이 앱이 업무 앱에 영향을 주지 않는지 확인하거나 차단이 발생하는 자주에 대해 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="04ac3-117">시작 **메뉴에 powershell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="04ac3-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="04ac3-118">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="04ac3-119">(가짜) 악성 도메인 방문</span><span class="sxs-lookup"><span data-stu-id="04ac3-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="04ac3-120">선택한 Internet Explorer, Google Chrome 또는 기타 브라우저를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="04ac3-121">[https://smartscreentestratings2.net](https://smartscreentestratings2.net)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="04ac3-122">네트워크 연결이 허용되고 테스트 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-122">The network connection will be allowed and a test message will be displayed.</span></span>

![연결 차단을 표시하는 알림 예: IT 관리자가 Windows Security에서 이 네트워크 연결을 차단했습니다.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="04ac3-125">Windows 이벤트 뷰어에서 네트워크 보호 이벤트 검토</span><span class="sxs-lookup"><span data-stu-id="04ac3-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="04ac3-126">차단된 앱을 검토하려면 Microsoft-Windows-Windows-Defender/Operational 로그에서 이벤트 뷰어를 열고 이벤트 ID 1125를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="04ac3-127">다음 표에는 모든 네트워크 보호 이벤트가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ac3-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="04ac3-128">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="04ac3-128">Event ID</span></span> | <span data-ttu-id="04ac3-129">제공/원본</span><span class="sxs-lookup"><span data-stu-id="04ac3-129">Provide/Source</span></span> | <span data-ttu-id="04ac3-130">설명</span><span class="sxs-lookup"><span data-stu-id="04ac3-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="04ac3-131">5007</span><span class="sxs-lookup"><span data-stu-id="04ac3-131">5007</span></span> | <span data-ttu-id="04ac3-132">Windows Defender(작동)</span><span class="sxs-lookup"><span data-stu-id="04ac3-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="04ac3-133">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="04ac3-133">Event when settings are changed</span></span> |
|<span data-ttu-id="04ac3-134">1125</span><span class="sxs-lookup"><span data-stu-id="04ac3-134">1125</span></span> | <span data-ttu-id="04ac3-135">Windows Defender(작동)</span><span class="sxs-lookup"><span data-stu-id="04ac3-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="04ac3-136">네트워크 연결이 감사된 경우 이벤트</span><span class="sxs-lookup"><span data-stu-id="04ac3-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="04ac3-137">1126</span><span class="sxs-lookup"><span data-stu-id="04ac3-137">1126</span></span> | <span data-ttu-id="04ac3-138">Windows Defender(작동)</span><span class="sxs-lookup"><span data-stu-id="04ac3-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="04ac3-139">네트워크 연결이 차단된 경우 이벤트</span><span class="sxs-lookup"><span data-stu-id="04ac3-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="04ac3-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04ac3-140">See also</span></span>

* [<span data-ttu-id="04ac3-141">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="04ac3-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="04ac3-142">네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="04ac3-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="04ac3-143">네트워크 보호 문제 해결</span><span class="sxs-lookup"><span data-stu-id="04ac3-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
