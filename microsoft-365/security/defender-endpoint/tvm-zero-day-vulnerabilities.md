---
title: 제로 데이 취약성 완화 - 위협 및 취약성 관리
description: 사용자 환경의 제로 데이 취약성을 찾아서 완화하는 방법을 위협 및 취약성 관리.
keywords: Endpoint tvm 제로 데이 취약성, tvm, 위협 & 취약성 관리, 0일, 0일, 0일 취약성 완화, 취약한 CVE
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ec8dd97a563edc487008d028a7cdc9f6ef3d17c1
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689088"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="e65de-104">제로 데이 취약성 완화 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="e65de-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e65de-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e65de-105">**Applies to:**</span></span>

- [<span data-ttu-id="e65de-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e65de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e65de-107">위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="e65de-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e65de-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e65de-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e65de-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e65de-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e65de-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="e65de-111">제로 데이 취약성은 공식 패치 또는 보안 업데이트가 릴리스되지 않은 공개된 취약성입니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="e65de-112">제로 데이 취약성은 심각도 수준이 높고 적극적으로 악용되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="e65de-113">위협 및 취약성 관리 정보가 있는 제로 데이 취약성만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="e65de-114">제로 데이 취약성에 대한 정보 찾기</span><span class="sxs-lookup"><span data-stu-id="e65de-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="e65de-115">제로 데이 취약점이 발견된 후 이 취약점에 대한 정보는 제로 데이의 다음 경험을 통해 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="e65de-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="e65de-116">0일 취약성 기능은 현재 모든 제품에서만 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-116">0-day vulnerability capability is currently available only for Windows products.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="e65de-117">위협 및 취약성 관리 대시보드</span><span class="sxs-lookup"><span data-stu-id="e65de-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="e65de-118">"최상위 보안 권장 사항" 카드에서 제로 데이 태그가 있는 추천을 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![제로 데이 태그가 있는 상위 권장 사항](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="e65de-120">"가장 취약한 소프트웨어" 카드에서 제로 데이 태그가 있는 최상위 소프트웨어를 찾아 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![제로 데이 태그가 있는 가장 취약한 소프트웨어.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="e65de-122">약점 페이지</span><span class="sxs-lookup"><span data-stu-id="e65de-122">Weaknesses page</span></span>

<span data-ttu-id="e65de-123">명명된 제로 데이 취약성에 대한 설명 및 세부 정보를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="e65de-124">이 취약성에 CVE-ID가 할당된 경우 CVE 이름 옆에 제로 데이 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="e65de-125">이 취약성에 할당된 CVE-ID가 없는 경우 내부의 임시 이름 아래에 "TVM-XXXX-XXXX"처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="e65de-126">공식 CVE-ID가 할당된 후 이름이 업데이트되지만 이전 내부 이름은 계속 검색할 수 있으며 사이드 패널에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![약점 페이지의 CVE-2020-17087에 대한 제로 데이 예제입니다.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="e65de-128">소프트웨어 인벤토리 페이지</span><span class="sxs-lookup"><span data-stu-id="e65de-128">Software inventory page</span></span>

<span data-ttu-id="e65de-129">제로 데이 태그가 있는 소프트웨어를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="e65de-130">"제로 데이" 태그로 필터링하여 제로 데이 취약점이 있는 소프트웨어만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![소프트웨어 인벤토리 Windows Server 2016 예제입니다.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="e65de-132">소프트웨어 페이지</span><span class="sxs-lookup"><span data-stu-id="e65de-132">Software page</span></span>

<span data-ttu-id="e65de-133">제로 데이 취약성의 영향을 받은 각 소프트웨어에 대해 제로 데이 태그를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![소프트웨어 페이지의 Windows Server 2016 예입니다.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="e65de-135">보안 권장 사항 페이지</span><span class="sxs-lookup"><span data-stu-id="e65de-135">Security recommendations page</span></span>

<span data-ttu-id="e65de-136">해결 옵션이 있는 경우 해결을 포함하여 수정 및 완화 옵션에 대한 명확한 제안을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="e65de-137">"제로 데이" 태그로 필터링하여 제로 데이 취약성을 해결한 보안 권장 사항만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="e65de-138">제로 데이 취약성 및 추가 취약점이 있는 소프트웨어가 있는 경우 모든 취약성에 대한 하나의 권장을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![보안 권장 사항 Windows Server 2016 예제입니다.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="e65de-140">제로 데이 취약성 해결</span><span class="sxs-lookup"><span data-stu-id="e65de-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="e65de-141">보안 권장 페이지로 이동하여 제로 데이가 있는 권장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="e65de-142">플라이아웃은 제로 데이 및 해당 소프트웨어의 기타 취약성에 대한 정보와 함께 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="e65de-143">완화 옵션 및 해결 옵션(사용 가능한 경우)에 대한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="e65de-144">해결 방법을 사용하면 패치 또는 보안 업데이트를 배포할 수 있을 때까지 이 제로 데이 취약성에 의해 노출되는 위험을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="e65de-145">수정 옵션을 열고 주의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="e65de-146">업데이트가 아직 릴리스되지 않았기 때문에 제로 데이 취약성에 대해 "주의 필요" 수정 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="e65de-147">수행할 특정 작업이 아니기 때문에 기한을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="e65de-148">수정하고자 하는 이 소프트웨어에 대한 이전 취약점이 있는 경우 "주의 필요" 수정 옵션을 다시 적용하고 "업데이트"를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![보안 권장 사항 페이지에서 Windows Server 2016 날 플라이아웃 예제입니다.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="e65de-150">제로 데이 재구성 활동 추적</span><span class="sxs-lookup"><span data-stu-id="e65de-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="e65de-151">재구성 위협 및 취약성 관리 페이지로 [이동하여](tvm-remediation.md) 재구성 활동 항목을 하세요.</span><span class="sxs-lookup"><span data-stu-id="e65de-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="e65de-152">"주의 필요" 수정 옵션을 선택한 경우 모니터링할 수 있는 실제 작업이 아니기 때문에 진행률 표시줄, 티켓 상태 또는 기한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="e65de-153">"소프트웨어 업데이트" 또는 "주의 필요" 같은 수정 유형별로 필터링하여 동일한 범주의 모든 활동 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="e65de-154">제로 데이 취약성 패치</span><span class="sxs-lookup"><span data-stu-id="e65de-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="e65de-155">제로 데이에 대한 패치가 릴리스될 때 권장되는 것은 "업데이트"로 변경하고 옆에 "제로 데이용 새 보안 업데이트"라는 파란색 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="e65de-156">더 이상 제로 데이로 고려하지 않습니다. 제로 데이 태그는 모든 페이지에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65de-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![새 패치 레이블로 "Microsoft Windows 10 업데이트"에 대한 권장입니다.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="e65de-158">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e65de-158">Related articles</span></span>

- [<span data-ttu-id="e65de-159">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="e65de-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e65de-160">Dashboard</span><span class="sxs-lookup"><span data-stu-id="e65de-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e65de-161">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="e65de-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e65de-162">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="e65de-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="e65de-163">내 조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="e65de-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
