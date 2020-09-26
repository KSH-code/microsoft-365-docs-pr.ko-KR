---
title: 민감도 레이블을 DLP 정책의 조건으로 사용(미리 보기)
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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235725"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="f2959-103">민감도 레이블을 DLP 정책의 조건으로 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f2959-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="f2959-104">[민감도 레이블](sensitivity-labels.md)을 이들 위치에서 DLP 정책의 조건으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="f2959-105">Exchange Online 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="f2959-105">Exchange Online email messages</span></span>
- <span data-ttu-id="f2959-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2959-106">SharePoint Online</span></span>
- <span data-ttu-id="f2959-107">비즈니스용 OneDrive 사이트</span><span class="sxs-lookup"><span data-stu-id="f2959-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="f2959-108">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="f2959-108">Windows 10 devices</span></span>

<span data-ttu-id="f2959-109">민감도 레이블은 \*\*콘텐츠가 포함하는 \*\* 목록에 옵션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![조건으로서의 민감도 레이블](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="f2959-111">지원되는 항목, 시나리오 및 정책 팁</span><span class="sxs-lookup"><span data-stu-id="f2959-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="f2959-112">이러한 항목 및 이러한 시나리오에 대해 민감도 레이블을 조건으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="f2959-113">지원되는 항목</span><span class="sxs-lookup"><span data-stu-id="f2959-113">Supported items</span></span>

|<span data-ttu-id="f2959-114">서비스</span><span class="sxs-lookup"><span data-stu-id="f2959-114">service</span></span>  |<span data-ttu-id="f2959-115">항목 유형</span><span class="sxs-lookup"><span data-stu-id="f2959-115">item type</span></span>  |<span data-ttu-id="f2959-116">사용 가능한 정책 팁</span><span class="sxs-lookup"><span data-stu-id="f2959-116">available to policy tip</span></span>  |<span data-ttu-id="f2959-117">적용 가능</span><span class="sxs-lookup"><span data-stu-id="f2959-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f2959-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="f2959-118">Exchange</span></span>    |<span data-ttu-id="f2959-119">전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="f2959-119">email message</span></span>         |<span data-ttu-id="f2959-120">예</span><span class="sxs-lookup"><span data-stu-id="f2959-120">yes</span></span>         |<span data-ttu-id="f2959-121">예</span><span class="sxs-lookup"><span data-stu-id="f2959-121">yes</span></span>         |
|<span data-ttu-id="f2959-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="f2959-122">Exchange</span></span>    |<span data-ttu-id="f2959-123">전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="f2959-123">email attachment</span></span>         |<span data-ttu-id="f2959-124">아니요 \*</span><span class="sxs-lookup"><span data-stu-id="f2959-124">no \*</span></span>         |<span data-ttu-id="f2959-125">아니요 \*</span><span class="sxs-lookup"><span data-stu-id="f2959-125">no \*</span></span>         |
|<span data-ttu-id="f2959-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2959-126">SharePoint Online</span></span>     |<span data-ttu-id="f2959-127">SharePoint Online의 항목</span><span class="sxs-lookup"><span data-stu-id="f2959-127">items in SharePoint Online</span></span>         |<span data-ttu-id="f2959-128">예</span><span class="sxs-lookup"><span data-stu-id="f2959-128">yes</span></span>         |<span data-ttu-id="f2959-129">예</span><span class="sxs-lookup"><span data-stu-id="f2959-129">yes</span></span>         |
|<span data-ttu-id="f2959-130">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f2959-130">OneDrive for Business</span></span>     |<span data-ttu-id="f2959-131">항목</span><span class="sxs-lookup"><span data-stu-id="f2959-131">items</span></span>         |<span data-ttu-id="f2959-132">예</span><span class="sxs-lookup"><span data-stu-id="f2959-132">yes</span></span>         |<span data-ttu-id="f2959-133">예</span><span class="sxs-lookup"><span data-stu-id="f2959-133">yes</span></span>         |
|<span data-ttu-id="f2959-134">Teams</span><span class="sxs-lookup"><span data-stu-id="f2959-134">Teams</span></span>     |<span data-ttu-id="f2959-135">Teams 채팅 및 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="f2959-135">Teams and channel messages</span></span>         |<span data-ttu-id="f2959-136">해당 없음</span><span class="sxs-lookup"><span data-stu-id="f2959-136">not applicable</span></span>         |<span data-ttu-id="f2959-137">해당 없음</span><span class="sxs-lookup"><span data-stu-id="f2959-137">not applicable</span></span>         |
|<span data-ttu-id="f2959-138">Teams</span><span class="sxs-lookup"><span data-stu-id="f2959-138">Teams</span></span>     |<span data-ttu-id="f2959-139">첨부 파일</span><span class="sxs-lookup"><span data-stu-id="f2959-139">attachements</span></span>         |<span data-ttu-id="f2959-140">예 \*\*</span><span class="sxs-lookup"><span data-stu-id="f2959-140">yes \*\*</span></span>         |<span data-ttu-id="f2959-141">예 \*\*</span><span class="sxs-lookup"><span data-stu-id="f2959-141">yes \*\*</span></span>         |
|<span data-ttu-id="f2959-142">Windows 10 장치(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f2959-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="f2959-143">항목</span><span class="sxs-lookup"><span data-stu-id="f2959-143">items</span></span>         |<span data-ttu-id="f2959-144">예</span><span class="sxs-lookup"><span data-stu-id="f2959-144">yes</span></span>         |<span data-ttu-id="f2959-145">예</span><span class="sxs-lookup"><span data-stu-id="f2959-145">yes</span></span>         |
|<span data-ttu-id="f2959-146">MCAS (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f2959-146">MCAS (preview)</span></span> |<span data-ttu-id="f2959-147">항목</span><span class="sxs-lookup"><span data-stu-id="f2959-147">items</span></span>         |<span data-ttu-id="f2959-148">예</span><span class="sxs-lookup"><span data-stu-id="f2959-148">yes</span></span>         |<span data-ttu-id="f2959-149">예</span><span class="sxs-lookup"><span data-stu-id="f2959-149">yes</span></span>         |

<span data-ttu-id="f2959-150">\* 전자 메일에 민감도 레이블의 DLP 감지가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="f2959-151">민감도 레이블이 부착된 전자 메일 첨부 파일의 DLP 감지는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="f2959-152">\*\* 1:1 채팅 혹은 채널을 통해 Teams 로 보낸 첨부 파일은 비즈니스용 One drive 및 SharePoint에 자동으로 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="f2959-153">따라서 SharePoint Online 또는 비즈니스용 One Drive가 DLP 정책에서 위치로 포함되는 경우, Teams에서 보낸 레이블이 지정된 첨부 파일은 이 조건의 범위에 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="f2959-154">DLP 정책에서 Teams를 위치로 선택할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="f2959-155">지원되는 시나리오</span><span class="sxs-lookup"><span data-stu-id="f2959-155">Supported scenarios</span></span>

- <span data-ttu-id="f2959-156">DLP 관리자는 하나 이상의 민감도 레이블을 조건으로 포함하도록 선택할 때 테넌트의 모든 민감도 레이블 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="f2959-157">위의 지원 행렬에 표시된 것과 같이 모든 작업에서 민감도 레이블을 조건으로 사용하는 것은 지원됨</span><span class="sxs-lookup"><span data-stu-id="f2959-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="f2959-158">DLP 정책 팁은 민감도 레이블을 조건으로 포함하는 DLP 정책에 대해 작업 전반에 결쳐 계속해서 표시됩니다(Outlook Win32 제외)</span><span class="sxs-lookup"><span data-stu-id="f2959-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="f2959-159">민감도 레이블이 조건과 일치하는 DLP 정책에서 일치하는 경우 민감도 레이블도 인시던트 보고서 전자 메일의 일부로서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="f2959-160">민감도 레이블 세부 정보는 또한 민감도 레이블이 조건으로 포함된 DLP 정책 일치에 대한 DLP 규칙 일치 감사 로그에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2959-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="f2959-161">지원 정책 팁</span><span class="sxs-lookup"><span data-stu-id="f2959-161">Support policy tips</span></span>


|<span data-ttu-id="f2959-162">워크로드</span><span class="sxs-lookup"><span data-stu-id="f2959-162">workload</span></span>  |<span data-ttu-id="f2959-163">지원되는 정책 팁/지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="f2959-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="f2959-164">OWA</span><span class="sxs-lookup"><span data-stu-id="f2959-164">OWA</span></span> |    <span data-ttu-id="f2959-165">지원</span><span class="sxs-lookup"><span data-stu-id="f2959-165">supported</span></span>     |
|<span data-ttu-id="f2959-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="f2959-166">Outlook Win 32</span></span>    |  <span data-ttu-id="f2959-167">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="f2959-167">not supported</span></span>       |
|<span data-ttu-id="f2959-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f2959-168">SharePoint</span></span>   |   <span data-ttu-id="f2959-169">지원</span><span class="sxs-lookup"><span data-stu-id="f2959-169">supported</span></span>      |
|<span data-ttu-id="f2959-170">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f2959-170">OneDrive for Business</span></span>    |    <span data-ttu-id="f2959-171">지원</span><span class="sxs-lookup"><span data-stu-id="f2959-171">supported</span></span>     |
|<span data-ttu-id="f2959-172">끝점 장치</span><span class="sxs-lookup"><span data-stu-id="f2959-172">endpoint devices</span></span>   |  <span data-ttu-id="f2959-173">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="f2959-173">not supported</span></span>       |
