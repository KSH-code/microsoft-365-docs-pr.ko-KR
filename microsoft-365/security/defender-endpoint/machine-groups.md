---
title: 끝점용 Microsoft Defender에서 장치 그룹 만들기 및 관리
description: 그룹에 적용되는 규칙을 준수하여 장치 그룹을 만들고 자동화된 수정 수준을 설정
keywords: 장치 그룹, 그룹, 수정, 수준, 규칙, aad 그룹, 역할, 할당, 순위
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
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860306"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="b8fd4-104">장치 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="b8fd4-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8fd4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b8fd4-105">**Applies to:**</span></span>
- <span data-ttu-id="b8fd4-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8fd4-106">Azure Active Directory</span></span>
- <span data-ttu-id="b8fd4-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="b8fd4-107">Office 365</span></span>

> <span data-ttu-id="b8fd4-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b8fd4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b8fd4-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="b8fd4-110">엔터프라이즈 시나리오에서는 보안 운영 팀에 일반적으로 장치 집합이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="b8fd4-111">이러한 장치는 도메인, 컴퓨터 이름 또는 지정된 태그와 같은 특성 집합에 따라 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="b8fd4-112">끝점용 Microsoft Defender에서 장치 그룹을 만들고 이를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="b8fd4-113">할당된 [RBAC](rbac.md) 역할이 있는 특정 Azure AD 사용자 그룹으로 관련 경고 및 데이터에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="b8fd4-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="b8fd4-114">여러 장치 집합에 대해 다른 자동 수정 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b8fd4-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="b8fd4-115">자동화된 조사 중에 적용할 특정 수정 수준 할당</span><span class="sxs-lookup"><span data-stu-id="b8fd4-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="b8fd4-116">조사에서 그룹 필터를 사용하여 **장치** 목록을 특정 장치 그룹으로 **필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8fd4-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="b8fd4-117">RBAC(역할 기반 액세스)의 컨텍스트에서 장치 그룹을 만들어 특정 작업을 수행하거나 사용자 그룹에 장치 그룹을 할당하여 정보를 볼 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="b8fd4-118">자세한 내용은 역할 기반 액세스 제어를 사용하여 포털 액세스 [관리를 참조하세요.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="b8fd4-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="b8fd4-119">RBAC 응용 프로그램을 포괄적으로 살펴보기 위해 [SOC가 RBAC를 통해 평평하게 실행 중인지 확인을 읽어야 합니다.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="b8fd4-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="b8fd4-120">디바이스 그룹을 만드는 프로세스의 일부로 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="b8fd4-121">이 그룹에 대한 자동화된 수정 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="b8fd4-122">수정 수준에 대한 자세한 내용은 자동화된 조사를 사용하여 위협 조사 및 [수정을 참조하세요.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="b8fd4-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="b8fd4-123">장치 이름, 도메인, 태그 및 OS 플랫폼에 따라 그룹에 속하는 장치 그룹을 결정하는 일치 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="b8fd4-124">장치가 다른 그룹과도 일치하면 가장 높은 순위의 장치 그룹에만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="b8fd4-125">디바이스 그룹에 대한 액세스 권한이 있는 Azure AD 사용자 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="b8fd4-126">장치 그룹을 만든 후 다른 그룹을 상대로 순위를 정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="b8fd4-127">Azure AD 그룹을 할당하지 않은 경우 모든 사용자가 디바이스 그룹에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="b8fd4-128">장치 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="b8fd4-128">Create a device group</span></span>

1. <span data-ttu-id="b8fd4-129">탐색 창에서 설정 장치  >  **그룹 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8fd4-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="b8fd4-130">장치 **그룹 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8fd4-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="b8fd4-131">그룹 이름 및 자동화 설정을 입력하고 그룹에 속하는 장치를 결정하는 일치 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="b8fd4-132">자동화된 [조사가 시작되는 방법을 참조합니다.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="b8fd4-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="b8fd4-133">조직 구성 단위로 장치를 그룹화하려는 경우 그룹 소속에 대한 레지스트리 키를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="b8fd4-134">장치 태그 지정에 대한 자세한 내용은 장치 태그 [만들기 및 관리를 참조하세요.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b8fd4-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="b8fd4-135">이 규칙에 따라 일치하게 될 여러 장치를 미리 본다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="b8fd4-136">규칙에 만족하면 사용자 액세스 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="b8fd4-137">만든 장치 그룹에 액세스할 수 있는 사용자 그룹을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b8fd4-138">RBAC 역할에 할당된 Azure AD 사용자 그룹에만 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="b8fd4-139">**닫기** 를 누르세요.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-139">Click **Close**.</span></span> <span data-ttu-id="b8fd4-140">구성 변경 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="b8fd4-141">장치 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="b8fd4-141">Manage device groups</span></span>

<span data-ttu-id="b8fd4-142">일치하는 동안 우선 순위가 더 높거나 낮게 부여될 수 있도록 장치 그룹의 순위를 승격하거나 강등할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="b8fd4-143">장치가 두 개 이상의 그룹에 일치하면 최고 순위 그룹에만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="b8fd4-144">그룹을 편집하고 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="b8fd4-145">장치 그룹을 삭제하면 전자 메일 알림 규칙에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="b8fd4-146">장치 그룹이 전자 메일 알림 규칙에 따라 구성된 경우 해당 규칙에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="b8fd4-147">장치 그룹이 전자 메일 알림에 대해 구성된 유일한 그룹인 경우 해당 전자 메일 알림 규칙이 장치 그룹과 함께 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="b8fd4-148">기본적으로 디바이스 그룹은 포털 액세스 권한이 있는 모든 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="b8fd4-149">Azure AD 사용자 그룹을 장치 그룹에 할당하여 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="b8fd4-150">그룹과 일치하지 않는 장치는 그룹이 없는 장치(기본값) 그룹에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="b8fd4-151">이 그룹의 순위를 변경하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="b8fd4-152">그러나 이 그룹의 수정 수준을 변경하고 이 그룹에 액세스할 수 있는 Azure AD 사용자 그룹을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="b8fd4-153">장치 그룹 구성에 변경 내용을 적용하는 데 최대 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8fd4-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8fd4-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b8fd4-154">Related topics</span></span>

- [<span data-ttu-id="b8fd4-155">역할 기반 액세스 제어를 사용하여 포털 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="b8fd4-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="b8fd4-156">장치 태그 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="b8fd4-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="b8fd4-157">Graph API를 사용하여 테넌트 장치 그룹 목록 표시</span><span class="sxs-lookup"><span data-stu-id="b8fd4-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
