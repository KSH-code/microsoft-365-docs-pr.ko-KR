---
title: Microsoft Defender 바이러스 백신 보호 모니터링 및 보고
description: Configuration Manager 또는 SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 보고서를 사용하며 PowerShell 및 WMI를 사용하여 Microsoft Defender AV를 모니터링합니다.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269591"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="00394-104">Microsoft Defender 바이러스 백신에 대한 보고</span><span class="sxs-lookup"><span data-stu-id="00394-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="00394-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="00394-105">**Applies to:**</span></span>

- [<span data-ttu-id="00394-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00394-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="00394-107">Microsoft Defender 바이러스 백신은 Windows 10, Windows Server 2019 및 Windows Server 2016에 기본 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00394-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="00394-108">Microsoft Defender 바이러스 백신은 끝점용 Microsoft Defender의 차세대 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="00394-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="00394-109">차세대 보호는 전자 메일, 앱, 클라우드 및 웹에서 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협으로부터 장치를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00394-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="00394-110">Microsoft Defender 바이러스 백신을 사용하면 보호 상태 및 경고를 검토할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00394-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="00394-111">Microsoft Endpoint Manager를 사용하여 [Microsoft Defender 바이러스 백신을 모니터링하거나](/configmgr/protect/deploy-use/monitor-endpoint-protection) 전자 메일 [경고를 만들 수 있습니다.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="00394-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="00394-112">또는 [Microsoft Intune을 사용하여 보호를 모니터링할 수 있습니다.](/intune/introduction-intune)</span><span class="sxs-lookup"><span data-stu-id="00394-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="00394-113">Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite에는 보호 업데이트 및 실시간 보호 설정을 포함하여 주요 Microsoft Defender 바이러스 백신 문제를 보고하는 업데이트 준수 추가 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00394-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="00394-114">타사 SIEM(보안 정보 및 이벤트 관리) 서버가 있는 경우 클라이언트 이벤트를 Windows Defender [있습니다.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="00394-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="00394-115">Windows 이벤트는 SAM(Security Account Manager) 이벤트(Windows[10에](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)대해 향상된 보안 [](/windows/device-security/auditing/security-auditing-overview) 계정 관리자) 및 보안 감사 항목 참조) 및 Windows Defender 이벤트를 포함하여 여러 보안 [이벤트 원본으로 구성됩니다.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="00394-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="00394-116">이러한 이벤트는 Windows 이벤트 수집기 를 사용하여 [중앙에서 집계할 수 있습니다.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="00394-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="00394-117">종종 SIEM 서버에는 Windows 이벤트에 대한 커넥터가 있어 SIEM 서버의 모든 보안 이벤트를 상관 관계화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00394-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="00394-118">[Log Analytics의 맬웨어](/azure/log-analytics/log-analytics-malware)평가 솔루션을 사용하여 맬웨어 이벤트를 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00394-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="00394-119">PowerShell, WMI 또는 Microsoft Azure의 상태를 모니터링하거나 확인하는 데 대한 자세한 내용은 (배포, 관리 및 보고 [옵션 표)를 참조하세요.](deploy-manage-report-microsoft-defender-antivirus.md#ref2)</span><span class="sxs-lookup"><span data-stu-id="00394-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="00394-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="00394-120">Related articles</span></span>

- [<span data-ttu-id="00394-121">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="00394-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="00394-122">Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="00394-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="00394-123">Microsoft Defender 바이러스 백신 배포</span><span class="sxs-lookup"><span data-stu-id="00394-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)