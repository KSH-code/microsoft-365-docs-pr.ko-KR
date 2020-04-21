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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 비즈니스용 Microsoft 365에서 관리 홈의 장치 작업 목록에 있는 다양 한 장치 상태에 대해 알아봅니다.
ms.openlocfilehash: 1a66e76dd3a74428923292427b01551db2449e48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627249"
---
# <a name="device-states"></a><span data-ttu-id="64b72-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="64b72-103">Device states</span></span>

<span data-ttu-id="64b72-104">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="64b72-106">**상태**</span><span class="sxs-lookup"><span data-stu-id="64b72-106">**Status**</span></span>|<span data-ttu-id="64b72-107">**설명**</span><span class="sxs-lookup"><span data-stu-id="64b72-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64b72-108">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="64b72-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="64b72-109">Microsoft 365 Business Premium에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="64b72-110">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="64b72-110">Retire pending</span></span>  <br/> |<span data-ttu-id="64b72-111">Microsoft 365 Business Premium이 장치에서 회사 데이터를 제거 하기 위해 준비 중입니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="64b72-112">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="64b72-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="64b72-113">Microsoft 365 Business Premium이 현재 장치에서 회사 데이터를 제거 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="64b72-114">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="64b72-114">Retire failed</span></span>  <br/> | <span data-ttu-id="64b72-115">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="64b72-116">사용 중지 취소 됨</span><span class="sxs-lookup"><span data-stu-id="64b72-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="64b72-117">사용 중지 작업이 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="64b72-118">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="64b72-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="64b72-119">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="64b72-120">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="64b72-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="64b72-121">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="64b72-122">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="64b72-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="64b72-123">공장 초기화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="64b72-124">닦아내기 취소</span><span class="sxs-lookup"><span data-stu-id="64b72-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="64b72-125">공장 초기화가 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="64b72-126">비정상</span><span class="sxs-lookup"><span data-stu-id="64b72-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="64b72-127">작업은 보류 중 (또는 진행 중) 이지만 장치가 30 + 일 동안 체크 인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="64b72-128">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="64b72-128">Delete pending</span></span>  <br/> |<span data-ttu-id="64b72-129">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="64b72-130">검색됨</span><span class="sxs-lookup"><span data-stu-id="64b72-130">Discovered</span></span>  <br/> |<span data-ttu-id="64b72-131">Microsoft 365 Business Premium이 장치를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="64b72-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
