---
title: 장치용 Microsoft Secure Score
description: 장치에 대한 점수는 응용 프로그램, 운영 체제, 네트워크, 계정 및 보안 제어 전반에 걸쳐 디바이스의 총 보안 구성 상태를 보여줍니다.
keywords: Microsoft Secure Score for Devices, Endpoint Microsoft Defender for Devices, Secure score, configuration score, 위협 및 취약성 관리, security controls, improvement opportunities, security configuration score over time, security posture, baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934084"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="1385c-104">장치용 Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="1385c-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1385c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1385c-105">**Applies to:**</span></span>

- [<span data-ttu-id="1385c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1385c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1385c-107">위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="1385c-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="1385c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1385c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1385c-109">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1385c-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1385c-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="1385c-111">구성 점수는 이제 장치용 Microsoft 위협 및 취약성 관리 점수의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="1385c-112">장치에 대한 점수는 디바이스의 위협 및 취약성 관리 [대시보드에](tvm-dashboard-insights.md) Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="1385c-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="1385c-113">장치에 대한 Microsoft 보안 점수가 높을수록 끝점이 사이버 보안 위협 공격으로부터 더 탄력적입니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="1385c-114">다음 범주에 걸쳐 디바이스의 전체 보안 구성 상태를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="1385c-115">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1385c-115">Application</span></span>
- <span data-ttu-id="1385c-116">운영 체제</span><span class="sxs-lookup"><span data-stu-id="1385c-116">Operating system</span></span>
- <span data-ttu-id="1385c-117">네트워크</span><span class="sxs-lookup"><span data-stu-id="1385c-117">Network</span></span>
- <span data-ttu-id="1385c-118">계정</span><span class="sxs-lookup"><span data-stu-id="1385c-118">Accounts</span></span>
- <span data-ttu-id="1385c-119">보안 제어</span><span class="sxs-lookup"><span data-stu-id="1385c-119">Security controls</span></span>

<span data-ttu-id="1385c-120">보안 권장 사항 페이지로 이동하여 관련 권장 사항을 볼 범주를 선택합니다. [](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="1385c-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="1385c-121">Microsoft 보안 점수 커넥터 켜기</span><span class="sxs-lookup"><span data-stu-id="1385c-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="1385c-122">끝점 신호를 위해 Microsoft Defender를 전달하여 장치 보안 상태의 Microsoft 보안 점수를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="1385c-123">전달된 데이터는 Microsoft 보안 점수 데이터와 동일한 위치에 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="1385c-124">변경 내용을 대시보드에 반영하는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="1385c-125">탐색 창에서 고급 설정   >  **이동**</span><span class="sxs-lookup"><span data-stu-id="1385c-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="1385c-126">**아래로 스크롤하여 Microsoft 보안** 점수로 이동하고 설정을 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="1385c-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="1385c-127">기본 **설정 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1385c-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="1385c-128">작동 방법</span><span class="sxs-lookup"><span data-stu-id="1385c-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="1385c-129">Microsoft Secure Score for Devices는 현재 그룹 정책을 통해 설정된 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="1385c-130">현재 부분 Intune 지원으로 인해 Intune을 통해 설정될 수 있는 구성이 잘못 구성된 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="1385c-131">조직에서 보안 구성 관리를 위해 Intune을 사용하는 경우 IT 관리자에게 문의하여 실제 구성 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="1385c-132">Microsoft Secure Score for Devices 카드의 데이터는 세세하고 지속적인 취약점 검색 프로세스의 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="1385c-133">다음을 지속적으로 구성 검색 평가를 통해 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="1385c-134">수집된 구성을 수집된 벤치마크와 비교하여 잘못 구성된 자산 검색</span><span class="sxs-lookup"><span data-stu-id="1385c-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="1385c-135">수정 또는 부분적으로 수정될 수 있는 취약성에 구성 매핑(위험 감소)</span><span class="sxs-lookup"><span data-stu-id="1385c-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="1385c-136">모범 사례 구성 벤치마크 수집 및 유지 관리(공급업체, 보안 피드, 내부 연구 팀)</span><span class="sxs-lookup"><span data-stu-id="1385c-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="1385c-137">모든 자산에서 보안 제어 구성 상태의 변경 사항 수집 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="1385c-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="1385c-138">보안 구성 개선</span><span class="sxs-lookup"><span data-stu-id="1385c-138">Improve your security configuration</span></span>

<span data-ttu-id="1385c-139">보안 권장 사항 목록의 문제를 수정하여 보안 구성을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="1385c-140">이렇게 할 때 장치에 대한 Microsoft 보안 점수가 개선될 수 있으며 조직은 사이버 보안 위협 및 취약성에 대해 더 탄력적으로 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="1385c-141">위협 및 취약성 관리 대시보드의 Microsoft Secure Score for Devices(장치 보안 점수) 카드에서 범주 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="1385c-142">해당 범주와 관련된 추천 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="1385c-143">보안 권장 사항 [**페이지로 이동합니다.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="1385c-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="1385c-144">모든 보안 권장 사항을 확인하려는 경우 보안 권장 사항 페이지로 이동한 후 검색 필드를 지우십시오.</span><span class="sxs-lookup"><span data-stu-id="1385c-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="1385c-145">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-145">Select an item on the list.</span></span> <span data-ttu-id="1385c-146">추천과 관련된 세부 정보가 있는 플라이아웃 패널이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="1385c-147">수정 **옵션 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1385c-147">Select **Remediation options**.</span></span>

   ![보안 제어 관련 보안 권장 사항](images/tvm_security_controls.png)

3. <span data-ttu-id="1385c-149">설명을 읽어 문제의 컨텍스트와 다음에 할 작업을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="1385c-150">기한을 선택하고 메모를 추가하고, 추가 작업 수행을 위해 전자 메일에 첨부할 수 있도록 모든 재구성 활동 데이터를 **CSV로** 내보내기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="1385c-151">**요청을 제출합니다.**</span><span class="sxs-lookup"><span data-stu-id="1385c-151">**Submit request**.</span></span> <span data-ttu-id="1385c-152">재구성 작업이 만들어졌다는 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="1385c-153">![재구성 작업 생성 확인](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="1385c-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="1385c-154">CSV 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-154">Save your CSV file.</span></span>
   <span data-ttu-id="1385c-155">![csv 파일 저장](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="1385c-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="1385c-156">IT 관리자에게 후속 전자 메일을 보내고 수정을 위해 시스템에서 전파하도록 허용하는 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="1385c-157">대시보드에서 **Microsoft Secure Score for Devices(장치용 Microsoft 보안 점수)** 카드를 다시 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="1385c-158">권장 보안 제어의 수가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="1385c-159">보안 **컨트롤을** 선택하여 보안 권장  사항 페이지로 돌아가면 해결한 항목이 더 이상 목록에 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="1385c-160">장치에 대한 Microsoft 보안 점수가 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1385c-161">취약성 평가 감지 비율을 높이기 위해 다음과 같은 필수 보안 업데이트를 다운로드하여 네트워크에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1385c-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="1385c-162">19H1 고객 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="1385c-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="1385c-163">RS5 고객 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="1385c-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="1385c-164">RS4 고객 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="1385c-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="1385c-165">RS3 고객 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="1385c-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="1385c-166">보안 업데이트를 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="1385c-166">To download the security updates:</span></span>
>1. <span data-ttu-id="1385c-167">Microsoft [업데이트 카탈로그로 이동하십시오.](https://www.catalog.update.microsoft.com/home.aspx)</span><span class="sxs-lookup"><span data-stu-id="1385c-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="1385c-168">다운로드해야 하는 보안 업데이트 KB 번호에 키를 입력한 다음 검색을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1385c-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="1385c-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1385c-169">Related topics</span></span>

- [<span data-ttu-id="1385c-170">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="1385c-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="1385c-171">Dashboard</span><span class="sxs-lookup"><span data-stu-id="1385c-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="1385c-172">노출 점수</span><span class="sxs-lookup"><span data-stu-id="1385c-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="1385c-173">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="1385c-173">Security recommendations</span></span>](tvm-security-recommendation.md)
