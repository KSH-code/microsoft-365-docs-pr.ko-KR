---
title: Office 365의 재구성 작업 자동화 조사 및 응답
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능의 수정 작업에 대해 알아봅니다.
ms.openlocfilehash: e75ef1523247cbddcf6cb28d69a889db1de8e42f
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228534"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="a7e2e-104">Office 365의 자동화 된 조사에 따라 수정 작업</span><span class="sxs-lookup"><span data-stu-id="a7e2e-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions-overview"></a><span data-ttu-id="a7e2e-105">재구성 작업 개요</span><span class="sxs-lookup"><span data-stu-id="a7e2e-105">Remediation actions overview</span></span>

<span data-ttu-id="a7e2e-106">Office 365의 [자동화 된 조사 및 응답 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Advanced Threat Protection은 특정 수정 작업을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="a7e2e-107">자동 조사가 실행 중이거나 완료 된 경우에는 일반적으로 보안 운영 팀의 승인이 요구 되는 하나 이상의 수정 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="a7e2e-108">다음 표에서는 현재 Office 365 Advanced Threat Protection에서 사용할 수 있는 수정 작업을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="a7e2e-109">작업</span><span class="sxs-lookup"><span data-stu-id="a7e2e-109">Action</span></span> | <span data-ttu-id="a7e2e-110">설명</span><span class="sxs-lookup"><span data-stu-id="a7e2e-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="a7e2e-111">차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="a7e2e-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="a7e2e-112">악성 Url이 포함 된 전자 메일 및 문서에 대해 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="a7e2e-113">이렇게 하면 사용자가 기존 Office 파일 또는 이전 전자 메일 메시지의 링크를 클릭할 때 [안전한 링크](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 를 통해 악성 링크 및 관련 웹 페이지를 차단 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="a7e2e-114">전자 메일 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="a7e2e-114">Soft delete email</span></span>  |<span data-ttu-id="a7e2e-115">사용자 사서함에서 특정 전자 메일 메시지 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="a7e2e-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="a7e2e-116">전자 메일 클러스터 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="a7e2e-116">Soft delete email clusters</span></span>  |<span data-ttu-id="a7e2e-117">모든 사용자의 사서함에서 쿼리와 일치 하는 악성 전자 메일 메시지를 소프트 삭제</span><span class="sxs-lookup"><span data-stu-id="a7e2e-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="a7e2e-118">외부 메일 전달 해제</span><span class="sxs-lookup"><span data-stu-id="a7e2e-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="a7e2e-119">특정 최종 사용자의 사서함에서 전달 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="a7e2e-120">보류 중인 작업 승인 (또는 거부)</span><span class="sxs-lookup"><span data-stu-id="a7e2e-120">Approve (or reject) pending actions</span></span>

![AIR 조사 작업 페이지](../../media/air-investigationactionspage.png)

<span data-ttu-id="a7e2e-122">[조사 세부 정보](air-view-investigation-results.md)를 볼 때 보류 중인 모든 수정 작업을 승인 하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="a7e2e-123">자동 조사가 완료 되도록 가능한 한 빨리이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e2e-124">재구성 작업을 승인 하거나 거부 하려면 적절 한 사용 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="a7e2e-125">[AIR 기능을 사용 하려면 필수 권한을](office-365-air.md#required-permissions-to-use-air-capabilities)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="a7e2e-126">**작업** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="a7e2e-127">목록에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-127">Select an item in the list.</span></span> <span data-ttu-id="a7e2e-128">승인 및 거부 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="a7e2e-129">선택한 항목에 대해 사용 가능한 정보를 검토 하 고 작업을 승인 하거나 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="a7e2e-130">**승인** 을 사용 하 여 업데이트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="a7e2e-131">**거부** 는 추가 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e2e-131">**Reject** takes no further action</span></span>

## <a name="related-articles"></a><span data-ttu-id="a7e2e-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="a7e2e-132">Related articles</span></span>

[<span data-ttu-id="a7e2e-133">Microsoft Threat Protection의 자동화 된 조사 및 응답에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="a7e2e-133">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)