---
title: Microsoft Defender ATP 서비스에서 장치 오프보딩
description: Microsoft Defender ATP 서비스에서 Windows 10 장치, 서버, 비 Windows 장치 온보딩
keywords: 오프보딩, 끝점 오프보딩용 Microsoft Defender, Windows atp 오프보딩
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a95ff5214ea9f696622ea184ece1c5aa9fb3db2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186968"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="c9268-104">Microsoft Defender for Endpoint Service에서 장치 오프보딩</span><span class="sxs-lookup"><span data-stu-id="c9268-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c9268-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c9268-105">**Applies to:**</span></span>
- [<span data-ttu-id="c9268-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c9268-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c9268-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9268-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c9268-108">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="c9268-108">**Platforms**</span></span>
- <span data-ttu-id="c9268-109">macOS</span><span class="sxs-lookup"><span data-stu-id="c9268-109">macOS</span></span>
- <span data-ttu-id="c9268-110">Linux</span><span class="sxs-lookup"><span data-stu-id="c9268-110">Linux</span></span>
- <span data-ttu-id="c9268-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c9268-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="c9268-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c9268-112">Windows Server 2016</span></span>

><span data-ttu-id="c9268-113">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c9268-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c9268-114">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c9268-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="c9268-115">기본 배포 방법에 따라 해당 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9268-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="c9268-116">장치 상태는 오프보더 후 [7일](fix-unhealthy-sensors.md#inactive-devices) 후에 비활성으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9268-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="c9268-117">오프보더된 장치의 데이터(예: 타임라인, 경고, 취약성 등)는 구성된 보존 기간이 만료될 때까지 [포털에](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9268-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="c9268-118">디바이스의 프로필(데이터 없이)은 180일 이상 장치 목록에 남아 있습니다. [](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c9268-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="c9268-119">또한 지난 30일 동안 활성이 아닌 장치는 조직의 위협 및 취약성 관리 노출 점수와 장치용 Microsoft 보안 점수를 반영하는 데이터에 반영되지 않습니다. [](tvm-exposure-score.md)</span><span class="sxs-lookup"><span data-stu-id="c9268-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="c9268-120">활성 장치만 표시하려면 상태, [](machines-view-overview.md#health-state)장치 [](machine-tags.md) 태그 또는 컴퓨터 그룹 을 [필터링할 수 있습니다.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="c9268-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="c9268-121">Windows 10 장치 오프보드</span><span class="sxs-lookup"><span data-stu-id="c9268-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="c9268-122">로컬 스크립트를 사용하여 디바이스 오프보딩</span><span class="sxs-lookup"><span data-stu-id="c9268-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="c9268-123">그룹 정책을 사용하여 디바이스 오프보드</span><span class="sxs-lookup"><span data-stu-id="c9268-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="c9268-124">모바일 장치 관리 도구를 사용하여 장치 오프보드</span><span class="sxs-lookup"><span data-stu-id="c9268-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="c9268-125">오프보드 서버</span><span class="sxs-lookup"><span data-stu-id="c9268-125">Offboard Servers</span></span>
- [<span data-ttu-id="c9268-126">오프보드 서버</span><span class="sxs-lookup"><span data-stu-id="c9268-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="c9268-127">비 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c9268-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="c9268-128">비 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c9268-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

