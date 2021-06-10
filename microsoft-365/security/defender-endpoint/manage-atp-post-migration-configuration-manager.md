---
title: Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리
description: Configuration Manager를 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, Configuration Manager, 끝점용 Microsoft Defender, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 71ad8f52fd9347abdf0146969bb84a19d8883262
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843067"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="ed0bf-104">Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="ed0bf-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ed0bf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ed0bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed0bf-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ed0bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ed0bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed0bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ed0bf-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ed0bf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed0bf-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ed0bf-110">장치에 대한 조직의 [](/mem)위협 방지 기능(끝점이라고도 하는 Microsoft Endpoint Manager)을 [](/mem/configmgr/core/understand/introduction) 관리하려면 Microsoft Intune(Intune) 및 Microsoft Endpoint Configuration Manager(Configuration Manager)가 포함된 Microsoft Endpoint Manager 를 사용하는 것이 좋습니다. [](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="ed0bf-110">We recommend using We recommend using [Microsoft Endpoint Manager](/mem), which includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="ed0bf-111">자세한 내용은 Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ed0bf-111">Learn more about Endpoint Manager</span></span>](/mem/endpoint-manager-overview)
- [<span data-ttu-id="ed0bf-112">Configuration Manager 및 Intune을 사용하여 Windows 10 디바이스에서 끝점용 Microsoft Defender 공동 관리</span><span class="sxs-lookup"><span data-stu-id="ed0bf-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="ed0bf-113">Configuration Manager를 통해 끝점용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="ed0bf-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="ed0bf-114">작업</span><span class="sxs-lookup"><span data-stu-id="ed0bf-114">Task</span></span>  |<span data-ttu-id="ed0bf-115">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="ed0bf-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="ed0bf-116">**Configuration Manager 콘솔이** 없는 경우 설치</span><span class="sxs-lookup"><span data-stu-id="ed0bf-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="ed0bf-117">*Configuration Manger 콘솔이 아직 없는 경우 이러한 리소스를 사용하여 비트를 다운로드하고 설치합니다.*</span><span class="sxs-lookup"><span data-stu-id="ed0bf-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="ed0bf-118">설치 미디어 사용</span><span class="sxs-lookup"><span data-stu-id="ed0bf-118">Get the installation media</span></span>](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="ed0bf-119">Configuration Manager 콘솔 설치</span><span class="sxs-lookup"><span data-stu-id="ed0bf-119">Install the Configuration Manager console</span></span>](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="ed0bf-120">**Configuration Manager를 사용하여 끝점용** Microsoft Defender에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="ed0bf-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="ed0bf-121">*디바이스(또는 끝점)가 아직 끝점용 Microsoft Defender에 온보딩되지 않은 경우 Configuration Manager를 사용하여 이 작업을 할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="ed0bf-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="ed0bf-122">Configuration Manager를 통해 끝점용 Microsoft Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="ed0bf-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="ed0bf-123">**클라이언트 컴퓨터(끝점)Windows** 맬웨어 방지 정책 및 방화벽 보안 관리</span><span class="sxs-lookup"><span data-stu-id="ed0bf-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="ed0bf-124">*끝점용 Microsoft Defender, 악용 방지, 응용 프로그램 제어, 맬웨어 방지, 방화벽 설정 등을 비롯한 끝점 보호 기능을 구성합니다.*</span><span class="sxs-lookup"><span data-stu-id="ed0bf-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="ed0bf-125">Configuration Manager: Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="ed0bf-125">Configuration Manager: Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="ed0bf-126">**조직의 장치에서 맬웨어** 방지 업데이트를 업데이트하는 방법 선택</span><span class="sxs-lookup"><span data-stu-id="ed0bf-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="ed0bf-127">*Configuration Manager에서 Endpoint Protection 사용하여 조직의 장치에서 맬웨어 방지 정의를 최신으로 유지하는 여러 방법 중 선택할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="ed0bf-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="ed0bf-128">사용자 정의 업데이트 Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="ed0bf-128">Configure definition updates for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="ed0bf-129">Configuration Manager를 사용하여 정의 업데이트 전달</span><span class="sxs-lookup"><span data-stu-id="ed0bf-129">Use Configuration Manager to deliver definition updates</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="ed0bf-130">**직원이 인터넷에서** 악성 콘텐츠를 사용하는 앱을 사용하지 못하도록 네트워크 보호를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ed0bf-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="ed0bf-131">*테스트 환경에서 [네트워크](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 보호를 위해 먼저 감사 모드를 사용하여 롤아웃하기 전에 차단되는 앱을 보는 것이 좋습니다.*</span><span class="sxs-lookup"><span data-stu-id="ed0bf-131">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="ed0bf-132">Configuration Manager를 통해 네트워크 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="ed0bf-132">Turn on network protection with Configuration Manager</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="ed0bf-133">**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="ed0bf-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="ed0bf-134">*제어된 폴더 액세스를 랜섬웨어 방지 보호라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="ed0bf-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="ed0bf-135">끝점 보호: 제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="ed0bf-135">Endpoint protection: Controlled folder access</span></span>](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="ed0bf-136">Microsoft Endpoint Configuration Manage에서 제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="ed0bf-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="ed0bf-137">사용자 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="ed0bf-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="ed0bf-138">아직 수행하지 않은 경우 경고를 보고 위협 방지 **기능을 구성하고 조직의** 전반적인 보안 Microsoft Defender 보안 센터 자세한 정보를 볼 수 있도록 Microsoft Defender 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed0bf-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="ed0bf-139">또한 최종 사용자가 2013에서 볼 수 있는 기능의 여부와 기능을 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="ed0bf-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="ed0bf-140">개요 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="ed0bf-140">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="ed0bf-141">끝점 보호: Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="ed0bf-141">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="ed0bf-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ed0bf-142">Next steps</span></span>

- [<span data-ttu-id="ed0bf-143">개요를 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="ed0bf-143">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="ed0bf-144">보안 Microsoft Defender 보안 센터 대시보드 방문</span><span class="sxs-lookup"><span data-stu-id="ed0bf-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="ed0bf-145">Intune을 사용하여 끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="ed0bf-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
