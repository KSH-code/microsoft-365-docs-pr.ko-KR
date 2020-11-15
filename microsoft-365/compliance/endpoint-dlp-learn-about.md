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
description: 'Microsoft 365 끝점 데이터 손실 방지는 파일 활동과 해당 파일에 대한 보호 작업의 모니터링을 끝점으로 확장합니다. 파일은 Microsoft 365 규정 준수 솔루션에서 확인할 수 있습니다. '
ms.openlocfilehash: e469872dac19db08f7b525c8a5ada725c75bfa10
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072977"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="102da-104">Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="102da-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="102da-p102">Microsoft 365 DLP(데이터 손실 방지)를 사용하여 중요하다고 판단한 항목에 대해 수행되는 작업을 모니터링하고 해당 항목이 의도치 않게 공유되는 것을 방지할 수 있습니다. DLP에 대한 자세한 내용은 [데이터 손실 방지 개요](data-loss-prevention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="102da-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="102da-p103">**끝점 데이터 손실 방지** (끝점 DLP)는 Windows 10 장치에 있는 중요한 항목으로 DLP의 활동 모니터링 및 보호 기능을 확장합니다. 장치가 Microsoft 365 규정 준수 솔루션에 등록되면, [활동 탐색기](data-classification-activity-explorer.md)에서 사용자가 중요한 항목으로 수행하는 작업에 대한 정보를 확인할 수 있으며 이러한 항목에 대해 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 보호 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="102da-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="102da-109">모니터링 및 조치를 취할 수 있는 끝점 활동</span><span class="sxs-lookup"><span data-stu-id="102da-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="102da-p104">Microsoft 끝점 DLP를 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다. 여기에는 다음과 같은 활동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="102da-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="102da-112">항목에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="102da-112">activity on item</span></span> |<span data-ttu-id="102da-113">감사/통제</span><span class="sxs-lookup"><span data-stu-id="102da-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="102da-114">생성</span><span class="sxs-lookup"><span data-stu-id="102da-114">created</span></span>    | <span data-ttu-id="102da-115">감사</span><span class="sxs-lookup"><span data-stu-id="102da-115">auditable</span></span>      |
|<span data-ttu-id="102da-116">이름 변경</span><span class="sxs-lookup"><span data-stu-id="102da-116">renamed</span></span>    |  <span data-ttu-id="102da-117">감사</span><span class="sxs-lookup"><span data-stu-id="102da-117">auditable</span></span>       |
|<span data-ttu-id="102da-118">이동식 미디어에 복사 또는 생성</span><span class="sxs-lookup"><span data-stu-id="102da-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="102da-119">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="102da-119">auditable and restrictable</span></span>|
|<span data-ttu-id="102da-120">네트워크 공유에 복사(예: \\my-server\fileshare)</span><span class="sxs-lookup"><span data-stu-id="102da-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="102da-121">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="102da-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="102da-122">인쇄</span><span class="sxs-lookup"><span data-stu-id="102da-122">printed</span></span> |    <span data-ttu-id="102da-123">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="102da-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="102da-124">Chromium Edge를 통해 클라우드에 복사</span><span class="sxs-lookup"><span data-stu-id="102da-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="102da-125">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="102da-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="102da-126">허용되지 않는 앱 및 브라우저로 액세스</span><span class="sxs-lookup"><span data-stu-id="102da-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="102da-127">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="102da-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="102da-128">끝점 DLP의 다양한 기능</span><span class="sxs-lookup"><span data-stu-id="102da-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="102da-129">끝점 DLP를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="102da-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="102da-130">장치 관리를 사용하도록 설정하기</span><span class="sxs-lookup"><span data-stu-id="102da-130">Enabling Device management</span></span>

<span data-ttu-id="102da-p105">장치 관리는 장치에서 원격 분석 수집을 사용하도록 설정하고 이를 끝점 DLP 및 [참가자 위험 관리](insider-risk-management.md)와 같은 Microsoft 365 규정 준수 솔루션으로 가져오는 기능입니다. DLP 정책에서 위치로 사용하려는 모든 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="102da-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="102da-133">![장치 관리를 사용하도록 설정](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="102da-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="102da-p106">온보딩 및 오프보딩은 장치 관리 센터에서 다운로드하는 스크립트를 통해 처리됩니다. 장치 관리 센터는 각 배포 방법에 대한 사용자 지정 스크립트를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="102da-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="102da-136">로컬 스크립트(최대 10대의 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="102da-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="102da-137">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="102da-137">Group policy</span></span>
- <span data-ttu-id="102da-138">System Center Configuration Manager(버전 1610 이상)</span><span class="sxs-lookup"><span data-stu-id="102da-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="102da-139">모바일 장치 관리/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="102da-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="102da-140">비 영구적인 컴퓨터에 대한 VDI 온보딩 스크립트</span><span class="sxs-lookup"><span data-stu-id="102da-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="102da-141">![장치 온보딩 페이지](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="102da-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="102da-142">[Microsoft 365 끝점 DLP 시작하기](endpoint-dlp-getting-started.md)의 절차를 사용하여 장치를 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="102da-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="102da-143">[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)를 통해 장치를 온보딩한 경우, 해당 장치는 장치 목록에 자동으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="102da-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="102da-144">![관리된 장치 목록](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="102da-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="102da-145">끝점 DLP 데이터 확인하기</span><span class="sxs-lookup"><span data-stu-id="102da-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="102da-p107">끝점 DLP는 MIME 형식에 따라 활동을 모니터링하여, 파일 확장명이 변경이 되더라도 작업이 캡처됩니다. 공개 미리 보기에서 다음을 모두 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="102da-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="102da-148">Word 파일</span><span class="sxs-lookup"><span data-stu-id="102da-148">Word files</span></span>
- <span data-ttu-id="102da-149">PowerPoint 파일</span><span class="sxs-lookup"><span data-stu-id="102da-149">PowerPoint files</span></span>
- <span data-ttu-id="102da-150">Excel 파일</span><span class="sxs-lookup"><span data-stu-id="102da-150">Excel files</span></span>
- <span data-ttu-id="102da-151">PDF 파일</span><span class="sxs-lookup"><span data-stu-id="102da-151">PDF files</span></span>
- <span data-ttu-id="102da-152">.csv 파일</span><span class="sxs-lookup"><span data-stu-id="102da-152">.csv files</span></span>
- <span data-ttu-id="102da-153">.tsv 파일</span><span class="sxs-lookup"><span data-stu-id="102da-153">.tsv files</span></span>
- <span data-ttu-id="102da-154">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="102da-154">.txt files</span></span>
- <span data-ttu-id="102da-155">RTF 파일</span><span class="sxs-lookup"><span data-stu-id="102da-155">.rtf files</span></span>
- <span data-ttu-id="102da-156">c 파일</span><span class="sxs-lookup"><span data-stu-id="102da-156">.c files</span></span>
- <span data-ttu-id="102da-157">클래스 파일</span><span class="sxs-lookup"><span data-stu-id="102da-157">.class files</span></span>
- <span data-ttu-id="102da-158">cpp 파일</span><span class="sxs-lookup"><span data-stu-id="102da-158">.cpp files</span></span>
- <span data-ttu-id="102da-159">cs 파일</span><span class="sxs-lookup"><span data-stu-id="102da-159">.cs files</span></span>
- <span data-ttu-id="102da-160">h 파일</span><span class="sxs-lookup"><span data-stu-id="102da-160">.h files</span></span>
- <span data-ttu-id="102da-161">.java 파일</span><span class="sxs-lookup"><span data-stu-id="102da-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="102da-p108">끝점 DLP는 DLP 정책을 기준으로 위의 모든 유형의 파일을 평가하고 그에 따라 보호 조치를 적용합니다. DLP 정책과 일치하는 모든 파일은 차단되지 않은 경우에도 지원되는 모든 작업에 대해 감사됩니다. 또한 Word, PowerPoint, Excel, PDF 및 .csv 파일에서 수행되는 파일 작업은 DLP 정책이 있는지 또는 이러한 파일과 일치하는지 여부에 관계없이 기본적으로 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="102da-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="102da-165">[DLP 경고 관리 대시보드](dlp-configure-view-alerts-policies.md)로 이동하여 끝점 장치에 적용되는 DLP 정책과 관련된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="102da-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![경고 정보](../media/Alert-info-1.png)

<span data-ttu-id="102da-167">동일한 대시보드에서 서식 있는 메타데이터와 관련된 이벤트 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="102da-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![이벤트 정보](../media/Event-info-1.png)

<span data-ttu-id="102da-169">장치가 등록되면 장치를 위치로 포함하는 모든 DLP 정책을 구성하고 배포하기 전에 감사 활동에 대한 정보가 활동 탐색기로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="102da-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="102da-170">![활동 탐색기의 끝점 DLP 이벤트](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="102da-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="102da-171">끝점 DLP는 감사 활동에 대한 광범위한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="102da-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="102da-172">예를 들어 파일이 이동식 USB 미디어에 복사되는 경우 활동 세부 정보에 다음 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="102da-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="102da-173">활동 유형</span><span class="sxs-lookup"><span data-stu-id="102da-173">activity type</span></span>
- <span data-ttu-id="102da-174">클라이언트 IP</span><span class="sxs-lookup"><span data-stu-id="102da-174">client IP</span></span>
- <span data-ttu-id="102da-175">대상 파일 경로</span><span class="sxs-lookup"><span data-stu-id="102da-175">target file path</span></span>
- <span data-ttu-id="102da-176">타임스탬프 발생</span><span class="sxs-lookup"><span data-stu-id="102da-176">happened timestamp</span></span>
- <span data-ttu-id="102da-177">파일 이름</span><span class="sxs-lookup"><span data-stu-id="102da-177">file name</span></span>
- <span data-ttu-id="102da-178">사용자</span><span class="sxs-lookup"><span data-stu-id="102da-178">user</span></span>
- <span data-ttu-id="102da-179">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="102da-179">file extension</span></span>
- <span data-ttu-id="102da-180">파일 크기</span><span class="sxs-lookup"><span data-stu-id="102da-180">file size</span></span>
- <span data-ttu-id="102da-181">중요한 정보 유형(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="102da-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="102da-182">SHA1 값</span><span class="sxs-lookup"><span data-stu-id="102da-182">sha1 value</span></span>
- <span data-ttu-id="102da-183">SHA256 값</span><span class="sxs-lookup"><span data-stu-id="102da-183">sha256 value</span></span>
- <span data-ttu-id="102da-184">이전 파일 이름</span><span class="sxs-lookup"><span data-stu-id="102da-184">previous file name</span></span>
- <span data-ttu-id="102da-185">위치</span><span class="sxs-lookup"><span data-stu-id="102da-185">location</span></span>
- <span data-ttu-id="102da-186">상위</span><span class="sxs-lookup"><span data-stu-id="102da-186">parent</span></span>
- <span data-ttu-id="102da-187">파일 경로</span><span class="sxs-lookup"><span data-stu-id="102da-187">filepath</span></span>
- <span data-ttu-id="102da-188">원본 위치 유형</span><span class="sxs-lookup"><span data-stu-id="102da-188">source location type</span></span>
- <span data-ttu-id="102da-189">플랫폼</span><span class="sxs-lookup"><span data-stu-id="102da-189">platform</span></span>
- <span data-ttu-id="102da-190">장치 이름</span><span class="sxs-lookup"><span data-stu-id="102da-190">device name</span></span>
- <span data-ttu-id="102da-191">대상 위치 유형</span><span class="sxs-lookup"><span data-stu-id="102da-191">destination location type</span></span>
- <span data-ttu-id="102da-192">복사를 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="102da-192">application that performed the copy</span></span>
- <span data-ttu-id="102da-193">엔드포인트용 Microsoft Defender 장치 ID(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="102da-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="102da-194">이동식 미디어 장치 제조업체</span><span class="sxs-lookup"><span data-stu-id="102da-194">removable media device manufacturer</span></span>
- <span data-ttu-id="102da-195">이동식 미디어 장치 모델</span><span class="sxs-lookup"><span data-stu-id="102da-195">removable media device model</span></span>
- <span data-ttu-id="102da-196">이동식 미디어 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="102da-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="102da-197">![USB 활동 특성에 복사](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="102da-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="102da-198">다음 단계</span><span class="sxs-lookup"><span data-stu-id="102da-198">Next steps</span></span>

<span data-ttu-id="102da-199">이제 끝점 DLP에 대해 살펴보았으므로 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="102da-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="102da-200">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="102da-200">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="102da-201">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="102da-201">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="102da-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="102da-202">See also</span></span>

- [<span data-ttu-id="102da-203">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="102da-203">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="102da-204">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="102da-204">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="102da-205">데이터 손실 방지 개요</span><span class="sxs-lookup"><span data-stu-id="102da-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="102da-206">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="102da-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="102da-207">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="102da-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="102da-208">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="102da-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="102da-209">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="102da-209">Insider Risk management</span></span>](insider-risk-management.md)
