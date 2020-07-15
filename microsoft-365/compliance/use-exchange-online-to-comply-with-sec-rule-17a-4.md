---
title: SEC Rule 17a-4를 준수하기 위해 Exchange Online과 보안 및 준수 센터 사용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: CFTC 규칙 1.31(c)-(d), FINRA 규칙 4511, SEC 규칙 17a-4의 규정 요구 사항을 충족하도록 Exchange Online 및 규정 준수 센터 구성
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127305"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="0d1e9-103">SEC Rule 17a-4를 준수하기 위해 Exchange Online과 보안 및 준수 센터 사용</span><span class="sxs-lookup"><span data-stu-id="0d1e9-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="0d1e9-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="0d1e9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0d1e9-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="0d1e9-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="0d1e9-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="0d1e9-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="0d1e9-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="0d1e9-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="0d1e9-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="0d1e9-111">이러한 조직이 보안 및 준수 센터가 Exchange online에 대한 규정 의무, 특히 규칙 17a-4 요구 사항을 충족하기 위해 어떻게 활용될 수 있는지 더 잘 이해할 수 있도록 Cohasset Associates와의 파트너십을 통해 평가를 발표했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="0d1e9-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="0d1e9-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="0d1e9-114">Cohasset 평가판 다운로드</span><span class="sxs-lookup"><span data-stu-id="0d1e9-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="0d1e9-115">[Cohasset 평가판을 여기에서 다운로드](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Cohasset Associates의 다운로드 가능한 평가의 제목 페이지](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="0d1e9-117">이 평가는 Exchange Online에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="0d1e9-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="0d1e9-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="0d1e9-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="0d1e9-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="0d1e9-122">보존 잠금을 사용하는 것이 권장 구성의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="0d1e9-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="0d1e9-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="0d1e9-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="0d1e9-125">보존 기간을 줄이면 보존할 수 있지만 보존 기간만 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="0d1e9-126">불변이란 필요한 보존 기간동안 해당 레코드를 덮어 쓰거나 지우거나 변경할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="0d1e9-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="0d1e9-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="0d1e9-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="0d1e9-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="0d1e9-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="0d1e9-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="0d1e9-132">정책의 보존 기간은 단축되지 않고 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="0d1e9-133">사용자를 정책에 추가할 수는 있지만 사용자를 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="0d1e9-134">보존 정책은 관리자가 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="0d1e9-135">보존 잠금 장치는 SEC 17a-4 규정 요구사항을 충족하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="0d1e9-136">보존 잠금을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="0d1e9-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="0d1e9-137">PowerShell을 사용하여 보존 정책을 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="0d1e9-138">자세한 내용은 [보존 잠금을 사용하여 규정 요구 사항 준수](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0d1e9-139">알려진 제한</span><span class="sxs-lookup"><span data-stu-id="0d1e9-139">Known limitations</span></span>

<span data-ttu-id="0d1e9-140">현재 Exchange Online에는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="0d1e9-141">팀 채팅 및 채널 메시지의 경우 스레드 통신을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="0d1e9-142">팀 채팅 및 채널 메시지에 좋아요는 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="0d1e9-143">이제 Microsoft 365 그룹 사서함에 대해 항목 수준 감사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="0d1e9-144">자세한 내용은 [사서함 감사 관리](enable-mailbox-auditing.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d1e9-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
