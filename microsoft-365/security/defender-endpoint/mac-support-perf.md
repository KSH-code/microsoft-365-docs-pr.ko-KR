---
title: Mac용 Microsoft Defender ATP의 성능 문제 해결
description: Mac용 Microsoft Defender ATP의 성능 문제를 해결합니다.
keywords: microsoft, defender, atp, mac, 성능
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
ms.openlocfilehash: f6dd5681dfafd069a4c52f72e1dc1733584283a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185912"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="7caaa-104">Mac용 끝점용 Microsoft Defender의 성능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7caaa-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7caaa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7caaa-105">**Applies to:**</span></span>

- [<span data-ttu-id="7caaa-106">Mac용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7caaa-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="7caaa-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7caaa-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7caaa-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7caaa-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7caaa-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7caaa-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7caaa-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7caaa-111">이 항목에서는 Mac용 끝점용 Microsoft Defender와 관련된 성능 문제를 좁히는 데 사용할 수 있는 몇 가지 일반적인 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="7caaa-112">RTP(실시간 보호)는 지속적으로 위협으로부터 장치를 모니터링하고 보호하는 Mac용 끝점용 Microsoft Defender의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="7caaa-113">이 구성은 파일 및 프로세스 모니터링 및 기타추론으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="7caaa-114">실행 중인 응용 프로그램 및 장치 특성에 따라 Mac용 끝점용 Microsoft Defender를 실행하면 하위 성능을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="7caaa-115">특히 짧은 시간 동안 많은 리소스에 액세스하는 응용 프로그램 또는 시스템 프로세스는 Mac용 끝점용 Microsoft Defender의 성능 문제를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="7caaa-116">다음 단계를 사용하여 이러한 문제를 해결하고 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="7caaa-117">다음 방법 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정하고 성능이 향상될지 여부를 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="7caaa-118">이 방법은 Mac용 끝점용 Microsoft Defender가 성능 문제에 기여하는지 여부를 좁히는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="7caaa-119">조직에서 장치를 관리하지 않는 경우 다음 옵션 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="7caaa-120">사용자 인터페이스에서</span><span class="sxs-lookup"><span data-stu-id="7caaa-120">From the user interface.</span></span> <span data-ttu-id="7caaa-121">Mac용 끝점용 Microsoft Defender를 열고 설정 **관리로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="7caaa-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![실시간 보호 스크린샷 관리](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="7caaa-123">터미널에서</span><span class="sxs-lookup"><span data-stu-id="7caaa-123">From the Terminal.</span></span> <span data-ttu-id="7caaa-124">보안을 위해 이 작업을 수행하려면 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="7caaa-125">조직에서 디바이스를 관리하는 경우 관리자가 [Mac용 Microsoft Defender에](mac-preferences.md)대한 기본 설정의 지침에 따라 실시간 보호를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="7caaa-126">찾기를 열고 응용 **프로그램**  >  **유틸리티로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="7caaa-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="7caaa-127">작업 **모니터를** 열고 시스템에서 리소스를 사용하는 응용 프로그램을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="7caaa-128">일반적인 예로는 소프트웨어 업데이트 프로그램 및 컴파일러가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="7caaa-129">성능 문제에 기여하는 프로세스 또는 디스크 위치에 대한 제외를 사용하여 Mac용 끝점에 대한 Microsoft Defender를 구성하고 실시간 보호를 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="7caaa-130">자세한 [내용은 Mac용 끝점에](mac-exclusions.md) 대한 Microsoft Defender 제외 구성 및 유효성 검사를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7caaa-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
