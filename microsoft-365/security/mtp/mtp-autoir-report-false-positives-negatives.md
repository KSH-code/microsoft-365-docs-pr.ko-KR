---
title: Microsoft 365 Defender에서 AIR에서 가긍성 또는 거짓 부정 처리
description: Microsoft 365 Defender에서 AIR에서 누락되거나 잘못 감지된 것이 있나요? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: ccfb2c8d9395d3f64b20980b156ed51545967101
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917073"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f8032-105">자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리</span><span class="sxs-lookup"><span data-stu-id="f8032-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f8032-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f8032-106">**Applies to:**</span></span>
- <span data-ttu-id="f8032-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8032-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="f8032-108">가짓 긍정/음수는 경우에 따라 위협 방지 솔루션에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="f8032-109">Microsoft [](mtp-autoir.md) 365 Defender의 자동화된 조사 및 대응 기능이 누락되거나 잘못 감지된 경우 보안 운영 팀에서 다음을 취할 수 있는 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-109">If [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="f8032-110">[Microsoft에 가짓 긍정/음수 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="f8032-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="f8032-111">[경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및</span><span class="sxs-lookup"><span data-stu-id="f8032-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="f8032-112">[장치에서 수행된 수정 작업을 취소합니다.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="f8032-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="f8032-113">다음 섹션에서는 이러한 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="f8032-114">분석을 위해 Microsoft에 가짓 긍정/음수 보고</span><span class="sxs-lookup"><span data-stu-id="f8032-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="f8032-115">누락되거나 잘못 검색된 항목</span><span class="sxs-lookup"><span data-stu-id="f8032-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="f8032-116">서비스</span><span class="sxs-lookup"><span data-stu-id="f8032-116">Service</span></span>  |<span data-ttu-id="f8032-117">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="f8032-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f8032-118">- 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="f8032-118">- Email message</span></span> <br/><span data-ttu-id="f8032-119">- 전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="f8032-119">- Email attachment</span></span> <br/><span data-ttu-id="f8032-120">- 전자 메일 메시지의 URL</span><span class="sxs-lookup"><span data-stu-id="f8032-120">- URL in an email message</span></span><br/><span data-ttu-id="f8032-121">- Office 파일의 URL</span><span class="sxs-lookup"><span data-stu-id="f8032-121">- URL in an Office file</span></span>      |[<span data-ttu-id="f8032-122">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8032-122">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)        |[<span data-ttu-id="f8032-123">검색을 위해 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="f8032-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="f8032-124">디바이스의 파일 또는 앱</span><span class="sxs-lookup"><span data-stu-id="f8032-124">File or app on a device</span></span>    |[<span data-ttu-id="f8032-125">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8032-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="f8032-126">맬웨어 분석을 위해 Microsoft에 파일 제출</span><span class="sxs-lookup"><span data-stu-id="f8032-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="f8032-127">가식이 재발하지 않도록 경고 조정</span><span class="sxs-lookup"><span data-stu-id="f8032-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="f8032-128">시나리오</span><span class="sxs-lookup"><span data-stu-id="f8032-128">Scenario</span></span> |<span data-ttu-id="f8032-129">서비스</span><span class="sxs-lookup"><span data-stu-id="f8032-129">Service</span></span> |<span data-ttu-id="f8032-130">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="f8032-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="f8032-131">- 합법적인 사용에 의해 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="f8032-132">- 경고가 부정확합니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="f8032-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f8032-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="f8032-134">또는</span><span class="sxs-lookup"><span data-stu-id="f8032-134">or</span></span> <br/>[<span data-ttu-id="f8032-135">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="f8032-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="f8032-136">Cloud App Security 포털에서 경고 관리</span><span class="sxs-lookup"><span data-stu-id="f8032-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="f8032-137">안전한 경우에도 파일, IP 주소, URL 또는 도메인이 장치에서 맬웨어로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="f8032-138">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8032-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="f8032-139">"허용" 작업을 사용하여 사용자 지정 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="f8032-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="f8032-140">장치에서 수행된 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="f8032-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="f8032-141">엔터티에 대해 수정 작업이 수행된 경우(예: 장치 또는 전자 메일 메시지) 영향을 받는 엔터티가 실제로 위협이 아닌 경우 보안 운영 팀은 알림 센터에서 수정 작업을 실행 취소할 [수 있습니다.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="f8032-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

1. <span data-ttu-id="f8032-142">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="f8032-143">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="f8032-144">사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="f8032-145">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f8032-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="f8032-146">플라이아웃 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8032-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="f8032-147">완료된 [작업 취소를 참조합니다.](mtp-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="f8032-147">See [Undo completed actions](mtp-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8032-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8032-148">See also</span></span>

- [<span data-ttu-id="f8032-149">자동화 조사 세부정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="f8032-149">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="f8032-150">Microsoft 365 Defender에서 고급 헌팅을 통해 위협을 사전 대응</span><span class="sxs-lookup"><span data-stu-id="f8032-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f8032-151">끝점용 Microsoft Defender에서 가짓 긍정/음수 해결</span><span class="sxs-lookup"><span data-stu-id="f8032-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)