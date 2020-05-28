---
title: 장치 상태
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 비즈니스용 Microsoft 365에서 관리 홈의 장치 작업 목록에 있는 다양 한 장치 상태에 대해 알아봅니다.
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400957"
---
# <a name="device-states"></a><span data-ttu-id="df44d-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="df44d-103">Device states</span></span>

<span data-ttu-id="df44d-104">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="df44d-106">**상태**</span><span class="sxs-lookup"><span data-stu-id="df44d-106">**Status**</span></span>|<span data-ttu-id="df44d-107">**설명**</span><span class="sxs-lookup"><span data-stu-id="df44d-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df44d-108">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="df44d-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="df44d-109">Microsoft 365 Business Premium에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="df44d-110">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="df44d-110">Retire pending</span></span>  <br/> |<span data-ttu-id="df44d-111">Microsoft 365 Business Premium이 장치에서 회사 데이터를 제거 하기 위해 준비 중입니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="df44d-112">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="df44d-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="df44d-113">Microsoft 365 Business Premium이 현재 장치에서 회사 데이터를 제거 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="df44d-114">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="df44d-114">Retire failed</span></span>  <br/> | <span data-ttu-id="df44d-115">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="df44d-116">사용 중지 취소 됨</span><span class="sxs-lookup"><span data-stu-id="df44d-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="df44d-117">사용 중지 작업이 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="df44d-118">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="df44d-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="df44d-119">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="df44d-120">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="df44d-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="df44d-121">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="df44d-122">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="df44d-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="df44d-123">공장 초기화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="df44d-124">닦아내기 취소</span><span class="sxs-lookup"><span data-stu-id="df44d-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="df44d-125">공장 초기화가 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="df44d-126">비정상</span><span class="sxs-lookup"><span data-stu-id="df44d-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="df44d-127">작업은 보류 중 (또는 진행 중) 이지만 장치가 30 + 일 동안 체크 인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="df44d-128">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="df44d-128">Delete pending</span></span>  <br/> |<span data-ttu-id="df44d-129">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="df44d-130">검색됨</span><span class="sxs-lookup"><span data-stu-id="df44d-130">Discovered</span></span>  <br/> |<span data-ttu-id="df44d-131">Microsoft 365 Business Premium이 장치를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="df44d-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
