---
title: Microsoft 365 Defender의 사용자 지정 검색 개요
description: 고급 헌팅을 사용하여 사용자 지정 검색을 만들고 경고를 생성하는 방법 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4a4b601b5f8b9a21d7e7260fcadf9fecd0e37c5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060799"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="090a8-104">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="090a8-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="090a8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="090a8-105">**Applies to:**</span></span>
- <span data-ttu-id="090a8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="090a8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="090a8-107">사용자 지정 검색을 사용하면 위반 활동 및 잘못 구성된 끝점을 포함하여 다양한 이벤트 및 시스템 상태의 사전 대응을 모니터링하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="090a8-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="090a8-108">이 작업은 경고 및 응답 작업을 자동으로 트리거하는 사용자 지정 가능한 검색 규칙에 의해 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="090a8-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="090a8-109">사용자 지정 검색은 고급 헌팅과 함께 작동하며, 네트워크의 광범위한 이벤트 및 시스템 정보 집합을 다루는 강력하고 유연한 쿼리 언어를 제공합니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="090a8-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="090a8-110">이러한 경고를 정기적으로 실행하여 일치하는 경우 경고를 생성하고 응답 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="090a8-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="090a8-111">사용자 지정 검색을 통해:</span><span class="sxs-lookup"><span data-stu-id="090a8-111">Custom detections provide:</span></span>
- <span data-ttu-id="090a8-112">고급 헌팅 쿼리로 구축된 규칙 기반 검색에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="090a8-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="090a8-113">자동 응답 작업</span><span class="sxs-lookup"><span data-stu-id="090a8-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="090a8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="090a8-114">See also</span></span>
- [<span data-ttu-id="090a8-115">사용자 지정 검색 규칙 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="090a8-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="090a8-116">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="090a8-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="090a8-117">끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="090a8-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
