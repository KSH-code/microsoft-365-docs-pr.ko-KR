---
title: 관리 계측을 사용하여 바이러스 Windows 예약
description: WMI를 사용하여 바이러스 백신 검사 예약
keywords: 빠른 검사, 전체 검사, WMI, 일정, 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879711"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="5efa4-104">WMI(Windows Management Instrumentation)를 사용하여 바이러스 백신 검사 예약</span><span class="sxs-lookup"><span data-stu-id="5efa4-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="5efa4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5efa4-105">**Applies to:**</span></span>

- [<span data-ttu-id="5efa4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5efa4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5efa4-107">이 문서에서는 WMI를 사용하여 예약된 검색을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5efa4-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="5efa4-108">검사 예약 및 검사 유형에 대한 자세한 내용은 [Configure scheduled quick or full Microsoft Defender 바이러스 백신 scan을 참조합니다.](schedule-antivirus-scans.md)</span><span class="sxs-lookup"><span data-stu-id="5efa4-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="5efa4-109">WMI(Windows 관리 명령)를 사용하여 검사 예약</span><span class="sxs-lookup"><span data-stu-id="5efa4-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="5efa4-110">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5efa4-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="5efa4-111">자세한 내용은 [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) API Windows Defender 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5efa4-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="5efa4-112">끝점이 사용되지 않는 경우 검색을 위한 WMI</span><span class="sxs-lookup"><span data-stu-id="5efa4-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="5efa4-113">다음 [속성에 MSFT_MpPreference 클래스의 Set](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5efa4-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="5efa4-114">API 및 허용되는 매개 변수에 대한 자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5efa4-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="5efa4-115">끝점이 사용되지 않는 시간을 위해 검색을 예약하는 경우 검색은 CPU 스로틀 구성을 적용하지 못하며 가능한 한 빨리 검색을 완료하기 위해 사용 가능한 리소스를 최대한 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="5efa4-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="5efa4-116">재구성 완료를 위한 검사 예정용 WMI</span><span class="sxs-lookup"><span data-stu-id="5efa4-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="5efa4-117">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5efa4-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="5efa4-118">자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5efa4-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="5efa4-119">일별 검색을 위한 WMI</span><span class="sxs-lookup"><span data-stu-id="5efa4-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="5efa4-120">다음 [  속성에 MSFT_MpPreference  ](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 클래스의 Set 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5efa4-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="5efa4-121">자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5efa4-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

