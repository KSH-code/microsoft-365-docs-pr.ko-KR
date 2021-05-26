---
title: DLP 정책에서 민감도 레이블을 조건으로 사용
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: DLP 정책에서 민감도 레이블을 조건으로 사용할 수 있는 서비스 및 항목 형식에 대해 배워봅니다.
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651095"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="2b106-103">DLP 정책에서 민감도 레이블을 조건으로 사용</span><span class="sxs-lookup"><span data-stu-id="2b106-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="2b106-104">[민감도 레이블](sensitivity-labels.md)을 이들 위치에서 DLP 정책의 조건으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="2b106-105">Exchange Online 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="2b106-105">Exchange Online email messages</span></span>
- <span data-ttu-id="2b106-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b106-106">SharePoint Online</span></span>
- <span data-ttu-id="2b106-107">비즈니스용 OneDrive 사이트</span><span class="sxs-lookup"><span data-stu-id="2b106-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="2b106-108">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="2b106-108">Windows 10 devices</span></span>

<span data-ttu-id="2b106-109">민감도 레이블은 **콘텐츠가 포함하는** 목록에 옵션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b106-110">![조건으로서의 민감도 레이블](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="2b106-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b106-111">DLP 정책을 적용할 위치로 **Teams 대화 및 채널 메시지** 를 선택한 경우 조건별 **민감도 레이블** 을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="2b106-112">지원되는 항목, 시나리오 및 정책 팁</span><span class="sxs-lookup"><span data-stu-id="2b106-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="2b106-113">이러한 항목 및 이러한 시나리오에 대해 민감도 레이블을 조건으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="2b106-114">지원되는 항목</span><span class="sxs-lookup"><span data-stu-id="2b106-114">Supported items</span></span>

