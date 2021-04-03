---
title: 지원 종료 소프트웨어 및 소프트웨어 버전 계획
description: 더 이상 지원되지 않는 소프트웨어 및 소프트웨어 버전을 검색하고 계획하여 보안 업데이트를 받을 수 없습니다.
keywords: 위협 및 취약성 관리, mdatp tvm 보안 권장, 사이버 보안 권장, 실행 가능한 보안 권장
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
ms.openlocfilehash: 29adf8a542d97a981a07dac167343f3774aa5af4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500149"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="3eed4-104">위협 및 취약성 관리를 사용하여 지원 종료 소프트웨어 및 소프트웨어 버전 계획</span><span class="sxs-lookup"><span data-stu-id="3eed4-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3eed4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3eed4-105">**Applies to:**</span></span>

- [<span data-ttu-id="3eed4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3eed4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3eed4-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="3eed4-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3eed4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3eed4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3eed4-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3eed4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3eed4-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="3eed4-111">소프트웨어 또는 소프트웨어 버전에 대한 EOS(서비스 종료)(EOS)는 더 이상 지원되거나 서비스되지 않고 보안 업데이트를 수신하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="3eed4-112">지원이 종료된 소프트웨어 또는 소프트웨어 버전을 사용하는 경우 조직이 보안 취약성, 법률 및 재무 위험에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="3eed4-113">보안 및 IT 관리자가 함께 작업하고 최적의 결과, 규정 준수 및 건전한 네트워크 에코시스템을 위해 조직의 소프트웨어 인벤토리를 구성하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="3eed4-114">지원 종료에 도달한 앱을 제거하거나 교체하고 더 이상 지원되지 않는 버전을 업데이트하는 옵션을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="3eed4-115">지원 날짜가 끝나기 전에  계획을 만들고 구현하는 것이 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="3eed4-116">더 이상 지원되지 않는 소프트웨어 또는 소프트웨어 버전 찾기</span><span class="sxs-lookup"><span data-stu-id="3eed4-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="3eed4-117">위협 및 취약성 관리 메뉴에서 보안 권장 [**사항으로 이동합니다.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="3eed4-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="3eed4-118">필터 **패널로** 이동하여 태그 섹션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="3eed4-119">EOS 태그 옵션 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="3eed4-120">그런 다음 **을 적용합니다.**</span><span class="sxs-lookup"><span data-stu-id="3eed4-120">Then **Apply**.</span></span>

    ![Screenshot tags that say EOS software, EOS versions, and Upcoming EOS versions.](images/tvm-eos-tag.png)

3. <span data-ttu-id="3eed4-122">지원이 종료된 소프트웨어, 지원 종료된 소프트웨어 버전 또는 예정된 지원 종료 버전과 관련된 권장 사항 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="3eed4-123">이러한 태그는 소프트웨어 인벤토리 [페이지에도 표시됩니다.](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="3eed4-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![EOS 태그가 있는 권장 사항.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="3eed4-125">버전 및 날짜 목록</span><span class="sxs-lookup"><span data-stu-id="3eed4-125">List of versions and dates</span></span>

<span data-ttu-id="3eed4-126">지원이 종료되거나 곧 지원이 종료되거나 지원이 종료된 버전 목록을 확인한 후 해당 날짜는 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3eed4-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="3eed4-127">지원이 종료된 버전이 있는 소프트웨어에 대한 보안 권장 플라이아웃에 메시지가 표시되거나 곧 지원이 종료될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![버전 배포 링크 스크린샷.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="3eed4-129">소프트웨어 **드릴다운** 페이지로 이동하려면 버전 배포 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="3eed4-130">지원 종료 또는 예정된 지원 종료로 식별되는 태그가 있는 필터링된 버전 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![지원 소프트웨어가 종료된 소프트웨어 드릴다운 페이지의 스크린샷.](images/software-drilldown-eos.png)

3. <span data-ttu-id="3eed4-132">열 표에서 버전 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="3eed4-133">예: 버전 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="3eed4-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="3eed4-134">지원 종료 날짜와 함께 플라이아웃이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-134">A flyout will appear with the end of support date.</span></span>

    ![지원 종료 날짜 스크린샷.](images/version-eos-date.png)

<span data-ttu-id="3eed4-136">지원 종료 상태로 인해 취약한 소프트웨어 및 소프트웨어 버전을 확인한 후 조직에서 해당 버전을 업데이트하거나 제거할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="3eed4-137">이렇게 하면 조직이 취약성 및 고급 영구 위협에 노출되는 것을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eed4-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3eed4-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3eed4-138">Related topics</span></span>

- [<span data-ttu-id="3eed4-139">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="3eed4-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3eed4-140">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="3eed4-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="3eed4-141">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="3eed4-141">Software inventory</span></span>](tvm-software-inventory.md)
