---
title: 끝점용 Microsoft Defender와 다른 Microsoft 솔루션 통합
description: Id용 Microsoft Defender 및 Azure 보안 센터를 포함하여 끝점용 Microsoft Defender가 다른 Microsoft 솔루션과 통합되는 방법을 설명합니다.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: Microsoft 365 defender, 조건부 액세스, Office, 고급 위협 방지, ID에 대한 Microsoft Defender, Office용 Microsoft Defender, Azure 보안 센터, Microsoft 클라우드 앱 보안, azure sentinel
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
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076492"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="593cc-104">끝점용 Microsoft Defender 및 기타 Microsoft 솔루션</span><span class="sxs-lookup"><span data-stu-id="593cc-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="593cc-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="593cc-105">**Applies to:**</span></span>
- [<span data-ttu-id="593cc-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="593cc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="593cc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="593cc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="593cc-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="593cc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="593cc-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="593cc-110">다른 Microsoft 솔루션과 통합</span><span class="sxs-lookup"><span data-stu-id="593cc-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="593cc-111">끝점용 Microsoft Defender는 다양한 Microsoft 솔루션과 직접 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-security-center"></a><span data-ttu-id="593cc-112">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="593cc-112">Azure Security Center</span></span>
<span data-ttu-id="593cc-113">끝점용 Microsoft Defender는 Windows Server의 끝점 감지 및 응답(EDR) 기능을 포함하여 포괄적인 서버 보호 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="593cc-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="593cc-114">Azure Sentinel</span></span>
<span data-ttu-id="593cc-115">끝점용 Microsoft Defender 커넥터를 사용하면 끝점용 Microsoft Defender의 경고를 Azure Sentinel로 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="593cc-116">이를 통해 조직 전체의 보안 이벤트를 보다 포괄적으로 분석하고 효과적이고 즉각적인 응답을 위해 플레이북을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="593cc-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="593cc-117">Azure Information Protection</span></span>
<span data-ttu-id="593cc-118">데이터 검색 및 데이터 보호를 통해 작업 공간에서 생산성을 유지하면서 중요한 데이터를 안전하게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-118">Keep sensitive data secure while enabling productivity in the workplace through data discovery and data protection.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="593cc-119">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="593cc-119">Conditional Access</span></span>
<span data-ttu-id="593cc-120">끝점용 Microsoft Defender의 동적 장치 위험 점수는 조건부 액세스 평가에 통합되어 보안 장치만 리소스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-120">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="593cc-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="593cc-121">Microsoft Cloud App Security</span></span>
<span data-ttu-id="593cc-122">Microsoft Cloud App Security는 끝점용 Microsoft Defender 끝점 신호를 활용하여 모든 끝점 모니터링 디바이스에서 지원되지 않는 클라우드 서비스(섀도 IT)를 사용하는 등 클라우드 응용 프로그램 사용을 직접 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-122">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="593cc-123">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="593cc-123">Microsoft Defender for Identity</span></span>
<span data-ttu-id="593cc-124">의심스러운 활동은 사용자 컨텍스트에서 실행되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-124">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="593cc-125">끝점용 Microsoft Defender와 Azure ATP의 통합을 통해 활동 및 ID 간에 사이버 보안 조사를 유연하게 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-125">The integration between Microsoft Defender for Endpoint and Azure ATP provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="593cc-126">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="593cc-126">Microsoft Defender for Office</span></span>
<span data-ttu-id="593cc-127">[Defender for Office 365는](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) ATP 안전한 링크, ATP 안전한 첨부 파일, 고급 피싱 방지 및 스푸핑 인텔리전스 기능을 통해 전자 메일 메시지 또는 파일의 맬웨어로부터 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-127">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="593cc-128">Office 365 ATP와 Microsoft Defender for Endpoint의 통합을 통해 보안 분석가가 공격 진입점을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-128">The integration between Office 365 ATP and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="593cc-129">위협 인텔리전스 공유를 통해 공격을 포함하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-129">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="593cc-130">지난 30일 이내에 이벤트에 대해 Office 365용 Defender가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-130">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="593cc-131">경고의 경우 Office 365용 Defender 데이터가 첫 번째 활동 시간을 기준으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-131">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="593cc-132">그런 다음 Office 365용 Defender에서 더 이상 데이터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-132">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="593cc-133">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="593cc-133">Skype for Business</span></span>
<span data-ttu-id="593cc-134">비즈니스용 Skype 통합은 분석가가 포털에서 간단한 단추를 통해 잠재적으로 손상된 사용자 또는 장치 소유자와 통신할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-134">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="593cc-135">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="593cc-135">Microsoft 365 Defender</span></span>
<span data-ttu-id="593cc-136">Microsoft 365 Defender를 통해 Endpoint용 Microsoft Defender 및 다양한 Microsoft 보안 솔루션은 엔드포인트, ID, 전자 메일 및 응용 프로그램 전반에 걸쳐 기본적으로 통합되는 통합 사전 및 사후 침해 엔터프라이즈 방어 제품군을 형성하여 정교한 공격을 감지, 방지, 조사 및 자동으로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="593cc-136">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="593cc-137">Microsoft 365 Defender에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="593cc-137">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="593cc-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="593cc-138">Related topics</span></span>
- [<span data-ttu-id="593cc-139">통합 및 기타 고급 기능 구성</span><span class="sxs-lookup"><span data-stu-id="593cc-139">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="593cc-140">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="593cc-140">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="593cc-141">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="593cc-141">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="593cc-142">조건부 액세스를 사용하여 사용자, 데이터 및 장치 보호</span><span class="sxs-lookup"><span data-stu-id="593cc-142">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
