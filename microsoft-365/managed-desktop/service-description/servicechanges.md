---
title: 서비스 변경 및 커뮤니케이션
description: 서비스에 대한 변경이 발생하고 전달되는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20af244d14f8f29e0175fb5e8efdabff94ff9a2b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244107"
---
# <a name="service-changes-and-communication"></a><span data-ttu-id="8a643-104">서비스 변경 및 커뮤니케이션</span><span class="sxs-lookup"><span data-stu-id="8a643-104">Service changes and communication</span></span>

<span data-ttu-id="8a643-105">경우에 따라 Microsoft에서 작업 방식에 대한 세부 정보를 변경해야 Microsoft Managed Desktop 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-105">Sometimes, Microsoft might need to change details about the way Microsoft Managed Desktop works.</span></span> <span data-ttu-id="8a643-106">마찬가지로 서비스에도 영향을 주는 변경을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-106">Similarly, you might need to make changes that would affect the service as well.</span></span> <span data-ttu-id="8a643-107">이러한 변경은 해당 변경의 중요도에 따라 다르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-107">We handle such changes differently depending on how significant they are.</span></span> <span data-ttu-id="8a643-108">이 항목에서는 주요 사항을 고려하는 변경 내용을 정의하고 변경 내용을 처리하는 방법과 다른 변경 내용을 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-108">This topic defines the changes we consider major, and explains how we handle them versus other changes.</span></span>



## <a name="changes-made-by-microsoft"></a><span data-ttu-id="8a643-109">Microsoft에서 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="8a643-109">Changes made by Microsoft</span></span>

<span data-ttu-id="8a643-110">조치가 필요한 주요 변경에 대해 최소 30일 전에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-110">We'll give you notice at least 30 days ahead of time for any major change that requires action.</span></span> <span data-ttu-id="8a643-111">관리자 포털 메시징 시스템을 사용하여 Microsoft Managed Desktop 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-111">We’ll let you know by using the Microsoft Managed Desktop Admin portal messaging system.</span></span>

<span data-ttu-id="8a643-112">**주요 변경** 사항은 이러한 영역에 영향을 줄 수 있는 변경 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-112">**Major changes** are those that might impact any of these areas:</span></span>
- <span data-ttu-id="8a643-113">일상적인 생산성에 영향을 주는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="8a643-113">Changes affecting daily productivity</span></span>
- <span data-ttu-id="8a643-114">사용자 지정된 기능 및 응용 프로그램 변경 사항</span><span class="sxs-lookup"><span data-stu-id="8a643-114">Changes to customized features and applications</span></span>
- <span data-ttu-id="8a643-115">표시되는 용량 증가 또는 감소</span><span class="sxs-lookup"><span data-stu-id="8a643-115">Increase or decrease of visible capacity</span></span>
- <span data-ttu-id="8a643-116">기술 지원 데스크 프로세스 및 참조 자료 또는 URL의 사용자 혼동 또는 변경을 유발할 수 있는 제품 브랜싱 변경</span><span class="sxs-lookup"><span data-stu-id="8a643-116">Changes in product branding that might cause user confusion or change in helpdesk processes and reference material or URLs</span></span>
- <span data-ttu-id="8a643-117">일상적인 작업에 대해 서비스에서 요구하는 권한 이상을 요구하는 변경 내용(문제를 방지하거나 수정하는 작업 제외)</span><span class="sxs-lookup"><span data-stu-id="8a643-117">Changes requiring permissions beyond those required by the service for daily operations, excluding actions that prevent or fix issues</span></span>
- <span data-ttu-id="8a643-118">데이터가 저장되는 위치에 대한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="8a643-118">Changes to where your data is stored</span></span>
- <span data-ttu-id="8a643-119">서비스 범위에 새 구성 요소 서비스 또는 응용 프로그램 추가</span><span class="sxs-lookup"><span data-stu-id="8a643-119">Adding a new component service or application to the scope of the service</span></span>
- <span data-ttu-id="8a643-120">서비스 범위에서 구성 요소 서비스 또는 응용 프로그램 제거</span><span class="sxs-lookup"><span data-stu-id="8a643-120">Removal of a component service or application from the scope of the service</span></span>
- <span data-ttu-id="8a643-121">서비스에 새 기능 추가</span><span class="sxs-lookup"><span data-stu-id="8a643-121">Adding new feature to the service</span></span>

> [!NOTE]
> <span data-ttu-id="8a643-122">30일 알림 정책에서 제외되는 인시던트 또는 보안 문제를 완화하기 위해 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-122">We might have to make changes to mitigate incidents or security issues that would be excluded from the 30-day notification policy.</span></span>

<span data-ttu-id="8a643-123">사용자 환경, 보안, 안정성 및 보고를 개선하기 위해 서비스를 정기적으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-123">We’ll routinely make other changes to the service to improve user experience, security, reliability, and reporting.</span></span> <span data-ttu-id="8a643-124">이러한 변경의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-124">Some examples of these changes include:</span></span>

