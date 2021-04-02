---
title: 사용 권한의 & - 위협 및 취약성 관리
description: 위협 및 취약점 관리 사용을 시작하기 전에 관련 구성 및 사용 권한이 있는지 확인해야 합니다.
keywords: 위협 & 관리 권한의 선행 요소, 위협 및 취약성 관리 권한 선행 요소, MDATP TVM 권한 선행 요소, 취약성 관리
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1d9c3233f72541ccd0463eefef93bde5e7d9900f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499956"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="40ea6-104">사용 권한의 & - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="40ea6-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40ea6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="40ea6-105">**Applies to:**</span></span>

- [<span data-ttu-id="40ea6-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="40ea6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="40ea6-107">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="40ea6-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="40ea6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40ea6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="40ea6-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="40ea6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40ea6-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="40ea6-111">장치가 다음을 하는지 확인:</span><span class="sxs-lookup"><span data-stu-id="40ea6-111">Ensure that your devices:</span></span>

- <span data-ttu-id="40ea6-112">끝점용 Microsoft Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="40ea6-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="40ea6-113">지원되는 [운영 체제 및 플랫폼 실행](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="40ea6-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="40ea6-114">취약성 평가 감지 비율을 높이기 위해 네트워크에 다음과 같은 필수 업데이트를 설치하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="40ea6-115">릴리스</span><span class="sxs-lookup"><span data-stu-id="40ea6-115">Release</span></span> | <span data-ttu-id="40ea6-116">보안 업데이트 KB 번호 및 링크</span><span class="sxs-lookup"><span data-stu-id="40ea6-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="40ea6-117">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="40ea6-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="40ea6-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) 및 [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="40ea6-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="40ea6-119">Windows 10 버전 1803</span><span class="sxs-lookup"><span data-stu-id="40ea6-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="40ea6-120">[KB4493464](https://support.microsoft.com/help/4493464) 및 [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="40ea6-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="40ea6-121">Windows 10 버전 1809</span><span class="sxs-lookup"><span data-stu-id="40ea6-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="40ea6-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="40ea6-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="40ea6-123">Windows 10 버전 1903</span><span class="sxs-lookup"><span data-stu-id="40ea6-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="40ea6-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="40ea6-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="40ea6-125">위협 및 취약성 관리에서 발견된 위협을 수정하는 데 도움이 있도록 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 및  [Microsoft Endpoint Configuration Manager에](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) 온보더스됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="40ea6-126">Configuration Manager를 사용하는 경우 콘솔을 최신 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="40ea6-127">**참고:** Intune 연결을 사용하도록 설정한 경우 수정 요청을 만들 때 Intune 보안 작업을 만드는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="40ea6-128">연결이 설정되어 있지 않은 경우 이 옵션이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="40ea6-129">장치 페이지에서 볼 수 있는 보안 권장 설정 하나 이상</span><span class="sxs-lookup"><span data-stu-id="40ea6-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="40ea6-130">태그가 지정되거나 공동 관리로 표시</span><span class="sxs-lookup"><span data-stu-id="40ea6-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="40ea6-131">관련 권한 옵션</span><span class="sxs-lookup"><span data-stu-id="40ea6-131">Relevant permission options</span></span>

1. <span data-ttu-id="40ea6-132">보안 관리자 또는 전역 관리자 역할이 할당된 계정을 사용하여 Microsoft Defender 보안 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="40ea6-133">탐색 창에서 설정 및 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="40ea6-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="40ea6-134">자세한 내용은 역할 기반 액세스 제어에 대한 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="40ea6-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="40ea6-135">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="40ea6-135">View data</span></span>

- <span data-ttu-id="40ea6-136">**보안 작업** - 포털의 모든 보안 작업 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="40ea6-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="40ea6-137">**위협 및 취약성 관리** - 포털에서 위협 및 취약성 관리 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="40ea6-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="40ea6-138">활성 수정 작업</span><span class="sxs-lookup"><span data-stu-id="40ea6-138">Active remediation actions</span></span>

- <span data-ttu-id="40ea6-139">**보안 작업** - 대응 조치 수행, 보류 중인 수정 작업 승인 또는 해지, 자동화 및 표시기를 위한 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="40ea6-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="40ea6-140">**위협 및 취약성 관리 - 예외 처리 -** 새 예외 만들기 및 활성 예외 관리</span><span class="sxs-lookup"><span data-stu-id="40ea6-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="40ea6-141">**위협 및 취약성 관리 -** 수정 처리 - 새 수정 요청을 제출하고, 티켓을 만들고, 기존 수정 활동을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="40ea6-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="40ea6-142">자세한 내용은 [RBAC 사용 권한 옵션을 참조하세요.](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="40ea6-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="40ea6-143">관련 문서</span><span class="sxs-lookup"><span data-stu-id="40ea6-143">Related articles</span></span>

- [<span data-ttu-id="40ea6-144">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="40ea6-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="40ea6-145">지원되는 운영 체제 및 플랫폼</span><span class="sxs-lookup"><span data-stu-id="40ea6-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="40ea6-146">장치 값 할당</span><span class="sxs-lookup"><span data-stu-id="40ea6-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="40ea6-147">위협 및 취약성 관리 대시보드</span><span class="sxs-lookup"><span data-stu-id="40ea6-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

