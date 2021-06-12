---
title: 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender 관리
description: 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, PowerShell, 끝점용 Microsoft Defender, edr
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
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ce204c1a90e57a651cf9c97974a8b35d405878cc
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908295"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="4432a-104">그룹 정책 개체를 사용하여 끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="4432a-104">Manage Microsoft Defender for Endpoint with Group Policy Objects</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4432a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4432a-105">**Applies to:**</span></span>
- [<span data-ttu-id="4432a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4432a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4432a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4432a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4432a-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4432a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4432a-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4432a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="4432a-110">디바이스에 [](/mem) 대한 Microsoft Endpoint Manager 보호 기능을 관리하기 위해 이 기능을 사용하는 것이 좋습니다(끝점이라고도 참조).</span><span class="sxs-lookup"><span data-stu-id="4432a-110">We recommend using [Microsoft Endpoint Manager](/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="4432a-111">Endpoint Manager [포함된](/mem/intune/fundamentals/what-is-intune) Microsoft Intune [및](/mem/configmgr/core/understand/introduction)Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="4432a-111">Endpoint Manager includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).</span></span> <span data-ttu-id="4432a-112">**[자세한 내용은 Endpoint Manager.](/mem/endpoint-manager-overview)**</span><span class="sxs-lookup"><span data-stu-id="4432a-112">**[Learn more about Endpoint Manager](/mem/endpoint-manager-overview)**.</span></span> 

<span data-ttu-id="4432a-113">Azure Active Directory 도메인 서비스의 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender의 일부 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4432a-113">You can use Group Policy Objects in Azure Active Directory Domain Services to manage some settings in Microsoft Defender for Endpoint.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="4432a-114">그룹 정책 개체를 사용하여 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="4432a-114">Configure Microsoft Defender for Endpoint with Group Policy Objects</span></span>

<span data-ttu-id="4432a-115">다음 표에는 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender를 구성하기 위해 수행할 수 있는 다양한 작업이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4432a-115">The following table lists various tasks you can perform to configure Microsoft Defender for Endpoint with Group Policy Objects.</span></span>

|<span data-ttu-id="4432a-116">작업</span><span class="sxs-lookup"><span data-stu-id="4432a-116">Task</span></span>  |<span data-ttu-id="4432a-117">자세한 정보를 알아볼 수 있는 리소스</span><span class="sxs-lookup"><span data-stu-id="4432a-117">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="4432a-118">**사용자 및 컴퓨터 개체에 대한 설정 관리**</span><span class="sxs-lookup"><span data-stu-id="4432a-118">**Manage settings for user and computer objects**</span></span> <br/><br/><span data-ttu-id="4432a-119">*기본 제공 그룹 정책 개체를 사용자 지정하거나 조직의 요구 사항에 맞게 사용자 지정 그룹 정책 개체 및 조직 구성 단위를 만들 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="4432a-119">*Customize built-in Group Policy Objects, or create custom Group Policy Objects and organizational units to suit your organizational needs.*</span></span>     |[<span data-ttu-id="4432a-120">도메인 서비스 관리 Azure Active Directory 그룹 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4432a-120">Administer Group Policy in an Azure Active Directory Domain Services managed domain</span></span>](/azure/active-directory-domain-services/manage-group-policy)   |
|<span data-ttu-id="4432a-121">**구성 Microsoft Defender 바이러스 백신**</span><span class="sxs-lookup"><span data-stu-id="4432a-121">**Configure Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="4432a-122">*조직 & 정책 설정, 제외, 수정 및 예약된 검사(끝점이라고도 하는 검사)를 비롯한 바이러스 백신 기능을 구성합니다.*</span><span class="sxs-lookup"><span data-stu-id="4432a-122">*Configure antivirus features & capabilities, including policy settings, exclusions, remediation, and scheduled scans on your organization's devices (also referred to as endpoints).*</span></span>   |[<span data-ttu-id="4432a-123">그룹 정책 설정을 사용하여 그룹 정책 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="4432a-123">Use Group Policy settings to configure and manage Microsoft Defender Antivirus</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[<span data-ttu-id="4432a-124">그룹 정책을 사용하여 클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="4432a-124">Use Group Policy to enable cloud-delivered protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|<span data-ttu-id="4432a-125">**조직의 공격 표면 감소 규칙 관리**</span><span class="sxs-lookup"><span data-stu-id="4432a-125">**Manage your organization's attack surface reduction rules**</span></span> <br/><br/><span data-ttu-id="4432a-126">*폴더에 있는 파일을 제외하거나 사용자 & 알림에 사용자 지정 텍스트를 추가하여 공격 표면 감소 규칙을 사용자 지정합니다.*</span><span class="sxs-lookup"><span data-stu-id="4432a-126">*Customize your attack surface reduction rules by excluding files & folders, or by adding custom text to notification alerts that appear on users' devices.*</span></span> |[<span data-ttu-id="4432a-127">그룹 정책 개체를 사용하여 공격 표면 감소 규칙 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4432a-127">Customize attack surface reduction rules with Group Policy Objects</span></span>](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|<span data-ttu-id="4432a-128">**Exploit Protection 설정 관리**</span><span class="sxs-lookup"><span data-stu-id="4432a-128">**Manage exploit protection settings**</span></span><br/><br/><span data-ttu-id="4432a-129">*Exploit Protection 설정을 사용자 지정하고 구성 파일을 가져온 다음 그룹 정책을 사용하여 해당 구성 파일을 배포할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="4432a-129">*You can customize your exploit protection settings, import a configuration file, and then use Group Policy to deploy that configuration file.*</span></span>  |[<span data-ttu-id="4432a-130">Exploit Protection 설정 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4432a-130">Customize exploit protection settings</span></span>](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[<span data-ttu-id="4432a-131">악용 보호 구성 가져오기, 내보내기 및 배포하기</span><span class="sxs-lookup"><span data-stu-id="4432a-131">Import, export, and deploy exploit protection configurations</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[<span data-ttu-id="4432a-132">그룹 정책을 사용하여 구성 배포</span><span class="sxs-lookup"><span data-stu-id="4432a-132">Use Group Policy to distribute the configuration</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|<span data-ttu-id="4432a-133">**직원이 인터넷에서** 악성 콘텐츠를 사용하는 앱을 사용하지 못하도록 네트워크 보호를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4432a-133">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="4432a-134">*테스트 환경에서 [네트워크](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 보호를 위해 먼저 감사 모드를 사용하여 롤아웃하기 전에 차단되는 앱을 보는 것이 좋습니다.*</span><span class="sxs-lookup"><span data-stu-id="4432a-134">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="4432a-135">그룹 정책을 사용하여 네트워크 보호 켜기</span><span class="sxs-lookup"><span data-stu-id="4432a-135">Turn on network protection using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|<span data-ttu-id="4432a-136">**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="4432a-136">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="4432a-137">*[제어된 폴더 액세스를](/microsoft-365/security/defender-endpoint/controlled-folders) 랜섬웨어 방지 보호라고도 합니다.*</span><span class="sxs-lookup"><span data-stu-id="4432a-137">*[Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span>  |[<span data-ttu-id="4432a-138">그룹 정책을 사용하여 제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="4432a-138">Enable controlled folder access using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|<span data-ttu-id="4432a-139">**인터넷의 Microsoft Defender SmartScreen** 파일로부터 보호하기 위해 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4432a-139">**Configure Microsoft Defender SmartScreen** to protect against malicious sites and files on the internet.</span></span>  |[<span data-ttu-id="4432a-140">그룹 Microsoft Defender SmartScreen 사용하여 그룹 정책 및 MDM(모바일 장치 관리) 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4432a-140">Configure Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|<span data-ttu-id="4432a-141">**암호화 및 BitLocker** 조직에서 실행되는 디바이스에 대한 정보를 보호할 수 Windows</span><span class="sxs-lookup"><span data-stu-id="4432a-141">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="4432a-142">BitLocker 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4432a-142">BitLocker Group Policy settings</span></span>](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|<span data-ttu-id="4432a-143">자격 증명 도난 공격으로부터 보호하도록 **Microsoft Defender Credential Guard** 구성</span><span class="sxs-lookup"><span data-stu-id="4432a-143">**Configure Microsoft Defender Credential Guard** to protect against credential theft attacks</span></span> |[<span data-ttu-id="4432a-144">그룹 Windows Defender Credential Guard 사용하여 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="4432a-144">Enable Windows Defender Credential Guard by using Group Policy</span></span>](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="4432a-145">사용자 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="4432a-145">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="4432a-146">아직 수행하지 않은 경우 Microsoft 365 Defender 포털을 구성하여 경고를 보고, 위협 방지 기능을 구성하고, 조직의 전반적인 보안 상태와 관련한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4432a-146">If you haven't already done so, configure your Microsoft 365 Defender portal to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> <span data-ttu-id="4432a-147">자세한 [내용은 Microsoft Defender 보안 센터.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="4432a-147">See [Microsoft Defender Security Center](microsoft-defender-security-center.md).</span></span> <span data-ttu-id="4432a-148">Defender 포털에서 최종 사용자가 볼 수 있는 기능과 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4432a-148">You can also configure whether and what features end users can see in the Microsoft 365 Defender portal.</span></span>

- [<span data-ttu-id="4432a-149">개요 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="4432a-149">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="4432a-150">끝점 보호: Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="4432a-150">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="4432a-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4432a-151">Next steps</span></span>

- [<span data-ttu-id="4432a-152">개요를 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="4432a-152">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="4432a-153">보안 Microsoft Defender 보안 센터 대시보드 방문</span><span class="sxs-lookup"><span data-stu-id="4432a-153">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="4432a-154">Intune을 사용하여 끝점용 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="4432a-154">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