- <span data-ttu-id="8a643-125">Windows 및 Office 설치</span><span class="sxs-lookup"><span data-stu-id="8a643-125">Installation of Windows and Office updates</span></span>
- <span data-ttu-id="8a643-126">장치에 적용된 보안 기준 업데이트</span><span class="sxs-lookup"><span data-stu-id="8a643-126">Updates to the security baseline applied to devices</span></span>
- <span data-ttu-id="8a643-127">지원되는 장치.</span><span class="sxs-lookup"><span data-stu-id="8a643-127">Supported devices.</span></span> <span data-ttu-id="8a643-128">추천 장치를 표시하기 위해 비즈니스 Microsoft Managed Desktop 사이트에서 Windows 10 Pro [필터링합니다.](https://www.microsoft.com/windowsforbusiness/view-all-devices)</span><span class="sxs-lookup"><span data-stu-id="8a643-128">To see recommended devices, filter for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span>

<span data-ttu-id="8a643-129">설정한 채널을 사용하여 이러한 변경 내용을 전달할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-129">We'll communicate these changes by using established channels.</span></span> <span data-ttu-id="8a643-130">변경 내용에 대한 질문이 있으면 Microsoft Managed Desktop [팀에 문의하세요.](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="8a643-130">If you have any questions about any changes, contact the Microsoft Managed Desktop [Operations team](../working-with-managed-desktop/admin-support.md).</span></span> <span data-ttu-id="8a643-131">서비스에 대한 변경 내용도 변경 기록 에 필요한 경우 [문서화됩니다.](../change-history-managed-desktop.md)</span><span class="sxs-lookup"><span data-stu-id="8a643-131">Changes to the service are also documented as needed in the [change history](../change-history-managed-desktop.md).</span></span>

<span data-ttu-id="8a643-132">Microsoft Managed Desktop 및 커뮤니케이션은 다음 두 가지 Microsoft 정책에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-132">Microsoft Managed Desktop changes and communications are governed by two Microsoft policies:</span></span>
- [<span data-ttu-id="8a643-133">최신 수명 주기 정책</span><span class="sxs-lookup"><span data-stu-id="8a643-133">Modern Lifecycle Policy</span></span>](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [<span data-ttu-id="8a643-134">Microsoft 365 통신 정책 변경</span><span class="sxs-lookup"><span data-stu-id="8a643-134">Microsoft 365 Change Communication Policy</span></span>](/office365/admin/manage/message-center)

## <a name="changes-you-make"></a><span data-ttu-id="8a643-135">변경한 내용</span><span class="sxs-lookup"><span data-stu-id="8a643-135">Changes you make</span></span>

<span data-ttu-id="8a643-136">환경에서 일부 변경 내용은 변경 내용에 영향을 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8a643-136">Some changes that you might make in your environment could impact Microsoft Managed Desktop.</span></span> <span data-ttu-id="8a643-137">이러한 주요 변경 내용의 경우 Microsoft Managed Desktop 관리 포털에서 서비스 요청을 제출하여 30일 이상의 공지를 Microsoft Managed Desktop 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-137">For these major changes, we ask that you give us at least 30 days’ notice by submitting a service request in the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="8a643-138">자세한 [내용은 관리자 지원 Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a643-138">See [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md) for instructions.</span></span> <span data-ttu-id="8a643-139">이를 통해 중단을 방지하기 위해 변경을 계획하고 준비할 수 있는 적절한 시간을 마련할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-139">This allows us adequate time to plan and prepare for the change to avoid disruptions.</span></span>

<span data-ttu-id="8a643-140">주요 변경 사항은 이러한 영역에 영향을 줄 수 있는 변경 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-140">Major changes are those that might impact any of these areas:</span></span>

- <span data-ttu-id="8a643-141">ID 시스템 및 그룹</span><span class="sxs-lookup"><span data-stu-id="8a643-141">Identity systems and groups</span></span>
- <span data-ttu-id="8a643-142">방화벽, 프록시 또는 캐싱, VPN 시스템 등의 네트워킹 및 네트워크 제어</span><span class="sxs-lookup"><span data-stu-id="8a643-142">Networking and network controls such as firewalls, proxy or caching, and VPN systems</span></span>
- <span data-ttu-id="8a643-143">클라우드 서비스 구성에 액세스하기 위한 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8a643-143">Controls for accessing cloud services configurations</span></span>
- <span data-ttu-id="8a643-144">네트워크 서비스의 ID 또는 보안에 사용되는 사용자 또는 장치 인증서</span><span class="sxs-lookup"><span data-stu-id="8a643-144">User or device certificates used for identity or securing of network services</span></span>
- <span data-ttu-id="8a643-145">서비스와 상호 작용하는 관리 시스템</span><span class="sxs-lookup"><span data-stu-id="8a643-145">Management systems that interact with the service</span></span>
- <span data-ttu-id="8a643-146">서비스와 상호 작용하는 보안 시스템 또는 에이전트</span><span class="sxs-lookup"><span data-stu-id="8a643-146">Security systems or agents that interact with the service</span></span>
- <span data-ttu-id="8a643-147">서비스와 연결되거나 Microsoft 365 클라우드 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="8a643-147">Configuration of any of the Microsoft 365 cloud services associated with, or used by, the service</span></span>

<span data-ttu-id="8a643-148">이러한 변경 내용이 중단되지 않을 가능성이 높기 때문에 미리 알려주지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a643-148">These changes aren’t likely to be disruptive, so you don’t need to let us know about them ahead of time:</span></span>

- <span data-ttu-id="8a643-149">고아 개체 정리</span><span class="sxs-lookup"><span data-stu-id="8a643-149">Orphaned object cleanup</span></span>
- <span data-ttu-id="8a643-150">서비스에서 사용자 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="8a643-150">Adding or removing users from the service</span></span>
- <span data-ttu-id="8a643-151">시스템 전달에 큰 영향을 끼치지 않는 시스템 Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="8a643-151">Configuration of system that does not have a material impact on the delivery of the Microsoft Managed Desktop</span></span>
- <span data-ttu-id="8a643-152">VPN 또는 프록시 응용 프로그램을 제외하고 응용 프로그램 버전 업데이트</span><span class="sxs-lookup"><span data-stu-id="8a643-152">Application version updates, with the exception of VPN or proxy applications</span></span>