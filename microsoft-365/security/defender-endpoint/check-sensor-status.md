---
title: 끝점용 Microsoft Defender에서 센서의 상태 확인
description: 장치의 센서 상태 확인을 통해 잘못 구성되거나, 비활성 상태인 경우 또는 센서 데이터를 보고하지 않는지 확인할 수 있습니다.
keywords: 센서, 센서 상태, 잘못 구성된, 비활성, 센서 데이터 없음, 센서 데이터, 통신 장애, 통신
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904167"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="0a678-104">끝점에 대한 Microsoft Defender의 센서 상태 확인</span><span class="sxs-lookup"><span data-stu-id="0a678-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a678-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0a678-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a678-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0a678-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a678-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a678-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0a678-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0a678-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0a678-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="0a678-110">센서 **문제가 있는 디바이스 타일은** 보안 작업 대시보드에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="0a678-111">이 타일은 센서 데이터를 제공하고 Endpoint 서비스용 Defender와 통신하는 개별 디바이스의 능력에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="0a678-112">주의가 필요한 장치 수를 보고하고 문제가 있는 장치를 식별하고 알려진 문제를 수정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="0a678-113">타일에는 서비스에 올바르게 보고하지 않는 장치 수에 대한 정보를 제공하는 두 가지 상태 표시기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="0a678-114">**잘못 구성되었습니다.** 이러한 장치는 센서 데이터를 부분적으로 Endpoint용 Defender 서비스에 보고하고 수정해야 하는 구성 오류가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="0a678-115">**비활성** - 지난 달에 7일 이상 Endpoint용 Defender 서비스에 보고를 중지한 장치.</span><span class="sxs-lookup"><span data-stu-id="0a678-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="0a678-116">그룹을 클릭하면 선택에 따라 필터링된 **장치** 목록으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![센서 문제 타일이 있는 장치의 스크린샷](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="0a678-118">장치 **목록에서** 다음 상태를 사용하여 상태 목록을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="0a678-119">**Active** - 끝점용 Defender 서비스에 적극적으로 보고하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="0a678-120">**잘못 구성되었습니다.** 이러한 장치는 센서 데이터를 부분적으로 Endpoint용 Defender 서비스에 보고하지만 수정해야 하는 구성 오류가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="0a678-121">잘못 구성한 장치에는 다음 문제 중 하나 또는 여러 가지가 조합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="0a678-122">**센서 데이터가 없음** - 장치가 센서 데이터 전송을 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="0a678-123">제한된 경고는 장치에서 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="0a678-124">**통신 장애** - 장치와 통신하는 기능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="0a678-125">심층 분석을 위한 파일 보내기, 파일 차단, 네트워크에서 장치와의 장치 차단 및 장치와의 통신이 필요한 기타 작업이 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="0a678-126">**비활성** - 끝점 서비스에 대한 Defender 보고를 중지한 장치.</span><span class="sxs-lookup"><span data-stu-id="0a678-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="0a678-127">내보내기 기능을 사용하여 전체 목록을 CSV 형식으로 다운로드할 **수도** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="0a678-128">필터에 대한 자세한 내용은 장치 목록 [보기 및 구성을 참조하세요.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0a678-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="0a678-129">CSV 형식으로 목록을 내보내 필터되지 않은 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="0a678-130">CSV 파일에는 보기 자체에 적용된 필터링에 관계없이 조직의 모든 장치가 포함되고 조직의 규모에 따라 다운로드하는 데 많은 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![장치 목록 페이지의 스크린샷](images/atp-devices-list-page.png)

<span data-ttu-id="0a678-132">잘못 구성되거나 비활성 장치를 클릭할 때 장치 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a678-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="0a678-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0a678-133">Related topic</span></span>
- [<span data-ttu-id="0a678-134">Endpoint용 Defender에서 불안정한 센서 수정</span><span class="sxs-lookup"><span data-stu-id="0a678-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
