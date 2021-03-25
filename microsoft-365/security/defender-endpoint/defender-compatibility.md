---
title: Endpoint용 Defender와의 Microsoft Defender 바이러스 백신 호환성
description: Microsoft Defender for Windows Defender 작동하는 방법과 타사 맬웨어 방지 클라이언트를 사용할 때 해당 기능이 작동하는 방법에 대해 자세히 알아보습니다.
keywords: windows defender 호환성, defender, Microsoft Defender atp, 끝점용 defender, 바이러스 백신, mde
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
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165961"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="55164-104">끝점용 Microsoft Defender와의 Microsoft Defender 바이러스 백신 호환성</span><span class="sxs-lookup"><span data-stu-id="55164-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55164-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="55164-105">**Applies to:**</span></span>
- [<span data-ttu-id="55164-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="55164-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55164-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55164-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="55164-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="55164-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55164-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="55164-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="55164-110">끝점용 Microsoft Defender 에이전트는 파일 검색과 같은 일부 기능에 대해 Microsoft Defender 바이러스 백신에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="55164-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="55164-111">Endpoint용 Defender는 Microsoft Defender 바이러스 백신 제외 설정을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55164-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="55164-112">Microsoft Defender 바이러스 백신이 활성 맬웨어 방지인지 여부에 관계 없는 경우 끝점 장치용 Defender에서 보안 인텔리전스 업데이트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55164-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="55164-113">자세한 내용은 Microsoft Defender 바이러스 백신 업데이트 관리 및 [기준 적용을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="55164-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="55164-114">타사 맬웨어 방지 클라이언트에 의해 온보딩된 장치가 보호되는 경우 해당 끝점의 Microsoft Defender 바이러스 백신이 수동 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="55164-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="55164-115">Microsoft Defender *바이러스* 백신은 계속 업데이트를 수신하며mspeng.exe프로세스는 실행 중인 서비스로 나열되지만 검색을 수행하지는 못하며 실행 중인 타사 맬웨어 방지 클라이언트를 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55164-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="55164-116">Microsoft Defender 바이러스 백신 인터페이스가 비활성화되어 장치의 사용자가 Microsoft Defender 바이러스 백신을 사용하여 요구 시 검사 또는 대부분의 옵션을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55164-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="55164-117">자세한 내용은 Microsoft [Defender 바이러스 백신 및 Endpoint 호환성을 위한 Defender 항목을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="55164-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
