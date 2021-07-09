---
title: 데이터 저장 위치 확인 및 데이터 보존 설정 업데이트
description: 데이터 저장소 위치 확인 및 끝점용 Microsoft Defender에 대한 데이터 보존 설정 업데이트
keywords: 데이터, 저장소, 설정, 보존, 업데이트
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
ms.openlocfilehash: eb9e4b905112d3d144b10d68418695df3cda29cb
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339253"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="cc85b-104">데이터 저장소 위치 확인 및 끝점용 Microsoft Defender에 대한 데이터 보존 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="cc85b-104">Verify data storage location and update data retention settings for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cc85b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cc85b-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc85b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cc85b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc85b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc85b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cc85b-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="cc85b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc85b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

<span data-ttu-id="cc85b-110">온보딩 프로세스 중에 마법사가 끝점용 Defender의 데이터 저장 및 보존 설정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-110">During the onboarding process, a wizard takes you through the data storage and retention settings of Defender for Endpoint.</span></span> 

<span data-ttu-id="cc85b-111">온보더링을 완료한 후 데이터 보존 설정 페이지에서 선택을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-111">After completing the onboarding, you can verify your selection in the data retention settings page.</span></span>

## <a name="verify-data-storage-location"></a><span data-ttu-id="cc85b-112">데이터 저장소 위치 확인</span><span class="sxs-lookup"><span data-stu-id="cc85b-112">Verify data storage location</span></span>
<span data-ttu-id="cc85b-113">설정 [단계 중에는](production-deployment.md)데이터를 저장할 위치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-113">During the [Set up phase](production-deployment.md), you would have selected the location to store your data.</span></span> 

<span data-ttu-id="cc85b-114">끝점 데이터 보존으로 이동하여 데이터 **설정**  >    >  **확인할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="cc85b-114">You can verify the data location by navigating to **Settings** > **Endpoints** > **Data retention**.</span></span>

## <a name="update-data-retention-settings"></a><span data-ttu-id="cc85b-115">데이터 보존 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="cc85b-115">Update data retention settings</span></span>

<span data-ttu-id="cc85b-116">데이터 보존 설정을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-116">You can update the data retention settings.</span></span> <span data-ttu-id="cc85b-117">기본적으로 보존 기간은 180일입니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-117">By default, the retention period is 180 days.</span></span> 

1. <span data-ttu-id="cc85b-118">탐색 창에서 **끝점 설정**  >    >  **보존을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cc85b-118">In the navigation pane, select **Settings** > **Endpoints** > **Data retention**.</span></span>

2. <span data-ttu-id="cc85b-119">드롭다운 목록에서 데이터 보존 기간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-119">Select the data retention duration from the drop-down list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc85b-120">다른 설정은 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc85b-120">Other settings are not editable.</span></span>

3. <span data-ttu-id="cc85b-121">기본 **설정 저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cc85b-121">Click **Save preferences**.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cc85b-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cc85b-122">Related topics</span></span>
- [<span data-ttu-id="cc85b-123">데이터 보존 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="cc85b-123">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="cc85b-124">Endpoint용 Defender에서 경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="cc85b-124">Configure alert notifications in Defender for Endpoint</span></span>](configure-email-notifications.md)
- [<span data-ttu-id="cc85b-125">고급 기능 구성</span><span class="sxs-lookup"><span data-stu-id="cc85b-125">Configure advanced features</span></span>](advanced-features.md)
