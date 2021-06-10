---
title: Microsoft Defender for Endpoint Service에서 장치 오프보딩
description: 끝점 Windows 10 Microsoft Defender의 Windows, 서버, 비영구 장치 온보딩
keywords: 오프보딩, 끝점 오프보딩용 Microsoft Defender, 오프보딩
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934156"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="8f18b-104">Microsoft Defender for Endpoint Service에서 장치 오프보딩</span><span class="sxs-lookup"><span data-stu-id="8f18b-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8f18b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8f18b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f18b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f18b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f18b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f18b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8f18b-108">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="8f18b-108">**Platforms**</span></span>
- <span data-ttu-id="8f18b-109">macOS</span><span class="sxs-lookup"><span data-stu-id="8f18b-109">macOS</span></span>
- <span data-ttu-id="8f18b-110">Linux</span><span class="sxs-lookup"><span data-stu-id="8f18b-110">Linux</span></span>
- <span data-ttu-id="8f18b-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8f18b-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="8f18b-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8f18b-112">Windows Server 2016</span></span>

><span data-ttu-id="8f18b-113">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8f18b-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8f18b-114">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8f18b-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="8f18b-115">기본 배포 방법에 따라 해당 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f18b-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="8f18b-116">장치 상태는 오프보더 후 [7일](fix-unhealthy-sensors.md#inactive-devices) 후에 비활성으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f18b-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="8f18b-117">오프보더된 장치의 데이터(예: 타임라인, 경고, 취약성 등)는 구성된 보존 기간이 만료될 때까지 [포털에](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f18b-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="8f18b-118">디바이스의 프로필(데이터 없이)은 180일 이상 장치 목록에 남아 있습니다. [](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8f18b-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="8f18b-119">또한 지난 30일 동안 활성이 아닌 장치는 조직의 노출 점수와 장치에 대한 Microsoft 보안 [](tvm-exposure-score.md) 점수를 위협 및 취약성 관리 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f18b-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="8f18b-120">활성 장치만 표시하려면 상태, [](machines-view-overview.md#health-state)장치 [](machine-tags.md) 태그 또는 컴퓨터 그룹 을 [필터링할 수 있습니다.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8f18b-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="8f18b-121">장치 Windows 10 오프보드</span><span class="sxs-lookup"><span data-stu-id="8f18b-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="8f18b-122">로컬 스크립트를 사용하여 디바이스 오프보딩</span><span class="sxs-lookup"><span data-stu-id="8f18b-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="8f18b-123">그룹 정책을 사용하여 디바이스 오프보드</span><span class="sxs-lookup"><span data-stu-id="8f18b-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="8f18b-124">모바일 장치 관리 도구를 사용하여 장치 오프보드</span><span class="sxs-lookup"><span data-stu-id="8f18b-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="8f18b-125">오프보드 서버</span><span class="sxs-lookup"><span data-stu-id="8f18b-125">Offboard Servers</span></span>
- [<span data-ttu-id="8f18b-126">오프보드 서버</span><span class="sxs-lookup"><span data-stu-id="8f18b-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="8f18b-127">비보안 Windows 오프보드</span><span class="sxs-lookup"><span data-stu-id="8f18b-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="8f18b-128">비보안 Windows 오프보드</span><span class="sxs-lookup"><span data-stu-id="8f18b-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

