---
title: 사용자 Microsoft Defender 바이러스 백신 구성 Microsoft Endpoint Manager
description: Microsoft Microsoft Endpoint Manager Microsoft Intune 사용하여 Microsoft Defender AV 및 Endpoint Protection
keywords: scep, intune, 끝점 보호, 구성
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683754"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="8449b-104">이 Microsoft Endpoint Manager 사용하여 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="8449b-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8449b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8449b-105">**Applies to:**</span></span>

- [<span data-ttu-id="8449b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8449b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8449b-107">검색을 [사용하여](/mem/endpoint-manager-overview) Microsoft Endpoint Manager 구성할 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="8449b-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) 및 [Configuration Manager는](/mem/configmgr/core/understand/introduction) 이제 Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="8449b-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="8449b-109">사용자 Microsoft Defender 바이러스 백신 검사 구성 Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="8449b-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="8449b-110">Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="8449b-111">**끝점 보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="8449b-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="8449b-112">관리에서 바이러스 백신 을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="8449b-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="8449b-113">사용자 Microsoft Defender 바이러스 백신 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="8449b-114">**관리** 에서 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="8449b-115">**구성 설정** 옆의 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="8449b-116">검사 **섹션을** 확장하고 검사 설정을 검토하거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="8449b-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="8449b-117">검토 **+ 저장 선택**</span><span class="sxs-lookup"><span data-stu-id="8449b-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="8449b-118">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="8449b-118">Need help?</span></span> <span data-ttu-id="8449b-119">에서 끝점 보안 [관리를 Microsoft Intune.](/mem/intune/protect/endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="8449b-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="8449b-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="8449b-120">Related articles</span></span>

- [<span data-ttu-id="8449b-121">관리 및 구성 도구에 대한 참조 문서</span><span class="sxs-lookup"><span data-stu-id="8449b-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8449b-122">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="8449b-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)