---
title: 보안 권장 사항에 대한 예외 만들기 및 보기 - 위협 및 취약성 관리
description: 위협 및 취약성 관리에서 보안 권장 사항에 대한 예외를 만들고 모니터링합니다.
keywords: microsoft defender atp tvm 수정, mdatp tvm, 위협 및 취약성 관리, 위협 & 취약성 관리, 위협 & 취약점 관리 수정, tvm 수정 intune, tvm 수정 sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13ac09b1ad918ed945edec6167fd57ea02b616ea
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500192"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="5856d-104">보안 권장 사항에 대한 예외 만들기 및 보기 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="5856d-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5856d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5856d-105">**Applies to:**</span></span>

- [<span data-ttu-id="5856d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5856d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5856d-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="5856d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5856d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5856d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5856d-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5856d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5856d-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="5856d-111">현재 권장 사항이 관련이 없는 경우 수정 요청 대신 권장 사항에 대한 예외를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="5856d-112">조직에 장치 그룹이 있는 경우 예외의 범위를 특정 장치 그룹으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="5856d-113">선택한 장치 그룹 또는 과거 및 현재에 있는 모든 장치 그룹에 대해 예외를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="5856d-114">권장에 대한 예외가 만들어질 경우 예외 기간이 끝날 때까지 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="5856d-115">권장 상태는 전체  예외 또는 부분 **예외(장치** 그룹)로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="5856d-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="5856d-116">Permissions</span></span>

<span data-ttu-id="5856d-117">"예외 처리" 권한이 있는 사용자만 예외(만들기 또는 취소 포함)를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="5856d-118">[RBAC 역할에 대해 자세히 알아보시다.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5856d-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![예외 처리 권한 보기](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="5856d-120">예외 만들기</span><span class="sxs-lookup"><span data-stu-id="5856d-120">Create an exception</span></span>

<span data-ttu-id="5856d-121">예외를 만들 보안 권장을 선택한 다음 예외  옵션을 선택하고 양식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

!["예외 옵션"에 대한 단추가 보안 권장 플라이아웃의 위치인 위치를 보여 줄 수 있습니다.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="5856d-123">장치 그룹에서 예외</span><span class="sxs-lookup"><span data-stu-id="5856d-123">Exception by device group</span></span>

<span data-ttu-id="5856d-124">모든 현재 장치 그룹에 예외를 적용하거나 특정 장치 그룹을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5856d-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="5856d-125">향후 장치 그룹은 예외에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="5856d-126">이미 예외가 있는 장치 그룹은 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="5856d-127">특정 장치 그룹만 선택하면 권장 상태가 "활성"에서 "부분 예외"로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="5856d-128">모든 장치 그룹을 선택하면 상태가 "전체 예외"로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-128">The state will change to “full exception” if you select all the device groups.</span></span>

![장치 그룹 드롭다운 표시](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="5856d-130">필터링된 보기</span><span class="sxs-lookup"><span data-stu-id="5856d-130">Filtered views</span></span>

<span data-ttu-id="5856d-131">위협 및 취약성 관리 페이지에서 장치 그룹으로 필터링한 경우 필터링된 장치 그룹만 옵션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="5856d-132">이 단추는 위협 및 취약성 관리 페이지에서 장치 그룹으로 필터링하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![선택한 장치 그룹 필터 표시](images/tvm-selected-device-groups.png)

<span data-ttu-id="5856d-134">필터링된 장치 그룹을 사용하여 예외 보기:</span><span class="sxs-lookup"><span data-stu-id="5856d-134">Exception view with filtered device groups:</span></span>

![필터링된 장치 그룹 드롭다운 표시](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="5856d-136">많은 수의 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="5856d-136">Large number of device groups</span></span>

<span data-ttu-id="5856d-137">조직에 20개 이상의 장치 그룹이 있는 경우 필터링된 장치 그룹 옵션 옆에 있는 편집을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5856d-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![많은 수의 그룹을 편집하는 방법을 보여 주며](images/tvm-exception-edit-groups.png)

<span data-ttu-id="5856d-139">포함된 장치 그룹을 검색하고 선택할 수 있는 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="5856d-140">검색 아래의 확인 표시 아이콘을 선택하여 모두 확인/선택을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![큰 장치 그룹 플라이아웃 표시](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="5856d-142">전역 예외</span><span class="sxs-lookup"><span data-stu-id="5856d-142">Global exceptions</span></span>

<span data-ttu-id="5856d-143">전역 관리자 권한(Microsoft Defender ATP 관리자)이 있는 경우 전역 예외를 만들고 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-143">If you have global administrator permissions (called Microsoft Defender ATP administrator), you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="5856d-144">이 설정은 조직의 **모든** 현재 및 향후 장치 그룹에 영향을 주며, 유사한 권한이 있는 사용자만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="5856d-145">권장 상태는 "활성"에서 "전체 예외"로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-145">The recommendation state will change from “active” to “full exception.”</span></span>

![전역 예외 옵션 표시](images/tvm-exception-global.png)

<span data-ttu-id="5856d-147">유의해야 할 몇 가지 사항:</span><span class="sxs-lookup"><span data-stu-id="5856d-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="5856d-148">권장 설정이 전역 예외에 해당되는 경우 전역 예외가 만료되거나 취소될 때까지 장치 그룹에 대해 새로 만든 예외가 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="5856d-149">이 시점이 지난 후 만료될 때까지 새 장치 그룹 예외가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="5856d-150">권장에 특정 장치 그룹에 대한 예외가 이미 있는 경우 전역 예외가 생성되면 장치 그룹 예외가 만료되거나 전역 예외가 만료되기 전에 취소될 때까지 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="5856d-151">사리</span><span class="sxs-lookup"><span data-stu-id="5856d-151">Justification</span></span>

<span data-ttu-id="5856d-152">해당 보안 권장을 수정하는 대신 제출해야 하는 예외에 대한 사당을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="5856d-153">사정 컨텍스트를 작성한 다음 예외 기간을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="5856d-154">다음 목록에는 예외 옵션의 사당이 자세히 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="5856d-155">**제3자** 제어 - 제3자 제품 또는 소프트웨어가 이미 이 권장을 해결합니다. 이 정당 유형을 선택하면 노출 점수가 낮아지며 위험이 감소하기 때문에 보안 점수가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="5856d-156">**대체 완화** - 내부 도구는 이미 이 권장을 해결합니다. 이 사정 유형을 선택하면 노출 점수가 낮아지며 위험이 감소하기 때문에 보안 점수가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="5856d-157">**위험 수락** - 낮은 위험에 노출되거나 권장을 구현하는 데 비용이 너무 많이 드는 경우</span><span class="sxs-lookup"><span data-stu-id="5856d-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="5856d-158">**계획된 재구성(유예)** - 이미 계획되어 있지만 실행 또는 권한 부여를 대기하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="5856d-159">모든 예외 보기</span><span class="sxs-lookup"><span data-stu-id="5856d-159">View all exceptions</span></span>

<span data-ttu-id="5856d-160">수정 **페이지의 예외** **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="5856d-161">정당성, 유형 및 상태별로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="5856d-162">자세한 정보가 있는 플라이아웃을 열기 위해 예외를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="5856d-163">장치 그룹당 예외에는 예외가 다루는 모든 장치 그룹 목록이 표시될 수 있습니다. 이 목록은 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="5856d-164">관련 권장 정보를 보거나 예외를 취소할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-164">You can also view the related recommendation or cancel the exception.</span></span>

![수정 페이지의 "예외" 탭 표시](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="5856d-166">예외를 취소하는 방법</span><span class="sxs-lookup"><span data-stu-id="5856d-166">How to cancel an exception</span></span>

<span data-ttu-id="5856d-167">예외를 취소하기 위해 수정 페이지의 **예외** **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="5856d-168">예외를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-168">Select the exception.</span></span>

<span data-ttu-id="5856d-169">모든 장치 그룹 또는 전역 예외에 대한 예외를 취소하려면 모든 장치 그룹에서 예외 취소 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="5856d-170">사용 권한이 있는 장치 그룹에 대한 예외만 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![취소 단추입니다.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="5856d-172">특정 장치 그룹에 대한 예외 취소</span><span class="sxs-lookup"><span data-stu-id="5856d-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="5856d-173">특정 장치 그룹을 선택하여 예외를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="5856d-174">장치 그룹에 대한 플라이아웃이 표시되고 예외 취소 **를 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5856d-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![특정 장치 그룹을 선택하는 방법을 보여 주며,](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="5856d-176">예외가 적용된 후의 영향 보기</span><span class="sxs-lookup"><span data-stu-id="5856d-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="5856d-177">보안 권장 사항 페이지에서  열 사용자 지정을 선택하고 노출된 장치(예외 후) 및 영향(예외 **후)** 확인란을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5856d-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![사용자 지정 열 옵션을 보여 주며,](images/tvm-after-exceptions.png)

<span data-ttu-id="5856d-179">노출된 장치(예외 이후) 열에는 예외가 적용된 후에도 여전히 취약성에 노출된 나머지 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="5856d-180">노출에 영향을 주는 예외 사당성에는 '제3자 제어' 및 '대체 완화'가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="5856d-181">다른 사정은 디바이스의 노출을 줄이지 않는 것이 아니며 여전히 노출된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="5856d-182">예외가 적용된 후의 영향(예외 이후)은 노출 점수 또는 보안 점수에 남은 영향을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="5856d-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="5856d-183">점수에 영향을 주는 예외 사당성에는 '제3자 제어' 및 '대체 완화'가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="5856d-184">다른 사당성은 장치의 노출을 줄이지 않습니다. 따라서 노출 점수와 보안 점수는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5856d-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![표의 열을 보여 주며,](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="5856d-186">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5856d-186">Related topics</span></span>

- [<span data-ttu-id="5856d-187">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="5856d-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5856d-188">취약성 수정</span><span class="sxs-lookup"><span data-stu-id="5856d-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="5856d-189">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="5856d-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="5856d-190">노출 점수</span><span class="sxs-lookup"><span data-stu-id="5856d-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="5856d-191">장치용 Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="5856d-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
