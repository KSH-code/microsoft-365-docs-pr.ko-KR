---
title: 장치 상태
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: 비즈니스용 Microsoft 365의 관리 홈의 장치 작업 목록에서 다양한 장치 상태 관련 정보를 확인합니다.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578470"
---
# <a name="device-states"></a><span data-ttu-id="685e4-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="685e4-103">Device states</span></span>

<span data-ttu-id="685e4-104">이 문서는 Microsoft 365 Business Premium에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="685e4-105">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="685e4-107">**상태**</span><span class="sxs-lookup"><span data-stu-id="685e4-107">**Status**</span></span>|<span data-ttu-id="685e4-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="685e4-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="685e4-109">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="685e4-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="685e4-110">Microsoft 365 Business Premium에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="685e4-111">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="685e4-111">Retire pending</span></span>  <br/> |<span data-ttu-id="685e4-112">Microsoft 365 Business Premium이 장치에서 회사 데이터를 제거할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="685e4-113">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="685e4-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="685e4-114">Microsoft 365 Business Premium이 현재 장치에서 회사 데이터를 제거하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="685e4-115">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="685e4-115">Retire failed</span></span>  <br/> | <span data-ttu-id="685e4-116">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="685e4-117">사용 중지 취소</span><span class="sxs-lookup"><span data-stu-id="685e4-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="685e4-118">사용 중지 작업이 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="685e4-119">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="685e4-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="685e4-120">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="685e4-121">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="685e4-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="685e4-122">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="685e4-123">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="685e4-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="685e4-124">초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="685e4-125">지우기 취소</span><span class="sxs-lookup"><span data-stu-id="685e4-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="685e4-126">초기화가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="685e4-127">비정상</span><span class="sxs-lookup"><span data-stu-id="685e4-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="685e4-128">작업이 보류 중(또는 진행 중)이지만 장치가 30일 이상 체크 인되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="685e4-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="685e4-129">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="685e4-129">Delete pending</span></span>  <br/> |<span data-ttu-id="685e4-130">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="685e4-131">검색됨</span><span class="sxs-lookup"><span data-stu-id="685e4-131">Discovered</span></span>  <br/> |<span data-ttu-id="685e4-132">Microsoft 365 Business Premium에서 장치를 검색했습니다.</span><span class="sxs-lookup"><span data-stu-id="685e4-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
