---
title: Microsoft Defender ATP의 사용자 지정 검색 개요
ms.reviewer: ''
description: 고급 헌팅을 사용하여 사용자 지정 검색을 만들고 경고를 생성하는 방법 이해
keywords: 사용자 지정 검색, 경고, 검색 규칙, 고급 헌팅, 헌팅, 쿼리, 응답 작업, 간격, mdatp, Microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500649"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="bce44-104">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="bce44-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bce44-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bce44-105">**Applies to:**</span></span>
- [<span data-ttu-id="bce44-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bce44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bce44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bce44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bce44-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="bce44-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bce44-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bce44-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="bce44-110">사용자 지정 검색을 사용하면 위반 활동 및 잘못 구성된 장치를 포함하여 다양한 이벤트 및 시스템 상태의 사전 모니터링 및 대응을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce44-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="bce44-111">경고 및 응답 작업을 자동으로 트리거하는 사용자 지정 가능한 검색 규칙으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce44-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="bce44-112">사용자 지정 검색은 고급 헌팅과 함께 작동하며, 네트워크의 광범위한 이벤트 및 시스템 정보 집합을 다루는 강력하고 유연한 쿼리 언어를 제공합니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bce44-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="bce44-113">이러한 경고를 정기적으로 실행하여 일치하는 경우 경고를 생성하고 응답 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce44-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="bce44-114">사용자 지정 검색을 통해:</span><span class="sxs-lookup"><span data-stu-id="bce44-114">Custom detections provide:</span></span>
- <span data-ttu-id="bce44-115">고급 헌팅 쿼리로 구축된 규칙 기반 검색에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="bce44-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="bce44-116">파일 및 장치에 적용되는 자동 응답 작업</span><span class="sxs-lookup"><span data-stu-id="bce44-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="bce44-117">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bce44-117">Related topics</span></span>
- [<span data-ttu-id="bce44-118">검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="bce44-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="bce44-119">검색 규칙 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="bce44-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="bce44-120">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="bce44-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
