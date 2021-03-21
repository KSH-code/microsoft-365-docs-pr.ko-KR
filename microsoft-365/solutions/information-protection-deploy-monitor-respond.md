---
title: 조직의 데이터 개인 정보 보호 인시던트 모니터링 및 대응
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 감사 및 경고 정책 및 데이터 주체 요청을 사용하여 개인 데이터 인시던트 모니터링 및 대응
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928427"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="07300-103">조직의 데이터 개인 정보 보호 인시던트 모니터링 및 대응</span><span class="sxs-lookup"><span data-stu-id="07300-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="07300-104">Microsoft 365 기능은 관련 기능을 운영할 때 조직의 데이터 개인 정보 인시던트 모니터링, 조사 및 대응에 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07300-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="07300-105">이러한 각 문서에 대한 프로세스, 절차 및 기타 설명서를 가지는 것은 규제 기관의 규정 준수를 입증하는 데도 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07300-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="07300-106">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="07300-106">These include:</span></span> 

- <span data-ttu-id="07300-107">감사 및 경고 정책</span><span class="sxs-lookup"><span data-stu-id="07300-107">Auditing and alert policies</span></span>
- <span data-ttu-id="07300-108">데이터 주체 요청(콘텐츠 검색 및 eDiscovery 포함)</span><span class="sxs-lookup"><span data-stu-id="07300-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="07300-109">추가 조사 도구 및 보고</span><span class="sxs-lookup"><span data-stu-id="07300-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="07300-110">모니터링 및 응답 도구 사용에 영향을 미치는 데이터 개인 정보 규정</span><span class="sxs-lookup"><span data-stu-id="07300-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="07300-111">다음은 정보 거버넌스 제어와 관련이 있을 수 있는 데이터 개인 정보 보호 규정의 샘플 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="07300-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="07300-112">LGPD 문서 46</span><span class="sxs-lookup"><span data-stu-id="07300-112">LGPD Article 46</span></span>
- <span data-ttu-id="07300-113">LGPD 문서 48</span><span class="sxs-lookup"><span data-stu-id="07300-113">LGPD Article 48</span></span>
- <span data-ttu-id="07300-114">GDPR 문서 (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="07300-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="07300-115">GDPR 문서 (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="07300-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="07300-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="07300-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="07300-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="07300-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="07300-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="07300-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="07300-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="07300-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="07300-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="07300-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="07300-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="07300-121">164.312(b))</span></span>
- <span data-ttu-id="07300-122">CCPA(1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="07300-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="07300-123">자세한 내용은 데이터 개인 정보 보호 위험 평가 [및 중요한 정보 식별을 참조하세요.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="07300-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="07300-124">데이터 개인 정보 규정은 일반적으로 모니터링 및 응답을 위해 다음을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="07300-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="07300-125">개인 데이터의 저장, 공유 및 처리와 관련된 활동에 대한 감사, 경고 및 보고</span><span class="sxs-lookup"><span data-stu-id="07300-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="07300-126">DSR(데이터 주체 요청)에 응답하고 경우에 따라 조사 및 기타 관리 조치를 수행하여 이러한 요청을 준수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07300-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="07300-127">조직은 다른 규정 준수 요구 또는 비즈니스상의 이유로 모니터링 및 대응 활동을 수행하고자 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07300-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="07300-128">데이터 개인 정보 보호에 대한 모니터링 및 응답 체계를 설정하는 것이 전체 모니터링 및 응답 계획, 구현 및 관리의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="07300-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="07300-129">데이터 개인 정보 규정에 대한 Microsoft 365의 모니터링 및 응답 체계를 시작하는 데 도움을 줄 수 있도록 이 문서에서는 Microsoft 365에서 다음 질문에 답변할 수 있는 유용한 기능을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="07300-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="07300-130">다양한 데이터 형식 및 원본에 대해 어떤 종류의 모니터링, 조사 및 보고 기술을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="07300-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="07300-131">데이터 주체 요청(DSRs)을 처리하는 데 필요한 메커니즘 및 수정 작업(예: 비음성, 수정 및 수정)입니다.</span><span class="sxs-lookup"><span data-stu-id="07300-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="07300-132">보안 및 준수 센터의 감사 및 경고 정책</span><span class="sxs-lookup"><span data-stu-id="07300-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="07300-133">감사, 고급 감사 및 경고 정책 설정에 대한 자세한 내용은 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="07300-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="07300-134">통합 감사</span><span class="sxs-lookup"><span data-stu-id="07300-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="07300-135">사서함 감사</span><span class="sxs-lookup"><span data-stu-id="07300-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="07300-136">고급 감사</span><span class="sxs-lookup"><span data-stu-id="07300-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="07300-137">알림 정책</span><span class="sxs-lookup"><span data-stu-id="07300-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="07300-138">GDPR 및 CCPA에 대한 데이터 주체 요청</span><span class="sxs-lookup"><span data-stu-id="07300-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="07300-139">Microsoft 365에서 DSR에 응답하는 데 대한 자세한 내용은 GDPR 및 [CCPA에](/compliance/regulatory/gdpr-dsr-Office365) 대한 데이터 주체 요청을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07300-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="07300-140">Microsoft Stream에서 삭제된 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="07300-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="07300-141">Microsoft Stream의 경우 사용자가 Azure AD(Azure Active Directory)에서 삭제될 때 해당 이름이 이전에 게시된 Stream 비디오와 연결된 경우 해당 전자 메일 주소는 비디오와 연결된 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07300-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="07300-142">Microsoft [Stream에서 삭제된 사용자 관리를](/stream/managing-deleted-users) 참조하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="07300-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="07300-143">조사 도구로 내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="07300-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="07300-144">[Microsoft 365의](../compliance/insider-risk-management.md) 내부자 위험 관리는 조직의 위험한 활동을 감지, 조사 및 조치를 취할 수 있도록 하여 내부 위험을 최소화하는 데 도움이 되는 Microsoft 규정 준수 관리 센터의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="07300-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>