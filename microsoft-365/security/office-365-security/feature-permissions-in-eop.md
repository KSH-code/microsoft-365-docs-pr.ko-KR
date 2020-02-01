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
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599315"
---
# <a name="feature-permissions-in-eop"></a><span data-ttu-id="70b75-103">EOP의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="70b75-103">Feature permissions in EOP</span></span>

<span data-ttu-id="70b75-104">EOP (Exchange Online Protection)를 관리 하기 위한 작업을 수행 하는 데 필요한 사용 권한은 관리 대상 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="70b75-104">The permissions required to perform tasks to manage Exchange Online Protection (EOP) vary depending on the feature you are managing.</span></span>

<span data-ttu-id="70b75-105">EOP를 설정하려면 Office 365 전역 관리자 또는 Exchange 회사 관리자(조직 관리 역할 그룹)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b75-105">To set up EOP, you must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

## <a name="exchange-online-protection-permissions"></a><span data-ttu-id="70b75-106">Exchange Online Protection 사용 권한</span><span class="sxs-lookup"><span data-stu-id="70b75-106">Exchange Online Protection permissions</span></span>

<span data-ttu-id="70b75-p101">EOP 기능을 관리하는 데 필요한 사용 권한을 확인하려면 다음 표를 참조하세요. 하나의 기능에 둘 이상의 역할 그룹이 나열되는 경우 기능을 사용할 역할 그룹 중 하나만 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b75-p101">To find out what permissions you need to manage EOP features, see the following table. If a feature lists more than one role group, you only need to be assigned one of the role groups to use the feature.</span></span>

|<span data-ttu-id="70b75-109">**기능**</span><span class="sxs-lookup"><span data-stu-id="70b75-109">**Feature**</span></span>|<span data-ttu-id="70b75-110">**필요한 권한**</span><span class="sxs-lookup"><span data-stu-id="70b75-110">**Permissions required**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70b75-111">맬웨어 방지</span><span class="sxs-lookup"><span data-stu-id="70b75-111">Anti-malware</span></span>|<span data-ttu-id="70b75-112">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-112">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-113">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-113">Hygiene Management</span></span>|
|<span data-ttu-id="70b75-114">스팸 방지</span><span class="sxs-lookup"><span data-stu-id="70b75-114">Anti-spam</span></span>|<span data-ttu-id="70b75-115">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-115">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-116">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-116">Hygiene Management</span></span>|
|<span data-ttu-id="70b75-117">메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="70b75-117">Mail flow rules</span></span>|<span data-ttu-id="70b75-118">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-118">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-119">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-119">Records Management</span></span>|
|<span data-ttu-id="70b75-120">도메인</span><span class="sxs-lookup"><span data-stu-id="70b75-120">Domains</span></span>|<span data-ttu-id="70b75-121">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-121">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-122">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-122">View-Only Organization Management</span></span>|
|<span data-ttu-id="70b75-123">ATP (Advanced Threat Protection)</span><span class="sxs-lookup"><span data-stu-id="70b75-123">Advanced Threat Protection (ATP)</span></span>|<span data-ttu-id="70b75-124">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-124">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-125">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-125">Hygiene Management</span></span>|
|<span data-ttu-id="70b75-126">Office 365 커넥터</span><span class="sxs-lookup"><span data-stu-id="70b75-126">Office 365 connectors</span></span>|<span data-ttu-id="70b75-127">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-127">Organization Management</span></span>|
|<span data-ttu-id="70b75-128">Message trace</span><span class="sxs-lookup"><span data-stu-id="70b75-128">Message trace</span></span>|<span data-ttu-id="70b75-129">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-129">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-130">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-130">View-Only Organization Management</span></span>|
|<span data-ttu-id="70b75-131">조직 구성</span><span class="sxs-lookup"><span data-stu-id="70b75-131">Organization configuration</span></span>|<span data-ttu-id="70b75-132">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-132">Organization Management</span></span>|
|<span data-ttu-id="70b75-133">격리</span><span class="sxs-lookup"><span data-stu-id="70b75-133">Quarantine</span></span>|<span data-ttu-id="70b75-134">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-134">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-135">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-135">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-136">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-136">Hygiene Management</span></span>|
|<span data-ttu-id="70b75-137">사용자, 연락처 및 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="70b75-137">Users, Contacts, and Role Groups</span></span>|<span data-ttu-id="70b75-138">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-138">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-139">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-139">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-140">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-140">Hygiene Management</span></span>|
|<span data-ttu-id="70b75-141">메일 그룹 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="70b75-141">Distribution Groups and Security Groups</span></span>|<span data-ttu-id="70b75-142">조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-142">Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-143">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-143">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="70b75-144">예방 조치 관리</span><span class="sxs-lookup"><span data-stu-id="70b75-144">Hygiene Management</span></span>|
|<span data-ttu-id="70b75-145">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="70b75-145">View reports</span></span>|<span data-ttu-id="70b75-146">조직 관리: 메일 보호 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70b75-146">Organization Management: Access to mail protection reports.</span></span> <br/><br/> <span data-ttu-id="70b75-147">보기 전용 받는 사람: 메일 보호 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70b75-147">View-Only Recipients: Access to mail protection reports.</span></span>  <br/><br/> <span data-ttu-id="70b75-148">준수 관리: 메일 보호 보고서 및 DLP (데이터 손실 방지) 보고서에 액세스 합니다 (구독에 DLP 기능이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="70b75-148">Compliance Management: Access to mail protection reports and Data Loss Prevention (DLP) reports (if your subscription has DLP capabilities).</span></span>|
