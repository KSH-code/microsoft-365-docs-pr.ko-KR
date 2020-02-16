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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 Business의 장치 상태에 대해 알아봅니다.
ms.openlocfilehash: 26b218cb7b6a14f17e33d34a2e712b06ac814c0c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065772"
---
# <a name="device-states"></a><span data-ttu-id="1fae8-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="1fae8-103">Device states</span></span>

<span data-ttu-id="1fae8-104">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="1fae8-106">**상태**</span><span class="sxs-lookup"><span data-stu-id="1fae8-106">**Status**</span></span>|<span data-ttu-id="1fae8-107">**설명**</span><span class="sxs-lookup"><span data-stu-id="1fae8-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fae8-108">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="1fae8-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="1fae8-109">Microsoft 365 Business에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="1fae8-110">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="1fae8-110">Retire pending</span></span>  <br/> |<span data-ttu-id="1fae8-111">Microsoft 365 Business가 장치에서 회사 데이터를 제거하기 위해 준비 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="1fae8-112">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="1fae8-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="1fae8-113">Microsoft 365 Business가 현재 장치에서 회사 데이터를 제거 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="1fae8-114">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="1fae8-114">Retire failed</span></span>  <br/> | <span data-ttu-id="1fae8-115">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="1fae8-116">사용 중지 취소 됨</span><span class="sxs-lookup"><span data-stu-id="1fae8-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="1fae8-117">사용 중지 작업이 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="1fae8-118">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="1fae8-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="1fae8-119">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="1fae8-120">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="1fae8-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="1fae8-121">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="1fae8-122">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="1fae8-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="1fae8-123">공장 초기화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="1fae8-124">닦아내기 취소</span><span class="sxs-lookup"><span data-stu-id="1fae8-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="1fae8-125">공장 초기화가 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="1fae8-126">비정상</span><span class="sxs-lookup"><span data-stu-id="1fae8-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="1fae8-127">작업은 보류 중 (또는 진행 중) 이지만 장치가 30 + 일 동안 체크 인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="1fae8-128">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="1fae8-128">Delete pending</span></span>  <br/> |<span data-ttu-id="1fae8-129">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="1fae8-130">검색됨</span><span class="sxs-lookup"><span data-stu-id="1fae8-130">Discovered</span></span>  <br/> |<span data-ttu-id="1fae8-131">Microsoft 365 Business가 장치를 검색했습니다.</span><span class="sxs-lookup"><span data-stu-id="1fae8-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
