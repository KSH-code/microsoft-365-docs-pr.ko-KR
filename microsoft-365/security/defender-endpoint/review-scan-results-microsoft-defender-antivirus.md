---
title: Microsoft Defender AV 검사 결과 검토
description: Microsoft Endpoint Configuration Manager, Microsoft Intune 또는 Windows 보안 앱을 사용하여 검사 결과 검토
keywords: 검사 결과, 수정, 전체 검사, 빠른 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764148"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="e7ca8-104">Microsoft Defender 바이러스 백신 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="e7ca8-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e7ca8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e7ca8-105">**Applies to:**</span></span>

- <span data-ttu-id="e7ca8-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="e7ca8-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="e7ca8-107">Microsoft Defender 바이러스 백신 검사가 완료되면 [](run-scan-microsoft-defender-antivirus.md) 필요한 검사인지 [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)예약 검사인지에 따라 결과가 기록됩니다. 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="e7ca8-108">Configuration Manager를 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="e7ca8-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="e7ca8-109">Endpoint [Protection 상태를 모니터링하는 방법을 참조합니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="e7ca8-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="e7ca8-110">PowerShell cmdlet을 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="e7ca8-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="e7ca8-111">다음 cmdlet은 끝점에서 각 검색을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="e7ca8-112">동일한 위협이 여러 번 검색된 경우 각 검색 시간을 기준으로 각 검색이 별도로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![PowerShell cmdlet 및 출력 스크린샷](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="e7ca8-114">특정 위협에 대한 검색만 표시하도록 출력을 `-ThreatID` 제한하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="e7ca8-115">위협 검색을 나열하지만 동일한 위협의 검색을 단일 항목으로 결합하려는 경우 다음 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![PowerShell 스크린샷](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="e7ca8-117">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="e7ca8-118">WMI(Windows Management Instruction)를 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="e7ca8-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="e7ca8-119">MSFT_MpThreat 클래스의 [ **Get** **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ca8-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="e7ca8-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e7ca8-120">Related articles</span></span>

- [<span data-ttu-id="e7ca8-121">Microsoft Defender 바이러스 백신 검사 및 수정 사용자 지정, 시작 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="e7ca8-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e7ca8-122">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="e7ca8-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)