---
title: 방식 TLS 1.0 및 1.1 in Office 365 GCC High 및 DoD
description: Microsoft가 Office 365의 GCC High 및 DoD 환경에서 TLS 1.1 및 1.0에 대 한 지원을 중단 하 고 TLS 1.2 사용을 준비 하는 방법에 대해 설명 합니다.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024828"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="d1b3a-103">방식 TLS 1.0 및 1.1 in Office 365 GCC High 및 DoD</span><span class="sxs-lookup"><span data-stu-id="d1b3a-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1b3a-104">전 세계에 전염병이 유행하고 있으며 Microsoft는 이로 인해 고객과 파트너가 영향을 받는다는 사실을 인지하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="d1b3a-105">상용 고객의 부담을 덜기 위해 TLS 1.0 및 1.1에 대한 지원 중단을 일시적으로 중단했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="d1b3a-106">현재의 위기가 안정화된 후에 개정된 일정에 따라 업데이트가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="d1b3a-107">(이 문서는 변경 사항을 반영하기 위해 개정되었습니다.)</span><span class="sxs-lookup"><span data-stu-id="d1b3a-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="d1b3a-108">요약</span><span class="sxs-lookup"><span data-stu-id="d1b3a-108">Summary</span></span>

<span data-ttu-id="d1b3a-109">FedRAMP (미 연방 위험 및 권한 부여 관리 프로그램)에 대 한 최신 준수 표준을 준수 하기 위해, GCC High 및 DoD 환경에 대해 Microsoft Office 365의 TLS (사용 중지 Transport Layer Security) 버전 1.1 및 1.0로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="d1b3a-110">이 변경 사항에 [대 한 자세한 내용을 보려면 Office 365에서 TLS 1.2의 필수 사용을 준비 하기 위한](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Microsoft 지원 서비스를 통해 이전에 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="d1b3a-111">데이터 보안이 중요 하다는 것을 이해 했으며, 서비스 사용에 영향을 줄 수 있는 변경 사항에 대 한 투명성을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="d1b3a-112">[MICROSOFT TLS 1.0 구현](https://support.microsoft.com/help/3117336) 에는 알려진 보안 취약점이 없더라도 FedRAMP 준수 표준에 대 한 커밋된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="d1b3a-113">따라서 사용 중지는 GCC High 및 DoD 환경에서 2020, 1 월 15 일에 시작 하는 TLS 1.1 및 365 1.0을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="d1b3a-114">TLS 1.1 및 1.0 종속성을 제거 하는 방법에 대 한 자세한 내용은 다음 백서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="d1b3a-115">TLS 1.0 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d1b3a-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="d1b3a-116">TLS 1.1 및 1.0에 대 한이 변경 내용을 준비할 때는 대신 TLS 버전 1.2을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="d1b3a-117">자세한 내용은 [Office 365에서 TLS 1.2의 필수 사용 준비](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="d1b3a-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d1b3a-118">More information</span></span>

<span data-ttu-id="d1b3a-119">2020 년 1 월 15 일부터 시작 하 여 GCC High 및 DoD 환경에서 Office 365을 사용 중지 TLS 1.1 및 1.0이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="d1b3a-120">2020 년 1 월 15 일까 지, 클라이언트 서버와 브라우저 서버의 모든 조합은 TLS 버전 1.2 (이상 버전)를 사용 하 여 Office 365 서비스에 문제가 없는 모든 연결을 설정할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="d1b3a-121">이렇게 하려면 클라이언트 서버 및 브라우저 서버의 특정 조합에 대 한 업데이트를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="d1b3a-122">TLS 버전 1.2 이상 버전의 1 월 2020 15 일을 업데이트 하지 않으면 Office 365에 연결 하려고 할 때 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="d1b3a-123">또한 해결의 일부로 TLS 1.2 이상 버전으로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="d1b3a-124">다음 클라이언트는 TLS 1.2를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="d1b3a-125">Android 4.3 이하 버전</span><span class="sxs-lookup"><span data-stu-id="d1b3a-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="d1b3a-126">Firefox 5.0 이하 버전</span><span class="sxs-lookup"><span data-stu-id="d1b3a-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="d1b3a-127">Windows 7 및 이전 버전의 Internet Explorer 8 – 10</span><span class="sxs-lookup"><span data-stu-id="d1b3a-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="d1b3a-128">Windows Phone 8.0의 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="d1b3a-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="d1b3a-129">Safari 6.0.4/OS X 10.8.4 및 이전 버전</span><span class="sxs-lookup"><span data-stu-id="d1b3a-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="d1b3a-130">Office 365 GCC High 및 DoD에 대 한 중단 된 액세스를 유지 관리할 수 있도록 클라이언트를 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="d1b3a-131">Microsoft Online services에 대 한 연결을 분석 하 여 대부분의 서비스 및 끝점이 아주 작은 TLS 1.1 및 1.0 사용을 확인 하지만, TLS 1.1 및 1.0에 대 한 지원을 위해 필요에 따라 영향을 받는 클라이언트나 서버를 업데이트할 수 있도록이 변경 사항에 대 한 통지를 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="d1b3a-132">하이브리드 시나리오 또는 AD FS (Active Directory Federation Services)에 대해 온-프레미스 인프라를 사용 하는 경우, 인프라에서 TLS 1.2 이상 버전을 사용 하는 인바운드 및 아웃 바운드 연결을 모두 지원할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="d1b3a-133">TLS 1.2를 사용할 수 없는 나열 된 클라이언트를 사용 하는 경우 발생할 수 있는 중단 외에도 TLS 1.1 및 1.0를 제거 하면 다음 Microsoft 제품을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="d1b3a-134">Lync 전화</span><span class="sxs-lookup"><span data-stu-id="d1b3a-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="d1b3a-135">참조</span><span class="sxs-lookup"><span data-stu-id="d1b3a-135">References</span></span>

<span data-ttu-id="d1b3a-136">다음 지원 문서에서는 클라이언트가 TLS 1.2을 사용 하 고 있는지 확인 하는 데 도움이 되는 지침 및 참조에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b3a-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="d1b3a-137">Office 365에서 TLS 1.2의 필수 사용 준비</span><span class="sxs-lookup"><span data-stu-id="d1b3a-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
