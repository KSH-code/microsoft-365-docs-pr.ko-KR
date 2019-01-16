---
title: 장치 상태
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 비즈니스에서 장치 상태에 대 한 설명 합니다.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869947"
---
# <a name="device-states"></a><span data-ttu-id="e222f-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="e222f-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="e222f-104">장치 상태</span><span class="sxs-lookup"><span data-stu-id="e222f-104">Device states</span></span>

<span data-ttu-id="e222f-105">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="e222f-107">**상태**</span><span class="sxs-lookup"><span data-stu-id="e222f-107">**Status**</span></span>|<span data-ttu-id="e222f-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e222f-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e222f-109">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="e222f-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="e222f-110">Microsoft 365 Business에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="e222f-111">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="e222f-111">Retire pending</span></span>  <br/> |<span data-ttu-id="e222f-112">Microsoft 365 Business가 장치에서 회사 데이터를 제거하기 위해 준비 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e222f-113">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="e222f-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="e222f-114">Microsoft 365 Business가 현재 장치에서 회사 데이터를 제거 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e222f-115">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="e222f-115">Retire failed</span></span>  <br/> | <span data-ttu-id="e222f-116">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="e222f-117">사용 중지 취소됨</span><span class="sxs-lookup"><span data-stu-id="e222f-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="e222f-118">사용 중지 작업이 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="e222f-119">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="e222f-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="e222f-120">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="e222f-121">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="e222f-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="e222f-122">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="e222f-123">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="e222f-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="e222f-124">초기화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="e222f-125">초기화 취소됨</span><span class="sxs-lookup"><span data-stu-id="e222f-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="e222f-126">초기화가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="e222f-127">비정상</span><span class="sxs-lookup"><span data-stu-id="e222f-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="e222f-128">작업이 보류 중(또는 진행 중)이지만, 장치가 30 이상 체크 인하지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="e222f-129">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="e222f-129">Delete pending</span></span>  <br/> |<span data-ttu-id="e222f-130">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="e222f-131">검색됨</span><span class="sxs-lookup"><span data-stu-id="e222f-131">Discovered</span></span>  <br/> |<span data-ttu-id="e222f-132">Microsoft 365 Business가 장치를 검색했습니다.</span><span class="sxs-lookup"><span data-stu-id="e222f-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
