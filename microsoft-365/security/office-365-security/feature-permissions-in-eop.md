---
title: EOP의 기능 사용 권한
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Microsoft EOP(Exchange Online Protection)를 관리하기 위한 작업을 수행하는 데 필요한 사용 권한은 관리 대상 기능에 따라 다릅니다.
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638121"
---
# <a name="feature-permissions-in-eop"></a><span data-ttu-id="465ab-103">EOP의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="465ab-103">Feature permissions in EOP</span></span>

<span data-ttu-id="465ab-104">EOP (Exchange Online Protection)를 관리 하기 위한 작업을 수행 하는 데 필요한 사용 권한은 관리 대상 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="465ab-104">The permissions required to perform tasks to manage Exchange Online Protection (EOP) vary depending on the feature you are managing.</span></span>

<span data-ttu-id="465ab-105">EOP를 설정 하려면 전역 관리자 또는 Exchange 회사 관리자 (조직 관리 역할 그룹) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="465ab-105">To set up EOP, you must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

## <a name="exchange-online-protection-permissions"></a><span data-ttu-id="465ab-106">Exchange Online Protection 사용 권한</span><span class="sxs-lookup"><span data-stu-id="465ab-106">Exchange Online Protection permissions</span></span>

<span data-ttu-id="465ab-p101">EOP 기능을 관리하는 데 필요한 사용 권한을 확인하려면 다음 표를 참조하세요. 하나의 기능에 둘 이상의 역할 그룹이 나열되는 경우 기능을 사용할 역할 그룹 중 하나만 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="465ab-p101">To find out what permissions you need to manage EOP features, see the following table. If a feature lists more than one role group, you only need to be assigned one of the role groups to use the feature.</span></span>

|<span data-ttu-id="465ab-109">**기능**</span><span class="sxs-lookup"><span data-stu-id="465ab-109">**Feature**</span></span>|<span data-ttu-id="465ab-110">**필요한 권한**</span><span class="sxs-lookup"><span data-stu-id="465ab-110">**Permissions required**</span></span>|
|:-----|:-----|
|<span data-ttu-id="465ab-111">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="465ab-111">Anti-malware</span></span>|<span data-ttu-id="465ab-112">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-112">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-113">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-113">Hygiene Management</span></span>|
|<span data-ttu-id="465ab-114">스팸 방지</span><span class="sxs-lookup"><span data-stu-id="465ab-114">Anti-spam</span></span>|<span data-ttu-id="465ab-115">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-115">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-116">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-116">Hygiene Management</span></span>|
|<span data-ttu-id="465ab-117">메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="465ab-117">Mail flow rules</span></span>|<span data-ttu-id="465ab-118">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-118">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-119">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-119">Records Management</span></span>|
|<span data-ttu-id="465ab-120">도메인</span><span class="sxs-lookup"><span data-stu-id="465ab-120">Domains</span></span>|<span data-ttu-id="465ab-121">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-121">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-122">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-122">View-Only Organization Management</span></span>|
|<span data-ttu-id="465ab-123">ATP (Advanced Threat Protection)</span><span class="sxs-lookup"><span data-stu-id="465ab-123">Advanced Threat Protection (ATP)</span></span>|<span data-ttu-id="465ab-124">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-124">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-125">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-125">Hygiene Management</span></span>|
|<span data-ttu-id="465ab-126">Microsoft 365 커넥터</span><span class="sxs-lookup"><span data-stu-id="465ab-126">Microsoft 365 connectors</span></span>|<span data-ttu-id="465ab-127">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-127">Organization Management</span></span>|
|<span data-ttu-id="465ab-128">Message trace</span><span class="sxs-lookup"><span data-stu-id="465ab-128">Message trace</span></span>|<span data-ttu-id="465ab-129">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-129">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-130">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-130">View-Only Organization Management</span></span>|
|<span data-ttu-id="465ab-131">조직 구성</span><span class="sxs-lookup"><span data-stu-id="465ab-131">Organization configuration</span></span>|<span data-ttu-id="465ab-132">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-132">Organization Management</span></span>|
|<span data-ttu-id="465ab-133">격리</span><span class="sxs-lookup"><span data-stu-id="465ab-133">Quarantine</span></span>|<span data-ttu-id="465ab-134">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-134">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-135">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-135">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-136">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-136">Hygiene Management</span></span>|
|<span data-ttu-id="465ab-137">사용자, 연락처 및 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="465ab-137">Users, Contacts, and Role Groups</span></span>|<span data-ttu-id="465ab-138">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-138">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-139">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-139">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-140">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-140">Hygiene Management</span></span>|
|<span data-ttu-id="465ab-141">메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="465ab-141">Distribution Groups and Security Groups</span></span>|<span data-ttu-id="465ab-142">조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-142">Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-143">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-143">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="465ab-144">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="465ab-144">Hygiene Management</span></span>|
|<span data-ttu-id="465ab-145">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="465ab-145">View reports</span></span>|<span data-ttu-id="465ab-146">조직 관리: 메일 보호 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465ab-146">Organization Management: Access to mail protection reports.</span></span> <br/><br/> <span data-ttu-id="465ab-147">보기 전용 받는 사람: 메일 보호 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465ab-147">View-Only Recipients: Access to mail protection reports.</span></span>  <br/><br/> <span data-ttu-id="465ab-148">준수 관리: 메일 보호 보고서 및 DLP (데이터 손실 방지) 보고서에 액세스 합니다 (구독에 DLP 기능이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="465ab-148">Compliance Management: Access to mail protection reports and Data Loss Prevention (DLP) reports (if your subscription has DLP capabilities).</span></span>|
