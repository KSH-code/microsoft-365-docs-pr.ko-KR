---
title: 무단 보호를 사용하여 보안 설정 보호
ms.reviewer: pahuijbr, hayhov, oogunrinde
manager: dansimp
description: 변조 방지를 사용하여 악성 앱이 중요한 보안 설정을 변경하지 못하게 합니다.
keywords: 맬웨어, defender, 바이러스 백신, 변조 방지
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 06/17/2021
ms.openlocfilehash: 7050a1588b71ac106d5364f29c76d379072e9511
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007420"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="1c680-104">무단 보호를 사용하여 보안 설정 보호</span><span class="sxs-lookup"><span data-stu-id="1c680-104">Protect security settings with tamper protection</span></span>

<span data-ttu-id="1c680-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1c680-105">**Applies to:**</span></span>

- [<span data-ttu-id="1c680-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1c680-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1c680-107">변조 보호는 다음 버전 중 하나를 실행하는 장치에서 사용할 수 Windows.</span><span class="sxs-lookup"><span data-stu-id="1c680-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="1c680-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1c680-108">Windows 10</span></span>
- <span data-ttu-id="1c680-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1c680-109">Windows Server 2019</span></span>
- <span data-ttu-id="1c680-110">Windows 서버, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="1c680-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="1c680-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1c680-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="1c680-112">개요</span><span class="sxs-lookup"><span data-stu-id="1c680-112">Overview</span></span>

<span data-ttu-id="1c680-113">일부 종류의 사이버 공격 중에 악의적인 공격자는 컴퓨터의 바이러스 백신 보호와 같은 보안 기능을 사용하지 않도록 설정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="1c680-114">악의적인 공격자들은 데이터에 더 쉽게 액세스하거나, 맬웨어를 설치하거나, 데이터, ID 및 장치를 악용하기 위해 보안 기능을 사용하지 않도록 설정하는 것을 좋아합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="1c680-115">변조 방지는 이러한 종류의 발생을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="1c680-116">변조 방지를 통해 악성 앱은 다음 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="1c680-117">바이러스 및 위협 방지를 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="1c680-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="1c680-118">실시간 보호를하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-118">Disabling real-time protection</span></span>
- <span data-ttu-id="1c680-119">동작 모니터링 끄기</span><span class="sxs-lookup"><span data-stu-id="1c680-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="1c680-120">바이러스 백신 비활성화(예: IOfficeAntivirus(IOAV))</span><span class="sxs-lookup"><span data-stu-id="1c680-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="1c680-121">클라우드 제공 보호를 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="1c680-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="1c680-122">보안 인텔리전스 업데이트 제거</span><span class="sxs-lookup"><span data-stu-id="1c680-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="1c680-123">작동 방법</span><span class="sxs-lookup"><span data-stu-id="1c680-123">How it works</span></span>

<span data-ttu-id="1c680-124">변조 방지는 기본적으로 Microsoft Defender 바이러스 백신 잠그고 다음과 같은 앱 및 방법을 통해 보안 설정이 변경되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="1c680-125">디바이스의 레지스트리 편집기에서 Windows 구성</span><span class="sxs-lookup"><span data-stu-id="1c680-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="1c680-126">PowerShell cmdlet을 통해 설정 변경</span><span class="sxs-lookup"><span data-stu-id="1c680-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="1c680-127">그룹 정책을 통해 보안 설정 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="1c680-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="1c680-128">변조 방지는 보안 설정을 볼 수 있도록 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="1c680-129">또한 변조 방지는 타사 바이러스 백신 앱이 앱에 등록되는 Windows 보안 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="1c680-130">조직에서 E5를 Windows 10 Enterprise K 경우 개별 사용자는 변조 보호 설정을 변경할 수 없습니다. 이러한 경우 변조 보호는 보안 팀에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="1c680-131">무슨 작업을 하고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="1c680-131">What do you want to do?</span></span>

| <span data-ttu-id="1c680-132">이 작업을 수행하기 위해...</span><span class="sxs-lookup"><span data-stu-id="1c680-132">To perform this task...</span></span> | <span data-ttu-id="1c680-133">이 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c680-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="1c680-134">테넌트 전체에서 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-134">Manage tamper protection across your tenant</span></span> <p><span data-ttu-id="1c680-135">이 Microsoft Defender 보안 센터 변조 보호를 켜거나 끄기</span><span class="sxs-lookup"><span data-stu-id="1c680-135">Use the Microsoft Defender Security Center to turn tamper protection on or off</span></span> | [<span data-ttu-id="1c680-136">조직에 대한 변조 방지를 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="1c680-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="1c680-137">조직의 변조 방지 설정 미세 조정</span><span class="sxs-lookup"><span data-stu-id="1c680-137">Fine-tune tamper protection settings in your organization</span></span> <p><span data-ttu-id="1c680-138">Intune(Microsoft Endpoint Manager)을 사용하여 변조 방지를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-138">Use Intune (Microsoft Endpoint Manager) to turn tamper protection on or off.</span></span> <span data-ttu-id="1c680-139">이 방법을 사용하여 일부 또는 모든 사용자에 대해 변조 방지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-139">You can configure tamper protection for some or all users with this method.</span></span> | [<span data-ttu-id="1c680-140">Intune을 사용하여 조직의 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-140">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="1c680-141">Configuration Manager를 통해 조직에 대한 변조 보호 설정(또는 해제)을 끄기</span><span class="sxs-lookup"><span data-stu-id="1c680-141">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="1c680-142">Configuration Manager 버전 2006에서 테넌트 첨부를 사용하여 조직의 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-142">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="1c680-143">개별 장치에 대한 변조 보호 켜기(또는 끄기)</span><span class="sxs-lookup"><span data-stu-id="1c680-143">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="1c680-144">개별 장치에서 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-144">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="1c680-145">장치에서의 변조 시도에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1c680-145">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="1c680-146">변조 시도에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1c680-146">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="1c680-147">보안 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="1c680-147">Review your security recommendations</span></span> | [<span data-ttu-id="1c680-148">보안 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="1c680-148">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="1c680-149">FAQ(질문과 대답) 목록 검토</span><span class="sxs-lookup"><span data-stu-id="1c680-149">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="1c680-150">FAQ 찾아보기</span><span class="sxs-lookup"><span data-stu-id="1c680-150">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

<span data-ttu-id="1c680-151">변조 방지를 사용하도록 설정하는 데 사용하는 방법 또는 관리 도구에 따라 MAPS(클라우드 제공 보호)에 종속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-151">Depending on the method or management tool you use to enable Tamper protection, there might be a dependency on MAPS (cloud-delivered protection).</span></span> 

<span data-ttu-id="1c680-152">다음 표에서는 메서드, 도구 및 종속성에 대해 자세히 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-152">The following table provides details on the methods, tools, and dependencies.</span></span>

| <span data-ttu-id="1c680-153">변조 방지를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="1c680-153">How Tamper protection is enabled</span></span>  | <span data-ttu-id="1c680-154">MAPS에 대한 종속성(클라우드 제공 보호)</span><span class="sxs-lookup"><span data-stu-id="1c680-154">Dependency on MAPS (cloud-delivered protection)</span></span>    |
|:----|:----|
| <span data-ttu-id="1c680-155">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1c680-155">Microsoft Intune</span></span>  | <span data-ttu-id="1c680-156">아니요</span><span class="sxs-lookup"><span data-stu-id="1c680-156">No</span></span> |
| <span data-ttu-id="1c680-157">Microsoft Endpoint Configuration Manager + 테넌트 첨부</span><span class="sxs-lookup"><span data-stu-id="1c680-157">Microsoft Endpoint Configuration Manager + Tenant Attach</span></span>  |     <span data-ttu-id="1c680-158">아니요</span><span class="sxs-lookup"><span data-stu-id="1c680-158">No</span></span>  |
| <span data-ttu-id="1c680-159">Microsoft Defender 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="1c680-159">Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>    |     <span data-ttu-id="1c680-160">예</span><span class="sxs-lookup"><span data-stu-id="1c680-160">Yes</span></span> |
| <span data-ttu-id="1c680-161">Microsoft 365 Defender 포털( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="1c680-161">Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>  |     <span data-ttu-id="1c680-162">예</span><span class="sxs-lookup"><span data-stu-id="1c680-162">Yes</span></span>  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="1c680-163">조직에 대한 변조 방지를 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="1c680-163">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="1c680-164">( ) 를 사용하여 테넌트에 대해 변조 보호를 켜거나 Microsoft Defender 보안 센터 [https://securitycenter.windows.com](https://securitycenter.windows.com) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-164">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="1c680-165">다음은 유의해야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-165">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="1c680-166">현재 새 배포에서는 Microsoft Defender 보안 센터 변조 방지를 관리하는 옵션이 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-166">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="1c680-167">기존 배포의 경우 옵트인(opt in)을 통해 변조 방지를 사용할 수 있습니다. 조만에 기본 방법을 옵트인(opt in)할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-167">For existing deployments, tamper protection is available on an opt-in basis, with plans to make opting in the default method in the near future.</span></span> <span data-ttu-id="1c680-168">(옵트인(opt in)을 Microsoft Defender 보안 센터 옵트인(opt **in)을 설정**  >  **고급 기능**  >  **변조 방지**.)</span><span class="sxs-lookup"><span data-stu-id="1c680-168">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="1c680-169">위조 방지 Microsoft Defender 보안 센터 사용하여 변조 방지를 관리할 때 Intune 또는 테넌트 연결 방법을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-169">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="1c680-170">Microsoft Defender 보안 센터 변조 보호를 관리하면 설정이 테넌트 전체에 적용되어 Windows 10, Windows Server 2016 또는 Windows Server 2019를 실행하는 모든 장치에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-170">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="1c680-171">변조 방지를 미세 조정하려면(예: 일부 장치에 대해 변조 보호를 설정하고 다른 장치에는 사용하지 않는 경우) 테넌트 연결과 함께 [Intune](#manage-tamper-protection-for-your-organization-using-intune) 또는 [Configuration Manager를 사용 합니다.](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)</span><span class="sxs-lookup"><span data-stu-id="1c680-171">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="1c680-172">하이브리드 환경이 있는 경우 Intune에서 구성된 변조 보호 설정이 해당 환경에서 구성된 설정보다 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="1c680-172">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="1c680-173">팜에서 변조 보호를 관리하기 위한 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="1c680-173">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="1c680-174">전역 관리자, [](/microsoft-365/security/defender-endpoint/assign-portal-access)보안 관리자 또는 보안 작업과 같은 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-174">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="1c680-175">사용자 Windows 다음 버전 중 하나를 실행해야 Windows.</span><span class="sxs-lookup"><span data-stu-id="1c680-175">Your Windows devices must be running one of the following versions of Windows:</span></span>

   - <span data-ttu-id="1c680-176">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1c680-176">Windows 10</span></span>
   - [<span data-ttu-id="1c680-177">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1c680-177">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="1c680-178">Windows 서버, 버전 [1803](/windows/release-health/status-windows-10-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="1c680-178">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="1c680-179">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1c680-179">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="1c680-180">릴리스에 대한 자세한 내용은 릴리스 [Windows 10 참조하세요.](/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="1c680-180">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="1c680-181">디바이스를 [끝점용 Microsoft Defender에 온보딩해야 합니다.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="1c680-181">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="1c680-182">장치에서 맬웨어 방지 플랫폼 버전 4.18.2010.7 이상 및 맬웨어 방지 엔진 버전 1.1.17600.5 이상을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-182">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="1c680-183">(Microsoft Defender 바이러스 백신[관리하고 기준을](manage-updates-baselines-microsoft-defender-antivirus.md)적용합니다.)</span><span class="sxs-lookup"><span data-stu-id="1c680-183">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="1c680-184">[클라우드 제공 보호를](enable-cloud-protection-microsoft-defender-antivirus.md) 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-184">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="1c680-185">팜에서 변조 보호를 켜거나 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="1c680-185">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![팜에서 변조 보호 Microsoft Defender 보안 센터](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="1c680-187">Microsoft Defender 보안 센터 [https://securitycenter.windows.com](https://securitycenter.windows.com) ()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-187">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="1c680-188">를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="1c680-188">Choose **Settings**.</span></span>

3. <span data-ttu-id="1c680-189">일반 **고급**  >  **기능으로 이동한** 다음 변조 방지를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-189">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="1c680-190">Intune을 사용하여 조직의 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-190">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="1c680-191">조직의 보안 팀에 포함되는 구독에 [Intune이](/intune/fundamentals/what-is-intune)포함되어 있는 경우 Microsoft Endpoint Manager 관리 센터에서 조직에 대한 변조 보호를 켜거나 끄면 됩니다( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ).</span><span class="sxs-lookup"><span data-stu-id="1c680-191">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).</span></span> <span data-ttu-id="1c680-192">변조 방지 설정을 미세 조정하려면 Intune을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-192">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="1c680-193">예를 들어 일부 장치에서 변조 방지를 사용하도록 설정하려는 경우 Intune을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-193">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="1c680-194">Intune에서 변조 방지를 관리하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c680-194">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="1c680-195">전역 관리자, [](/microsoft-365/security/defender-endpoint/assign-portal-access)보안 관리자 또는 보안 작업과 같은 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-195">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="1c680-196">조직에서 [Intune을 사용하여 장치를 관리합니다.](/intune/fundamentals/what-is-device-management)</span><span class="sxs-lookup"><span data-stu-id="1c680-196">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="1c680-197">([Intune 라이선스가](/intune/fundamentals/licenses) 필요합니다. Intune은 Microsoft 365 E5.)</span><span class="sxs-lookup"><span data-stu-id="1c680-197">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="1c680-198">사용자 Windows OS [1709,](/windows/release-health/status-windows-10-1709)Windows 10 [1809](/windows/release-health/status-windows-10-1803)이상을 실행해야 합니다. [](/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="1c680-198">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="1c680-199">릴리스에 대한 자세한 내용은 릴리스 [Windows 10 참조하세요.](/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="1c680-199">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="1c680-200">보안 인텔리전스가 버전 [](https://www.microsoft.com/wdsi/definitions) 1.287.60.0 이상으로 Windows 보안 기능을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-200">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="1c680-201">장치는 맬웨어 방지 플랫폼 버전 4.18.1906.3 이상 및 맬웨어 방지 엔진 버전 1.1.15500.X 이상을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-201">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="1c680-202">(Microsoft Defender 바이러스 백신[관리하고 기준을](manage-updates-baselines-microsoft-defender-antivirus.md)적용합니다.)</span><span class="sxs-lookup"><span data-stu-id="1c680-202">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="1c680-203">Intune에서 변조 보호 켜기(또는 끄기)</span><span class="sxs-lookup"><span data-stu-id="1c680-203">Turn tamper protection on (or off) in Intune</span></span>

![Intune을 통해 변조 보호 켜기](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="1c680-205">Microsoft Endpoint Manager [관리 센터로 이동하고](https://endpoint.microsoft.com) 직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-205">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="1c680-206">장치 **구성**  >  **프로필을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c680-206">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="1c680-207">다음 설정을 포함하는 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-207">Create a profile that includes the following settings:</span></span>

    - <span data-ttu-id="1c680-208">**플랫폼: Windows 10 이상**</span><span class="sxs-lookup"><span data-stu-id="1c680-208">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="1c680-209">**프로필 유형: 끝점 보호**</span><span class="sxs-lookup"><span data-stu-id="1c680-209">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="1c680-210">**범주: Microsoft Defender 보안 센터**</span><span class="sxs-lookup"><span data-stu-id="1c680-210">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="1c680-211">**변조 방지: 사용**</span><span class="sxs-lookup"><span data-stu-id="1c680-211">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="1c680-212">프로필을 하나 이상의 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-212">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-server-2016-or-windows-version-1709-1803-or-1809"></a><span data-ttu-id="1c680-213">1709, Windows Server 2016, Windows 또는 1809 버전을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-213">Are you using Windows Server 2016, or Windows version 1709, 1803, or 1809?</span></span>

<span data-ttu-id="1c680-214">Windows Server 2016, Windows 10 버전 1709, 1803 또는 [1809를](/windows/release-health/status-windows-10-1809-and-windows-server-2019)사용하는 경우 앱 앱에  변조 보호가 Windows 보안 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-214">If you are using Windows Server 2016, Windows 10 version 1709, 1803, or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="1c680-215">대신 PowerShell을 사용하여 변조 방지를 사용할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-215">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span> 
   
<span data-ttu-id="1c680-216">이 Windows Server 2016 경우 설정 변조 방지를 사용하는 경우 앱 앱이 실시간 보호 상태를 정확하게 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-216">On Windows Server 2016, the Settings app will not accurately reflect the status of real-time protection when tamper protection is enabled.</span></span>
   
#### <a name="use-powershell-to-determine-whether-tamper-protection-andor-real-time-protection-are-turned-on"></a><span data-ttu-id="1c680-217">PowerShell을 사용하여 변조 방지 및/또는 실시간 보호가 켜져 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="1c680-217">Use PowerShell to determine whether tamper protection and/or real-time protection are turned on</span></span>

1. <span data-ttu-id="1c680-218">앱 Windows PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="1c680-218">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="1c680-219">[Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-219">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="1c680-220">결과 목록에서 를 `IsTamperProtected` 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-220">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="1c680-221">true 값은  변조 방지를 사용할 수 있는 것입니다. 결과 목록에서 를 `RealTimeProtectionEnabled` 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-221">(A value of *true* means tamper protection is enabled.) In the list of results, look for `RealTimeProtectionEnabled`.</span></span> <span data-ttu-id="1c680-222">true 값은 변조 방지를 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-222">(A value of true means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="1c680-223">Configuration Manager 버전 2006을 사용하여 조직의 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-223">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="1c680-224">[Configuration Manager 버전 2006을](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)사용하는 경우 테넌트 연결 이라는 방법을 사용하여 Windows 10, Windows Server 2016 및 Windows Server 2019에서 변조 보호 설정을 관리할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1c680-224">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="1c680-225">테넌트 연결 기능을 사용하면 프레미스 전용 Configuration Manager 장치를 Microsoft Endpoint Manager 관리 센터에 동기화한 다음 끝점 보안 구성 정책을 장치용 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-225">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Windows 보안 환경 Endpoint Manager":::

> [!NOTE]
> <span data-ttu-id="1c680-227">이 절차를 사용하여 Server 2019 및 2019에서 실행되는 장치로 변조 Windows 10 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-227">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="1c680-228">이 절차에 언급된 리소스의 선행 절차 및 기타 정보를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-228">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="1c680-229">테넌트 연결 설정</span><span class="sxs-lookup"><span data-stu-id="1c680-229">Set up tenant attach.</span></span> <span data-ttu-id="1c680-230">자세한 내용은 테넌트 연결 Microsoft Endpoint Manager 장치 동기화 및 장치 작업을 [참조하세요.](/mem/configmgr/tenant-attach/device-sync-actions)</span><span class="sxs-lookup"><span data-stu-id="1c680-230">To learn more, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="1c680-231">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security**  >  **Antivirus**, and then choose + **Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="1c680-231">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="1c680-232">플랫폼 **목록에서** Windows 10 및 Windows **서버(ConfigMgr)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c680-232">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="1c680-233">프로필 **목록에서** 환경 **Windows 보안(미리 보기)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c680-233">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="1c680-234">디바이스 컬렉션에 정책을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-234">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="1c680-235">이 메서드에 대한 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="1c680-235">Need help with this method?</span></span> 

<span data-ttu-id="1c680-236">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c680-236">See the following resources:</span></span>

- [<span data-ttu-id="1c680-237">설정 환경 Windows 보안 프로필에 대한 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1c680-237">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="1c680-238">Tech Community 블로그: Configuration Manager 테넌트 연결 클라이언트에 대한 변조 방지 발표</span><span class="sxs-lookup"><span data-stu-id="1c680-238">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="1c680-239">개별 장치에서 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-239">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="1c680-240">변조 방지 블록은 레지스트리를 통해 Microsoft Defender 바이러스 백신 수정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-240">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="1c680-241">변조 방지가 이러한 설정을 수정하는 타사 **보안** 제품 또는 엔터프라이즈 설치 스크립트를 방해하지 않도록 보장하려면  Windows 보안 보안 인텔리전스를 버전 1.287.60.0 이상으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-241">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="1c680-242">(보안 [인텔리전스 업데이트 참조)](https://www.microsoft.com/wdsi/definitions)</span><span class="sxs-lookup"><span data-stu-id="1c680-242">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="1c680-243">이 업데이트를 만든 후 변조 보호는 레지스트리 설정을 계속 보호하며 로그는 오류를 반환하지 않고 수정을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-243">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="1c680-244">가정용 사용자 또는 보안 팀에서 관리하는 설정이 없는 경우 Windows 보안 앱을 사용하여 변조 방지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-244">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="1c680-245">변조 방지와 같은 보안 설정을 변경하려면 장치에 적절한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-245">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="1c680-246">앱 앱에 다음과 같은 Windows 보안 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-246">Here's what you see in the Windows Security app:</span></span>

![팜에서 변조 보호가 Windows 10 Home K](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="1c680-248">시작 **을** 선택하고 보안 입력을 *시작합니다.*</span><span class="sxs-lookup"><span data-stu-id="1c680-248">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="1c680-249">검색 결과에서 를 **Windows 보안.**</span><span class="sxs-lookup"><span data-stu-id="1c680-249">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="1c680-250">바이러스 **& 위협 방지 바이러스**& 설정을  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c680-250">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="1c680-251">변조 **보호를 설정** 또는 **해제로** **설정**</span><span class="sxs-lookup"><span data-stu-id="1c680-251">Set **Tamper Protection** to **On** or **Off**.</span></span>

## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="1c680-252">변조 시도에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1c680-252">View information about tampering attempts</span></span>

<span data-ttu-id="1c680-253">변조 시도는 일반적으로 더 큰 사이버 공격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-253">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="1c680-254">악의적인 악의적인 악의적인 는 보안 설정을 변하지 않고 유지하려는 시도입니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-254">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="1c680-255">조직의 보안 팀의 일부인 경우 이러한 시도에 대한 정보를 확인한 다음 적절한 조치를 취하여 위협을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-255">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="1c680-256">변조 시도가 감지되면 에 경고가 [](/microsoft-365/security/defender-endpoint/portal-overview) [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 보안 센터( ).</span><span class="sxs-lookup"><span data-stu-id="1c680-256">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender 보안 센터](images/tamperattemptalert.png)

<span data-ttu-id="1c680-258">Microsoft [엔드포인트 감지 및 응답](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 및 [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) 고급 헌팅 기능을 사용하여 보안 운영 팀은 이러한 시도를 조사하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-258">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="1c680-259">보안 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="1c680-259">Review your security recommendations</span></span>

<span data-ttu-id="1c680-260">변조 방지는 위협 및 [& 관리 기능과 통합됩니다.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="1c680-260">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="1c680-261">[보안 권장 사항에는](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 변조 방지가 설정되어 있는지 확인이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-261">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="1c680-262">예를 들어 변조에서 *검색할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1c680-262">For example, you can search on *tamper*.</span></span> <span data-ttu-id="1c680-263">결과에서 변조 보호  켜기 를 선택하여 자세한 내용을 알아보고 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-263">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![변조 방지 켜기](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="1c680-265">위협 및 취약성 & 대한 자세한 내용은 에서 위협 & 취약성 관리를 [Microsoft Defender 보안 센터.](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="1c680-265">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1c680-266">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="1c680-266">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="1c680-267">어떤 Windows OS 버전에서 변조 보호를 구성할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-267">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="1c680-268">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)이상과 [끝점용 Microsoft Defender](/microsoft-365/security/defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="1c680-268">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="1c680-269">테넌트 연결과 함께 Configuration Manager 버전 2006을 사용하는 경우 변조 방지를 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-269">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="1c680-270">테넌트 연결: 관리 센터에서 끝점 보안 바이러스 백신 정책 만들기 및 배포(미리 [보기)를 참조하세요.](/mem/configmgr/tenant-attach/deploy-antivirus-policy)</span><span class="sxs-lookup"><span data-stu-id="1c680-270">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="1c680-271">변조 방지는 타사 바이러스 백신 등록에 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-271">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="1c680-272">아니요.</span><span class="sxs-lookup"><span data-stu-id="1c680-272">No.</span></span> <span data-ttu-id="1c680-273">타사 바이러스 백신 제품은 계속 응용 프로그램에 Windows 보안 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-273">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="1c680-274">장치에서 Microsoft Defender 바이러스 백신 활성화되지 않은 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-274">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="1c680-275">끝점용 Microsoft Defender에 온보딩된 디바이스는 수동 Microsoft Defender 바이러스 백신 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-275">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="1c680-276">변조 보호는 서비스 및 해당 기능을 계속 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-276">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="1c680-277">변조 보호를 켜고 끄는 방법</span><span class="sxs-lookup"><span data-stu-id="1c680-277">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="1c680-278">가정용 사용자인 경우 개별 장치에서 변조 보호 [관리를 참조하세요.](#manage-tamper-protection-on-an-individual-device)</span><span class="sxs-lookup"><span data-stu-id="1c680-278">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="1c680-279">끝점용 Microsoft [Defender를](/microsoft-365/security/defender-endpoint)사용하는 조직인 경우 다른 끝점 보호 기능을 관리하는 방법과 유사한 Intune에서 변조 보호를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-279">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="1c680-280">이 문서의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c680-280">See the following sections of this article:</span></span> 

- [<span data-ttu-id="1c680-281">Intune을 사용하여 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-281">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="1c680-282">Configuration Manager, 버전 2006을 사용하여 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-282">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="1c680-283">다음을 사용하여 변조 방지 Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="1c680-283">Manage tamper protection using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="1c680-284">Intune에서 변조 보호를 구성하는 것은 그룹 정책을 통해 Microsoft Defender 바이러스 백신 어떻게 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-284">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="1c680-285">일반 그룹 정책은 변조 방지에 적용되지 않습니다. 변조 방지가 Microsoft Defender 바이러스 백신 설정에 대한 변경 내용은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-285">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="1c680-286">끝점용 Microsoft Defender의 경우 전체 조직을 대상으로 하는 Intune에서 변조 보호를 구성하고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="1c680-286">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="1c680-287">Intune 또는 Microsoft Endpoint Manager 변조 보호 구성은 전체 조직 및 특정 장치 및 사용자 그룹을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-287">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1c680-288">팜에서 변조 보호를 구성할 수 Microsoft Endpoint Configuration Manager?</span><span class="sxs-lookup"><span data-stu-id="1c680-288">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="1c680-289">테넌트 첨부를 사용하는 경우 테넌트 첨부 파일을 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1c680-289">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1c680-290">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c680-290">See the following resources:</span></span>
- [<span data-ttu-id="1c680-291">Configuration Manager 버전 2006을 사용하여 조직의 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="1c680-291">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="1c680-292">Tech Community 블로그: Configuration Manager 테넌트 연결 클라이언트에 대한 변조 방지 발표</span><span class="sxs-lookup"><span data-stu-id="1c680-292">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="1c680-293">I have the Windows E3 enrollment.</span><span class="sxs-lookup"><span data-stu-id="1c680-293">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="1c680-294">Intune에서 변조 보호 구성을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-294">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="1c680-295">현재 Intune에서 변조 보호를 구성하는 것은 [끝점용 Microsoft Defender가 있는 고객만 사용할 수 있습니다.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="1c680-295">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="1c680-296">장치에서 변조 방지를 사용하도록 설정한 경우 Intune, Microsoft Endpoint Configuration Manager 및 Windows Management Instrumentation에서 끝점용 Microsoft Defender 설정을 변경하려고 할 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-296">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="1c680-297">변조 방지로 보호되는 기능은 변경할 수 없습니다. 이러한 변경 요청은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-297">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="1c680-298">엔터프라이즈 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-298">I’m an enterprise customer.</span></span> <span data-ttu-id="1c680-299">로컬 관리자가 장치에서 변조 보호를 변경할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-299">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="1c680-300">아니요.</span><span class="sxs-lookup"><span data-stu-id="1c680-300">No.</span></span> <span data-ttu-id="1c680-301">로컬 관리자는 변조 방지 설정을 변경하거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-301">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="1c680-302">장치가 끝점용 Microsoft Defender를 사용하여 온보딩된 후 오프보드 상태로 넘어가면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="1c680-302">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="1c680-303">장치가 끝점용 Microsoft Defender에서 오프보딩된 경우 변조 방지가 켜져 있습니다. 이는 관리되지 않는 장치의 기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-303">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="1c680-304">변경된 변조 보호 상태에 대한 경고가 Microsoft Defender 보안 센터?</span><span class="sxs-lookup"><span data-stu-id="1c680-304">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="1c680-305">예.</span><span class="sxs-lookup"><span data-stu-id="1c680-305">Yes.</span></span> <span data-ttu-id="1c680-306">경고는 경고 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1c680-306">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="1c680-307">보안 운영 팀은 다음 예와 같은 헌팅 쿼리를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c680-307">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="1c680-308">[변조 시도에 대한 정보를 을 를 으로 본다.](#view-information-about-tampering-attempts)</span><span class="sxs-lookup"><span data-stu-id="1c680-308">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c680-309">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c680-309">See also</span></span>

[<span data-ttu-id="1c680-310">보안 기능을 Windows PC의 보안 Endpoint Protection Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1c680-310">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="1c680-311">끝점용 Microsoft Defender 개요 보기</span><span class="sxs-lookup"><span data-stu-id="1c680-311">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="1c680-312">함께 활용: Microsoft Defender 바이러스 백신 및 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1c680-312">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)