|<span data-ttu-id="2b106-115">서비스</span><span class="sxs-lookup"><span data-stu-id="2b106-115">Service</span></span>  |<span data-ttu-id="2b106-116">항목 종류</span><span class="sxs-lookup"><span data-stu-id="2b106-116">Item type</span></span>  |<span data-ttu-id="2b106-117">사용 가능한 정책 팁</span><span class="sxs-lookup"><span data-stu-id="2b106-117">Available to policy tip</span></span>  |<span data-ttu-id="2b106-118">적용 가능</span><span class="sxs-lookup"><span data-stu-id="2b106-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="2b106-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="2b106-119">Exchange</span></span>    |<span data-ttu-id="2b106-120">전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="2b106-120">email message</span></span>         |<span data-ttu-id="2b106-121">예</span><span class="sxs-lookup"><span data-stu-id="2b106-121">yes</span></span>         |<span data-ttu-id="2b106-122">예</span><span class="sxs-lookup"><span data-stu-id="2b106-122">yes</span></span>         |
|<span data-ttu-id="2b106-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="2b106-123">Exchange</span></span>    |<span data-ttu-id="2b106-124">전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="2b106-124">email attachment</span></span>         |<span data-ttu-id="2b106-125">아니요</span><span class="sxs-lookup"><span data-stu-id="2b106-125">no</span></span>         |<span data-ttu-id="2b106-126">예\*</span><span class="sxs-lookup"><span data-stu-id="2b106-126">yes \*</span></span>         |
|<span data-ttu-id="2b106-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b106-127">SharePoint Online</span></span>     |<span data-ttu-id="2b106-128">SharePoint Online의 항목</span><span class="sxs-lookup"><span data-stu-id="2b106-128">items in SharePoint Online</span></span>         |<span data-ttu-id="2b106-129">예</span><span class="sxs-lookup"><span data-stu-id="2b106-129">yes</span></span>         |<span data-ttu-id="2b106-130">예</span><span class="sxs-lookup"><span data-stu-id="2b106-130">yes</span></span>         |
|<span data-ttu-id="2b106-131">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="2b106-131">OneDrive for Business</span></span>     |<span data-ttu-id="2b106-132">항목</span><span class="sxs-lookup"><span data-stu-id="2b106-132">items</span></span>         |<span data-ttu-id="2b106-133">예</span><span class="sxs-lookup"><span data-stu-id="2b106-133">yes</span></span>         |<span data-ttu-id="2b106-134">예</span><span class="sxs-lookup"><span data-stu-id="2b106-134">yes</span></span>         |
|<span data-ttu-id="2b106-135">Teams</span><span class="sxs-lookup"><span data-stu-id="2b106-135">Teams</span></span>     |<span data-ttu-id="2b106-136">Teams 채팅 및 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="2b106-136">Teams and channel messages</span></span>         |<span data-ttu-id="2b106-137">해당 없음</span><span class="sxs-lookup"><span data-stu-id="2b106-137">not applicable</span></span>         |<span data-ttu-id="2b106-138">해당 없음</span><span class="sxs-lookup"><span data-stu-id="2b106-138">not applicable</span></span>         |
|<span data-ttu-id="2b106-139">Teams</span><span class="sxs-lookup"><span data-stu-id="2b106-139">Teams</span></span>     |<span data-ttu-id="2b106-140">첨부 파일</span><span class="sxs-lookup"><span data-stu-id="2b106-140">attachments</span></span>         |<span data-ttu-id="2b106-141">예 \*\*</span><span class="sxs-lookup"><span data-stu-id="2b106-141">yes \*\*</span></span>         |<span data-ttu-id="2b106-142">예 \*\*</span><span class="sxs-lookup"><span data-stu-id="2b106-142">yes \*\*</span></span>         |
|<span data-ttu-id="2b106-143">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="2b106-143">Windows 10 devices</span></span>     |<span data-ttu-id="2b106-144">항목</span><span class="sxs-lookup"><span data-stu-id="2b106-144">items</span></span>         |<span data-ttu-id="2b106-145">예</span><span class="sxs-lookup"><span data-stu-id="2b106-145">yes</span></span>         |<span data-ttu-id="2b106-146">예</span><span class="sxs-lookup"><span data-stu-id="2b106-146">yes</span></span>         |
|<span data-ttu-id="2b106-147">MCAS (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2b106-147">MCAS (preview)</span></span> |<span data-ttu-id="2b106-148">항목</span><span class="sxs-lookup"><span data-stu-id="2b106-148">items</span></span>         |<span data-ttu-id="2b106-149">예</span><span class="sxs-lookup"><span data-stu-id="2b106-149">yes</span></span>         |<span data-ttu-id="2b106-150">예</span><span class="sxs-lookup"><span data-stu-id="2b106-150">yes</span></span>         |

<span data-ttu-id="2b106-151">민감도 레이블이 부착된 전자 메일 첨부 파일의 \* DLP 감지는 Office 파일 형식에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="2b106-152">\*\* 1:1 채팅 혹은 채널을 통해 Teams 로 보낸 첨부 파일은 비즈니스용 One drive 및 SharePoint에 자동으로 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="2b106-153">따라서 SharePoint Online 또는 비즈니스용 One Drive가 DLP 정책에서 위치로 포함되는 경우, Teams에서 보낸 레이블이 지정된 첨부 파일은 이 조건의 범위에 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="2b106-154">DLP 정책에서 Teams를 위치로 선택할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="2b106-155">지원되는 시나리오</span><span class="sxs-lookup"><span data-stu-id="2b106-155">Supported scenarios</span></span>

- <span data-ttu-id="2b106-156">DLP 관리자는 하나 이상의 민감도 레이블을 조건으로 포함하도록 선택할 때 테넌트의 모든 민감도 레이블 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="2b106-157">위의 지원 매트릭스에 표시된 대로 민감도 레이블을 조건으로 사용하는 것은 모든 워크로드에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="2b106-158">DLP 정책 팁은 민감도 레이블을 조건으로 포함하는 DLP 정책에 대해 작업 전반에 결쳐 계속해서 표시됩니다(Outlook Win32 제외)</span><span class="sxs-lookup"><span data-stu-id="2b106-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="2b106-159">민감도 레이블이 조건과 일치하는 DLP 정책에서 일치하는 경우 민감도 레이블도 인시던트 보고서 전자 메일의 일부로서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="2b106-160">민감도 레이블 세부 정보는 또한 민감도 레이블이 조건으로 포함된 DLP 정책 일치에 대한 DLP 규칙 일치 감사 로그에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b106-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="2b106-161">지원 정책 팁</span><span class="sxs-lookup"><span data-stu-id="2b106-161">Support policy tips</span></span>


|<span data-ttu-id="2b106-162">워크로드</span><span class="sxs-lookup"><span data-stu-id="2b106-162">Workload</span></span>  |<span data-ttu-id="2b106-163">지원되는/지원되지 않는 정책 팁</span><span class="sxs-lookup"><span data-stu-id="2b106-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="2b106-164">OWA</span><span class="sxs-lookup"><span data-stu-id="2b106-164">OWA</span></span> |    <span data-ttu-id="2b106-165">지원</span><span class="sxs-lookup"><span data-stu-id="2b106-165">supported</span></span>     |
|<span data-ttu-id="2b106-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="2b106-166">Outlook Win 32</span></span>    |  <span data-ttu-id="2b106-167">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="2b106-167">not supported</span></span>       |
|<span data-ttu-id="2b106-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2b106-168">SharePoint</span></span>   |   <span data-ttu-id="2b106-169">지원</span><span class="sxs-lookup"><span data-stu-id="2b106-169">supported</span></span>      |
|<span data-ttu-id="2b106-170">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="2b106-170">OneDrive for Business</span></span>    |    <span data-ttu-id="2b106-171">지원</span><span class="sxs-lookup"><span data-stu-id="2b106-171">supported</span></span>     |
|<span data-ttu-id="2b106-172">끝점 장치</span><span class="sxs-lookup"><span data-stu-id="2b106-172">endpoint devices</span></span>   |  <span data-ttu-id="2b106-173">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="2b106-173">not supported</span></span>       |
