---
title: Microsoft 365 GCC High 및 DoD에서 TLS 1.0 및 1.1을 사용 하지 않습니다.
description: Microsoft가 Microsoft 365의 GCC High 및 DoD 환경에서 TLS 1.1 및 1.0에 대한 지원을 사용할 수 없는 방법을 논의합니다.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: d4da76268791e36bd01b5d6f6140fd52c70b3b4a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454197"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="d96b9-103">Microsoft 365 GCC High 및 DoD에서 TLS 1.0 및 1.1을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="d96b9-104">요약</span><span class="sxs-lookup"><span data-stu-id="d96b9-104">Summary</span></span>

<span data-ttu-id="d96b9-105">FedRAMP(Federal Risk and Authorization Management Program)에 대한 최신 규정 준수 표준을 준수하기 위해 Microsoft 365 for GCC High 및 DoD 환경에서 TLS(전송 계층 보안) 버전 1.1 및 1.0을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="d96b9-106">이 변경 사항은 [Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비에서 Microsoft 지원을 통해 이전에 발표했습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="d96b9-107">데이터의 보안이 중요하며, 서비스 사용에 영향을 줄 수 있는 변경 내용에 대한 투명성을 확보하기 위해 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="d96b9-108">Microsoft [TLS 1.0](https://support.microsoft.com/help/3117336) 구현에는 알려진 보안 취약성은 없습니다. 하지만 FedRAMP 규정 준수 표준을 준수하기 위해 계속 최선을 다하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="d96b9-109">따라서 2020년 1월 15일 GCC High 및 DoD 환경에서 Microsoft 365에서 TLS 1.1 및 1.0을 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="d96b9-110">TLS 1.1 및 1.0 종속성 제거 방법에 대한 자세한 내용은 다음 백서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d96b9-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="d96b9-111">TLS 1.0 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d96b9-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="d96b9-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d96b9-112">More information</span></span>

<span data-ttu-id="d96b9-113">2020년 1월 15일부터 GCC High 및 DoD 환경의 Microsoft 365에서 TLS 1.1 및 1.0을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="d96b9-114">2020년 1월 15일까지 모든 클라이언트 서버 및 브라우저 서버 조합은 TLS 버전 1.2(또는 이후 버전)를 사용하여 Microsoft 365에 대한 문제 없이 모든 연결을 만들 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="d96b9-115">이 경우 클라이언트 서버와 브라우저 서버의 특정 조합에 대한 업데이트가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="d96b9-116">SharePoint 및 OneDrive의 경우 TLS 1.2를 지원하도록 .NET을 업데이트하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="d96b9-117">자세한 내용은 [클라이언트에서 TLS 1.2를 사용하도록 설정하는 방법을 참조하세요.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="d96b9-117">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="d96b9-118">Office 365 GCC High 및 DoD에 대한 무정한 액세스를 유지 관리하려면 클라이언트 컴퓨터를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="d96b9-119">TLS 1.2를 사용하려면 TLS 1.0 또는 TLS 1.1을 통해 Microsoft 365 API를 호출하는 응용 프로그램을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="d96b9-120">.NET 4.5는 기본적으로 TLS 1.1로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="d96b9-121">.NET 구성을 업데이트하려면 [클라이언트에서 TLS(전송 계층 보안) 1.2를](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="d96b9-122">자세한 내용은 [Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d96b9-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="d96b9-123">다음 클라이언트 응용 프로그램에서 TLS 1.2를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="d96b9-124">Android 4.3 이하 버전</span><span class="sxs-lookup"><span data-stu-id="d96b9-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="d96b9-125">Firefox 5.0 이하 버전</span><span class="sxs-lookup"><span data-stu-id="d96b9-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="d96b9-126">windows 7 및 이전 버전의 Internet Explorer 8–10</span><span class="sxs-lookup"><span data-stu-id="d96b9-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="d96b9-127">windows Internet Explorer 8.0의 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="d96b9-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="d96b9-128">Safari 6.0.4/OS X 10.8.4 이전 버전</span><span class="sxs-lookup"><span data-stu-id="d96b9-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="d96b9-129">Microsoft Online 서비스에 대한 현재 연결을 분석한 결과 대부분의 서비스 및 끝점에 TLS 1.1 및 1.0 사용량이 거의 없는 것으로 나타났지만 TLS 1.1 및 1.0에 대한 지원이 종료되기 전에 필요한 경우 영향을 받는 클라이언트 또는 서버를 업데이트할 수 있도록 이 변경에 대한 공지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="d96b9-130">하이브리드 시나리오 또는 AD FS(Active Directory Federation Services)에 대해 모든 사내 인프라를 사용하는 경우 인프라가 TLS 1.2(또는 이후 버전)를 사용하는 인바운드 및 아웃바운드 연결을 모두 지원할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="d96b9-131">TLS 1.2를 사용할 수 없는 나열된 클라이언트를 사용하는 경우의 정전 외에도 TLS 1.1 및 1.0을 제거하면 다음 Microsoft 제품을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d96b9-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="d96b9-132">Lync 전화</span><span class="sxs-lookup"><span data-stu-id="d96b9-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="d96b9-133">참조</span><span class="sxs-lookup"><span data-stu-id="d96b9-133">References</span></span>

<span data-ttu-id="d96b9-134">클라이언트가 TLS 1.2를 사용하고 있는지를 확인 하는 데 도움이 되는 지침 및 참조는 [Office 365에서 TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d96b9-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
