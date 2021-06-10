---
title: Microsoft Defender AV 검사 결과 검토
description: Microsoft Endpoint Configuration Manager, Microsoft Intune 또는 앱 앱을 사용하여 검사 Windows 보안 검토
keywords: 검사 결과, 수정, 전체 검사, 빠른 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ec3dd2edc09d504af0ed76b17577130b1cdce1b7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275375"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="11c1a-104">검사 Microsoft Defender 바이러스 백신 검토</span><span class="sxs-lookup"><span data-stu-id="11c1a-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="11c1a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="11c1a-105">**Applies to:**</span></span>

- [<span data-ttu-id="11c1a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="11c1a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="11c1a-107">검사가 Microsoft Defender 바이러스 백신 검사가 완료되면 결과가 기록되어 [](run-scan-microsoft-defender-antivirus.md) 결과를 볼 [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c1a-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="11c1a-108">Configuration Manager를 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="11c1a-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="11c1a-109">상태 [를 모니터링하는 Endpoint Protection 참조합니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="11c1a-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="11c1a-110">PowerShell cmdlet을 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="11c1a-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="11c1a-111">다음 cmdlet은 끝점에서 각 검색을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11c1a-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="11c1a-112">동일한 위협이 여러 번 검색된 경우 각 검색 시간을 기준으로 각 검색이 별도로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="11c1a-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![PowerShell cmdlet 및 출력 스크린샷](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="11c1a-114">특정 위협에 대한 검색만 표시하도록 출력을 `-ThreatID` 제한하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c1a-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="11c1a-115">위협 검색을 나열하지만 동일한 위협의 검색을 단일 항목으로 결합하려는 경우 다음 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c1a-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![PowerShell 스크린샷](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="11c1a-117">PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender/) 구성하고 실행을 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="11c1a-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="11c1a-118">WMI(Windows 관리 지침)를 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="11c1a-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="11c1a-119">MSFT_MpThreat 클래스의 [ **Get** **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11c1a-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="11c1a-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="11c1a-120">Related articles</span></span>

- [<span data-ttu-id="11c1a-121">사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토</span><span class="sxs-lookup"><span data-stu-id="11c1a-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="11c1a-122">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="11c1a-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)