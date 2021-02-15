---
title: Microsoft Managed Desktop의 보안 작업
description: 보안 운영 센터에서 제공하는 서비스 및 프로세스
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4464c9c491af11831a3511dab60a472f1584d7f6
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840345"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a><span data-ttu-id="e2701-104">Microsoft Managed Desktop의 보안 작업</span><span class="sxs-lookup"><span data-stu-id="e2701-104">Security operations in Microsoft Managed Desktop</span></span>

<span data-ttu-id="e2701-105">정보 보안 직원과 함께 Microsoft Managed Desktop Security Operations Center(SOC) 파트너가 데스크톱 환경을 안전하게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-105">The Microsoft Managed Desktop Security Operations Center (SOC) partners with your information security staff to keep your desktop environment secure.</span></span> <span data-ttu-id="e2701-106">당사의 팀은 전문 분석을 통해 관리되는 장치의 모든 보안 경고를 수신하고 대응하며, 필요한 경우 보안 인시던트 대응 활동을 주도합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-106">Our team receives and responds to all security alerts on managed devices with expert analysis and, when needed, we drive security incident response activities.</span></span> <span data-ttu-id="e2701-107">SOC 사용에 대한 자세한 내용은 관리 포털에서 운영 설명서를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="e2701-107">For more information about working with the SOC, review operational documentation at your Admin portal.</span></span>

<span data-ttu-id="e2701-108">SOC는 소프트웨어, 네트워크 또는 인간 공격자에 대한 일반적인 공격 방법을 포함하여 현재 및 새로운 위협 환경의 전문 지식이 있는 Microsoft 상시 직원으로부터 24/7/365 범위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-108">The SOC offers 24/7/365 coverage from Microsoft full-time employees with expertise in the current and emerging threat landscape, including common attack methods through software, network, or human adversaries.</span></span>

<span data-ttu-id="e2701-109">SOC는 다음 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-109">The SOC provides these services:</span></span>
- <span data-ttu-id="e2701-110">감지된 이벤트에 대한 신속하고 정확한 대응, 데이터 분석을 통해 장치 또는 환경에 대한 전반적인 위험을 파악하고 평가</span><span class="sxs-lookup"><span data-stu-id="e2701-110">Quick and accurate response to detected events, with analysis of data to identify the impact and assess the overall risk to a device or your environment</span></span>
- <span data-ttu-id="e2701-111">알려진 손상 또는 의심되는 손상으로부터 환경을 보호하기 위한 장치 관리 및 차단 작업으로 확산을 방지하여 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-111">Device management and isolation actions to protect your environment from known or suspected compromises, reducing risk by preventing spread</span></span>
- <span data-ttu-id="e2701-112">보안 인시던트 대응 프로세스를 진행하여 보안 팀과 시기적소하고 정확한 의사소통 보장</span><span class="sxs-lookup"><span data-stu-id="e2701-112">Driving the security incident response process, ensuring timely and accurate communication with your security team</span></span>
- <span data-ttu-id="e2701-113">위협 및 취약성 데이터를 기반으로 하여 위험에 노출되기 전에 위험을 식별하고 해결하기 위한 분석 및 권장 사항</span><span class="sxs-lookup"><span data-stu-id="e2701-113">Analysis and recommendations based on threat and vulnerability data to identify and address risks before they're exploited</span></span>
- <span data-ttu-id="e2701-114">알려진 위협과 잠재적인 위협 모두에 대한 지표 및 엔터티를 식별하기 위해 관리되는 장치에서 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="e2701-114">Advanced hunting across the managed devices to identify indicators and entities for both known and potential threats</span></span>

## <a name="processes"></a><span data-ttu-id="e2701-115">프로세스</span><span class="sxs-lookup"><span data-stu-id="e2701-115">Processes</span></span>

