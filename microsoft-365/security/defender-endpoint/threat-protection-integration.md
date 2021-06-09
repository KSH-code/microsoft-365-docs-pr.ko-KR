---
title: 끝점용 Microsoft Defender와 다른 Microsoft 솔루션 통합
description: Id용 Microsoft Defender 및 Azure Defender를 포함하여 끝점용 Microsoft Defender가 다른 Microsoft 솔루션과 통합되는 방법을 알아보십시오.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: Microsoft 365 defender, 조건부 액세스, office, 끝점용 Microsoft Defender, ID용 Microsoft Defender, Office용 Microsoft Defender, Azure Defender, Microsoft 클라우드 앱 보안, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8973a78787345532055161507e2d30f75b3b2cf1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844973"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="8b1bf-104">끝점용 Microsoft Defender 및 기타 Microsoft 솔루션</span><span class="sxs-lookup"><span data-stu-id="8b1bf-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8b1bf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8b1bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="8b1bf-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8b1bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8b1bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8b1bf-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8b1bf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8b1bf-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="8b1bf-110">다른 Microsoft 솔루션과 통합</span><span class="sxs-lookup"><span data-stu-id="8b1bf-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="8b1bf-111">끝점용 Microsoft Defender는 다양한 Microsoft 솔루션과 직접 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="8b1bf-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="8b1bf-112">Azure Defender</span></span>
<span data-ttu-id="8b1bf-113">끝점용 Microsoft Defender는 EDR 서버의 엔드포인트 감지 및 응답(EDR) 기능을 포함하여 포괄적인 서버 보호 솔루션을 Windows 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="8b1bf-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="8b1bf-114">Azure Sentinel</span></span>
<span data-ttu-id="8b1bf-115">끝점용 Microsoft Defender 커넥터를 사용하면 끝점용 Microsoft Defender의 경고를 Azure Sentinel로 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="8b1bf-116">이를 통해 조직 전체의 보안 이벤트를 보다 포괄적으로 분석하고 효과적이고 즉각적인 응답을 위해 플레이북을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="8b1bf-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="8b1bf-117">Azure Information Protection</span></span>
<span data-ttu-id="8b1bf-118">Endpoint DLP 기능이 끝점 디바이스에 저장된 중요한 데이터에 대한 향상된 검색 및 보호 솔루션을 통합하여 솔루션 간의 가시성과 통합을 용이하게 하도록 지원하기 때문에 최근에 Azure Information Protection 통합이 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="8b1bf-119">이 사실은 다음 블로그에서 [발표했습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)</span><span class="sxs-lookup"><span data-stu-id="8b1bf-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="8b1bf-120">고객이 끝점 DLP를 사용하여 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="8b1bf-121">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="8b1bf-121">Conditional Access</span></span>
<span data-ttu-id="8b1bf-122">끝점용 Microsoft Defender의 동적 장치 위험 점수는 조건부 액세스 평가에 통합되어 보안 장치만 리소스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="8b1bf-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8b1bf-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="8b1bf-124">Microsoft Cloud App Security 끝점용 Microsoft Defender 끝점 신호를 활용하여 모든 끝점 모니터링 장치용 Microsoft Defender에서 지원되지 않는 클라우드 서비스(섀도 IT)를 사용하는 등 클라우드 응용 프로그램 사용을 직접 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="8b1bf-125">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8b1bf-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="8b1bf-126">의심스러운 활동은 사용자 컨텍스트에서 실행되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="8b1bf-127">끝점용 Microsoft Defender와 ID용 Microsoft Defender의 통합은 활동 및 ID 간에 사이버 보안 조사를 유연하게 진행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="8b1bf-128">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="8b1bf-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="8b1bf-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) 안전한 링크, 안전한 첨부 파일, 고급 피싱 방지 및 스푸핑 인텔리전스 기능을 통해 전자 메일 메시지 또는 파일의 맬웨어로부터 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="8b1bf-130">Microsoft Defender for Office 365 Microsoft Defender for Endpoint를 통합하면 보안 분석가가 공격 진입점을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="8b1bf-131">위협 인텔리전스 공유를 통해 공격을 포함하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="8b1bf-132">데이터 Office 365 지난 30일 이내에 이벤트에 대해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="8b1bf-133">경고의 경우 첫 번째 Office 365 데이터를 위한 Defender가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="8b1bf-134">그런 다음에는 Defender에서 더 이상 데이터를 사용할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="8b1bf-135">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="8b1bf-135">Skype for Business</span></span>
<span data-ttu-id="8b1bf-136">비즈니스용 Skype 통합을 통해 분석가가 포털에서 간단한 단추를 통해 잠재적으로 손상된 사용자 또는 장치 소유자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="8b1bf-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1bf-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="8b1bf-138">Microsoft 365 Defender를 통해 엔드포인트용 Microsoft Defender 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 구성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1bf-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="8b1bf-139">Defender에 대한 Microsoft 365 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="8b1bf-139">Learn more about Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="8b1bf-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8b1bf-140">Related topics</span></span>
- [<span data-ttu-id="8b1bf-141">통합 및 기타 고급 기능 구성</span><span class="sxs-lookup"><span data-stu-id="8b1bf-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="8b1bf-142">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="8b1bf-142">Microsoft 365 Defender overview</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="8b1bf-143">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="8b1bf-143">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="8b1bf-144">조건부 액세스를 사용하여 사용자, 데이터 및 장치 보호</span><span class="sxs-lookup"><span data-stu-id="8b1bf-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
