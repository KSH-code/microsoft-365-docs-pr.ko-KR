---
title: Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 끝점 데이터 손실 방지는 파일 활동의 모니터링 및 해당 파일에 대한 보호 작업을 끝점으로 확장합니다. 파일은 Microsoft 365 규정 준수 솔루션에서 확인할 수 있습니다. '
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279312"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="7833f-104">Microsoft 365 끝점 데이터 손실 방지 알아보기</span><span class="sxs-lookup"><span data-stu-id="7833f-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="7833f-105">Microsoft 365 DLP(데이터 손실 방지)를 사용하여 중요한 항목에 대해 수행 중인 작업을 모니터링하고 해당 항목이 의도치 않게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="7833f-106">DLP에 대한 자세한 내용은 [데이터 손실 방지 개요](data-loss-prevention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7833f-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="7833f-107">**끝점 데이터 손실 방지**(끝점 DLP)는 DLP의 활동 모니터링 및 보호 기능을 Windows 10 장치의 중요한 항목으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="7833f-108">장치가 Microsoft 365 규정 준수 솔루션에 등록된 경우 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="7833f-109">모니터링 및 조치 가능한 끝점 활동</span><span class="sxs-lookup"><span data-stu-id="7833f-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="7833f-110">Microsoft 끝점 DLP를 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="7833f-111">활동</span><span class="sxs-lookup"><span data-stu-id="7833f-111">activity</span></span> |<span data-ttu-id="7833f-112">설명</span><span class="sxs-lookup"><span data-stu-id="7833f-112">description</span></span>  | <span data-ttu-id="7833f-113">감사/통제</span><span class="sxs-lookup"><span data-stu-id="7833f-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="7833f-114">클라우드 서비스로 업로드 또는 허용되지 않은 브라우저에서 액세스</span><span class="sxs-lookup"><span data-stu-id="7833f-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="7833f-115">사용자가 항목을 제한된 서비스 도메인에 업로드하거나 브라우저를 통해 항목에 액세스하려는 경우 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="7833f-116">DLP에 허용되지 않는 브라우저로 나열되는 브라우저를 사용하는 경우에는 업로드 작업이 차단되고 사용자는 Edge Chromium을 사용하도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="7833f-117">Edge Chromium에서는 DLP 정책 구성을 기반으로 업로드 또는 액세스를 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="7833f-118">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="7833f-118">auditable and restrictable</span></span>|
|<span data-ttu-id="7833f-119">다른 앱으로 복사</span><span class="sxs-lookup"><span data-stu-id="7833f-119">copy to other app</span></span>    |<span data-ttu-id="7833f-120">사용자가 보호되는 항목에서 정보를 복사한 후 다른 앱, 프로세스 또는 항목에 붙여넣기를 시도하는 경우 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="7833f-121">이 작업으로는 동일한 앱, 프로세스 또는 항목 내에서의 정보 복사 및 붙여넣기는 감지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="7833f-122">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="7833f-122">auditable and restrictable</span></span>|
|<span data-ttu-id="7833f-123">USB 이동식 미디어에 복사</span><span class="sxs-lookup"><span data-stu-id="7833f-123">copy to USB removable media</span></span> |<span data-ttu-id="7833f-124">사용자가 항목이나 정보를 이동식 미디어 또는 USB 장치에 복사하려고 할 때이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="7833f-125">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="7833f-125">auditable and restrictable</span></span>|
|<span data-ttu-id="7833f-126">네트워크 공유 위치에 복사</span><span class="sxs-lookup"><span data-stu-id="7833f-126">copy to a network share</span></span>    |<span data-ttu-id="7833f-127">사용자가 항목을 네트워크 공유 또는 매핑된 네트워크 드라이브로 복사하려고 할 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="7833f-128">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="7833f-128">auditable and restrictable</span></span>|
|<span data-ttu-id="7833f-129">문서 인쇄</span><span class="sxs-lookup"><span data-stu-id="7833f-129">print a document</span></span>    |<span data-ttu-id="7833f-130">사용자가 보호된 항목을 로컬 또는 네트워크 프린터로 인쇄하려고 할 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="7833f-131">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="7833f-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="7833f-132">항목 만들기</span><span class="sxs-lookup"><span data-stu-id="7833f-132">create an item</span></span>|<span data-ttu-id="7833f-133">사용자가 항목을 만들 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-133">Detects when a user creates an item</span></span>| <span data-ttu-id="7833f-134">감사</span><span class="sxs-lookup"><span data-stu-id="7833f-134">auditable</span></span>|
|<span data-ttu-id="7833f-135">항목 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="7833f-135">rename an item</span></span>|<span data-ttu-id="7833f-136">사용자가 항목 이름을 바꿀 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-136">Detects when a user renames an item</span></span>| <span data-ttu-id="7833f-137">감사</span><span class="sxs-lookup"><span data-stu-id="7833f-137">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="7833f-138">모니터링된 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-138">Monitored files</span></span>

<span data-ttu-id="7833f-139">끝점 DLP는 다음 파일 형식의 모니터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-139">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="7833f-140">Word 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-140">Word files</span></span>
- <span data-ttu-id="7833f-141">PowerPoint 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-141">PowerPoint files</span></span>
- <span data-ttu-id="7833f-142">Excel 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-142">Excel files</span></span>
- <span data-ttu-id="7833f-143">PDF 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-143">PDF files</span></span>
- <span data-ttu-id="7833f-144">.csv 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-144">.csv files</span></span>
- <span data-ttu-id="7833f-145">.tsv 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-145">.tsv files</span></span>
- <span data-ttu-id="7833f-146">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-146">.txt files</span></span>
- <span data-ttu-id="7833f-147">RTF 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-147">.rtf files</span></span>
- <span data-ttu-id="7833f-148">c 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-148">.c files</span></span>
- <span data-ttu-id="7833f-149">클래스 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-149">.class files</span></span>
- <span data-ttu-id="7833f-150">cpp 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-150">.cpp files</span></span>
- <span data-ttu-id="7833f-151">cs 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-151">.cs files</span></span>
- <span data-ttu-id="7833f-152">h 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-152">.h files</span></span>
- <span data-ttu-id="7833f-153">java 파일</span><span class="sxs-lookup"><span data-stu-id="7833f-153">.java files</span></span>
 
<span data-ttu-id="7833f-154">기본적으로 끝점 DLP는 정책 일치가 없는 경우에도 이러한 파일 유형에 대한 작업을 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-154">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="7833f-155">정책 일치의 데이터만 모니터링하려는 경우 끝점 DLP 전역 설정에서 **장치의 항상 감사 파일 활동** 을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-155">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="7833f-156">Word, PowerPoint, Excel, PDF 및 .csv 파일의 작업은 항상 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-156">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="7833f-157">끝점 DLP는 활동 기반의 Om MIME 유형을 모니터링하므로 파일 확장명이 변경되더라도 활동은 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-157">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="7833f-158">끝점 DLP의 다양한 기능</span><span class="sxs-lookup"><span data-stu-id="7833f-158">What's different in Endpoint DLP</span></span>

<span data-ttu-id="7833f-159">끝점 DLP를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-159">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="7833f-160">장치 관리 사용 설정</span><span class="sxs-lookup"><span data-stu-id="7833f-160">Enabling Device management</span></span>

<span data-ttu-id="7833f-161">장치 관리는 장치에서 원격 분석 수집을 사용하도록 설정하고 원격 분석 수집을 끝점 DLP 및 [참가자 위험 관리](insider-risk-management.md)와 같은 Microsoft 365 규정 준수 솔루션으로 가져오는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-161">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="7833f-162">DLP 정책에서 위치로 사용하려는 모든 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-162">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7833f-163">![장치 관리를 사용하도록 설정](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="7833f-163">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="7833f-164">장치 관리 센터에서 다운로드한 스크립트를 통해 온보딩 및 오프보딩이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-164">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="7833f-165">해당 센터는 각 배포 방법에 대한 사용자 지정 스크립트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-165">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="7833f-166">로컬 스크립트(최대 10대의 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="7833f-166">local script (up to 10 machines)</span></span>
- <span data-ttu-id="7833f-167">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="7833f-167">Group policy</span></span>
- <span data-ttu-id="7833f-168">System Center Configuration Manager(버전 1610 이상)</span><span class="sxs-lookup"><span data-stu-id="7833f-168">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="7833f-169">모바일 장치 관리/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7833f-169">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="7833f-170">비 영구적인 컴퓨터에 대한 VDI 온보딩 스크립트</span><span class="sxs-lookup"><span data-stu-id="7833f-170">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7833f-171">![장치 온보딩 페이지](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="7833f-171">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="7833f-172">[Microsoft 365 끝점 DLP 시작하기](endpoint-dlp-getting-started.md)의 절차를 사용하여 장치를 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="7833f-172">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="7833f-173">[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)를 통해 장치를 온보딩한 경우, 해당 장치는 장치 목록에 자동으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-173">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7833f-174">![관리된 장치 목록](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="7833f-174">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="7833f-175">끝점 DLP 데이터 확인하기</span><span class="sxs-lookup"><span data-stu-id="7833f-175">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="7833f-176">[DLP 경고 관리 대시보드](dlp-configure-view-alerts-policies.md)로 이동하여 끝점 장치에 적용되는 DLP 정책과 관련된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-176">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![경고 정보](../media/Alert-info-1.png)

<span data-ttu-id="7833f-178">동일한 대시보드에서 서식 있는 메타데이터와 관련된 이벤트 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-178">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![이벤트 정보](../media/Event-info-1.png)

<span data-ttu-id="7833f-180">장치가 등록되면 장치를 위치로 포함하는 모든 DLP 정책을 구성하고 배포하기 전에 감사 활동에 대한 정보가 활동 탐색기로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-180">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7833f-181">![활동 탐색기의 끝점 DLP 이벤트](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="7833f-181">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="7833f-182">끝점 DLP는 감사 활동에 대한 광범위한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-182">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="7833f-183">예를 들어 파일이 이동식 USB 미디어에 복사되는 경우 활동 세부 정보에 다음 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-183">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="7833f-184">활동 유형</span><span class="sxs-lookup"><span data-stu-id="7833f-184">activity type</span></span>
- <span data-ttu-id="7833f-185">클라이언트 IP</span><span class="sxs-lookup"><span data-stu-id="7833f-185">client IP</span></span>
- <span data-ttu-id="7833f-186">대상 파일 경로</span><span class="sxs-lookup"><span data-stu-id="7833f-186">target file path</span></span>
- <span data-ttu-id="7833f-187">타임스탬프 발생</span><span class="sxs-lookup"><span data-stu-id="7833f-187">happened timestamp</span></span>
- <span data-ttu-id="7833f-188">파일 이름</span><span class="sxs-lookup"><span data-stu-id="7833f-188">file name</span></span>
- <span data-ttu-id="7833f-189">사용자</span><span class="sxs-lookup"><span data-stu-id="7833f-189">user</span></span>
- <span data-ttu-id="7833f-190">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="7833f-190">file extension</span></span>
- <span data-ttu-id="7833f-191">파일 크기</span><span class="sxs-lookup"><span data-stu-id="7833f-191">file size</span></span>
- <span data-ttu-id="7833f-192">중요한 정보 유형(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="7833f-192">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="7833f-193">SHA1 값</span><span class="sxs-lookup"><span data-stu-id="7833f-193">sha1 value</span></span>
- <span data-ttu-id="7833f-194">SHA256 값</span><span class="sxs-lookup"><span data-stu-id="7833f-194">sha256 value</span></span>
- <span data-ttu-id="7833f-195">이전 파일 이름</span><span class="sxs-lookup"><span data-stu-id="7833f-195">previous file name</span></span>
- <span data-ttu-id="7833f-196">위치</span><span class="sxs-lookup"><span data-stu-id="7833f-196">location</span></span>
- <span data-ttu-id="7833f-197">상위</span><span class="sxs-lookup"><span data-stu-id="7833f-197">parent</span></span>
- <span data-ttu-id="7833f-198">파일 경로</span><span class="sxs-lookup"><span data-stu-id="7833f-198">filepath</span></span>
- <span data-ttu-id="7833f-199">원본 위치 유형</span><span class="sxs-lookup"><span data-stu-id="7833f-199">source location type</span></span>
- <span data-ttu-id="7833f-200">플랫폼</span><span class="sxs-lookup"><span data-stu-id="7833f-200">platform</span></span>
- <span data-ttu-id="7833f-201">장치 이름</span><span class="sxs-lookup"><span data-stu-id="7833f-201">device name</span></span>
- <span data-ttu-id="7833f-202">대상 위치 유형</span><span class="sxs-lookup"><span data-stu-id="7833f-202">destination location type</span></span>
- <span data-ttu-id="7833f-203">복사를 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7833f-203">application that performed the copy</span></span>
- <span data-ttu-id="7833f-204">엔드포인트용 Microsoft Defender 장치 ID(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="7833f-204">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="7833f-205">이동식 미디어 장치 제조업체</span><span class="sxs-lookup"><span data-stu-id="7833f-205">removable media device manufacturer</span></span>
- <span data-ttu-id="7833f-206">이동식 미디어 장치 모델</span><span class="sxs-lookup"><span data-stu-id="7833f-206">removable media device model</span></span>
- <span data-ttu-id="7833f-207">이동식 미디어 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="7833f-207">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7833f-208">![USB 활동 특성에 복사](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="7833f-208">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="7833f-209">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7833f-209">Next steps</span></span>

<span data-ttu-id="7833f-210">이제 끝점 DLP에 대해 살펴보았으므로 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7833f-210">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="7833f-211">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="7833f-211">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="7833f-212">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="7833f-212">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="7833f-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7833f-213">See also</span></span>

- [<span data-ttu-id="7833f-214">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="7833f-214">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="7833f-215">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="7833f-215">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="7833f-216">데이터 손실 방지 개요</span><span class="sxs-lookup"><span data-stu-id="7833f-216">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="7833f-217">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="7833f-217">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="7833f-218">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="7833f-218">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="7833f-219">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7833f-219">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="7833f-220">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="7833f-220">Insider Risk management</span></span>](insider-risk-management.md)
