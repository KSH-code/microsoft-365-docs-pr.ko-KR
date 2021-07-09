---
title: 알림 큐의 Microsoft 365 Defender
ms.reviewer: ''
description: 알림에 표시되어 있는 경고 보기 및 Microsoft 365 Defender
keywords: ''
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
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: ed65c836e74d5394d3b291ca3ebb5e781e37afa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339565"
---
# <a name="alerts-queue-in-microsoft-365-defender"></a><span data-ttu-id="8a61c-103">알림 큐의 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a61c-103">Alerts queue in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a61c-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8a61c-104">**Applies to:**</span></span>
- [<span data-ttu-id="8a61c-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a61c-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="8a61c-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8a61c-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8a61c-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8a61c-108">장치, 파일 또는 사용자 계정과 같은 엔터티에서 볼 수 있는 위협을 효과적으로 조사할 수 있도록 큐를 보고 관리하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="8a61c-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8a61c-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8a61c-109">In this section</span></span>
<span data-ttu-id="8a61c-110">항목</span><span class="sxs-lookup"><span data-stu-id="8a61c-110">Topic</span></span> | <span data-ttu-id="8a61c-111">설명</span><span class="sxs-lookup"><span data-stu-id="8a61c-111">Description</span></span> 
:---|:---
[<span data-ttu-id="8a61c-112">경고 큐 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="8a61c-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="8a61c-113">네트워크에서 플래그가 지정된 경고 목록을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="8a61c-114">경고 관리</span><span class="sxs-lookup"><span data-stu-id="8a61c-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="8a61c-115">경고 상태를 변경하고 보안 작업 구성원에게 경고를 할당하는 등의 경고를 관리하는 방법에 대해 알아보고 경고 기록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="8a61c-116">경고 조사</span><span class="sxs-lookup"><span data-stu-id="8a61c-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="8a61c-117">네트워크에 영향을 주는 경고를 조사하고 해당 경고의 의미와 경고를 해결하는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="8a61c-118">파일 조사</span><span class="sxs-lookup"><span data-stu-id="8a61c-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="8a61c-119">특정 경고, 동작 또는 이벤트와 관련된 파일의 세부 정보를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="8a61c-120">장치 조사</span><span class="sxs-lookup"><span data-stu-id="8a61c-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="8a61c-121">특정 경고, 동작 또는 이벤트와 관련된 장치의 세부 정보를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="8a61c-122">IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="8a61c-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="8a61c-123">네트워크의 장치와 외부 IP(인터넷 프로토콜) 주소 간의 통신을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="8a61c-124">도메인 조사</span><span class="sxs-lookup"><span data-stu-id="8a61c-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="8a61c-125">도메인을 조사하여 네트워크의 장치와 서버가 알려진 악성 도메인과 통신하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="8a61c-126">사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="8a61c-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="8a61c-127">가장 활발한 경고가 있는 사용자 계정을 식별하고 잠재적으로 손상된 자격 증명의 사례를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="8a61c-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


