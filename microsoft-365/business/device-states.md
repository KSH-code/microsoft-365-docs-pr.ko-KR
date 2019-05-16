---
title: 장치 상태
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
ms.openlocfilehash: 06e5c800e6a104785c1fd0724223e05d7729722e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072723"
---
# <a name="device-states"></a><span data-ttu-id="49980-103">장치 상태</span><span class="sxs-lookup"><span data-stu-id="49980-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="49980-104">장치 상태</span><span class="sxs-lookup"><span data-stu-id="49980-104">Device states</span></span>

<span data-ttu-id="49980-105">**장치 작업** 목록(관리 홈 \> **장치 작업**)의 장치는 다음 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="49980-107">**상태**</span><span class="sxs-lookup"><span data-stu-id="49980-107">**Status**</span></span>|<span data-ttu-id="49980-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="49980-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="49980-109">Intune에서 관리</span><span class="sxs-lookup"><span data-stu-id="49980-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="49980-110">Microsoft 365 Business에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="49980-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="49980-111">사용 중지 보류 중</span><span class="sxs-lookup"><span data-stu-id="49980-111">Retire pending</span></span>  <br/> |<span data-ttu-id="49980-112">Microsoft 365 Business가 장치에서 회사 데이터를 제거하기 위해 준비 중입니다.</span><span class="sxs-lookup"><span data-stu-id="49980-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="49980-113">사용 중지 진행 중</span><span class="sxs-lookup"><span data-stu-id="49980-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="49980-114">Microsoft 365 Business가 현재 장치에서 회사 데이터를 제거 중입니다.</span><span class="sxs-lookup"><span data-stu-id="49980-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="49980-115">사용 중지 실패</span><span class="sxs-lookup"><span data-stu-id="49980-115">Retire failed</span></span>  <br/> | <span data-ttu-id="49980-116">회사 데이터 제거 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="49980-117">사용 중지 취소됨</span><span class="sxs-lookup"><span data-stu-id="49980-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="49980-118">사용 중지 작업이 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="49980-119">초기화 보류 중</span><span class="sxs-lookup"><span data-stu-id="49980-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="49980-120">초기화를 시작하기 위해 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="49980-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="49980-121">초기화 진행 중</span><span class="sxs-lookup"><span data-stu-id="49980-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="49980-122">초기화가 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="49980-123">초기화 실패</span><span class="sxs-lookup"><span data-stu-id="49980-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="49980-124">초기화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="49980-125">초기화 취소됨</span><span class="sxs-lookup"><span data-stu-id="49980-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="49980-126">초기화가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="49980-127">비정상</span><span class="sxs-lookup"><span data-stu-id="49980-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="49980-128">작업이 보류 중(또는 진행 중)이지만, 장치가 30 이상 체크 인하지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="49980-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="49980-129">삭제 보류 중</span><span class="sxs-lookup"><span data-stu-id="49980-129">Delete pending</span></span>  <br/> |<span data-ttu-id="49980-130">삭제 작업이 보류 중입니다.</span><span class="sxs-lookup"><span data-stu-id="49980-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="49980-131">검색됨</span><span class="sxs-lookup"><span data-stu-id="49980-131">Discovered</span></span>  <br/> |<span data-ttu-id="49980-132">Microsoft 365 Business가 장치를 검색했습니다.</span><span class="sxs-lookup"><span data-stu-id="49980-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
