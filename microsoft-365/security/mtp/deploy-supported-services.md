---
title: Microsoft 365 Defender에서 지원하는 서비스 배포
description: Microsoft 365 Defender에서 통합할 수 있는 Microsoft 보안 서비스, 라이선스 요구 사항 및 배포 절차에 대해 자세히 알아보는 방법을 설명합니다.
keywords: 배포, 라이선스, 지원되는 서비스, 프로비전, 구성 Microsoft Threat Protection, M365, 라이선스 자격, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, Advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928965"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="1b9a6-104">지원 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="1b9a6-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b9a6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1b9a6-105">**Applies to:**</span></span>
- <span data-ttu-id="1b9a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1b9a6-107">[Microsoft 365 Defender는](microsoft-threat-protection.md) 정교한 공격에 대한 중앙 집중식 검색, 예방 및 조사 기능을 제공하기 위해 다양한 Microsoft 보안 서비스를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-107">[Microsoft 365 Defender](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="1b9a6-108">이 문서에서는 지원되는 서비스, 해당 라이선스 요구 사항, 하나 이상의 서비스 배포와 관련된 이점 및 제한 사항, 그리고 개별적으로 완전히 배포하는 방법에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="1b9a6-109">지원되는 서비스</span><span class="sxs-lookup"><span data-stu-id="1b9a6-109">Supported services</span></span>
<span data-ttu-id="1b9a6-110">Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합을 사용하면 지원되는 다음 서비스에 액세스할 수 있으며 Microsoft 365 보안 센터에서 Microsoft 365 Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="1b9a6-111">라이선스 요구 사항 참조</span><span class="sxs-lookup"><span data-stu-id="1b9a6-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="1b9a6-112">지원되는 서비스</span><span class="sxs-lookup"><span data-stu-id="1b9a6-112">Supported service</span></span> | <span data-ttu-id="1b9a6-113">설명</span><span class="sxs-lookup"><span data-stu-id="1b9a6-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="1b9a6-114">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="1b9a6-115">강력한 동작 센서, 클라우드 분석 및 위협 인텔리전스를 중심으로 구축된 엔드포인트 보호 제품군</span><span class="sxs-lookup"><span data-stu-id="1b9a6-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="1b9a6-116">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="1b9a6-117">전자 메일 및 기타 공동 작업 도구를 포함하여 Office 365의 앱 및 데이터에 대한 고급 보호</span><span class="sxs-lookup"><span data-stu-id="1b9a6-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="1b9a6-118">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="1b9a6-119">상관된 Active Directory 신호를 사용하여 고급 위협, 손상된 ID 및 악의적인 내부자에 대한 방어</span><span class="sxs-lookup"><span data-stu-id="1b9a6-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="1b9a6-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1b9a6-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1b9a6-121">Microsoft 및 타사 클라우드 서비스 전반에 걸쳐 사이버 위협 식별 및 퇴치</span><span class="sxs-lookup"><span data-stu-id="1b9a6-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="1b9a6-122">배포된 서비스 및 기능</span><span class="sxs-lookup"><span data-stu-id="1b9a6-122">Deployed services and functionality</span></span>
<span data-ttu-id="1b9a6-123">Microsoft 365 Defender는 지원되는 서비스를 배포할 때 더 나은 가시성, 상관 관계 및 수정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="1b9a6-124">전체 배포의 이점</span><span class="sxs-lookup"><span data-stu-id="1b9a6-124">Benefits of full deployment</span></span>
<span data-ttu-id="1b9a6-125">Microsoft 365 Defender의 완전한 이점을 얻기 위해 지원되는 모든 서비스를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="1b9a6-126">다음은 전체 배포의 주요 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="1b9a6-127">인시던트는 사용 가능한 모든 센서 및 서비스별 분석 기능의 경고 및 이벤트 신호에 따라 식별 및 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="1b9a6-128">AIR(자동화된 조사 및 수정) 플레이북은 장치, 사서함 및 사용자 계정을 비롯한 다양한 엔터티 유형에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="1b9a6-129">장치, 사서함 및 기타 엔터티의 이벤트 및 엔터티 데이터에 대해 보다 포괄적인 고급 헌팅 스케마를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="1b9a6-130">제한된 배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="1b9a6-130">Limited deployment scenarios</span></span>
<span data-ttu-id="1b9a6-131">배포하는 지원되는 각 서비스는 상호 관련 정보뿐만 아니라 매우 다양한 원시 신호 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="1b9a6-132">제한된 배포로 인해 Microsoft 365 Defender 기능이 꺼지지지만 끝점, 앱, 데이터 및 ID에 대한 포괄적인 가시성을 제공하는 기능이 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="1b9a6-133">동시에 모든 수정 기능은 배포한 서비스에서 관리할 수 있는 엔터티에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="1b9a6-134">아래 표에는 지원되는 각 서비스가 추가 데이터를 제공하는 방법, 데이터와 상호 관련되어 추가 정보를 얻을 수 있는 기회, 더 나은 수정 및 응답 기능이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="1b9a6-135">서비스</span><span class="sxs-lookup"><span data-stu-id="1b9a6-135">Service</span></span> | <span data-ttu-id="1b9a6-136">데이터(상호 관련 & 신호)</span><span class="sxs-lookup"><span data-stu-id="1b9a6-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="1b9a6-137">응답 범위 & 수정</span><span class="sxs-lookup"><span data-stu-id="1b9a6-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="1b9a6-138">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="1b9a6-139">- 끝점 상태 및 원시 이벤트</span><span class="sxs-lookup"><span data-stu-id="1b9a6-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="1b9a6-140">- 바이러스 백신, EDR, 공격 표면 감소를 포함한 끝점 감지 및 경고</span><span class="sxs-lookup"><span data-stu-id="1b9a6-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="1b9a6-141">- 끝점에서 관찰된 파일 및 기타 엔터티에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="1b9a6-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="1b9a6-142">끝점</span><span class="sxs-lookup"><span data-stu-id="1b9a6-142">Endpoints</span></span> |
|<span data-ttu-id="1b9a6-143">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="1b9a6-144">- 메일 및 사서함 상태 및 원시 이벤트</span><span class="sxs-lookup"><span data-stu-id="1b9a6-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="1b9a6-145">- 전자 메일, 첨부 파일 및 링크 검색</span><span class="sxs-lookup"><span data-stu-id="1b9a6-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="1b9a6-146">- 사서함</span><span class="sxs-lookup"><span data-stu-id="1b9a6-146">- Mailboxes</span></span><br /><span data-ttu-id="1b9a6-147">- Microsoft 365 계정</span><span class="sxs-lookup"><span data-stu-id="1b9a6-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="1b9a6-148">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="1b9a6-149">- 인증 이벤트를 포함한 Active Directory 신호</span><span class="sxs-lookup"><span data-stu-id="1b9a6-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="1b9a6-150">- ID 관련 동작 감지</span><span class="sxs-lookup"><span data-stu-id="1b9a6-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="1b9a6-151">ID</span><span class="sxs-lookup"><span data-stu-id="1b9a6-151">Identities</span></span> |
| <span data-ttu-id="1b9a6-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1b9a6-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1b9a6-153">- 사용되지 않는 클라우드 앱 및 서비스 검색(섀도 IT)</span><span class="sxs-lookup"><span data-stu-id="1b9a6-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="1b9a6-154">- 클라우드 앱에 데이터 노출</span><span class="sxs-lookup"><span data-stu-id="1b9a6-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="1b9a6-155">- 클라우드 앱과 관련된 위협 활동</span><span class="sxs-lookup"><span data-stu-id="1b9a6-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="1b9a6-156">클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="1b9a6-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="1b9a6-157">서비스 배포</span><span class="sxs-lookup"><span data-stu-id="1b9a6-157">Deploy the services</span></span>
<span data-ttu-id="1b9a6-158">일반적으로 각 서비스를 배포하려면 테넌트와 일부 초기 구성을 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="1b9a6-159">다음 표를 참조하여 이러한 각 서비스가 배포되는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9a6-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="1b9a6-160">서비스</span><span class="sxs-lookup"><span data-stu-id="1b9a6-160">Service</span></span> | <span data-ttu-id="1b9a6-161">프로비전 지침</span><span class="sxs-lookup"><span data-stu-id="1b9a6-161">Provisioning instructions</span></span> | <span data-ttu-id="1b9a6-162">초기 구성</span><span class="sxs-lookup"><span data-stu-id="1b9a6-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="1b9a6-163">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="1b9a6-164">끝점용 Microsoft Defender 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="1b9a6-164">Microsoft Defender for Endpoint deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="1b9a6-165">*프로비전 지침 참조*</span><span class="sxs-lookup"><span data-stu-id="1b9a6-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="1b9a6-166">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="1b9a6-167">*없음, Office 365로 프로비전*</span><span class="sxs-lookup"><span data-stu-id="1b9a6-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="1b9a6-168">Office 365용 Microsoft Defender 정책 구성</span><span class="sxs-lookup"><span data-stu-id="1b9a6-168">Configure Microsoft Defender for Office 365 policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="1b9a6-169">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9a6-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="1b9a6-170">빠른 시작: ID용 Microsoft Defender 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="1b9a6-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="1b9a6-171">*프로비전 지침 참조*</span><span class="sxs-lookup"><span data-stu-id="1b9a6-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="1b9a6-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1b9a6-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1b9a6-173">*없음*</span><span class="sxs-lookup"><span data-stu-id="1b9a6-173">*None*</span></span> | [<span data-ttu-id="1b9a6-174">빠른 시작: Microsoft Cloud App Security 시작</span><span class="sxs-lookup"><span data-stu-id="1b9a6-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="1b9a6-175">지원되는 서비스를 배포한 후 [Microsoft 365 Defender를 켜야 합니다.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="1b9a6-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b9a6-176">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1b9a6-176">Related topics</span></span>

- [<span data-ttu-id="1b9a6-177">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="1b9a6-177">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1b9a6-178">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="1b9a6-178">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="1b9a6-179">끝점용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="1b9a6-179">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="1b9a6-180">Office 365용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="1b9a6-180">Microsoft Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="1b9a6-181">Microsoft Cloud App Security 개요</span><span class="sxs-lookup"><span data-stu-id="1b9a6-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="1b9a6-182">Id용 Microsoft Defender 개요</span><span class="sxs-lookup"><span data-stu-id="1b9a6-182">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
