---
title: EOP의 기능 사용 권한
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
ms.openlocfilehash: dcf56a5295f7964b2271331deb2e7f8c1ba1635e
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871854"
---
# <a name="feature-permissions-in-eop"></a><span data-ttu-id="e36b1-103">EOP의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e36b1-103">Feature permissions in EOP</span></span>

<span data-ttu-id="e36b1-104">EOP (Exchange Online Protection)를 관리 하기 위한 작업을 수행 하는 데 필요한 사용 권한은 관리 대상 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e36b1-104">The permissions required to perform tasks to manage Exchange Online Protection (EOP) vary depending on the feature you are managing.</span></span>

<span data-ttu-id="e36b1-105">EOP를 설정하려면 Office 365 전역 관리자 또는 Exchange 회사 관리자(조직 관리 역할 그룹)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36b1-105">To set up EOP, you must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

## <a name="exchange-online-protection-permissions"></a><span data-ttu-id="e36b1-106">Exchange Online Protection 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e36b1-106">Exchange Online Protection permissions</span></span>

<span data-ttu-id="e36b1-p101">EOP 기능을 관리하는 데 필요한 사용 권한을 확인하려면 다음 표를 참조하세요. 하나의 기능에 둘 이상의 역할 그룹이 나열되는 경우 기능을 사용할 역할 그룹 중 하나만 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36b1-p101">To find out what permissions you need to manage EOP features, see the following table. If a feature lists more than one role group, you only need to be assigned one of the role groups to use the feature.</span></span>

|<span data-ttu-id="e36b1-109">**기능**</span><span class="sxs-lookup"><span data-stu-id="e36b1-109">**Feature**</span></span>|<span data-ttu-id="e36b1-110">**필요한 권한**</span><span class="sxs-lookup"><span data-stu-id="e36b1-110">**Permissions required**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e36b1-111">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="e36b1-111">Anti-malware</span></span>|<span data-ttu-id="e36b1-112">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-112">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-113">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-113">Hygiene Management</span></span>|
|<span data-ttu-id="e36b1-114">스팸 방지</span><span class="sxs-lookup"><span data-stu-id="e36b1-114">Anti-spam</span></span>|<span data-ttu-id="e36b1-115">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-115">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-116">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-116">Hygiene Management</span></span>|
|<span data-ttu-id="e36b1-117">메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="e36b1-117">Mail flow rules</span></span>|<span data-ttu-id="e36b1-118">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-118">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-119">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-119">Records Management</span></span>|
|<span data-ttu-id="e36b1-120">도메인</span><span class="sxs-lookup"><span data-stu-id="e36b1-120">Domains</span></span>|<span data-ttu-id="e36b1-121">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-121">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-122">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-122">View-Only Organization Management</span></span>|
|<span data-ttu-id="e36b1-123">ATP (Advanced Threat Protection)</span><span class="sxs-lookup"><span data-stu-id="e36b1-123">Advanced Threat Protection (ATP)</span></span>|<span data-ttu-id="e36b1-124">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-124">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-125">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-125">Hygiene Management</span></span>|
|<span data-ttu-id="e36b1-126">Office 365 커넥터</span><span class="sxs-lookup"><span data-stu-id="e36b1-126">Office 365 connectors</span></span>|<span data-ttu-id="e36b1-127">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-127">Organization Management</span></span>|
|<span data-ttu-id="e36b1-128">Message trace</span><span class="sxs-lookup"><span data-stu-id="e36b1-128">Message trace</span></span>|<span data-ttu-id="e36b1-129">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-129">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-130">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-130">View-Only Organization Management</span></span>|
|<span data-ttu-id="e36b1-131">조직 구성</span><span class="sxs-lookup"><span data-stu-id="e36b1-131">Organization configuration</span></span>|<span data-ttu-id="e36b1-132">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-132">Organization Management</span></span>|
|<span data-ttu-id="e36b1-133">격리</span><span class="sxs-lookup"><span data-stu-id="e36b1-133">Quarantine</span></span>|<span data-ttu-id="e36b1-134">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-134">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-135">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-135">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-136">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-136">Hygiene Management</span></span>|
|<span data-ttu-id="e36b1-137">사용자, 연락처 및 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="e36b1-137">Users, Contacts, and Role Groups</span></span>|<span data-ttu-id="e36b1-138">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-138">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-139">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-139">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-140">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-140">Hygiene Management</span></span>|
|<span data-ttu-id="e36b1-141">메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="e36b1-141">Distribution Groups and Security Groups</span></span>|<span data-ttu-id="e36b1-142">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-142">Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-143">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-143">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="e36b1-144">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="e36b1-144">Hygiene Management</span></span>|
|<span data-ttu-id="e36b1-145">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="e36b1-145">View reports</span></span>|<span data-ttu-id="e36b1-146">조직 관리: 메일 보호 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36b1-146">Organization Management: Access to mail protection reports.</span></span> <br/><br/> <span data-ttu-id="e36b1-147">보기 전용 받는 사람: 메일 보호 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e36b1-147">View-Only Recipients: Access to mail protection reports.</span></span>  <br/><br/> <span data-ttu-id="e36b1-148">준수 관리: 메일 보호 보고서 및 DLP (데이터 손실 방지) 보고서에 액세스 합니다 (구독에 DLP 기능이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="e36b1-148">Compliance Management: Access to mail protection reports and Data Loss Prevention (DLP) reports (if your subscription has DLP capabilities).</span></span>|
