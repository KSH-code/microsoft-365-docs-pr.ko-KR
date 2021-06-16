---
title: Microsoft Defender 바이러스 백신 평가
description: 규모에 제한이 없는 기업은 이 가이드를 사용하여 조직에서 제공하는 보호를 평가하고 Microsoft Defender 바이러스 백신 Windows 10.
keywords: Microsoft Defender 바이러스 백신, 클라우드, 맬웨어 방지, 보안, defender, 평가, 테스트, 보호, 비교, 실시간 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c558a7799bff61a0ee80db31ee476ad611053c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926622"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="2eeda-104">Microsoft Defender 바이러스 백신 평가</span><span class="sxs-lookup"><span data-stu-id="2eeda-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2eeda-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2eeda-105">**Applies to:**</span></span>

- [<span data-ttu-id="2eeda-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2eeda-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2eeda-107">이 가이드를 사용하여 바이러스, 맬웨어 및 Microsoft Defender 바이러스 백신 응용 프로그램을 보호할 수 있는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="2eeda-108">Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 데모 웹 사이트를 방문하여 demo.wd.microsoft.com 작동을 확인하고 작동 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="2eeda-109">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="2eeda-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="2eeda-110">빠른 학습(신속한 차단 포함)</span><span class="sxs-lookup"><span data-stu-id="2eeda-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="2eeda-111">잠재적으로 원치 않는 응용 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="2eeda-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="2eeda-112">또한 중소기업과 대기업 둘 다에서 사용할 수 있는 Microsoft Defender 바이러스 백신 중요한 차세대 보호 기능과 네트워크에서 맬웨어 감지 및 보호를 강화하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="2eeda-113">각 설정을 독립적으로 구성 및 평가하도록 선택하거나 한 번씩 모두 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="2eeda-114">일반적인 평가 시나리오에 따라 유사한 설정을 그룹화하고 PowerShell을 사용하여 설정을 사용하도록 설정하기 위한 지침을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="2eeda-115">이 가이드는 오프라인에서 볼 수 있도록 PDF 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="2eeda-116">PDF 형식으로 가이드 다운로드</span><span class="sxs-lookup"><span data-stu-id="2eeda-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="2eeda-117">가이드에 설명된 모든 설정을 자동으로 사용하도록 설정하는 PowerShell을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="2eeda-118">위의 PDF 다운로드와 함께 또는 PowerShell 갤러리에서 개별적으로 스크립트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="2eeda-119">PowerShell 스크립트를 다운로드하여 설정 자동 구성</span><span class="sxs-lookup"><span data-stu-id="2eeda-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="2eeda-120">이 가이드는 현재 단일 컴퓨터 평가를 위해 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="2eeda-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="2eeda-121">이 가이드의 모든 설정을 사용하도록 설정하는 것은 실제 배포에 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eeda-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="2eeda-122">네트워크에서 실제 배포 및 모니터링을 위한 최신 권장 사항은 Microsoft Defender 바이러스 백신 [배포를 Microsoft Defender 바이러스 백신.](deploy-manage-report-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2eeda-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2eeda-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2eeda-123">Related topics</span></span>

- [<span data-ttu-id="2eeda-124">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="2eeda-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="2eeda-125">배포 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="2eeda-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)