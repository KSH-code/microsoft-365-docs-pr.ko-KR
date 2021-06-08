---
title: 끝점용 Microsoft Defender에서 방화벽 보고 호스트
description: 보안 센터에서 방화벽 보고를 Microsoft 365 볼 수 있습니다.
keywords: windows defender, 방화벽
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809305"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="249b9-104">끝점용 Microsoft Defender에서 방화벽 보고 호스트</span><span class="sxs-lookup"><span data-stu-id="249b9-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="249b9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="249b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="249b9-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="249b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="249b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="249b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="249b9-108">관리자인 경우 이제 보안 센터 에 방화벽 [보고를 Microsoft 365 있습니다.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="249b9-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="249b9-109">이 기능을 사용하면 중앙 위치에서 Windows 10 및 Windows Server 2019 방화벽 보고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="249b9-110">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="249b9-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="249b9-111">Server 2019 또는 Windows 10 Windows 실행 중이야 합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="249b9-112">디바이스를 Microsoft Defender for Endpoint 서비스에 온보딩하는 경우 여기를 [참조하세요.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="249b9-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="249b9-113">보안 Microsoft 365 센터에서 데이터 수신을 시작하려면 고급  보안이 있는 사용자에 대해 감사 Windows Defender 방화벽 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="249b9-114">필터링 플랫폼 패킷 삭제 감사</span><span class="sxs-lookup"><span data-stu-id="249b9-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="249b9-115">필터링 플랫폼 연결 감사</span><span class="sxs-lookup"><span data-stu-id="249b9-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="249b9-116">그룹 정책 개체 편집기, 로컬 보안 정책 또는 로컬 보안 정책을 사용하여 이러한 이벤트를 auditpol.exe 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="249b9-117">자세한 내용은 여기를 [참조하세요.](/windows/win32/fwp/auditing-and-logging)</span><span class="sxs-lookup"><span data-stu-id="249b9-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="249b9-118">PowerShell 명령은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="249b9-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="249b9-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="249b9-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="249b9-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="249b9-121">프로세스</span><span class="sxs-lookup"><span data-stu-id="249b9-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="249b9-122">위 섹션의 지침을 따르고 초기 미리 보기 참가를 위해 장치를 올바르게 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="249b9-123">이벤트를 사용하도록 설정하면 Microsoft 365 센터에서 데이터 모니터링을 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="249b9-124">원격 IP, 원격 포트, 로컬 포트, 로컬 IP, 컴퓨터 이름, 인바운드 및 아웃바운드 연결에서 프로세스</span><span class="sxs-lookup"><span data-stu-id="249b9-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="249b9-125">이제 관리자는 여기에서 방화벽 Windows 볼 수 [있습니다.](https://security.microsoft.com/firewall)</span><span class="sxs-lookup"><span data-stu-id="249b9-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="249b9-126">사용자 지정 보고 스크립트를 다운로드하여 [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) 추가 보고를 용이하게 할 수 Windows Defender 방화벽 작업을 모니터링할 수 Power BI.</span><span class="sxs-lookup"><span data-stu-id="249b9-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="249b9-127">데이터가 반영되기까지 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="249b9-128">지원되는 시나리오</span><span class="sxs-lookup"><span data-stu-id="249b9-128">Supported scenarios</span></span>
<span data-ttu-id="249b9-129">링0 미리 보기 중에 지원되는 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="249b9-130">보안 센터의 방화벽 보고</span><span class="sxs-lookup"><span data-stu-id="249b9-130">Firewall reporting in security center</span></span>

<span data-ttu-id="249b9-131">다음은 방화벽 보고서 페이지의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="249b9-132">여기에서 인바운드, 아웃바운드 및 응용 프로그램 활동에 대한 요약을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="249b9-133">로 이동하여 이 페이지에 직접 액세스할 수 https://security.microsoft.com/firewall 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="249b9-134">![방화벽 보고 호스트 페이지](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="249b9-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="249b9-135">방화벽 차단 인바운드 연결 카드 아래쪽에 있는 보고서 보안 보고서 장치(섹션)로 이 보고서에 액세스할  >    >   **수도** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="249b9-136">"차단된 연결이 있는 컴퓨터"에서 장치로</span><span class="sxs-lookup"><span data-stu-id="249b9-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="249b9-137">카드는 대화형 개체를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-137">Cards support interactive objects.</span></span> <span data-ttu-id="249b9-138">새 탭에서 시작되는 장치 이름을 클릭하여 디바이스의 활동을 드릴다운하고 장치 타임라인 탭으로 바로 https://securitycenter.microsoft.com 이동하면 됩니다. </span><span class="sxs-lookup"><span data-stu-id="249b9-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="249b9-139">![차단된 연결이 있는 컴퓨터](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="249b9-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="249b9-140">이제 타임라인  탭을 선택하여 해당 디바이스와 연결된 이벤트 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="249b9-141">보기 창의  오른쪽 위 모서리에 있는 필터 단추를 클릭한 후 원하는 이벤트 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="249b9-142">이 경우 방화벽 이벤트를 **선택하면** 창이 방화벽 이벤트로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="249b9-143">![필터 단추](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="249b9-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="249b9-144">고급 헌팅 드릴(미리 보기 새로 고침)</span><span class="sxs-lookup"><span data-stu-id="249b9-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="249b9-145">방화벽 보고서는 고급 헌팅  열기 단추를 클릭하여 카드에서 고급 헌팅으로 직접 드릴링을 **지원합니다.**</span><span class="sxs-lookup"><span data-stu-id="249b9-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="249b9-146">쿼리가 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="249b9-147">![고급 헌팅 단추 열기](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="249b9-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="249b9-148">이제 쿼리를 실행할 수 있으며 지난 30일 동안의 모든 관련 방화벽 이벤트를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="249b9-149">추가 보고 또는 사용자 지정 변경의 경우 추가 분석을 위해 쿼리를 Power BI 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249b9-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="249b9-150">사용자 지정 보고 스크립트를 다운로드하여 [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) 사용자 지정 보고를 사용하여 Windows Defender 방화벽 작업을 모니터링하면 사용자 지정 보고를 Power BI.</span><span class="sxs-lookup"><span data-stu-id="249b9-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 