- <span data-ttu-id="e2701-116">Microsoft Managed Desktop Security Operations는 Microsoft의 사이버 방어 운영 센터와 파트너십을 체결한 정규 Microsoft 직원이 [직원으로 고용합니다.](https://www.microsoft.com/msrc/cdoc)</span><span class="sxs-lookup"><span data-stu-id="e2701-116">Microsoft Managed Desktop Security Operations is staffed by full-time Microsoft employees in partnership with Microsoft’s [Cyber Defense Operations Center](https://www.microsoft.com/msrc/cdoc).</span></span> 
- <span data-ttu-id="e2701-117">SOC는 Microsoft Managed Desktop에서 아직 볼 수 없는 것로부터 장치를 보호하기 위해 내부 및 외부의 회사 전반의 신호를 사용하여 장치를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-117">Our SOC uses collective signals from across our company, both internal and external, to protect your devices--even from things we have not yet seen in Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="e2701-118">Microsoft 보안 솔루션은 많은 사이버 보안 보호 표준에 부합합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-118">Microsoft security solutions align to many cybersecurity protection standards.</span></span> <span data-ttu-id="e2701-119">SOC 작업은 NIST 800-61 r2(National Institute of Standards and Technology Computer Security Incident Response Guide)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-119">SOC operations are based on the National Institute of Standards and Technology Computer Security Incident Response Handling Guide (NIST 800-61 r2).</span></span>
- <span data-ttu-id="e2701-120">이 프로세스를 통해 다음과 같은 단계를 통해 환경을 보다 잘 방어할 수 있는 방법에 대한 분석 및 문서화 및 복구 후 인사이트를 위해 적절한 정보 및 증거 수집이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-120">The process allows for proper collection of information and evidence, for analysis and documentation and post-recovery insights into ways to better defend your environment through these phases:</span></span>
    - <span data-ttu-id="e2701-121">준비, 검색 및 분석</span><span class="sxs-lookup"><span data-stu-id="e2701-121">Preparation, detection, and analysis</span></span>
    - <span data-ttu-id="e2701-122">포함</span><span class="sxs-lookup"><span data-stu-id="e2701-122">Containment</span></span>
    - <span data-ttu-id="e2701-123">지우기</span><span class="sxs-lookup"><span data-stu-id="e2701-123">Eradication</span></span>
    - <span data-ttu-id="e2701-124">복구</span><span class="sxs-lookup"><span data-stu-id="e2701-124">Recovery</span></span>
    - <span data-ttu-id="e2701-125">인시던트 후 활동</span><span class="sxs-lookup"><span data-stu-id="e2701-125">Post-incident activity</span></span>
- <span data-ttu-id="e2701-126">Microsoft Managed Desktop 고객은 Microsoft 위협 전문가 서비스에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-126">Microsoft Managed Desktop customers are eligible to enroll in the Microsoft Threat Experts service.</span></span> <span data-ttu-id="e2701-127">SOC는 이 서비스를 통해 경고 문의, 잠재적으로 손상된 장치, 의심스러운 네트워크 연결의 근본 원인 및 지속적인 고급 영구 위협 캠페인과 관련하여 기타 위협 인텔리전스를 포함하여 조직에 영향을 주는 복잡한 위협을 보다 잘 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-127">The SOC liaises with this service to understand better the complex threats affecting your organization, including alert inquiries, potentially compromised devices, root cause of a suspicious network connection, and other threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="e2701-128">자세한 내용은 [Microsoft 위협 전문가를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)</span><span class="sxs-lookup"><span data-stu-id="e2701-128">For more information, see [Microsoft Threat Experts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).</span></span>
- <span data-ttu-id="e2701-129">SOC의 위협 및 취약성 관리 프로세스는 Microsoft의 일부 서비스를 사용하여 위협으로부터 보호하기 위해 조직에 대한 권장 사항을 알리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-129">SOC’s Threat and Vulnerability Management process uses some of Microsoft’s services to help inform recommendations for your organization to protect against threats.</span></span> <span data-ttu-id="e2701-130">SOC는 끝점 보안 센터에 대한 Microsoft Defender 및 Microsoft 내부 및 외부의 관련 취약성 데이터 원본의 데이터를 사용하여 취약성 및 잘못 구성을 검색하고 실행 가능한 보고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2701-130">The SOC consumes data from your Microsoft Defender for Endpoint Security Center and from relevant vulnerability data sources within and outside of Microsoft to discover vulnerabilities and misconfigurations and provide actionable reporting.</span></span>
