---
title: 제로 데이 취약성 완화 - 위협 및 취약성 관리
description: 위협 및 취약성 관리를 통해 환경에서 제로 데이 취약성을 찾아 완화하는 방법을 학습합니다.
keywords: mdatp tvm 제로 데이 취약성, tvm, 위협 & 취약성 관리, 제로 데이, 0일, 0일 취약성 완화, 취약한 CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b2092f24e4ee3e35918fbdc54b68570ef29fd08e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076447"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="563e7-104">제로 데이 취약성 완화 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="563e7-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="563e7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="563e7-105">**Applies to:**</span></span>

- [<span data-ttu-id="563e7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="563e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="563e7-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="563e7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="563e7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="563e7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="563e7-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="563e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="563e7-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="563e7-111">제로 데이 취약성은 공식 패치 또는 보안 업데이트가 릴리스되지 않은 공개된 취약성입니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="563e7-112">제로 데이 취약성은 심각도 수준이 높고 적극적으로 악용되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="563e7-113">위협 및 취약성 관리는 제로 데이 취약성 정보만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="563e7-114">제로 데이 취약성에 대한 정보 찾기</span><span class="sxs-lookup"><span data-stu-id="563e7-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="563e7-115">제로 데이 취약점이 발견된 후 Microsoft Defender 보안 센터의 다음 환경을 통해 해당 정보에 대한 정보가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="563e7-116">위협 및 취약성 관리 대시보드</span><span class="sxs-lookup"><span data-stu-id="563e7-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="563e7-117">"최상위 보안 권장 사항" 카드에서 제로 데이 태그가 있는 추천을 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![제로 데이 태그가 있는 상위 권장 사항](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="563e7-119">"가장 취약한 소프트웨어" 카드에서 제로 데이 태그가 있는 최상위 소프트웨어를 찾아 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![제로 데이 태그가 있는 가장 취약한 소프트웨어.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="563e7-121">약점 페이지</span><span class="sxs-lookup"><span data-stu-id="563e7-121">Weaknesses page</span></span>

<span data-ttu-id="563e7-122">명명된 제로 데이 취약성에 대한 설명 및 세부 정보를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="563e7-123">이 취약성에 CVE-ID가 할당된 경우 CVE 이름 옆에 제로 데이 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="563e7-124">이 취약성에 할당된 CVE-ID가 없는 경우 내부의 임시 이름 아래에 "TVM-XXXX-XXXX"처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="563e7-125">공식 CVE-ID가 할당된 후 이름이 업데이트되지만 이전 내부 이름은 계속 검색할 수 있으며 사이드 패널에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![약점 페이지의 CVE-2020-17087에 대한 제로 데이 예제입니다.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="563e7-127">소프트웨어 인벤토리 페이지</span><span class="sxs-lookup"><span data-stu-id="563e7-127">Software inventory page</span></span>

<span data-ttu-id="563e7-128">제로 데이 태그가 있는 소프트웨어를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="563e7-129">"제로 데이" 태그로 필터링하여 제로 데이 취약점이 있는 소프트웨어만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![소프트웨어 인벤토리 페이지의 Windows Server 2016 제로 데이 예제입니다.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="563e7-131">소프트웨어 페이지</span><span class="sxs-lookup"><span data-stu-id="563e7-131">Software page</span></span>

<span data-ttu-id="563e7-132">제로 데이 취약성의 영향을 받은 각 소프트웨어에 대해 제로 데이 태그를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Windows Server 2016 소프트웨어 페이지의 제로 데이 예제입니다.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="563e7-134">보안 권장 사항 페이지</span><span class="sxs-lookup"><span data-stu-id="563e7-134">Security recommendations page</span></span>

<span data-ttu-id="563e7-135">해결 옵션이 있는 경우 해결을 포함하여 수정 및 완화 옵션에 대한 명확한 제안을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="563e7-136">"제로 데이" 태그로 필터링하여 제로 데이 취약성을 해결한 보안 권장 사항만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="563e7-137">제로 데이 취약성 및 추가 취약점이 있는 소프트웨어가 있는 경우 모든 취약성에 대한 하나의 권장을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![보안 권장 사항 페이지의 Windows Server 2016 제로 데이 예제입니다.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="563e7-139">제로 데이 취약성 해결</span><span class="sxs-lookup"><span data-stu-id="563e7-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="563e7-140">보안 권장 페이지로 이동하여 제로 데이가 있는 권장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="563e7-141">플라이아웃은 제로 데이 및 해당 소프트웨어의 기타 취약성에 대한 정보와 함께 열립니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="563e7-142">완화 옵션 및 해결 옵션(사용 가능한 경우)에 대한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="563e7-143">해결 방법을 사용하면 패치 또는 보안 업데이트를 배포할 수 있을 때까지 이 제로 데이 취약성에 의해 노출되는 위험을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="563e7-144">수정 옵션을 열고 주의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="563e7-145">업데이트가 아직 릴리스되지 않았기 때문에 제로 데이 취약성에 대해 "주의 필요" 수정 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="563e7-146">수행할 특정 작업이 아니기 때문에 기한을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="563e7-147">수정하고자 하는 이 소프트웨어에 대한 이전 취약점이 있는 경우 "주의 필요" 수정 옵션을 다시 적용하고 "업데이트"를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![보안 권장 사항 페이지에서 Windows Server 2016의 제로 데이 플라이아웃 예](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="563e7-149">제로 데이 재구성 활동 추적</span><span class="sxs-lookup"><span data-stu-id="563e7-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="563e7-150">위협 및 취약성 관리 [](tvm-remediation.md) 수정 페이지로 이동하여 수정 활동 항목을 하세요.</span><span class="sxs-lookup"><span data-stu-id="563e7-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="563e7-151">"주의 필요" 수정 옵션을 선택한 경우 모니터링할 수 있는 실제 작업이 아니기 때문에 진행률 표시줄, 티켓 상태 또는 기한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="563e7-152">"소프트웨어 업데이트" 또는 "주의 필요" 같은 수정 유형별로 필터링하여 동일한 범주의 모든 활동 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="563e7-153">제로 데이 취약성 패치</span><span class="sxs-lookup"><span data-stu-id="563e7-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="563e7-154">제로 데이에 대한 패치가 릴리스될 때 권장되는 것은 "업데이트"로 변경하고 옆에 "제로 데이용 새 보안 업데이트"라는 파란색 레이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="563e7-155">더 이상 제로 데이로 고려하지 않습니다. 제로 데이 태그는 모든 페이지에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="563e7-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![새 패치 레이블로 "Microsoft Windows 10 업데이트"에 대한 권장입니다.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="563e7-157">관련 문서</span><span class="sxs-lookup"><span data-stu-id="563e7-157">Related articles</span></span>

- [<span data-ttu-id="563e7-158">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="563e7-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="563e7-159">Dashboard</span><span class="sxs-lookup"><span data-stu-id="563e7-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="563e7-160">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="563e7-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="563e7-161">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="563e7-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="563e7-162">내 조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="563e7-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
