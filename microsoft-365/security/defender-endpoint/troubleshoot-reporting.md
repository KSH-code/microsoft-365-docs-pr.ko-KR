---
title: Microsoft Defender AV에 대한 보고 도구 문제 해결
description: 업데이트 준수에서 Microsoft Defender AV 보호 상태 보고를 시도할 때 일반적인 문제 식별 및 해결
keywords: 문제 해결, 오류, 수정, 업데이트 준수, oms, 모니터링, 보고서, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ab987089c20d0a1d0baed152e7ddcfdd2878cc65
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843461"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="d0d1b-104">업데이트 규정 준수에서 Microsoft Defender 바이러스 백신 보고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d0d1b-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d0d1b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d0d1b-105">**Applies to:**</span></span>

- [<span data-ttu-id="d0d1b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0d1b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="d0d1b-107">2020년 3월 31일, 업데이트 준수의 Microsoft Defender 바이러스 백신 보고 기능이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="d0d1b-108">보안 기능 및 업데이트를 더 Microsoft Endpoint Manager 사용하여 보안 준수 정책을 계속 [정의하고](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="d0d1b-109">업데이트 준수와 함께 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="d0d1b-110">E3, B, F1, VL 및 Pro 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="d0d1b-111">그러나 E5 라이선스의 경우 [끝점 포털용 Microsoft Defender를 사용해야 합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="d0d1b-112">라이선스 옵션에 대한 자세한 내용은 Windows 10 [라이선스 옵션을 참조하세요.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="d0d1b-113">Windows [분석](/windows/deployment/update/update-compliance-using#wdav-assessment) 업데이트 준수를 사용하여 네트워크에서 장치를 사용하는 장치 또는 끝점의 보호 상태에 대한 보고를 받을 Microsoft Defender 바이러스 백신 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="d0d1b-114">일반적으로 문제의 가장 일반적인 지표는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="d0d1b-115">예상한 모든 장치의 소수 또는 하위 집합만 표시</span><span class="sxs-lookup"><span data-stu-id="d0d1b-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="d0d1b-116">어떤 장치도 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-116">You do not see any devices at all</span></span>
- <span data-ttu-id="d0d1b-117">보고 있는 보고서 및 정보가 기한이 지난 경우(며칠이 지난 경우)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="d0d1b-118">업데이트 준수와 관련이 없는 Microsoft Defender 바이러스 백신 서비스와 관련된 일반적인 오류 코드 및 이벤트 MICROSOFT DEFENDER 바이러스 백신 [참조하세요.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="d0d1b-119">이러한 문제를 해결하는 데는 다음 세 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="d0d1b-120">모든 선행 준비를 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="d0d1b-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="d0d1b-121">클라우드 기반 서비스에 Windows Defender 연결 확인</span><span class="sxs-lookup"><span data-stu-id="d0d1b-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="d0d1b-122">지원 로그 제출</span><span class="sxs-lookup"><span data-stu-id="d0d1b-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="d0d1b-123">일반적으로 업데이트 준수에 장치가 나타나기 시작하는 데 3일이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="d0d1b-124">선행 준비 확인</span><span class="sxs-lookup"><span data-stu-id="d0d1b-124">Confirm prerequisites</span></span>

<span data-ttu-id="d0d1b-125">장치가 업데이트 준수에 제대로 표시하려면 업데이트 준수 서비스 및 업데이트 준수 서비스에 대한 특정 선행 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="d0d1b-126">끝점에서 단독 Microsoft Defender 바이러스 백신 보호 앱으로 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="d0d1b-127">다른 바이러스 백신 앱을 사용하는 [경우 Microsoft Defender AV가](microsoft-defender-antivirus-compatibility.md) 자체적으로 비활성화되어 끝점이 업데이트 준수에 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="d0d1b-128">[클라우드 제공 보호가 사용하도록 설정됩니다.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="d0d1b-129">끝점에서 [Microsoft Defender AV 클라우드에 연결할 수 있습니다.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="d0d1b-130">끝점이 1607 Windows 10 실행 중인 경우 Windows 10 진단 데이터를 고급 [수준으로 설정해야 합니다.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)</span><span class="sxs-lookup"><span data-stu-id="d0d1b-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="d0d1b-131">모든 요구 사항이 충족된 후 3일이 지났습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="d0d1b-132">"업데이트 준수와 함께 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="d0d1b-133">E3, B, F1, VL 및 Pro 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="d0d1b-134">그러나 E5 라이선스의 경우 끝점 포털용 Microsoft Defender 포털(/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="d0d1b-135">라이선스 옵션에 대한 자세한 내용은 Windows 10 라이선스 옵션을 참조하세요."</span><span class="sxs-lookup"><span data-stu-id="d0d1b-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="d0d1b-136">위의 선행 구성이 모두 충족된 경우 다음 단계로 진행하여 진단 정보를 수집하고 이를 저희에게 보내야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d1b-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d0d1b-137">업데이트 준수 문제 해결을 위한 진단 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d0d1b-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="d0d1b-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d0d1b-138">Related topics</span></span>

- [<span data-ttu-id="d0d1b-139">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="d0d1b-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d0d1b-140">배포 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="d0d1b-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)