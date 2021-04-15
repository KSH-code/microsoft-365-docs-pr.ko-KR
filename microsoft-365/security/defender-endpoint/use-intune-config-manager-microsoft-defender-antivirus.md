---
title: Configuration Manager 및 Intune을 통해 Microsoft Defender 바이러스 백신 구성
description: Microsoft Endpoint Manager 및 Microsoft Intune을 사용하여 Microsoft Defender AV 및 Endpoint Protection 구성
keywords: scep, intune, 끝점 보호, 구성
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/26/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 647bda97cfbec5e1583ef66ebd3e9d445371d540
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749871"
---
# <a name="use-microsoft-endpoint-manager-and-microsoft-intune-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="b031d-104">Microsoft Endpoint Manager 및 Microsoft Intune을 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="b031d-104">Use Microsoft Endpoint Manager and Microsoft Intune to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b031d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b031d-105">**Applies to:**</span></span>

- <span data-ttu-id="b031d-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="b031d-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="b031d-107">Microsoft Endpoint Manager 또는 Microsoft Intune을 사용하여 네트워크의 끝점을 관리하는 경우 이제 Microsoft Endpoint Manager를 사용하여 Microsoft Defender 바이러스 백신 스캔을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b031d-107">If you were using Microsoft Endpoint Manager or Microsoft Intune to manage the endpoints on your network, you can now use Microsoft Endpoint Manager to manage Microsoft Defender Antivirus scans.</span></span>

1. <span data-ttu-id="b031d-108">Microsoft Endpoint Manager 관리 센터에서 ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) 끝점 **보안으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="b031d-108">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Endpoint Security**.</span></span>

2. <span data-ttu-id="b031d-109">관리에서 바이러스 백신 을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="b031d-109">Under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="b031d-110">Microsoft Defender 바이러스 백신 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b031d-110">Select your Microsoft Defender Antivirus policy.</span></span> 

4. <span data-ttu-id="b031d-111">관리에서 속성을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="b031d-111">Under **Manage**, choose **Properties**.</span></span>

5. <span data-ttu-id="b031d-112">구성 설정 **옆에 있는** 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b031d-112">Next to **Configuration settings**, choose **Edit**.</span></span>

6. <span data-ttu-id="b031d-113">검사 **섹션을** 확장하고 검사 설정을 검토하거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b031d-113">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

7. <span data-ttu-id="b031d-114">검토 **+ 저장 선택**</span><span class="sxs-lookup"><span data-stu-id="b031d-114">Choose **Review + save**</span></span>

<span data-ttu-id="b031d-115">도움이 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="b031d-115">Need help?</span></span> <span data-ttu-id="b031d-116">[Microsoft Intune에서 끝점 보안 관리를 참조합니다.](/mem/intune/protect/endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="b031d-116">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="b031d-117">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b031d-117">Related articles</span></span>

- [<span data-ttu-id="b031d-118">관리 및 구성 도구에 대한 참조 항목</span><span class="sxs-lookup"><span data-stu-id="b031d-118">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b031d-119">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="b031d-119">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)