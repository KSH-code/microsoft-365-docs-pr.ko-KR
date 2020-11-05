---
title: Microsoft 365 서비스 및 응용 프로그램과의 SIEM 서버 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Microsoft 365 클라우드 서비스 및 응용 프로그램과의 SIEM (보안 정보 및 이벤트 관리) 서버 통합에 대 한 개요를 확인 하세요.
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919767"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="e8829-103">Microsoft 365 서비스 및 응용 프로그램과의 SIEM (보안 정보 및 이벤트 관리) 서버 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="e8829-104">요약</span><span class="sxs-lookup"><span data-stu-id="e8829-104">Summary</span></span>

<span data-ttu-id="e8829-105">조직에서 SIEM (보안 정보 및 이벤트 관리) 서버를 사용 하거나 사용할 계획 입니까?</span><span class="sxs-lookup"><span data-stu-id="e8829-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="e8829-106">Microsoft 365 또는 Office 365와 통합 되는 방식을 궁금할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e8829-107">이 문서에서는 SIEM server를 Microsoft 365 서비스 및 응용 프로그램에 통합 하는 데 사용할 수 있는 리소스 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="e8829-108">아직 SIEM 서버가 없고 옵션을 탐색 하는 경우 **[Microsoft Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview)** 을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8829-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="e8829-109">SIEM 서버가 필요 합니까?</span><span class="sxs-lookup"><span data-stu-id="e8829-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="e8829-110">SIEM 서버가 필요한 지 여부는 조직의 보안 요구 사항 및 데이터 위치와 같은 많은 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="e8829-111">Microsoft 365에는 SIEM 서버와 같은 추가 서버 없이 다양 한 조직의 보안 요구 사항을 충족 하는 다양 한 보안 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="e8829-112">일부 조직에는 SIEM 서버를 사용 해야 하는 특별 한 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="e8829-113">그 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-113">Here are some examples:</span></span>

- <span data-ttu-id="e8829-114">*Fabrikam* 에는 온-프레미스와 일부 콘텐츠 및 응용 프로그램, 클라우드 (하이브리드 클라우드 배포)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="e8829-115">모든 콘텐츠 및 응용 프로그램에서 보안 보고서를 가져오려면 Fabrikam은 SIEM 서버를 구현 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="e8829-116">*Contoso* 는 보안 요구 사항이 특별히 엄격한 금융 서비스 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="e8829-117">필요한 추가 보안 보호 기능을 활용 하기 위해 해당 환경에 SIEM 서버를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="e8829-118">Microsoft 365과의 SIEM 서버 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="e8829-119">SIEM 서버는 다양 한 Microsoft 365 서비스 및 응용 프로그램에서 데이터를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="e8829-120">다음 표에는 몇 가지 Microsoft 365 서비스와 응용 프로그램과 SIEM 서버 입력 및 리소스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="e8829-121">Microsoft 365 서비스 또는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e8829-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="e8829-122">SIEM server 입력/메서드</span><span class="sxs-lookup"><span data-stu-id="e8829-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="e8829-123">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="e8829-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="e8829-124">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8829-124">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="e8829-125">감사 로그</span><span class="sxs-lookup"><span data-stu-id="e8829-125">Audit logs</span></span>|[<span data-ttu-id="e8829-126">Microsoft Defender for Office 365의 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-126">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="e8829-127">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8829-127">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="e8829-128">Azure에서 호스트 되는 HTTPS 끝점</span><span class="sxs-lookup"><span data-stu-id="e8829-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="e8829-129">REST API</span><span class="sxs-lookup"><span data-stu-id="e8829-129">REST API</span></span>|[<span data-ttu-id="e8829-130">SIEM 도구에 대 한 알림 가져오기</span><span class="sxs-lookup"><span data-stu-id="e8829-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="e8829-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8829-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="e8829-132">로그 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-132">Log integration</span></span>|[<span data-ttu-id="e8829-133">Microsoft Cloud App Security와의 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="e8829-134">[Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview)을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="e8829-135">Azure 센티널은 Microsoft 솔루션용 커넥터와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="e8829-136">이러한 커넥터는 "외부에서" 사용 가능 하며 실시간 통합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="e8829-137">Microsoft 365 Defender 솔루션 및 microsoft 365 서비스 (Office 365, Azure AD, Id 용 Microsoft Defender, Microsoft Cloud App Security 등)와 함께 Azure 센티널을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-137">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="e8829-138">감사 로깅을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-138">Audit logging must be turned on</span></span>

<span data-ttu-id="e8829-139">SIEM 서버 통합을 구성 하기 전에 감사 로깅이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8829-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="e8829-140">SharePoint Online, 비즈니스용 OneDrive 및 Azure Active Directory의 경우 [보안 & 준수 센터에서 감사 로깅이 설정 됩니다](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="e8829-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="e8829-141">Exchange Online의 경우 [사서함 감사 관리](../../compliance/enable-mailbox-auditing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8829-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="e8829-142">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="e8829-142">More resources</span></span>

[<span data-ttu-id="e8829-143">Azure Defender에서 보안 솔루션 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-143">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="e8829-144">SIEM을 사용 하 여 Microsoft Graph 보안 API 알림 통합</span><span class="sxs-lookup"><span data-stu-id="e8829-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
