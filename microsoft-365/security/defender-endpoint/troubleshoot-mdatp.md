---
title: 끝점 서비스 문제에 대한 Microsoft Defender 문제 해결
description: 서비스에 액세스하려고 할 때 서버 오류와 같은 알려진 문제에 대한 해결 방법과 해결 방법을 찾아야 합니다.
keywords: 끝점에 대한 Microsoft Defender 문제 해결, Windows ATP 문제 해결, 서버 오류, 액세스 거부, 잘못된 자격 증명, 데이터 없음, 대시보드 포털, 허용, 이벤트 뷰어
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 112f682836da37ddfb51c103282518ff74563727
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186020"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="1e856-104">서비스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1e856-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e856-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1e856-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e856-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1e856-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e856-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e856-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1e856-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1e856-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1e856-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="1e856-110">이 섹션에서는 Microsoft Defender Advanced Threat 서비스를 사용할 때 발생할 수 있는 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="1e856-111">서버 오류 - 잘못된 자격 증명으로 인해 액세스가 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="1e856-112">서비스에 액세스하려고 할 때 서버 오류가 발생하는 경우 브라우저 쿠키 설정을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="1e856-113">쿠키를 허용하도록 브라우저를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="1e856-114">포털에 누락된 요소 또는 데이터</span><span class="sxs-lookup"><span data-stu-id="1e856-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="1e856-115">Microsoft Defender 보안 센터에 일부 요소 또는 데이터가 없는 경우 프록시 설정으로 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-115">If some elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="1e856-116">프록시 허용 `*.securitycenter.windows.com` 목록에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-116">Make sure that `*.securitycenter.windows.com` is included the proxy allowlist.</span></span>


> [!NOTE]
> <span data-ttu-id="1e856-117">다음 끝점을 추가할 때 HTTPS 프로토콜을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="1e856-118">끝점용 Microsoft Defender 서비스에서 이벤트 뷰어에 이벤트 또는 오류 로그 표시</span><span class="sxs-lookup"><span data-stu-id="1e856-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="1e856-119">Microsoft Defender [for](event-error-codes.md) Endpoint 서비스에서 보고하는 이벤트 ID 목록은 이벤트 뷰어를 사용하여 이벤트 및 오류 검토를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e856-119">See [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="1e856-120">이 문서에는 이벤트 오류에 대한 문제 해결 단계도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-120">The article also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="1e856-121">다시 시작한 후 끝점용 Microsoft Defender 서비스가 시작되지 못하고 오류 577이 표시</span><span class="sxs-lookup"><span data-stu-id="1e856-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="1e856-122">장치 온보딩이 성공적으로 완료되지만 재부팅 후 Microsoft Defender for Endpoint가 시작되지 않는 경우 오류 577이 표시되어 있는 경우 정책에 Windows Defender 사용하지 않도록 설정되어 있지 않은지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="1e856-123">자세한 내용은 정책에서 Microsoft Defender 바이러스 백신이 사용하지 [않도록 설정되지 않은지 확인을 참조하세요.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="1e856-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="1e856-124">지역별 형식의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="1e856-124">Known issues with regional formats</span></span>

<span data-ttu-id="1e856-125">**날짜 및 시간 형식**</span><span class="sxs-lookup"><span data-stu-id="1e856-125">**Date and time formats**</span></span><br>
<span data-ttu-id="1e856-126">시간 및 날짜 형식에 몇 가지 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="1e856-127">지원되는 날짜 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-127">The following date formats are supported:</span></span>
- <span data-ttu-id="1e856-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="1e856-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="1e856-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="1e856-129">dd/MM/yyyy</span></span>

<span data-ttu-id="1e856-130">다음 날짜 및 시간 형식은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="1e856-131">날짜 형식 yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="1e856-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="1e856-132">날짜 형식 dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="1e856-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="1e856-133">날짜 형식(yy)</span><span class="sxs-lookup"><span data-stu-id="1e856-133">Date format with yy.</span></span> <span data-ttu-id="1e856-134">yyyy만 표시</span><span class="sxs-lookup"><span data-stu-id="1e856-134">Will only show yyyy.</span></span>
- <span data-ttu-id="1e856-135">시간 형식 HH:mm:ss는 지원되지 않습니다(12시간 AM/PM 형식은 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="1e856-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="1e856-136">24시간 형식만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="1e856-137">**0000**</span><span class="sxs-lookup"><span data-stu-id="1e856-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="1e856-138">숫자에서 구분으로 콤보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="1e856-139">숫자가 1000을 나타내는 콤보로 구분되는 지역은 점만 구분 구분선으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="1e856-140">예를 들어 15,5K는 15.5K로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="1e856-141">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1e856-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1e856-142">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="1e856-143">Microsoft Defender for Endpoint 테넌트가 유럽에서 자동으로 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="1e856-144">Azure 보안 센터를 사용하여 서버를 모니터링하면 끝점 테넌트용 Microsoft Defender가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="1e856-145">끝점용 Microsoft Defender 데이터는 기본적으로 유럽에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e856-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="1e856-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1e856-146">Related topics</span></span>
- [<span data-ttu-id="1e856-147">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1e856-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="1e856-148">이벤트 뷰어를 사용하여 이벤트 및 오류 검토</span><span class="sxs-lookup"><span data-stu-id="1e856-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
