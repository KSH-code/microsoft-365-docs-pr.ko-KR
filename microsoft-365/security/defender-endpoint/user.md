---
title: 사용자 리소스 유형
description: 사용자와 관련된 최신 Microsoft Defender for Endpoint 경고를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197960"
---
# <a name="user-resource-type"></a><span data-ttu-id="6a21c-104">사용자 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="6a21c-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a21c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6a21c-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a21c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a21c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6a21c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a21c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a21c-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6a21c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a21c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="6a21c-110">메서드</span><span class="sxs-lookup"><span data-stu-id="6a21c-110">Method</span></span>|<span data-ttu-id="6a21c-111">반환 형식</span><span class="sxs-lookup"><span data-stu-id="6a21c-111">Return Type</span></span> |<span data-ttu-id="6a21c-112">설명</span><span class="sxs-lookup"><span data-stu-id="6a21c-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="6a21c-113">목록 사용자 관련 경고</span><span class="sxs-lookup"><span data-stu-id="6a21c-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="6a21c-114">[경고](alerts.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6a21c-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="6a21c-115">사용자와 연결된 모든 경고를 [나열합니다.](user.md)</span><span class="sxs-lookup"><span data-stu-id="6a21c-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="6a21c-116">사용자 관련 장치 목록</span><span class="sxs-lookup"><span data-stu-id="6a21c-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="6a21c-117">[machine collection(컴퓨터](machine.md) 컬렉션)</span><span class="sxs-lookup"><span data-stu-id="6a21c-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="6a21c-118">사용자가 로그온한 모든 장치를 [나열합니다.](user.md)</span><span class="sxs-lookup"><span data-stu-id="6a21c-118">List all the devices that were logged on by a [user](user.md).</span></span>
