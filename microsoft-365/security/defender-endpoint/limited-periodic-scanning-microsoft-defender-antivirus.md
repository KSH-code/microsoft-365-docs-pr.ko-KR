---
title: 제한된 주기적 Microsoft Defender 바이러스 백신 검사 기능 사용
description: 제한된 주기적 검색을 통해 설치된 다른 AV 공급자와 함께 Microsoft Defender 바이러스 백신을 사용할 수 있습니다.
keywords: lps, 제한, 주기적, 검사, 검사, 호환성, 제3자, 기타 av, 사용 안 하게
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82c4bc1feec1556dc864558a843ed5e911c3ef3d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764486"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="4d00c-104">Microsoft Defender 바이러스 백신에서 제한된 주기적 검사 사용</span><span class="sxs-lookup"><span data-stu-id="4d00c-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4d00c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4d00c-105">**Applies to:**</span></span>

- <span data-ttu-id="4d00c-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="4d00c-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="4d00c-107">제한된 주기적 검사는 Windows 10 장치에 다른 바이러스 백신 제품을 설치할 때 사용할 수 있는 특수한 유형의 위협 감지 및 수정입니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="4d00c-108">특정 상황에서만 사용하도록 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="4d00c-109">제한된 주기적 검사 및 Microsoft Defender 바이러스 백신이 다른 바이러스 백신 제품과 작동하는 방식에 대한 자세한 내용은 Microsoft Defender 바이러스 백신 [호환성을 참조하세요.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="4d00c-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="4d00c-110">**엔터프라이즈 환경에서는 이 기능을 사용하지 않는 것이 좋습니다. 이는 주로 소비자를 위한 기능입니다.**</span><span class="sxs-lookup"><span data-stu-id="4d00c-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="4d00c-111">이 기능은 Microsoft Defender 바이러스 백신 기능의 제한된 하위 집합만 사용하여 맬웨어를 감지하며, 대부분의 맬웨어 및 사용자 원치 않는 소프트웨어를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="4d00c-112">또한 관리 및 보고 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="4d00c-113">Microsoft는 엔터프라이즈에서 기본 바이러스 백신 솔루션을 선택하고 단독으로 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="4d00c-114">제한된 주기적 검색을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="4d00c-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="4d00c-115">기본적으로 Microsoft Defender 바이러스 백신은 다른 바이러스 백신 제품이 설치되지 않은 경우 또는 다른 제품이 만료되었거나 제대로 작동하지 않는 경우 Windows 10 장치에서 자체적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="4d00c-116">Microsoft Defender 바이러스 백신을 사용하도록 설정하면 일반적인 옵션이 해당 장치에서 구성하는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![검사 옵션, 설정 및 업데이트 옵션을 포함하여 Microsoft Defender AV 옵션을 보여 주는 Windows 보안 앱](images/vtp-wdav.png)

<span data-ttu-id="4d00c-118">다른 바이러스 백신 제품이 설치되어 올바르게 작동하면 Microsoft Defender 바이러스 백신이 자체적으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="4d00c-119">Windows 보안 앱은 바이러스  & 위협 방지 섹션을 변경하여 AV 제품에 대한 상태를 표시하고 제품의 구성 옵션에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="4d00c-120">타사 AV 제품 아래에 새 링크가 Microsoft Defender 바이러스 백신 **옵션으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="4d00c-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="4d00c-121">이 링크를 클릭하면 제한된 주기적 검색을 가능하게 하는 토글이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="4d00c-122">제한된 주기적 옵션은 주기적 검색을 사용하도록 설정하거나 사용하지 않도록 설정하는 토글입니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="4d00c-123">으로 전환을 **슬라이딩하면** 타사 AV 제품 아래에 표준 Microsoft Defender AV 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="4d00c-124">제한된 주기적 검사 옵션이 페이지 아래쪽에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d00c-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4d00c-125">관련 문서</span><span class="sxs-lookup"><span data-stu-id="4d00c-125">Related articles</span></span>

- [<span data-ttu-id="4d00c-126">동작,추론적 및 실시간 보호 구성</span><span class="sxs-lookup"><span data-stu-id="4d00c-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4d00c-127">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="4d00c-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)