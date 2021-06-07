---
title: Endpoint용 Defender와의 바이러스 백신 솔루션 호환성
description: Microsoft Defender for endpoint에서 Windows Defender 작동하는 방법과 타사 맬웨어 방지 클라이언트를 사용할 때 작동하는 방식에 대해 자세히 알아보습니다.
keywords: windows defender 호환성, defender, Endpoint용 Microsoft Defender, 끝점용 Defender, 바이러스 백신, mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782888"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="23596-104">Endpoint용 Microsoft Defender와의 바이러스 백신 솔루션 호환성</span><span class="sxs-lookup"><span data-stu-id="23596-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23596-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="23596-105">**Applies to:**</span></span>
- [<span data-ttu-id="23596-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23596-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23596-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23596-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="23596-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="23596-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23596-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="23596-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="23596-110">끝점용 Microsoft Defender 에이전트는 파일 Microsoft Defender 바이러스 백신 같은 일부 기능에 대한 지원 여부에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="23596-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="23596-111">Endpoint용 Defender는 제외 Microsoft Defender 바이러스 백신 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23596-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="23596-112">맬웨어 방지가 활성 상태인지 여부에 Microsoft Defender 바이러스 백신용 Defender에서 보안 인텔리전스 업데이트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23596-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="23596-113">자세한 내용은 업데이트 관리 [및 Microsoft Defender 바이러스 백신 적용을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="23596-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="23596-114">온보드 장치가 타사 맬웨어 방지 클라이언트에 의해 보호되는 경우 Microsoft Defender 바이러스 백신 끝점에서 수동 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="23596-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="23596-115">Microsoft Defender 바이러스 백신 업데이트가 계속 수신되고mspeng.exe 프로세스가 실행 중인 서비스로 나열되지만 검사는 수행되지 않습니다. 실행 중인 타사 맬웨어 방지 클라이언트는 대체되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23596-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="23596-116">Microsoft Defender 바이러스 백신 인터페이스가 사용하지 않도록 설정되어 디바이스의 사용자는 이 인터페이스를 사용하여 Microsoft Defender 바이러스 백신 또는 대부분의 옵션을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23596-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="23596-117">자세한 내용은 끝점 호환성 [Microsoft Defender 바이러스 백신 및 Defender를 참조하세요.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="23596-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
