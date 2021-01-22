---
title: Microsoft 365 Defender에서 AIR에서 가긍성 또는 거짓 부정 처리
description: Microsoft 365 Defender에서 AIR에서 누락되거나 잘못 감지된 것이 있나요? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930357"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="b7917-105">자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리</span><span class="sxs-lookup"><span data-stu-id="b7917-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b7917-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b7917-106">**Applies to:**</span></span>
- <span data-ttu-id="b7917-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7917-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="b7917-108">Microsoft [](mtp-autoir.md) 365 Defender의 자동화된 조사 및 대응 기능이 누락되거나 잘못된 것을 감지했습니까?</span><span class="sxs-lookup"><span data-stu-id="b7917-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="b7917-109">이를 해결하기 위해 취할 수 있는 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="b7917-110">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-110">You can:</span></span>

- <span data-ttu-id="b7917-111">[Microsoft에 가짓 긍정/거짓 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="b7917-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="b7917-112">[경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및</span><span class="sxs-lookup"><span data-stu-id="b7917-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="b7917-113">장치에서 수행된 재구성 [작업을 취소합니다.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="b7917-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="b7917-114">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b7917-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="b7917-115">분석을 위해 Microsoft에 가짓 긍정/부정 보고</span><span class="sxs-lookup"><span data-stu-id="b7917-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="b7917-116">누락되거나 잘못 검색된 항목</span><span class="sxs-lookup"><span data-stu-id="b7917-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="b7917-117">서비스</span><span class="sxs-lookup"><span data-stu-id="b7917-117">Service</span></span>  |<span data-ttu-id="b7917-118">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="b7917-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b7917-119">- 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="b7917-119">- Email message</span></span> <br/><span data-ttu-id="b7917-120">- 전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="b7917-120">- Email attachment</span></span> <br/><span data-ttu-id="b7917-121">- 전자 메일 메시지의 URL</span><span class="sxs-lookup"><span data-stu-id="b7917-121">- URL in an email message</span></span><br/><span data-ttu-id="b7917-122">- Office 파일의 URL</span><span class="sxs-lookup"><span data-stu-id="b7917-122">- URL in an Office file</span></span>      |[<span data-ttu-id="b7917-123">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7917-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="b7917-124">의심되는 스팸, 피싱, URL 및 파일을 검사하기 위해 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="b7917-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="b7917-125">디바이스의 파일 또는 앱</span><span class="sxs-lookup"><span data-stu-id="b7917-125">File or app on a device</span></span>    |[<span data-ttu-id="b7917-126">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7917-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="b7917-127">맬웨어 분석을 위해 Microsoft에 파일 제출</span><span class="sxs-lookup"><span data-stu-id="b7917-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="b7917-128">가식이 재발하지 않도록 경고 조정</span><span class="sxs-lookup"><span data-stu-id="b7917-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="b7917-129">시나리오</span><span class="sxs-lookup"><span data-stu-id="b7917-129">Scenario</span></span> |<span data-ttu-id="b7917-130">서비스</span><span class="sxs-lookup"><span data-stu-id="b7917-130">Service</span></span> |<span data-ttu-id="b7917-131">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="b7917-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="b7917-132">- 합법적인 사용에 의해 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="b7917-133">- 경고가 부정확합니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="b7917-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b7917-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="b7917-135">또는</span><span class="sxs-lookup"><span data-stu-id="b7917-135">or</span></span> <br/>[<span data-ttu-id="b7917-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="b7917-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="b7917-137">Cloud App Security 포털에서 경고 관리</span><span class="sxs-lookup"><span data-stu-id="b7917-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="b7917-138">안전한 경우에도 파일, IP 주소, URL 또는 도메인은 장치에서 맬웨어로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="b7917-139">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7917-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="b7917-140">"허용" 작업을 사용하여 사용자 지정 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="b7917-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="b7917-141">장치에서 수행된 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="b7917-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="b7917-142">디바이스(예: Windows 10 장치)에서 수정 작업이 수행된 경우 항목이 실제로 위협이 아닌 경우 보안 운영 팀은 관리 센터에서 수정 작업을 실행 취소할 [수 있습니다.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="b7917-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7917-143">다음 작업을 수행하기 전에 [필요한](mtp-action-center.md#required-permissions-for-action-center-tasks) 권한이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7917-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="b7917-144">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="b7917-145">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="b7917-146">사용 기록 **탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="b7917-147">그러면 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="b7917-148">필터를 사용하여 결과 목록의 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="b7917-149">선택한 항목에 대한 플라이아웃에서 조사 **열기 페이지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7917-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="b7917-150">조사 세부 정보 보기에서 작업 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="b7917-151">완료 상태인 항목을 선택하고 결정 열에서 승인됨과 같은 링크를 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7917-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="b7917-152">그러면 동작에 대한 자세한 정보가 있는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b7917-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="b7917-153">작업을 실행 취소하려면 수정 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7917-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7917-154">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7917-154">See also</span></span>

- [<span data-ttu-id="b7917-155">자동화 조사 세부정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="b7917-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="b7917-156">Microsoft 365 Defender에서 고급 헌팅을 통해 위협을 사전 예방적으로 헌팅</span><span class="sxs-lookup"><span data-stu-id="b7917-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
