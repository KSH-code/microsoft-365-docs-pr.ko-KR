---
title: 배포 그룹에 장치 할당
description: 장치를 배치할 배포 그룹을 지정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985639"
---
# <a name="assign-devices-to-a-deployment-group"></a><span data-ttu-id="cc814-104">배포 그룹에 장치 할당</span><span class="sxs-lookup"><span data-stu-id="cc814-104">Assign devices to a deployment group</span></span>

<span data-ttu-id="cc814-105">Microsoft Managed Desktop 배포 그룹에 장치를 할당하지만 관리 포털을 사용하여 디바이스가 장치에 할당된 그룹을 지정하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-105">Microsoft Managed Desktop will assign devices to the various deployment groups, but you can specify or change group a device is assigned to a device by using the Admin portal.</span></span> <span data-ttu-id="cc814-106">디바이스가 등록된 후 또는 사용자가 등록된 후 할당을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-106">You change the assignment after a device is registered or after a user has enrolled.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc814-107">할당을 변경하면 해당 그룹과 관련한 정책이 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-107">If you change the assignment, policies that are specific to that group will be applied to the device.</span></span> <span data-ttu-id="cc814-108">변경으로 최신 버전의 업데이트가 설치될 Windows 10(모든 새로운 기능 또는 품질 업데이트 포함)가 설치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-108">The change might install the latest version of Windows 10 (including any new feature or quality updates).</span></span> <span data-ttu-id="cc814-109">처음에는 몇 대의 장치만 이동한 다음 결과 사용자 환경을 검사하는 것이 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-109">It's best to move just a few devices at first and then check the resulting user experience.</span></span> <span data-ttu-id="cc814-110">특정 업데이트가 장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-110">Be aware that certain updates will restart the device.</span></span> <span data-ttu-id="cc814-111">할당할 올바른 장치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-111">Double-check that you've selected the right devices to assign.</span></span> <span data-ttu-id="cc814-112">배정이 적용될 때 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-112">It can take up to 24 hours for the assignment to take effect.</span></span>

<span data-ttu-id="cc814-113">배포 그룹에 장치를 할당하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-113">To assign devices to a deployment group, follow these steps.</span></span> <span data-ttu-id="cc814-114">별도의 장치를 다른 그룹으로 이동하려는 경우 각 그룹에 대해 이러한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-114">If you want to move separate devices to different groups, repeat these steps for each group.</span></span>

1. <span data-ttu-id="cc814-115">In Microsoft Endpoint Manager, select **Devices** in the left pane.</span><span class="sxs-lookup"><span data-stu-id="cc814-115">In Microsoft Endpoint Manager, select **Devices** in the left pane.</span></span> <span data-ttu-id="cc814-116">장치 **Microsoft Managed Desktop** 디바이스를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cc814-116">In the **Microsoft Managed Desktop** section, select **Devices**.</span></span>
2. <span data-ttu-id="cc814-117">할당할 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-117">Select the devices you want to assign.</span></span> <span data-ttu-id="cc814-118">선택한 모든 장치가 지정한 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-118">All selected devices will be assigned to the group you specify.</span></span>
3. <span data-ttu-id="cc814-119">메뉴에서 **장치** 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-119">Select **Device actions** from the menu.</span></span>
4. <span data-ttu-id="cc814-120">그룹에 **장치 할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cc814-120">Select **Assign device to group**.</span></span> <span data-ttu-id="cc814-121">플라이 인이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-121">A fly-in opens.</span></span>
5. <span data-ttu-id="cc814-122">드롭다운 메뉴를 사용하여 장치를 이동할 그룹을 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cc814-122">Use the drop-down menu to select the group to move devices to, and then select **Save**.</span></span> <span data-ttu-id="cc814-123">할당한 **그룹이** 보류 **중으로 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="cc814-123">The **Group assigned by** will change to **Pending**.</span></span>

<span data-ttu-id="cc814-124">배정이 완료되면  할당한 그룹이  관리자(변경한 것으로 표시)로 변경되어 그룹 열에 새 그룹 할당이 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="cc814-124">When the assignment is complete, **Group assigned by** will change to **Admin** (indicated that you made the change) and the **Group** column will show the new group assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="cc814-125">장치가 "오류" 또는 "보류 중" 등록 상태인 경우 다른 그룹으로 장치를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-125">You can't move devices to other groups if they're in the "error" or "pending" registration state.</span></span>
>
><span data-ttu-id="cc814-126">장치가 제대로 제거되지 않은 경우 상태가 "준비"로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-126">If a device hasn't been properly removed, it could show a status of "ready."</span></span> <span data-ttu-id="cc814-127">이러한 장치를 이동하면 이동이 완료되지 않는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc814-127">If you move such a device, it's possible that the move won't complete.</span></span> <span data-ttu-id="cc814-128">5단계에서 보류 중으로  변경하여 할당된 그룹이 표시되지 않는 경우 Intune에서 디바이스를 검색하여 사용할 수 있는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="cc814-128">If you don't see **Group assigned by** change to **Pending** in Step 5, check that the device is available by searching for it in Intune.</span></span> <span data-ttu-id="cc814-129">자세한 내용은 [Intune에서 장치 자세히 보기](/mem/intune/remote-actions/device-inventory)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc814-129">For more information, see [See device details in Intune](/mem/intune/remote-actions/device-inventory).</span></span>