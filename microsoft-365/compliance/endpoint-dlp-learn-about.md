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
ms.openlocfilehash: c97368dd48515dc787dbac66aa93844889efbdbc
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314419"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="8d47d-104">Microsoft 365 끝점 데이터 손실 방지 알아보기</span><span class="sxs-lookup"><span data-stu-id="8d47d-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="8d47d-105">Microsoft 365 DLP(데이터 손실 방지)를 사용하여 중요한 항목에 대해 수행 중인 작업을 모니터링하고 해당 항목이 의도치 않게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="8d47d-106">DLP에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d47d-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="8d47d-107">**끝점 데이터 손실 방지**(끝점 DLP)는 DLP의 활동 모니터링 및 보호 기능을 Windows 10 장치의 중요한 항목으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="8d47d-108">장치가 Microsoft 365 규정 준수 솔루션에 등록된 경우 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="8d47d-109">이동식 저장소에 대한 디바이스 제어를 찾고 있는 경우 [엔드포인트용 Microsoft Defender 디바이스 제어 이동식 저장소 액세스 제어](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d47d-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="8d47d-110">모니터링 및 조치 가능한 끝점 활동</span><span class="sxs-lookup"><span data-stu-id="8d47d-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="8d47d-111">Microsoft 끝점 DLP를 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="8d47d-112">활동</span><span class="sxs-lookup"><span data-stu-id="8d47d-112">Activity</span></span> |<span data-ttu-id="8d47d-113">설명</span><span class="sxs-lookup"><span data-stu-id="8d47d-113">Description</span></span>  | <span data-ttu-id="8d47d-114">감사/통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="8d47d-115">클라우드 서비스로 업로드 또는 허용되지 않은 브라우저에서 액세스</span><span class="sxs-lookup"><span data-stu-id="8d47d-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="8d47d-116">사용자가 항목을 제한된 서비스 도메인에 업로드하거나 브라우저를 통해 항목에 액세스하려는 경우 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="8d47d-117">DLP에 허용되지 않는 브라우저로 나열되는 브라우저를 사용하는 경우에는 업로드 작업이 차단되고 사용자는 Edge Chromium을 사용하도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="8d47d-118">Edge Chromium에서는 DLP 정책 구성을 기반으로 업로드 또는 액세스를 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="8d47d-119">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-119">auditable and restrictable</span></span>|
|<span data-ttu-id="8d47d-120">다른 앱으로 복사</span><span class="sxs-lookup"><span data-stu-id="8d47d-120">copy to other app</span></span>    |<span data-ttu-id="8d47d-121">사용자가 보호되는 항목에서 정보를 복사한 후 다른 앱, 프로세스 또는 항목에 붙여넣기를 시도하는 경우 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="8d47d-122">이 작업으로는 동일한 앱, 프로세스 또는 항목 내에서의 정보 복사 및 붙여넣기는 감지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="8d47d-123">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-123">auditable and restrictable</span></span>|
|<span data-ttu-id="8d47d-124">USB 이동식 미디어에 복사</span><span class="sxs-lookup"><span data-stu-id="8d47d-124">copy to USB removable media</span></span> |<span data-ttu-id="8d47d-125">사용자가 항목이나 정보를 이동식 미디어 또는 USB 장치에 복사하려고 할 때이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="8d47d-126">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-126">auditable and restrictable</span></span>|
|<span data-ttu-id="8d47d-127">네트워크 공유 위치에 복사</span><span class="sxs-lookup"><span data-stu-id="8d47d-127">copy to a network share</span></span>    |<span data-ttu-id="8d47d-128">사용자가 항목을 네트워크 공유 또는 매핑된 네트워크 드라이브로 복사하려고 할 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="8d47d-129">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-129">auditable and restrictable</span></span>|
|<span data-ttu-id="8d47d-130">문서 인쇄</span><span class="sxs-lookup"><span data-stu-id="8d47d-130">print a document</span></span>    |<span data-ttu-id="8d47d-131">사용자가 보호된 항목을 로컬 또는 네트워크 프린터로 인쇄하려고 할 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="8d47d-132">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="8d47d-133">원격 세션에 복사</span><span class="sxs-lookup"><span data-stu-id="8d47d-133">copy to a remote session</span></span>|<span data-ttu-id="8d47d-134">사용자가 원격 데스크톱 세션에 항목을 복사하려고 할 때 감지</span><span class="sxs-lookup"><span data-stu-id="8d47d-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="8d47d-135">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-135">auditable and restrictable</span></span>|
|<span data-ttu-id="8d47d-136">Bluetooth 장치에 복사</span><span class="sxs-lookup"><span data-stu-id="8d47d-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="8d47d-137">사용자가 허용하지 않는 Bluetooth 앱(끝점 DLP 설정의 허용하지 않는 Bluetooth aps 목록에 정의된 경우)에 대한 복사를 시도하는 경우를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="8d47d-138">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="8d47d-138">auditable and restrictable</span></span>|
|<span data-ttu-id="8d47d-139">항목 만들기</span><span class="sxs-lookup"><span data-stu-id="8d47d-139">create an item</span></span>|<span data-ttu-id="8d47d-140">사용자가 항목을 만들 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-140">Detects when a user creates an item</span></span>| <span data-ttu-id="8d47d-141">감사</span><span class="sxs-lookup"><span data-stu-id="8d47d-141">auditable</span></span>|
|<span data-ttu-id="8d47d-142">항목 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="8d47d-142">rename an item</span></span>|<span data-ttu-id="8d47d-143">사용자가 항목 이름을 바꿀 때 이를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-143">Detects when a user renames an item</span></span>| <span data-ttu-id="8d47d-144">감사</span><span class="sxs-lookup"><span data-stu-id="8d47d-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="8d47d-145">모니터링된 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-145">Monitored files</span></span>

<span data-ttu-id="8d47d-146">끝점 DLP는 다음 파일 형식의 모니터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-146">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="8d47d-147">Word 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-147">Word files</span></span>
- <span data-ttu-id="8d47d-148">PowerPoint 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-148">PowerPoint files</span></span>
- <span data-ttu-id="8d47d-149">Excel 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-149">Excel files</span></span>
- <span data-ttu-id="8d47d-150">PDF 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-150">PDF files</span></span>
- <span data-ttu-id="8d47d-151">.csv 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-151">.csv files</span></span>
- <span data-ttu-id="8d47d-152">.tsv 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-152">.tsv files</span></span>
- <span data-ttu-id="8d47d-153">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-153">.txt files</span></span>
- <span data-ttu-id="8d47d-154">RTF 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-154">.rtf files</span></span>
- <span data-ttu-id="8d47d-155">c 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-155">.c files</span></span>
- <span data-ttu-id="8d47d-156">클래스 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-156">.class files</span></span>
- <span data-ttu-id="8d47d-157">cpp 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-157">.cpp files</span></span>
- <span data-ttu-id="8d47d-158">cs 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-158">.cs files</span></span>
- <span data-ttu-id="8d47d-159">h 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-159">.h files</span></span>
- <span data-ttu-id="8d47d-160">java 파일</span><span class="sxs-lookup"><span data-stu-id="8d47d-160">.java files</span></span>

<span data-ttu-id="8d47d-161">기본적으로 끝점 DLP는 정책 일치가 없는 경우에도 이러한 파일 유형에 대한 작업을 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-161">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="8d47d-162">정책 일치의 데이터만 모니터링하려는 경우 끝점 DLP 전역 설정에서 **장치의 항상 감사 파일 활동** 을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="8d47d-163">이 설정이 켜져 있으면 장치가 정책에 의해 대상이 지정되지 않더라도 Word, PowerPoint, Excel, PDF 및 .csv 파일의 작업이 항상 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-163">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="8d47d-164">끝점 DLP는 활동 기반의 Om MIME 유형을 모니터링하므로 파일 확장명이 변경되더라도 활동은 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="8d47d-165">끝점 DLP의 다양한 기능</span><span class="sxs-lookup"><span data-stu-id="8d47d-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="8d47d-166">끝점 DLP를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="8d47d-167">장치 관리 사용 설정</span><span class="sxs-lookup"><span data-stu-id="8d47d-167">Enabling Device management</span></span>

<span data-ttu-id="8d47d-168">장치 관리는 장치에서 원격 분석 수집을 사용하도록 설정하고 원격 분석 수집을 끝점 DLP 및 [참가자 위험 관리](insider-risk-management.md)와 같은 Microsoft 365 규정 준수 솔루션으로 가져오는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="8d47d-169">DLP 정책에서 위치로 사용하려는 모든 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-170">![장치 관리를 사용하도록 설정](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="8d47d-171">장치 관리 센터에서 다운로드한 스크립트를 통해 온보딩 및 오프보딩이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="8d47d-172">해당 센터는 각 배포 방법에 대한 사용자 지정 스크립트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="8d47d-173">로컬 스크립트(최대 10대의 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="8d47d-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="8d47d-174">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="8d47d-174">Group policy</span></span>
- <span data-ttu-id="8d47d-175">System Center Configuration Manager(버전 1610 이상)</span><span class="sxs-lookup"><span data-stu-id="8d47d-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="8d47d-176">모바일 장치 관리/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8d47d-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="8d47d-177">비 영구적인 컴퓨터에 대한 VDI 온보딩 스크립트</span><span class="sxs-lookup"><span data-stu-id="8d47d-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-178">![장치 온보딩 페이지](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="8d47d-179">[Microsoft 365 끝점 DLP 시작하기](endpoint-dlp-getting-started.md)의 절차를 사용하여 장치를 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="8d47d-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="8d47d-180">[엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)를 통해 장치를 온보딩한 경우, 해당 장치는 장치 목록에 자동으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-181">![관리된 장치 목록](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="8d47d-182">끝점 DLP 데이터 확인하기</span><span class="sxs-lookup"><span data-stu-id="8d47d-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="8d47d-183">[DLP 경고 관리 대시보드](dlp-configure-view-alerts-policies.md)로 이동하여 끝점 장치에 적용되는 DLP 정책과 관련된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-184">![경고 정보](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="8d47d-185">동일한 대시보드에서 서식 있는 메타데이터와 관련된 이벤트 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-186">![이벤트 정보](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="8d47d-187">장치가 등록되면 장치를 위치로 포함하는 모든 DLP 정책을 구성하고 배포하기 전에 감사 활동에 대한 정보가 활동 탐색기로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-188">![활동 탐색기의 끝점 DLP 이벤트](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="8d47d-189">끝점 DLP는 감사 활동에 대한 광범위한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="8d47d-190">예를 들어 파일이 이동식 USB 미디어에 복사되는 경우 활동 세부 정보에 다음 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="8d47d-191">활동 유형</span><span class="sxs-lookup"><span data-stu-id="8d47d-191">activity type</span></span>
- <span data-ttu-id="8d47d-192">클라이언트 IP</span><span class="sxs-lookup"><span data-stu-id="8d47d-192">client IP</span></span>
- <span data-ttu-id="8d47d-193">대상 파일 경로</span><span class="sxs-lookup"><span data-stu-id="8d47d-193">target file path</span></span>
- <span data-ttu-id="8d47d-194">타임스탬프 발생</span><span class="sxs-lookup"><span data-stu-id="8d47d-194">happened timestamp</span></span>
- <span data-ttu-id="8d47d-195">파일 이름</span><span class="sxs-lookup"><span data-stu-id="8d47d-195">file name</span></span>
- <span data-ttu-id="8d47d-196">사용자</span><span class="sxs-lookup"><span data-stu-id="8d47d-196">user</span></span>
- <span data-ttu-id="8d47d-197">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="8d47d-197">file extension</span></span>
- <span data-ttu-id="8d47d-198">파일 크기</span><span class="sxs-lookup"><span data-stu-id="8d47d-198">file size</span></span>
- <span data-ttu-id="8d47d-199">중요한 정보 유형(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="8d47d-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="8d47d-200">SHA1 값</span><span class="sxs-lookup"><span data-stu-id="8d47d-200">sha1 value</span></span>
- <span data-ttu-id="8d47d-201">SHA256 값</span><span class="sxs-lookup"><span data-stu-id="8d47d-201">sha256 value</span></span>
- <span data-ttu-id="8d47d-202">이전 파일 이름</span><span class="sxs-lookup"><span data-stu-id="8d47d-202">previous file name</span></span>
- <span data-ttu-id="8d47d-203">위치</span><span class="sxs-lookup"><span data-stu-id="8d47d-203">location</span></span>
- <span data-ttu-id="8d47d-204">상위</span><span class="sxs-lookup"><span data-stu-id="8d47d-204">parent</span></span>
- <span data-ttu-id="8d47d-205">파일 경로</span><span class="sxs-lookup"><span data-stu-id="8d47d-205">filepath</span></span>
- <span data-ttu-id="8d47d-206">원본 위치 유형</span><span class="sxs-lookup"><span data-stu-id="8d47d-206">source location type</span></span>
- <span data-ttu-id="8d47d-207">플랫폼</span><span class="sxs-lookup"><span data-stu-id="8d47d-207">platform</span></span>
- <span data-ttu-id="8d47d-208">장치 이름</span><span class="sxs-lookup"><span data-stu-id="8d47d-208">device name</span></span>
- <span data-ttu-id="8d47d-209">대상 위치 유형</span><span class="sxs-lookup"><span data-stu-id="8d47d-209">destination location type</span></span>
- <span data-ttu-id="8d47d-210">복사를 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8d47d-210">application that performed the copy</span></span>
- <span data-ttu-id="8d47d-211">엔드포인트용 Microsoft Defender 장치 ID(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="8d47d-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="8d47d-212">이동식 미디어 장치 제조업체</span><span class="sxs-lookup"><span data-stu-id="8d47d-212">removable media device manufacturer</span></span>
- <span data-ttu-id="8d47d-213">이동식 미디어 장치 모델</span><span class="sxs-lookup"><span data-stu-id="8d47d-213">removable media device model</span></span>
- <span data-ttu-id="8d47d-214">이동식 미디어 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="8d47d-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d47d-215">![USB 활동 특성에 복사](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="8d47d-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d47d-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8d47d-216">Next steps</span></span>

<span data-ttu-id="8d47d-217">이제 끝점 DLP에 대해 살펴보았으므로 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d47d-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="8d47d-218">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="8d47d-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="8d47d-219">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="8d47d-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="8d47d-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d47d-220">See also</span></span>

- [<span data-ttu-id="8d47d-221">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="8d47d-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="8d47d-222">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="8d47d-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="8d47d-223">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="8d47d-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8d47d-224">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="8d47d-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="8d47d-225">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="8d47d-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8d47d-226">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d47d-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="8d47d-227">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="8d47d-227">Insider Risk management</span></span>](insider-risk-management.md)
