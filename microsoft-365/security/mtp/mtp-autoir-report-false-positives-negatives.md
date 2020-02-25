---
title: Microsoft Threat Protection의 AIR에서 가양성 또는 거짓 네거티브 처리
description: Microsoft Threat Protection의 AIR에서 누락 되었거나 지워지는이 감지 되었습니까? 분석을 위해 Microsoft에 가양성 또는 거짓 네거티브를 전송 하는 방법을 알아봅니다.
keywords: 자동, 조사, 경고, 트리거, 작업, 재구성, 거짓 긍정, 거짓 음수
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2f3808f599caa4ed347fc182005397c14b9f51b2
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42262005"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="7db8f-105">자동화 된 조사 및 응답 기능에서 가양성/네거티브 처리</span><span class="sxs-lookup"><span data-stu-id="7db8f-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="7db8f-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7db8f-106">**Applies to:**</span></span>
- <span data-ttu-id="7db8f-107">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="7db8f-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="7db8f-108">Microsoft Threat Protection에 대 [한 자동화 된 조사 및 응답 기능이](mtp-autoir.md) 없거나 지워지는에서 감지 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="7db8f-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="7db8f-109">이 문제를 해결 하기 위해 수행할 수 있는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="7db8f-110">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-110">You can:</span></span>

- <span data-ttu-id="7db8f-111">[허위 긍정/음수를 Microsoft에 보고 합니다](#report-a-false-positivenegative-to-microsoft-for-analysis).</span><span class="sxs-lookup"><span data-stu-id="7db8f-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="7db8f-112">필요한 경우 [경고를 조정 합니다](#adjust-an-alert-to-prevent-false-positives-from-recurring) . 한</span><span class="sxs-lookup"><span data-stu-id="7db8f-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="7db8f-113">[장치에 대해 수행 된 재구성 작업을 실행 취소](#undo-a-remediation-action-that-was-taken-on-a-device)합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="7db8f-114">이 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7db8f-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="7db8f-115">분석을 위해 Microsoft에 가양성/음수 보고</span><span class="sxs-lookup"><span data-stu-id="7db8f-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="7db8f-116">누락 된 항목 또는 지워지는 검색</span><span class="sxs-lookup"><span data-stu-id="7db8f-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="7db8f-117">서비스</span><span class="sxs-lookup"><span data-stu-id="7db8f-117">Service</span></span>  |<span data-ttu-id="7db8f-118">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="7db8f-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7db8f-119">-전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="7db8f-119">- Email message</span></span> <br/><span data-ttu-id="7db8f-120">-전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="7db8f-120">- Email attachment</span></span> <br/><span data-ttu-id="7db8f-121">-전자 메일 메시지의 URL</span><span class="sxs-lookup"><span data-stu-id="7db8f-121">- URL in an email message</span></span><br/><span data-ttu-id="7db8f-122">-Office 파일의 URL</span><span class="sxs-lookup"><span data-stu-id="7db8f-122">- URL in an Office file</span></span>      |[<span data-ttu-id="7db8f-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7db8f-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="7db8f-124">의심 스러운 스팸, 피싱, Url 및 파일을 Microsoft에 Office 365 검색에 제출</span><span class="sxs-lookup"><span data-stu-id="7db8f-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="7db8f-125">장치에 있는 파일 또는 앱</span><span class="sxs-lookup"><span data-stu-id="7db8f-125">File or app on a device</span></span>    |[<span data-ttu-id="7db8f-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7db8f-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="7db8f-127">맬웨어 분석을 위해 Microsoft에 파일 제출</span><span class="sxs-lookup"><span data-stu-id="7db8f-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="7db8f-128">경고를 조정 하 여 가양성이 되풀이 되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="7db8f-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="7db8f-129">시나리오</span><span class="sxs-lookup"><span data-stu-id="7db8f-129">Scenario</span></span> |<span data-ttu-id="7db8f-130">서비스</span><span class="sxs-lookup"><span data-stu-id="7db8f-130">Service</span></span> |<span data-ttu-id="7db8f-131">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="7db8f-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="7db8f-132">-합법적인 사용을 통해 알림이 트리거되는 경우</span><span class="sxs-lookup"><span data-stu-id="7db8f-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="7db8f-133">-경고가 부정확 함</span><span class="sxs-lookup"><span data-stu-id="7db8f-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="7db8f-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7db8f-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="7db8f-135">또는</span><span class="sxs-lookup"><span data-stu-id="7db8f-135">or</span></span> <br/>[<span data-ttu-id="7db8f-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="7db8f-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="7db8f-137">Cloud App Security 포털에서 알림 관리</span><span class="sxs-lookup"><span data-stu-id="7db8f-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="7db8f-138">파일, IP 주소, URL 또는 도메인은 안전한 경우에도 장치에서 맬웨어로 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="7db8f-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7db8f-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="7db8f-140">"허용" 작업을 사용 하 여 사용자 지정 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="7db8f-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="7db8f-141">장치에서 수행한 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="7db8f-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="7db8f-142">장치에서 수정 작업을 수행 하는 경우 (예: Windows 10 장치) 해당 항목이 실제로 정리 되 면 보안 운영 팀이 [작업 센터](mtp-action-center.md)에서 수정 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7db8f-143">다음 작업을 수행 하기 전에 [필요한 사용 권한이](mtp-action-center.md#required-permissions-for-action-center-tasks) 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="7db8f-144">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="7db8f-145">탐색 창에서 **작업 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="7db8f-146">**기록** 탭에서 취소할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="7db8f-147">플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="7db8f-148">필터를 사용 하 여 결과 목록의 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="7db8f-149">선택한 항목에 대 한 플라이 아웃에서 **열기 조사 페이지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="7db8f-150">조사 세부 정보 보기에서 **작업** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="7db8f-151">상태가 **완료**됨 인 항목을 선택 하 고 **결정 사항** 열에서 **승인**됨과 같은 링크를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="7db8f-152">그러면 작업에 대 한 자세한 정보가 포함 된 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="7db8f-153">작업을 실행 취소 하려면 **수정 관리 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7db8f-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7db8f-154">관련 문서</span><span class="sxs-lookup"><span data-stu-id="7db8f-154">Related articles</span></span>

- [<span data-ttu-id="7db8f-155">자동화된 조사 및 대응과 관련된 조치 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="7db8f-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="7db8f-156">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="7db8f-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="7db8f-157">Microsoft Threat Protection의 고급 헌팅을 통한 위협에 대한 사전 대응</span><span class="sxs-lookup"><span data-stu-id="7db8f-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
