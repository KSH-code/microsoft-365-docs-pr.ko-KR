---
title: Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리
description: Configuration Manager를 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, Configuration Manager, windows defender Advanced Threat Protection, atp, edr
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
ms.openlocfilehash: bd6b6bd2721b686ab10922d09a9e94b9ebcce522
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185656"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="1c416-104">Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="1c416-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c416-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1c416-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c416-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1c416-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1c416-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c416-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1c416-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1c416-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1c416-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1c416-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="1c416-110">[Microsoft Intune(Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 및 [Microsoft Endpoint Configuration Manager(Configuration](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) Manager)를 포함하는 [Microsoft Endpoint Manager를](https://docs.microsoft.com/mem)사용하여 디바이스에 대한 조직의 위협 방지 기능(끝점이라고도 칭)을 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c416-110">We recommend using We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), which includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="1c416-111">Endpoint Manager에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="1c416-111">Learn more about Endpoint Manager</span></span>](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [<span data-ttu-id="1c416-112">Configuration Manager 및 Intune을 사용하여 Windows 10 장치에서 끝점용 Microsoft Defender 공동 관리</span><span class="sxs-lookup"><span data-stu-id="1c416-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="1c416-113">Configuration Manager를 통해 끝점용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="1c416-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="1c416-114">작업 </span><span class="sxs-lookup"><span data-stu-id="1c416-114">Task</span></span>  |<span data-ttu-id="1c416-115">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="1c416-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="1c416-116">**Configuration Manager 콘솔이** 없는 경우 설치</span><span class="sxs-lookup"><span data-stu-id="1c416-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="1c416-117">*Configuration Manger 콘솔이 아직 없는 경우 이러한 리소스를 사용하여 비트를 다운로드하고 설치합니다.*</span><span class="sxs-lookup"><span data-stu-id="1c416-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="1c416-118">설치 미디어 사용</span><span class="sxs-lookup"><span data-stu-id="1c416-118">Get the installation media</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="1c416-119">Configuration Manager 콘솔 설치</span><span class="sxs-lookup"><span data-stu-id="1c416-119">Install the Configuration Manager console</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="1c416-120">**Configuration Manager를 사용하여 끝점용** Microsoft Defender에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="1c416-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="1c416-121">*디바이스(또는 끝점)가 아직 끝점용 Microsoft Defender에 온보딩되지 않은 경우 Configuration Manager를 사용하여 이 작업을 할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1c416-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="1c416-122">Configuration Manager를 통해 끝점용 Microsoft Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="1c416-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="1c416-123">**클라이언트 컴퓨터(끝점)에** 대한 맬웨어 방지 정책 및 Windows 방화벽 보안 관리</span><span class="sxs-lookup"><span data-stu-id="1c416-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="1c416-124">*끝점용 Microsoft Defender, 악용 방지, 응용 프로그램 제어, 맬웨어 방지, 방화벽 설정 등을 비롯한 끝점 보호 기능을 구성합니다.*</span><span class="sxs-lookup"><span data-stu-id="1c416-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="1c416-125">Configuration Manager: Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="1c416-125">Configuration Manager: Endpoint Protection</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="1c416-126">**조직의 장치에서 맬웨어** 방지 업데이트를 업데이트하는 방법 선택</span><span class="sxs-lookup"><span data-stu-id="1c416-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="1c416-127">*Configuration Manager의 Endpoint Protection을 사용하면 조직의 장치에서 맬웨어 방지 정의를 최신으로 유지하는 여러 방법 중 선택할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1c416-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="1c416-128">Endpoint Protection에 대한 정의 업데이트 구성</span><span class="sxs-lookup"><span data-stu-id="1c416-128">Configure definition updates for Endpoint Protection</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="1c416-129">Configuration Manager를 사용하여 정의 업데이트 전달</span><span class="sxs-lookup"><span data-stu-id="1c416-129">Use Configuration Manager to deliver definition updates</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="1c416-130">**직원이 인터넷에서** 악성 콘텐츠를 사용하는 앱을 사용하지 못하도록 네트워크 보호를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1c416-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="1c416-131">*테스트 환경에서 [네트워크](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 보호를 위해 먼저 감사 모드를 사용하여 롤아웃하기 전에 차단되는 앱을 보는 것이 좋습니다.*</span><span class="sxs-lookup"><span data-stu-id="1c416-131">*We recommend using [audit mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="1c416-132">Configuration Manager를 통해 네트워크 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="1c416-132">Turn on network protection with Configuration Manager</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="1c416-133">**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="1c416-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="1c416-134">*제어된 폴더 액세스를 랜섬웨어 방지 보호라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="1c416-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="1c416-135">끝점 보호: 제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="1c416-135">Endpoint protection: Controlled folder access</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="1c416-136">Microsoft Endpoint Configuration Manage에서 제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="1c416-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="1c416-137">Microsoft Defender 보안 센터 구성</span><span class="sxs-lookup"><span data-stu-id="1c416-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="1c416-138">아직 수행하지 않은 경우 경고를 보고, 위협 방지 기능을 구성하고, 조직의 전반적인 보안태세에 대한 자세한 정보를 볼 수 있도록 **Microsoft Defender** 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c416-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="1c416-139">Microsoft Defender 보안 센터에서 최종 사용자가 볼 수 있는 기능의 여부와 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c416-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="1c416-140">Microsoft Defender 보안 센터 개요</span><span class="sxs-lookup"><span data-stu-id="1c416-140">Overview of the Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="1c416-141">끝점 보호: Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="1c416-141">Endpoint protection: Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="1c416-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1c416-142">Next steps</span></span>

- [<span data-ttu-id="1c416-143">위협 및 취약성 관리 개요 보기</span><span class="sxs-lookup"><span data-stu-id="1c416-143">Get an overview of threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="1c416-144">Microsoft Defender 보안 센터 보안 작업 대시보드 방문</span><span class="sxs-lookup"><span data-stu-id="1c416-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="1c416-145">Intune을 사용하여 끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="1c416-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
