---
title: Microsoft 규정 준수 확장(미리 보기)에 대해 알아보기
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 규정 준수 확장을 통해 파일 활동 및 보호 작업을 Google Chrome 브라우저로 확장
ms.openlocfilehash: c8a5795b3be8b393fd3a934504449bf6db0c2f01
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113384"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a><span data-ttu-id="d77c0-103">Microsoft 규정 준수 확장(미리 보기)에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="d77c0-103">Learn about the Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="d77c0-104">[끝점 데이터 손실 방지](endpoint-dlp-learn-about.md)(끝점 DLP)는 [Microsoft 365 데이터 손실 방지(DLP)](dlp-learn-about-dlp.md)의 활동 모니터링 및 보호 기능을 Windows 10 장치의 중요한 항목으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d77c0-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="d77c0-105">장치가 Microsoft 365 규정 준수 솔루션에 등록된 경우 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d77c0-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="d77c0-106">Windows 10 장치에 Microsoft 규정 준수 확장을 설치하면 조직에서는 사용자가 Google Chrome을 사용하여 클라우드 서비스에 중요한 항목에 액세스하거나 업로드하려고 할 때 이를 모니터링하고 DLP를 통해 보호 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d77c0-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="d77c0-107">모니터링하고 조치를 취할 수 있는 활동</span><span class="sxs-lookup"><span data-stu-id="d77c0-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="d77c0-108">Microsoft 규정 준수 확장을 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d77c0-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="d77c0-109">활동</span><span class="sxs-lookup"><span data-stu-id="d77c0-109">activity</span></span> |<span data-ttu-id="d77c0-110">설명</span><span class="sxs-lookup"><span data-stu-id="d77c0-110">description</span></span>  | <span data-ttu-id="d77c0-111">지원되는 정책 작업</span><span class="sxs-lookup"><span data-stu-id="d77c0-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d77c0-112">파일을 클라우드로 복사함</span><span class="sxs-lookup"><span data-stu-id="d77c0-112">file copied to cloud</span></span>  | <span data-ttu-id="d77c0-113">사용자가 Chrome 브라우저를 통해 제한된 서비스 도메인에 중요한 항목 업로드를 시도하는 경우 감지</span><span class="sxs-lookup"><span data-stu-id="d77c0-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="d77c0-114">감사, 차단</span><span class="sxs-lookup"><span data-stu-id="d77c0-114">audit, block</span></span>|
|<span data-ttu-id="d77c0-115">인쇄된 파일</span><span class="sxs-lookup"><span data-stu-id="d77c0-115">file printed</span></span>  |<span data-ttu-id="d77c0-116">사용자가 Chrome 브라우저에 열려 있는 중요한 항목을 로컬 또는 네트워크 프린터에 인쇄하려고 할 때 감지</span><span class="sxs-lookup"><span data-stu-id="d77c0-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="d77c0-117">감사, 오버라이드로 차단, 차단</span><span class="sxs-lookup"><span data-stu-id="d77c0-117">audit, block with override, block</span></span>|
|<span data-ttu-id="d77c0-118">파일을 클립보드로 복사함</span><span class="sxs-lookup"><span data-stu-id="d77c0-118">file copied to clipboard</span></span> |<span data-ttu-id="d77c0-119">사용자가 Chrome 브라우저에서 보고 있는 중요한 항목의 정보를 복사하려고 시도하는 경우를 감지한 다음 다른 앱, 프로세스 또는 항목에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d77c0-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="d77c0-120">감사, 오버라이드로 차단, 차단</span><span class="sxs-lookup"><span data-stu-id="d77c0-120">audit, block with override, block</span></span>|
|<span data-ttu-id="d77c0-121">이동식 저장소에 복사된 파일</span><span class="sxs-lookup"><span data-stu-id="d77c0-121">file copied to removable storage</span></span>    | <span data-ttu-id="d77c0-122">사용자가 Chrome 브라우저에 열려 있는 중요한 항목에서 이동식 미디어 또는 USB 장치로 중요한 항목 또는 정보를 복사하려고 할 때 감지</span><span class="sxs-lookup"><span data-stu-id="d77c0-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="d77c0-123">감사, 오버라이드로 차단, 차단</span><span class="sxs-lookup"><span data-stu-id="d77c0-123">audit, block with override, block</span></span>|
|<span data-ttu-id="d77c0-124">파일을 네트워크 공유에 복사함</span><span class="sxs-lookup"><span data-stu-id="d77c0-124">file copied to network share</span></span>  |<span data-ttu-id="d77c0-125">사용자가 Chrome 브라우저에 열려 있는 중요한 항목에서 네트워크 공유 또는 매핑된 네트워크 드라이브로 중요한 항목 또는 정보를 복사하려고 하는 경우 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="d77c0-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="d77c0-126">감사, 오버라이드로 차단, 차단</span><span class="sxs-lookup"><span data-stu-id="d77c0-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="d77c0-127">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="d77c0-127">Deployment process</span></span>
1. [<span data-ttu-id="d77c0-128">끝점 데이터 손실 방지 시작</span><span class="sxs-lookup"><span data-stu-id="d77c0-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="d77c0-129">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="d77c0-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="d77c0-130">Windows 10 장치에 확장 설치</span><span class="sxs-lookup"><span data-stu-id="d77c0-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="d77c0-131">클라우드 서비스에 대한 업로드를 제한하는 [DLP 정책을 만들거나 편집](create-test-tune-dlp-policy.md)하거나 허용되지 않는 브라우저 작업으로 액세스하여 Windows 10 장치에 적용</span><span class="sxs-lookup"><span data-stu-id="d77c0-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="d77c0-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d77c0-132">Next steps</span></span>

<span data-ttu-id="d77c0-133">전체 배포 절차 및 시나리오는 [Microsoft 규정 준수 확장 시작하기](dlp-chrome-get-started.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d77c0-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="d77c0-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d77c0-134">See also</span></span>

- [<span data-ttu-id="d77c0-135">Microsoft 규정 준수 확장 시작하기</span><span class="sxs-lookup"><span data-stu-id="d77c0-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="d77c0-136">Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d77c0-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="d77c0-137">Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기</span><span class="sxs-lookup"><span data-stu-id="d77c0-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="d77c0-138">Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기</span><span class="sxs-lookup"><span data-stu-id="d77c0-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="d77c0-139">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="d77c0-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="d77c0-140">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="d77c0-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="d77c0-141">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="d77c0-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d77c0-142">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d77c0-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="d77c0-143">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="d77c0-143">Insider Risk management</span></span>](insider-risk-management.md)
