---
title: 디바이스 태그 만들기 및 관리
description: 장치 태그를 사용하여 디바이스를 그룹화하여 컨텍스트를 캡처하고 인시던트의 일부로 동적 목록 만들기를 사용하도록 설정
keywords: 태그, 장치 태그, 장치 그룹, 그룹, 수정, 수준, 규칙, aad 그룹, 역할, 할당, 순위
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
ms.technology: mde
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187592"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="8a158-104">디바이스 태그 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="8a158-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a158-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8a158-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a158-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a158-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a158-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a158-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8a158-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8a158-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8a158-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8a158-110">장치에 태그를 추가하여 논리 그룹 소속을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="8a158-111">장치 태그는 네트워크의 적절한 매핑을 지원하여 컨텍스트를 캡처하고 인시던트의 일부로 동적 목록을 만들 수 있도록 서로 다른 태그를 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="8a158-112">태그는 장치 목록 보기에서  필터로 사용할 수도, 디바이스를 그룹화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="8a158-113">장치 그룹화에 대한 자세한 내용은 장치 그룹 만들기 [및 관리를 참조하세요.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8a158-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="8a158-114">다음과 같은 방법으로 디바이스에 태그를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="8a158-115">포털 사용</span><span class="sxs-lookup"><span data-stu-id="8a158-115">Using the portal</span></span>
- <span data-ttu-id="8a158-116">레지스트리 키 값 설정</span><span class="sxs-lookup"><span data-stu-id="8a158-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="8a158-117">디바이스에 태그를 추가하는 시간과 장치 목록 및 디바이스 페이지의 가용성 사이에 몇 가지 대기 시간이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="8a158-118">API를 사용하여 장치 태그를 추가하려면 장치 태그 [API 추가 또는 제거를 참조하세요.](add-or-remove-machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="8a158-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="8a158-119">포털을 사용하여 장치 태그 추가 및 관리</span><span class="sxs-lookup"><span data-stu-id="8a158-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="8a158-120">태그를 관리할 디바이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="8a158-121">다음 보기에서 디바이스를 선택하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="8a158-122">**보안 작업 대시보드** - 활성 경고가 있는 상위 디바이스 섹션에서 장치 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="8a158-123">**경고 큐** - 경고 큐에서 장치 아이콘 옆에 있는 장치 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="8a158-124">**장치 목록** - 장치 목록에서 장치 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="8a158-125">**검색 상자** - 드롭다운 메뉴에서 장치를 선택하고 장치 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="8a158-126">파일 및 IP 보기를 통해 경고 페이지로 이동될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="8a158-127">응답 **작업의** 행에서 태그 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![태그 관리 단추의 이미지](images/manage-tags.png)

3. <span data-ttu-id="8a158-129">태그를 찾거나 만들 입력</span><span class="sxs-lookup"><span data-stu-id="8a158-129">Type to find or create tags</span></span>

    ![device1에 태그를 추가하는 이미지](images/new-tags.png)

<span data-ttu-id="8a158-131">태그는 장치 보기에 추가된 후 장치 목록 보기에도 **반영됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8a158-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="8a158-132">그런 다음 태그 **필터를** 사용하여 관련 장치 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="8a158-133">괄호가 포함된 태그 이름에는 필터링이 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="8a158-134">새 태그를 만들면 기존 태그 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="8a158-135">이 목록에는 포털을 통해 만들어진 태그만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="8a158-136">클라이언트 장치에서 만든 기존 태그는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="8a158-137">이 보기에서 태그를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-137">You can also delete tags from this view.</span></span>

![device2에 태그를 추가하는 이미지](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="8a158-139">레지스트리 키 값을 설정하여 장치 태그 추가</span><span class="sxs-lookup"><span data-stu-id="8a158-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="8a158-140">다음 장치에서만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="8a158-141">Windows 10 버전 1709 이상</span><span class="sxs-lookup"><span data-stu-id="8a158-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="8a158-142">Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="8a158-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="8a158-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8a158-143">Windows Server 2016</span></span>
>- <span data-ttu-id="8a158-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8a158-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="8a158-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="8a158-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="8a158-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8a158-146">Windows 8.1</span></span>
>- <span data-ttu-id="8a158-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="8a158-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="8a158-148">태그에서 설정할 수 있는 최대 문자 수는 200개입니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="8a158-149">태그가 비슷한 디바이스는 특정 장치 목록에 상황에 맞는 작업을 적용해야 하는 경우 편리한 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="8a158-150">디바이스에 태그를 추가하려면 다음 레지스트리 키 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="8a158-151">레지스트리 키: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="8a158-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="8a158-152">레지스트리 키 값(REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="8a158-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="8a158-153">레지스트리 키 데이터: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="8a158-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="8a158-154">장치 태그는 하루 한 번 생성되는 장치 정보 보고서의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="8a158-155">또는 새 장치 정보 보고서를 전송하는 끝점을 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="8a158-156">위의 레지스트리 키를 사용하여 추가된 태그를 제거해야 하는 경우 'Group' 키를 제거하는 대신 레지스트리 키 데이터의 내용을 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a158-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
