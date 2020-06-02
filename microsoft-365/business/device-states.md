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
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471182"
---
# <a name="device-states"></a><span data-ttu-id="44ed4-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="44ed4-103">Device states</span></span>

<span data-ttu-id="44ed4-104">이 문서는 Microsoft 365 Business Premium에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="44ed4-105">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="44ed4-107">**상태**</span><span class="sxs-lookup"><span data-stu-id="44ed4-107">**Status**</span></span>|<span data-ttu-id="44ed4-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="44ed4-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44ed4-109">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="44ed4-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="44ed4-110">Microsoft 365 Business Premium에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="44ed4-111">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="44ed4-111">Retire pending</span></span>  <br/> |<span data-ttu-id="44ed4-112">Microsoft 365 Business Premium이 장치에서 회사 데이터를 제거 하기 위해 준비 중입니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="44ed4-113">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="44ed4-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="44ed4-114">Microsoft 365 Business Premium이 현재 장치에서 회사 데이터를 제거 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="44ed4-115">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="44ed4-115">Retire failed</span></span>  <br/> | <span data-ttu-id="44ed4-116">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="44ed4-117">사용 중지 취소 됨</span><span class="sxs-lookup"><span data-stu-id="44ed4-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="44ed4-118">사용 중지 작업이 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="44ed4-119">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="44ed4-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="44ed4-120">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="44ed4-121">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="44ed4-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="44ed4-122">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="44ed4-123">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="44ed4-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="44ed4-124">공장 초기화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="44ed4-125">닦아내기 취소</span><span class="sxs-lookup"><span data-stu-id="44ed4-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="44ed4-126">공장 초기화가 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="44ed4-127">비정상</span><span class="sxs-lookup"><span data-stu-id="44ed4-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="44ed4-128">작업은 보류 중 (또는 진행 중) 이지만 장치가 30 + 일 동안 체크 인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="44ed4-129">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="44ed4-129">Delete pending</span></span>  <br/> |<span data-ttu-id="44ed4-130">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="44ed4-131">검색됨</span><span class="sxs-lookup"><span data-stu-id="44ed4-131">Discovered</span></span>  <br/> |<span data-ttu-id="44ed4-132">Microsoft 365 Business Premium이 장치를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44ed4-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
