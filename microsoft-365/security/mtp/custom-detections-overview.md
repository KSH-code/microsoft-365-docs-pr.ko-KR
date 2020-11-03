---
title: Microsoft 365 Defender의 사용자 지정 검색 개요
description: 고급 검색을 사용 하 여 사용자 지정 검색을 만들고 알림을 생성 하는 방법을 이해 합니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365 및 microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fe2b9f1b52fa2c8d9031bb58597992f3dda91520
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843915"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="ac6d5-104">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="ac6d5-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ac6d5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ac6d5-105">**Applies to:**</span></span>
- <span data-ttu-id="ac6d5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac6d5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ac6d5-107">사용자 지정 검색을 사용 하면 의심 스러운 위반 작업과 잘못 구성 된 끝점을 포함 하 여 다양 한 이벤트 및 시스템 상태를 사전에 모니터링 하 고 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6d5-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="ac6d5-108">이는 응답 작업 뿐만 아니라 경고를 자동으로 트리거하는 사용자 지정 가능한 검색 규칙이 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6d5-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="ac6d5-109">사용자 지정 검색 기능은 네트워크에서 광범위 한 이벤트 및 시스템 정보 집합을 다루는 강력 하 고 유연한 쿼리 언어를 제공 하는 [고급 구하기](advanced-hunting-overview.md)기능을 사용 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6d5-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="ac6d5-110">이러한 항목은 일치 하는 모든 경우에 알림을 생성 하 고 응답 작업을 수행 하 여 정기적인 간격으로 실행 되도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6d5-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="ac6d5-111">사용자 지정 검색은 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6d5-111">Custom detections provide:</span></span>
- <span data-ttu-id="ac6d5-112">고급 검색 쿼리를 통해 작성 된 규칙 기반 감지에 대 한 경고</span><span class="sxs-lookup"><span data-stu-id="ac6d5-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="ac6d5-113">자동 응답 작업</span><span class="sxs-lookup"><span data-stu-id="ac6d5-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="ac6d5-114">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ac6d5-114">Related topic</span></span>
- [<span data-ttu-id="ac6d5-115">사용자 지정 검색 규칙 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ac6d5-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="ac6d5-116">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="ac6d5-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
