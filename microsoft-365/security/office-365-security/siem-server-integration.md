---
title: MICROSOFT 365 서비스 및 응용 프로그램과 SIEM 서버 통합
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Microsoft 365 클라우드 서비스 및 응용 프로그램과 SIEM(보안 정보 및 이벤트 관리) 서버 통합 개요 보기
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167146"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="a7a02-103">Microsoft 365 서비스 및 응용 프로그램과 SIEM(보안 정보 및 이벤트 관리) 서버 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="a7a02-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="a7a02-104">**Applies to**</span></span>
- [<span data-ttu-id="a7a02-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a7a02-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="a7a02-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="a7a02-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="a7a02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7a02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="a7a02-108">요약</span><span class="sxs-lookup"><span data-stu-id="a7a02-108">Summary</span></span>

<span data-ttu-id="a7a02-109">조직에서 SIEM(보안 정보 및 이벤트 관리) 서버를 사용 중입니까 아니면 사용 계획입니까?</span><span class="sxs-lookup"><span data-stu-id="a7a02-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="a7a02-110">Microsoft 365 또는 Office 365와 어떻게 통합하는지 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a7a02-111">이 문서에서는 SIEM 서버를 Microsoft 365 서비스 및 응용 프로그램과 통합하는 데 사용할 수 있는 리소스 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="a7a02-112">SIEM 서버가 아직 없는 경우 **[Microsoft Azure Sentinel을 고려하세요.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="a7a02-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="a7a02-113">SIEM 서버가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="a7a02-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="a7a02-114">SIEM 서버가 필요한지 여부는 조직의 보안 요구 사항 및 데이터가 있는 위치와 같은 다양한 요인에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="a7a02-115">Microsoft 365에는 SIEM 서버와 같은 추가 서버 없이도 많은 조직의 보안 요구를 충족하는 다양한 보안 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="a7a02-116">일부 조직에서는 SIEM 서버를 사용해야 하는 특별한 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="a7a02-117">그 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-117">Here are some examples:</span></span>

- <span data-ttu-id="a7a02-118">*Fabrikam에는* 일부 콘텐츠 및 응용 프로그램이 있으며, 일부 콘텐츠와 응용 프로그램은 클라우드에 있습니다(하이브리드 클라우드 배포).</span><span class="sxs-lookup"><span data-stu-id="a7a02-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="a7a02-119">모든 콘텐츠 및 응용 프로그램에서 보안 보고서를 얻기 위해 Fabrikam은 SIEM 서버를 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="a7a02-120">*Contoso는* 특히 엄격한 보안 요구 사항이 있는 금융 서비스 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="a7a02-121">필요한 추가 보안 보호를 활용하기 위해 환경에 SIEM 서버를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="a7a02-122">MICROSOFT 365와 SIEM 서버 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="a7a02-123">SIEM 서버는 다양한 Microsoft 365 서비스 및 응용 프로그램에서 데이터를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="a7a02-124">다음 표에는 자세한 내용을 알아보기 위한 SIEM 서버 입력 및 리소스와 함께 여러 Microsoft 365 서비스 및 응용 프로그램이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="a7a02-125">Microsoft 365 서비스 또는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a7a02-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="a7a02-126">SIEM 서버 입력/메서드</span><span class="sxs-lookup"><span data-stu-id="a7a02-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="a7a02-127">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="a7a02-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="a7a02-128">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a7a02-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="a7a02-129">감사 로그</span><span class="sxs-lookup"><span data-stu-id="a7a02-129">Audit logs</span></span>|[<span data-ttu-id="a7a02-130">Microsoft Defender for Office 365와 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="a7a02-131">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a7a02-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="a7a02-132">Azure에서 호스트된 HTTPS 끝점</span><span class="sxs-lookup"><span data-stu-id="a7a02-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="a7a02-133">REST API</span><span class="sxs-lookup"><span data-stu-id="a7a02-133">REST API</span></span>|[<span data-ttu-id="a7a02-134">SIEM 도구로 경고 끌어오기</span><span class="sxs-lookup"><span data-stu-id="a7a02-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="a7a02-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a7a02-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="a7a02-136">로그 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-136">Log integration</span></span>|[<span data-ttu-id="a7a02-137">MICROSOFT Cloud App Security와 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="a7a02-138">[Azure Sentinel을 살펴보아야 합니다.](https://docs.microsoft.com/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="a7a02-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="a7a02-139">Azure Sentinel은 Microsoft 솔루션용 커넥터와 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="a7a02-140">이러한 커넥터는 "첫 실행"할 수 있으며 실시간 통합을 위해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="a7a02-141">Office 365, Azure AD, ID용 Microsoft Defender, Microsoft Cloud App Security 등을 비롯한 Microsoft 365 Defender 솔루션 및 Microsoft 365 서비스와 함께 Azure Sentinel을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="a7a02-142">감사 로깅을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-142">Audit logging must be turned on</span></span>

<span data-ttu-id="a7a02-143">SIEM 서버 통합을 구성하기 전에 감사 로깅을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a02-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="a7a02-144">SharePoint Online, 비즈니스용 OneDrive 및 Azure Active Directory의 경우 보안 및 준수 센터에서 감사 [로깅이 & 있습니다.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="a7a02-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="a7a02-145">Exchange Online의 경우 사서함 감사 [관리를 참조하세요.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="a7a02-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="a7a02-146">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a7a02-146">More resources</span></span>

[<span data-ttu-id="a7a02-147">Azure Defender에서 보안 솔루션 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="a7a02-148">Microsoft Graph Security API 경고를 SIEM과 통합</span><span class="sxs-lookup"><span data-stu-id="a7a02-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
