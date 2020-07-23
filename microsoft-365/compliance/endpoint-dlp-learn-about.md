---
title: Microsoft 365 끝점 데이터 손실 방지(미리 보기) 알아보기
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
- SPO_Content
search.appverid:
- MET150
description: 'Microsoft 365 끝점 데이터 손실 방지는 파일 활동의 모니터링 및 해당 파일에 대한 보호 작업을 끝점으로 확장합니다. 파일은 Microsoft 365 규정 준수 솔루션에서 확인할 수 있습니다. '
ms.openlocfilehash: 5dfe8fae1e000b97d7c2a17d3d7582fd1b24934e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199986"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="602e2-104">Microsoft 365 끝점 데이터 손실 방지(미리 보기) 알아보기</span><span class="sxs-lookup"><span data-stu-id="602e2-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="602e2-105">Microsoft 365 DLP(데이터 손실 방지)를 사용하여 중요한 항목에 대해 수행 중인 작업을 모니터링하고 해당 항목이 의도치 않게 공유되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="602e2-106">DLP에 대한 자세한 내용은 [데이터 손실 방지 개요](data-loss-prevention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="602e2-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="602e2-107">**끝점 데이터 손실 방지**(끝점 DLP)는 DLP의 활동 모니터링 및 보호 기능을 Windows 10 장치의 중요한 항목으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="602e2-108">장치가 장치 관리에 등록된 경우 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-108">Once devices are onboarded into device management, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="602e2-109">모니터링 및 조치 가능한 끝점 활동</span><span class="sxs-lookup"><span data-stu-id="602e2-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="602e2-110">Microsoft 끝점 DLP를 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="602e2-111">해당 활동은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-111">This includes:</span></span>


|<span data-ttu-id="602e2-112">항목에 대한 활동</span><span class="sxs-lookup"><span data-stu-id="602e2-112">activity on item</span></span> |<span data-ttu-id="602e2-113">감사/통제</span><span class="sxs-lookup"><span data-stu-id="602e2-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="602e2-114">생성</span><span class="sxs-lookup"><span data-stu-id="602e2-114">created</span></span>    | <span data-ttu-id="602e2-115">감사</span><span class="sxs-lookup"><span data-stu-id="602e2-115">auditable</span></span>      |
|<span data-ttu-id="602e2-116">이름 변경</span><span class="sxs-lookup"><span data-stu-id="602e2-116">renamed</span></span>    |  <span data-ttu-id="602e2-117">감사</span><span class="sxs-lookup"><span data-stu-id="602e2-117">auditable</span></span>       |
|<span data-ttu-id="602e2-118">이동식 미디어에 복사 또는 생성</span><span class="sxs-lookup"><span data-stu-id="602e2-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="602e2-119">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="602e2-119">auditable and restrictable</span></span>|
|<span data-ttu-id="602e2-120">네트워크 공유에 복사(예: \\my-server\fileshare)</span><span class="sxs-lookup"><span data-stu-id="602e2-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="602e2-121">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="602e2-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="602e2-122">인쇄</span><span class="sxs-lookup"><span data-stu-id="602e2-122">printed</span></span> |    <span data-ttu-id="602e2-123">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="602e2-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="602e2-124">Chromium Edge를 통해 클라우드에 복사</span><span class="sxs-lookup"><span data-stu-id="602e2-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="602e2-125">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="602e2-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="602e2-126">허용되지 않는 앱 및 브라우저로 액세스</span><span class="sxs-lookup"><span data-stu-id="602e2-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="602e2-127">감사 및 통제</span><span class="sxs-lookup"><span data-stu-id="602e2-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="602e2-128">끝점 DLP의 다양한 기능</span><span class="sxs-lookup"><span data-stu-id="602e2-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="602e2-129">끝점 DLP를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="602e2-130">장치 관리 사용 설정</span><span class="sxs-lookup"><span data-stu-id="602e2-130">Enabling Device management</span></span>

<span data-ttu-id="602e2-131">장치 관리는 장치에서 원격 분석 수집을 사용하도록 설정하고 원격 분석 수집을 끝점 DLP 및 [참가자 위험 관리](insider-risk-management.md)와 같은 Microsoft 365 규정 준수 솔루션으로 가져오는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="602e2-132">DLP 정책에서 위치로 사용하려는 모든 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![장치 관리 사용 설정](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="602e2-134">장치 관리 센터에서 다운로드한 스크립트를 통해 온보딩 및 오프보딩이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="602e2-135">해당 센터는 각 배포 방법에 대한 사용자 지정 스크립트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="602e2-136">로컬 스크립트(최대 10대의 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="602e2-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="602e2-137">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="602e2-137">Group policy</span></span>
- <span data-ttu-id="602e2-138">System Center Configuration Manager(버전 1610 이상)</span><span class="sxs-lookup"><span data-stu-id="602e2-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="602e2-139">모바일 장치 관리/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="602e2-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="602e2-140">비 영구적인 컴퓨터에 대한 VDI 온보딩 스크립트</span><span class="sxs-lookup"><span data-stu-id="602e2-140">VDI onboarding scripts for non-persistent machines</span></span>

![장치 온보딩 페이지](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="602e2-142">[Microsoft 365 끝점 DLP 시작하기](endpoint-dlp-getting-started.md)의 절차를 사용하여 장치를 등록하세요.</span><span class="sxs-lookup"><span data-stu-id="602e2-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="602e2-143">[Microsoft Defender Advanced Threat Protection(Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)를 통해 장치를 등록한 경우 해당 장치는 자동으로 장치 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![관리된 장치 목록](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="602e2-145">끝점 DLP 데이터 확인하기</span><span class="sxs-lookup"><span data-stu-id="602e2-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="602e2-146">끝점 DLP는 활동 기반의 Om MIME 유형을 모니터링하므로 파일 확장명이 변경되더라도 활동은 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="602e2-147">공개 미리 보기에서 다음의 사항을 모두 봅니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-147">At public preview it watches all:</span></span>

- <span data-ttu-id="602e2-148">Word 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-148">Word files</span></span>
- <span data-ttu-id="602e2-149">PowerPoint 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-149">PowerPoint files</span></span>
- <span data-ttu-id="602e2-150">Excel 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-150">Excel files</span></span>
- <span data-ttu-id="602e2-151">PDF 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-151">PDF files</span></span>
- <span data-ttu-id="602e2-152">.csv 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-152">.csv files</span></span>
- <span data-ttu-id="602e2-153">.tsv 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-153">.tsv files</span></span>
- <span data-ttu-id="602e2-154">c 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-154">c files</span></span>
- <span data-ttu-id="602e2-155">클래스 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-155">class files</span></span>
- <span data-ttu-id="602e2-156">cpp 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-156">cpp files</span></span>
- <span data-ttu-id="602e2-157">cs 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-157">cs files</span></span>
- <span data-ttu-id="602e2-158">h 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-158">h files</span></span>
- <span data-ttu-id="602e2-159">java 파일</span><span class="sxs-lookup"><span data-stu-id="602e2-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="602e2-160">.txt와 원본 코드 파일은 기본적으로 감사되지 않습니다. DLP는 적용된 정책에 대해 해당 파일을 평가하고 이에 따라 사용자 작업이 감사 또는 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="602e2-161">장치가 등록되면 장치를 위치로 포함하는 모든 DLP 정책을 구성하고 배포하기 전에 감사 활동에 대한 정보가 활동 탐색기로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![활동 탐색기의 끝점 DLP 이벤트](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="602e2-163">끝점 DLP는 감사 활동에 대한 광범위한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="602e2-164">예를 들어 파일이 이동식 USB 미디어에 복사되는 경우 활동 세부 정보에 다음 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="602e2-165">활동 유형</span><span class="sxs-lookup"><span data-stu-id="602e2-165">activity type</span></span>
- <span data-ttu-id="602e2-166">클라이언트 IP</span><span class="sxs-lookup"><span data-stu-id="602e2-166">client IP</span></span>
- <span data-ttu-id="602e2-167">대상 파일 경로</span><span class="sxs-lookup"><span data-stu-id="602e2-167">target file path</span></span>
- <span data-ttu-id="602e2-168">타임스탬프 발생</span><span class="sxs-lookup"><span data-stu-id="602e2-168">happened timestamp</span></span>
- <span data-ttu-id="602e2-169">파일 이름</span><span class="sxs-lookup"><span data-stu-id="602e2-169">file name</span></span>
- <span data-ttu-id="602e2-170">사용자</span><span class="sxs-lookup"><span data-stu-id="602e2-170">user</span></span>
- <span data-ttu-id="602e2-171">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="602e2-171">file extension</span></span>
- <span data-ttu-id="602e2-172">파일 크기</span><span class="sxs-lookup"><span data-stu-id="602e2-172">file size</span></span>
- <span data-ttu-id="602e2-173">중요한 정보 유형(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="602e2-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="602e2-174">SHA1 값</span><span class="sxs-lookup"><span data-stu-id="602e2-174">sha1 value</span></span>
- <span data-ttu-id="602e2-175">SHA256 값</span><span class="sxs-lookup"><span data-stu-id="602e2-175">sha256 value</span></span>
- <span data-ttu-id="602e2-176">이전 파일 이름</span><span class="sxs-lookup"><span data-stu-id="602e2-176">previous file name</span></span>
- <span data-ttu-id="602e2-177">위치</span><span class="sxs-lookup"><span data-stu-id="602e2-177">location</span></span>
- <span data-ttu-id="602e2-178">상위</span><span class="sxs-lookup"><span data-stu-id="602e2-178">parent</span></span>
- <span data-ttu-id="602e2-179">파일 경로</span><span class="sxs-lookup"><span data-stu-id="602e2-179">filepath</span></span>
- <span data-ttu-id="602e2-180">원본 위치 유형</span><span class="sxs-lookup"><span data-stu-id="602e2-180">source location type</span></span>
- <span data-ttu-id="602e2-181">플랫폼</span><span class="sxs-lookup"><span data-stu-id="602e2-181">platform</span></span>
- <span data-ttu-id="602e2-182">장치 이름</span><span class="sxs-lookup"><span data-stu-id="602e2-182">device name</span></span>
- <span data-ttu-id="602e2-183">대상 위치 유형</span><span class="sxs-lookup"><span data-stu-id="602e2-183">destination location type</span></span>
- <span data-ttu-id="602e2-184">복사를 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="602e2-184">application that performed the copy</span></span>
- <span data-ttu-id="602e2-185">MDATP 장치 ID(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="602e2-185">MDATP device ID (if applicable)</span></span>
- <span data-ttu-id="602e2-186">이동식 미디어 장치 제조업체</span><span class="sxs-lookup"><span data-stu-id="602e2-186">removable media device manufacturer</span></span>
- <span data-ttu-id="602e2-187">이동식 미디어 장치 모델</span><span class="sxs-lookup"><span data-stu-id="602e2-187">removable media device model</span></span>
- <span data-ttu-id="602e2-188">이동식 미디어 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="602e2-188">removable media device serial number</span></span>

![USB 활동 특성에 복사](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="602e2-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="602e2-190">Next steps</span></span>

<span data-ttu-id="602e2-191">이제 끝점 DLP에 대해 살펴보았으므로 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="602e2-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="602e2-192">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="602e2-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="602e2-193">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="602e2-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="602e2-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="602e2-194">See also</span></span>

- [<span data-ttu-id="602e2-195">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="602e2-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="602e2-196">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="602e2-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="602e2-197">데이터 손실 방지 개요</span><span class="sxs-lookup"><span data-stu-id="602e2-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="602e2-198">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="602e2-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="602e2-199">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="602e2-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="602e2-200">Microsoft Defender Advanced Threat Protection(Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="602e2-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="602e2-201">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="602e2-201">Insider Risk management</span></span>](insider-risk-management.md)