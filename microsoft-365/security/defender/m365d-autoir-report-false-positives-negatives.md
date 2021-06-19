---
title: 2016년 4월 1일부로 가짓 긍정 Microsoft 365 Defender
description: AIR에서 누락되거나 잘못 감지된 것이 Microsoft 365 Defender? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022537"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="0eb87-105">2016년 4월 1일부로 가짓 긍정 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0eb87-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0eb87-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0eb87-106">**Applies to:**</span></span>
- <span data-ttu-id="0eb87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0eb87-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="0eb87-108">경우에 따라 모든 위협 방지 솔루션에서 가긍성 또는 부정이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="0eb87-109">[누락되거나](m365d-autoir.md) 잘못 검색된 Microsoft 365 Defender 자동화된 조사 및 대응 기능이 있는 경우 보안 운영 팀이 취할 수 있는 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="0eb87-110">Microsoft에 가짓 긍정/음수 보고</span><span class="sxs-lookup"><span data-stu-id="0eb87-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="0eb87-111">[경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우)</span><span class="sxs-lookup"><span data-stu-id="0eb87-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="0eb87-112">장치에서 수행된 수정 작업 취소</span><span class="sxs-lookup"><span data-stu-id="0eb87-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="0eb87-113">다음 섹션에서는 이러한 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="0eb87-114">분석을 위해 Microsoft에 가짓 긍정/음수 보고</span><span class="sxs-lookup"><span data-stu-id="0eb87-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="0eb87-115">누락되거나 잘못 검색된 항목</span><span class="sxs-lookup"><span data-stu-id="0eb87-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="0eb87-116">서비스</span><span class="sxs-lookup"><span data-stu-id="0eb87-116">Service</span></span>  |<span data-ttu-id="0eb87-117">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="0eb87-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0eb87-118">- 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="0eb87-118">- Email message</span></span> <br/><span data-ttu-id="0eb87-119">- 전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="0eb87-119">- Email attachment</span></span> <br/><span data-ttu-id="0eb87-120">- 전자 메일 메시지의 URL</span><span class="sxs-lookup"><span data-stu-id="0eb87-120">- URL in an email message</span></span><br/><span data-ttu-id="0eb87-121">- Office URL</span><span class="sxs-lookup"><span data-stu-id="0eb87-121">- URL in an Office file</span></span>      |[<span data-ttu-id="0eb87-122">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0eb87-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="0eb87-123">검색을 위해 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="0eb87-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="0eb87-124">디바이스의 파일 또는 앱</span><span class="sxs-lookup"><span data-stu-id="0eb87-124">File or app on a device</span></span>    |[<span data-ttu-id="0eb87-125">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0eb87-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="0eb87-126">맬웨어 분석을 위해 Microsoft에 파일 제출</span><span class="sxs-lookup"><span data-stu-id="0eb87-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="0eb87-127">가식이 재발하지 않도록 경고 조정</span><span class="sxs-lookup"><span data-stu-id="0eb87-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="0eb87-128">시나리오</span><span class="sxs-lookup"><span data-stu-id="0eb87-128">Scenario</span></span> |<span data-ttu-id="0eb87-129">서비스</span><span class="sxs-lookup"><span data-stu-id="0eb87-129">Service</span></span> |<span data-ttu-id="0eb87-130">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="0eb87-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="0eb87-131">- 합법적인 사용에 의해 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="0eb87-132">- 경고가 부정확합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="0eb87-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0eb87-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="0eb87-134">또는</span><span class="sxs-lookup"><span data-stu-id="0eb87-134">or</span></span> <br/>[<span data-ttu-id="0eb87-135">Azure 위협 방지</span><span class="sxs-lookup"><span data-stu-id="0eb87-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="0eb87-136">사이트 포털에서 Cloud App Security 관리</span><span class="sxs-lookup"><span data-stu-id="0eb87-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="0eb87-137">안전한 경우에도 파일, IP 주소, URL 또는 도메인이 장치에서 맬웨어로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="0eb87-138">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0eb87-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="0eb87-139">"허용" 작업을 사용하여 사용자 지정 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="0eb87-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="0eb87-140">장치에서 수행된 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="0eb87-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="0eb87-141">엔터티에 대해 수정 작업이 수행된 경우(예: 장치 또는 전자 메일 메시지) 영향을 받는 엔터티가 실제로 위협이 아닌 경우 보안 운영 팀은 알림 센터에서 수정 작업을 실행 취소할 [수 있습니다.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="0eb87-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="0eb87-142">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="0eb87-143">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="0eb87-144">사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="0eb87-145">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0eb87-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="0eb87-146">플라이아웃 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0eb87-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="0eb87-147">완료된 [작업 취소를 참조합니다.](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="0eb87-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="0eb87-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0eb87-148">See also</span></span>

- [<span data-ttu-id="0eb87-149">자동화 조사 세부정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="0eb87-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="0eb87-150">고급 헌팅을 통해 위협을 사전 예방적으로 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0eb87-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
