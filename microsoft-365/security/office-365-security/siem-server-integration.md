---
title: Microsoft 365 서비스 및 응용 프로그램과의 SIEM 서버 통합
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 이 문서를 읽으면 Microsoft 365과의 SIEM server 통합에 대 한 개요를 확인할 수 있습니다.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677511"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="4b390-103">Microsoft 365 서비스 및 응용 프로그램과의 SIEM 서버 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="4b390-104">요약</span><span class="sxs-lookup"><span data-stu-id="4b390-104">Summary</span></span>

<span data-ttu-id="4b390-105">조직에서 SIEM (보안 정보 및 이벤트 관리) 서버를 사용 하는 경우 또는 SIEM 서버를 곧 가져올 계획인 경우 Microsoft 365 또는 Office 365와 통합 되는 방법을 궁금할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="4b390-106">이 문서에서는 Microsoft 365 서비스 및 응용 프로그램과의 SIEM server 통합을 설정 하는 데 사용할 수 있는 리소스 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="4b390-107">아직 SIEM 서버가 없고 옵션을 탐색 하는 경우 **[Microsoft Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview)** 을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b390-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="4b390-108">SIEM 서버가 필요 합니까?</span><span class="sxs-lookup"><span data-stu-id="4b390-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="4b390-109">SIEM 서버가 필요한 지 여부는 조직의 보안 요구 사항 및 데이터 위치와 같은 많은 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="4b390-110">Microsoft 365에는 SIEM 서버와 같은 추가 서버 없이 다양 한 조직의 보안 요구 사항을 충족 하는 다양 한 보안 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="4b390-111">일부 조직에는 SIEM 서버를 사용 해야 하는 특별 한 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="4b390-112">그 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-112">Here are some examples:</span></span>

- <span data-ttu-id="4b390-113">*Fabrikam* 에는 온-프레미스와 일부 콘텐츠 및 응용 프로그램, 클라우드 (하이브리드 클라우드 배포)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="4b390-114">모든 콘텐츠 및 응용 프로그램에서 보안 보고서를 가져오려면 Fabrikam은 SIEM 서버를 구현 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="4b390-115">*Contoso* 는 보안 요구 사항이 특별히 엄격한 금융 서비스 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="4b390-116">필요한 추가 보안 보호 기능을 활용 하기 위해 해당 환경에 SIEM 서버를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="4b390-117">Microsoft 365과의 SIEM 서버 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="4b390-118">SIEM 서버는 다양 한 Microsoft 365 서비스 및 응용 프로그램에서 데이터를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="4b390-119">다음 표에서는 siem 서버 입력과 함께 몇 가지 Microsoft 365 서비스 및 응용 프로그램과 siem 서버 통합에 대해 자세히 알아볼 수 있는 리소스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="4b390-120">Microsoft 365 서비스 또는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4b390-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="4b390-121">SIEM 서버 입력</span><span class="sxs-lookup"><span data-stu-id="4b390-121">SIEM server inputs</span></span> | <span data-ttu-id="4b390-122">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="4b390-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="4b390-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4b390-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="4b390-124">감사 로그</span><span class="sxs-lookup"><span data-stu-id="4b390-124">Audit logs</span></span> | [<span data-ttu-id="4b390-125">SIEM과 Office 365 Advanced Threat Protection의 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="4b390-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4b390-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="4b390-127">Azure에서 호스트 되는 HTTPS 끝점</span><span class="sxs-lookup"><span data-stu-id="4b390-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="4b390-128">REST API</span><span class="sxs-lookup"><span data-stu-id="4b390-128">REST API</span></span>| [<span data-ttu-id="4b390-129">SIEM 도구에 대 한 알림 가져오기</span><span class="sxs-lookup"><span data-stu-id="4b390-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="4b390-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4b390-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="4b390-131">로그 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-131">Log integration</span></span> | [<span data-ttu-id="4b390-132">Microsoft Cloud App Security와의 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="4b390-133">Microsoft 솔루션용으로 제공 되는 다양 한 유형의 [Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview), Microsoft 위협 보호 솔루션을 포함 하 여 실시간 통합 제공, Office 365, azure AD, azure ATP, Microsoft Cloud App 보안 등의 microsoft 365 원본에 포함 된</span><span class="sxs-lookup"><span data-stu-id="4b390-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="4b390-134">감사 로깅을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-134">Audit logging must be turned on</span></span>

<span data-ttu-id="4b390-135">SIEM 서버 통합을 구성 하기 전에 감사 로깅이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b390-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="4b390-136">SharePoint Online, 비즈니스용 OneDrive 및 Azure Active Directory의 경우 [보안 & 준수 센터에서 감사 로깅이 설정 됩니다](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="4b390-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="4b390-137">Exchange Online의 경우 [감사 로깅은 Windows PowerShell을 사용 하 여 설정 됩니다](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="4b390-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="4b390-138">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="4b390-138">Additional resources</span></span>

[<span data-ttu-id="4b390-139">Azure 보안 센터에서 보안 솔루션 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="4b390-140">SIEM을 사용 하 여 Microsoft Graph 보안 API 알림 통합</span><span class="sxs-lookup"><span data-stu-id="4b390-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)