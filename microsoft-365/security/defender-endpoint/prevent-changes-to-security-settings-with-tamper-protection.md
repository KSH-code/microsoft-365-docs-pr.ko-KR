---
title: 변조 방지를 사용하여 보안 설정 보호
ms.reviewer: shwjha, hayhov
manager: dansimp
description: 변조 방지를 사용하여 악성 앱이 중요한 보안 설정을 변경하지 못하게 합니다.
keywords: 맬웨어, defender, 바이러스 백신, 변조 방지
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 84864965d7a18902a01307c1dcf373fa7c0534e8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765578"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="7c9af-104">변조 방지를 사용하여 보안 설정 보호</span><span class="sxs-lookup"><span data-stu-id="7c9af-104">Protect security settings with tamper protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7c9af-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7c9af-105">**Applies to:**</span></span>

- <span data-ttu-id="7c9af-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="7c9af-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="7c9af-107">변조 보호는 다음 Windows 버전 중 하나를 실행하는 장치에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="7c9af-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c9af-108">Windows 10</span></span>
- <span data-ttu-id="7c9af-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c9af-109">Windows Server 2019</span></span>
- <span data-ttu-id="7c9af-110">Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="7c9af-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="7c9af-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7c9af-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="7c9af-112">개요</span><span class="sxs-lookup"><span data-stu-id="7c9af-112">Overview</span></span>

<span data-ttu-id="7c9af-113">일부 종류의 사이버 공격 중에 악의적인 공격자는 컴퓨터의 바이러스 백신 보호와 같은 보안 기능을 사용하지 않도록 설정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="7c9af-114">악의적인 공격자들은 데이터에 더 쉽게 액세스하거나, 맬웨어를 설치하거나, 데이터, ID 및 장치를 악용하기 위해 보안 기능을 사용하지 않도록 설정하는 것을 좋아합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="7c9af-115">변조 방지는 이러한 종류의 발생을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="7c9af-116">변조 방지를 통해 악성 앱은 다음 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="7c9af-117">바이러스 및 위협 방지를 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="7c9af-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="7c9af-118">실시간 보호를하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-118">Disabling real-time protection</span></span>
- <span data-ttu-id="7c9af-119">동작 모니터링 끄기</span><span class="sxs-lookup"><span data-stu-id="7c9af-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="7c9af-120">바이러스 백신 비활성화(예: IOfficeAntivirus(IOAV))</span><span class="sxs-lookup"><span data-stu-id="7c9af-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="7c9af-121">클라우드 제공 보호를 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="7c9af-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="7c9af-122">보안 인텔리전스 업데이트 제거</span><span class="sxs-lookup"><span data-stu-id="7c9af-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="7c9af-123">작동 방식</span><span class="sxs-lookup"><span data-stu-id="7c9af-123">How it works</span></span>

<span data-ttu-id="7c9af-124">변조 보호는 기본적으로 Microsoft Defender 바이러스 백신을 잠그고 다음과 같은 앱 및 방법을 통해 보안 설정이 변경되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="7c9af-125">Windows 장치의 레지스트리 편집기에서 설정 구성</span><span class="sxs-lookup"><span data-stu-id="7c9af-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="7c9af-126">PowerShell cmdlet을 통해 설정 변경</span><span class="sxs-lookup"><span data-stu-id="7c9af-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="7c9af-127">그룹 정책을 통해 보안 설정 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="7c9af-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="7c9af-128">변조 방지는 보안 설정을 볼 수 있도록 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="7c9af-129">또한 변조 방지는 타사 바이러스 백신 앱이 Windows 보안 앱에 등록되는 방식에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="7c9af-130">조직에서 Windows 10 Enterprise E5를 사용하는 경우 개별 사용자는 변조 방지 설정을 변경할 수 없습니다. 이러한 경우 변조 보호는 보안 팀에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="7c9af-131">무슨 작업을 하고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="7c9af-131">What do you want to do?</span></span>

| <span data-ttu-id="7c9af-132">이 작업을 수행하기 위해...</span><span class="sxs-lookup"><span data-stu-id="7c9af-132">To perform this task...</span></span> | <span data-ttu-id="7c9af-133">이 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c9af-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="7c9af-134">Microsoft Defender 보안 센터에서 변조 보호 켜기(또는 끄기)</span><span class="sxs-lookup"><span data-stu-id="7c9af-134">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> <p><span data-ttu-id="7c9af-135">테넌트 전체에서 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-135">Manage tamper protection across your tenant</span></span> | [<span data-ttu-id="7c9af-136">Microsoft Defender 보안 센터를 사용하여 조직의 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="7c9af-137">Intune을 사용하여 조직 전체 또는 일부에 대해 변조 보호 설정(또는 해제)을 끄기</span><span class="sxs-lookup"><span data-stu-id="7c9af-137">Turn tamper protection on (or off) for all or part of your organization using Intune</span></span> <p><span data-ttu-id="7c9af-138">조직의 변조 방지 설정 미세 조정</span><span class="sxs-lookup"><span data-stu-id="7c9af-138">Fine-tune tamper protection settings in your organization</span></span> | [<span data-ttu-id="7c9af-139">Intune을 사용하여 조직의 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-139">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="7c9af-140">Configuration Manager를 통해 조직에 대한 변조 보호 설정(또는 해제)을 끄기</span><span class="sxs-lookup"><span data-stu-id="7c9af-140">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="7c9af-141">Configuration Manager 버전 2006에서 테넌트 첨부를 사용하여 조직의 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-141">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="7c9af-142">개별 장치에 대한 변조 보호 켜기(또는 끄기)</span><span class="sxs-lookup"><span data-stu-id="7c9af-142">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="7c9af-143">개별 장치에서 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-143">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="7c9af-144">장치에서의 변조 시도에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="7c9af-144">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="7c9af-145">변조 시도에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="7c9af-145">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="7c9af-146">보안 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="7c9af-146">Review your security recommendations</span></span> | [<span data-ttu-id="7c9af-147">보안 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="7c9af-147">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="7c9af-148">FAQ(질문과 대답) 목록 검토</span><span class="sxs-lookup"><span data-stu-id="7c9af-148">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="7c9af-149">FAQ 찾아보기</span><span class="sxs-lookup"><span data-stu-id="7c9af-149">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="7c9af-150">Microsoft Defender 보안 센터를 사용하여 조직의 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-150">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="7c9af-151">Microsoft Defender 보안 센터( )를 사용하여 테넌트에 대해 변조 보호를 설정하거나 해제할 수 [https://securitycenter.windows.com](https://securitycenter.windows.com) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-151">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="7c9af-152">다음은 유의해야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-152">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="7c9af-153">현재 Microsoft Defender 보안 센터에서 변조 보호를 관리하는 옵션은 기본적으로 새 배포에 대해 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-153">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="7c9af-154">기존 배포의 경우 옵트인(opt in)을 통해 변조 보호를 사용할 수 있습니다. 조만에 이 방법을 기본 방법으로 만들 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-154">For existing deployments, tamper protection is available on an opt-in basis, with plans to make this the default method in the near future.</span></span> <span data-ttu-id="7c9af-155">(옵트인(opt in)하려면 Microsoft Defender 보안 센터에서 설정을 **선택합니다.**  >  **고급 기능**  >  **변조 방지**.)</span><span class="sxs-lookup"><span data-stu-id="7c9af-155">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="7c9af-156">Microsoft Defender 보안 센터를 사용하여 변조 방지를 관리할 때 Intune 또는 테넌트 연결 방법을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-156">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="7c9af-157">Microsoft Defender 보안 센터에서 변조 보호를 관리하는 경우 이 설정은 테넌트 전체에 적용되고 Windows 10, Windows Server 2016 또는 Windows Server 2019를 실행하는 모든 장치에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-157">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="7c9af-158">변조 방지를 미세 조정하려면(예: 일부 장치에 대해 변조 보호를 설정하고 다른 장치에는 사용하지 않는 경우) 테넌트 연결과 함께 [Intune](#manage-tamper-protection-for-your-organization-using-intune) 또는 [Configuration Manager를 사용 합니다.](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)</span><span class="sxs-lookup"><span data-stu-id="7c9af-158">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="7c9af-159">하이브리드 환경이 있는 경우 Intune에 구성된 변조 보호 설정이 Microsoft Defender 보안 센터에 구성된 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-159">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="7c9af-160">Microsoft Defender 보안 센터에서 변조 보호를 관리하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c9af-160">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="7c9af-161">전역 관리자, [](/microsoft-365/security/defender-endpoint/assign-portal-access)보안 관리자 또는 보안 작업과 같은 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-161">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="7c9af-162">Windows 장치에서 다음 Windows 버전 중 하나를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-162">Your Windows devices must be running one of the following versions of Windows:</span></span>
   - <span data-ttu-id="7c9af-163">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c9af-163">Windows 10</span></span>
   - [<span data-ttu-id="7c9af-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c9af-164">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="7c9af-165">Windows Server, 버전 [1803](/windows/release-health/status-windows-10-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="7c9af-165">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="7c9af-166">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7c9af-166">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="7c9af-167">릴리스에 대한 자세한 내용은 [Windows 10 릴리스 정보를 참조하세요.](/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="7c9af-167">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="7c9af-168">디바이스를 [끝점용 Microsoft Defender에 온보딩해야 합니다.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="7c9af-168">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="7c9af-169">장치에서 맬웨어 방지 플랫폼 버전 4.18.2010.7 이상 및 맬웨어 방지 엔진 버전 1.1.17600.5 이상을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-169">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="7c9af-170">([Microsoft Defender 바이러스 백신 업데이트를 관리하고 기준을](manage-updates-baselines-microsoft-defender-antivirus.md)적용합니다.)</span><span class="sxs-lookup"><span data-stu-id="7c9af-170">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="7c9af-171">[클라우드 제공 보호를](enable-cloud-protection-microsoft-defender-antivirus.md) 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-171">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="7c9af-172">Microsoft Defender 보안 센터에서 변조 보호 켜기(또는 끄기)</span><span class="sxs-lookup"><span data-stu-id="7c9af-172">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![Microsoft Defender 보안 센터에서 변조 보호 켜기](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="7c9af-174">Microsoft Defender 보안 센터()로 이동하여 [https://securitycenter.windows.com](https://securitycenter.windows.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-174">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="7c9af-175">설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-175">Choose **Settings**.</span></span>

3. <span data-ttu-id="7c9af-176">일반 **고급**  >  **기능으로 이동한** 다음 변조 방지를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-176">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="7c9af-177">Intune을 사용하여 조직의 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-177">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="7c9af-178">조직의 보안 팀에 포함된 구독에 [Intune이](/intune/fundamentals/what-is-intune)포함되어 있는 경우 [Microsoft Endpoint Manager](https://endpoint.microsoft.com) 관리 센터 포털에서 조직에 대한 변조 보호를 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-178">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) portal.</span></span> <span data-ttu-id="7c9af-179">변조 방지 설정을 미세 조정하려면 Intune을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-179">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="7c9af-180">예를 들어 일부 장치에서 변조 방지를 사용하도록 설정하려는 경우 Intune을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-180">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="7c9af-181">Intune에서 변조 방지를 관리하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c9af-181">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="7c9af-182">전역 관리자, [](/microsoft-365/security/defender-endpoint/assign-portal-access)보안 관리자 또는 보안 작업과 같은 적절한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-182">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="7c9af-183">조직에서 [Intune을 사용하여 장치를 관리합니다.](/intune/fundamentals/what-is-device-management)</span><span class="sxs-lookup"><span data-stu-id="7c9af-183">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="7c9af-184">([Intune 라이선스가](/intune/fundamentals/licenses) 필요합니다. Intune은 Microsoft 365 E5에 포함되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="7c9af-184">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="7c9af-185">Windows 장치에서 Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-185">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="7c9af-186">릴리스에 대한 자세한 내용은 [Windows 10 릴리스 정보를 참조하세요.](/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="7c9af-186">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="7c9af-187">버전 1.287.60.0 이상으로 업데이트된 보안 인텔리전스와 함께 Windows 보안을 사용하고 있어야 합니다. [](https://www.microsoft.com/wdsi/definitions)</span><span class="sxs-lookup"><span data-stu-id="7c9af-187">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="7c9af-188">장치는 맬웨어 방지 플랫폼 버전 4.18.1906.3 이상 및 맬웨어 방지 엔진 버전 1.1.15500.X 이상을 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-188">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="7c9af-189">([Microsoft Defender 바이러스 백신 업데이트를 관리하고 기준을](manage-updates-baselines-microsoft-defender-antivirus.md)적용합니다.)</span><span class="sxs-lookup"><span data-stu-id="7c9af-189">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="7c9af-190">Intune에서 변조 보호 켜기(또는 끄기)</span><span class="sxs-lookup"><span data-stu-id="7c9af-190">Turn tamper protection on (or off) in Intune</span></span>

![Intune을 통해 변조 보호 켜기](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="7c9af-192">[Microsoft Endpoint Manager](https://endpoint.microsoft.com) 관리 센터로 이동하여 직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-192">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="7c9af-193">장치 **구성**  >  **프로필을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-193">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="7c9af-194">다음 설정을 포함하는 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-194">Create a profile that includes the following settings:</span></span>
    - <span data-ttu-id="7c9af-195">**플랫폼: Windows 10 이상**</span><span class="sxs-lookup"><span data-stu-id="7c9af-195">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="7c9af-196">**프로필 유형: 끝점 보호**</span><span class="sxs-lookup"><span data-stu-id="7c9af-196">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="7c9af-197">**범주: Microsoft Defender 보안 센터**</span><span class="sxs-lookup"><span data-stu-id="7c9af-197">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="7c9af-198">**변조 방지: 사용**</span><span class="sxs-lookup"><span data-stu-id="7c9af-198">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="7c9af-199">프로필을 하나 이상의 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-199">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a><span data-ttu-id="7c9af-200">Windows OS 1709, 1803 또는 1809를 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-200">Are you using Windows OS 1709, 1803, or 1809?</span></span>

<span data-ttu-id="7c9af-201">Windows 10 OS [1709, 1803](/windows/release-health/status-windows-10-1709)또는 [1809를](/windows/release-health/status-windows-10-1809-and-windows-server-2019)사용하는 경우  Windows 보안 앱에서 변조 보호가 표시되지 않습니다. [](/windows/release-health/status-windows-10-1803)</span><span class="sxs-lookup"><span data-stu-id="7c9af-201">If you are using Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="7c9af-202">대신 PowerShell을 사용하여 변조 방지를 사용할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-202">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span>

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a><span data-ttu-id="7c9af-203">PowerShell을 사용하여 변조 방지가 켜져 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7c9af-203">Use PowerShell to determine whether tamper protection is turned on</span></span>

1. <span data-ttu-id="7c9af-204">앱 Windows PowerShell 를 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c9af-204">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="7c9af-205">[Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-205">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="7c9af-206">결과 목록에서 를 `IsTamperProtected` 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-206">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="7c9af-207">true 값은  변조 방지를 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-207">(A value of *true* means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="7c9af-208">Configuration Manager 버전 2006을 사용하여 조직의 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-208">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="7c9af-209">[Configuration Manager 버전 2006을](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)사용하는 경우 테넌트 연결 이라는 방법을 사용하여 Windows 10, Windows Server 2016 및 Windows Server 2019에서 변조 보호 설정을 관리할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="7c9af-209">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="7c9af-210">테넌트 연결 기능을 사용하면 Microsoft Endpoint Manager 관리 센터에 On-premises-only Configuration Manager 장치를 동기화한 다음 끝점 보안 구성 정책을 디바이스의 모든 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-210">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

![Endpoint Manager의 Windows 보안 환경](images/win-security- exp-policy-endpt-security.png)

> [!NOTE]
> <span data-ttu-id="7c9af-212">이 절차를 사용하여 Windows 10 및 Windows Server 2019를 실행하는 장치로 변조 보호를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-212">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="7c9af-213">이 절차에 언급된 리소스의 선행 절차 및 기타 정보를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-213">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="7c9af-214">테넌트 연결 설정</span><span class="sxs-lookup"><span data-stu-id="7c9af-214">Set up tenant attach.</span></span> <span data-ttu-id="7c9af-215">이에 대한 도움말은 Microsoft Endpoint Manager 테넌트 연결: 장치 동기화 및 장치 [작업을 참조하세요.](/mem/configmgr/tenant-attach/device-sync-actions)</span><span class="sxs-lookup"><span data-stu-id="7c9af-215">To get help with this, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="7c9af-216">Microsoft [Endpoint Manager 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431) **끝점** 보안 바이러스 백신으로 이동한 다음  >  + 정책 **만들기 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-216">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="7c9af-217">플랫폼 **목록에서** **Windows 10 및 Windows Server(ConfigMgr)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-217">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="7c9af-218">프로필 **목록에서** Windows 보안 환경(미리 **보기)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-218">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="7c9af-219">디바이스 컬렉션에 정책을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-219">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="7c9af-220">이 메서드에 대한 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-220">Need help with this method?</span></span> 

<span data-ttu-id="7c9af-221">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c9af-221">See the following resources:</span></span>

- [<span data-ttu-id="7c9af-222">Microsoft Intune의 Windows 보안 환경 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="7c9af-222">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="7c9af-223">기술 커뮤니티 블로그: Configuration Manager 테넌트 연결 클라이언트에 대한 변조 방지 발표</span><span class="sxs-lookup"><span data-stu-id="7c9af-223">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="7c9af-224">개별 장치에서 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-224">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="7c9af-225">변조 방지 블록은 레지스트리를 통해 Microsoft Defender 바이러스 백신 설정을 수정하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-225">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="7c9af-226">변조 방지가 이러한 설정을 수정하는 타사 보안 제품 또는 엔터프라이즈 설치 스크립트를 방해하지 않도록 보장하려면 **Windows 보안으로** 이동하여 보안 인텔리전스를 버전 1.287.60.0 이상으로 업데이트합니다. </span><span class="sxs-lookup"><span data-stu-id="7c9af-226">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="7c9af-227">(보안 [인텔리전스 업데이트 참조)](https://www.microsoft.com/wdsi/definitions)</span><span class="sxs-lookup"><span data-stu-id="7c9af-227">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="7c9af-228">이 업데이트를 만든 후 변조 보호는 레지스트리 설정을 계속 보호하며 로그는 오류를 반환하지 않고 수정을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-228">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="7c9af-229">가정용 사용자 또는 보안 팀에서 관리하는 설정이 없는 경우 Windows 보안 앱을 사용하여 변조 방지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-229">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="7c9af-230">변조 방지와 같은 보안 설정을 변경하려면 장치에 적절한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-230">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="7c9af-231">Windows 보안 앱에 표시하는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-231">Here's what you see in the Windows Security app:</span></span>

![Windows 10 Home에서 변조 보호 설정](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="7c9af-233">시작 **을** 선택하고 보안 입력을 *시작합니다.*</span><span class="sxs-lookup"><span data-stu-id="7c9af-233">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="7c9af-234">검색 결과에서 **Windows 보안 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-234">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="7c9af-235">바이러스 **& 위협 방지 바이러스**& 설정을  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-235">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="7c9af-236">변조 **보호를 설정** 또는 **해제로** **설정**</span><span class="sxs-lookup"><span data-stu-id="7c9af-236">Set **Tamper Protection** to **On** or **Off**.</span></span>



## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="7c9af-237">변조 시도에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="7c9af-237">View information about tampering attempts</span></span>

<span data-ttu-id="7c9af-238">변조 시도는 일반적으로 더 큰 사이버 공격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-238">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="7c9af-239">악의적인 악의적인 악의적인 는 보안 설정을 변하지 않고 유지하려는 시도입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-239">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="7c9af-240">조직의 보안 팀의 일부인 경우 이러한 시도에 대한 정보를 확인한 다음 적절한 조치를 취하여 위협을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-240">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="7c9af-241">변조 시도가 감지되면 [Microsoft Defender](/microsoft-365/security/defender-endpoint/portal-overview) 보안 센터()에서 경고가 [https://securitycenter.windows.com](https://securitycenter.windows.com) 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-241">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender 보안 센터](images/tamperattemptalert.png)

<span data-ttu-id="7c9af-243">[끝점용](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Microsoft Defender의 엔드포인트 감지 및 응답 및 고급 헌팅 기능을 사용하여 보안 운영 팀은 이러한 시도를 조사하고 해결할 수 있습니다. [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)</span><span class="sxs-lookup"><span data-stu-id="7c9af-243">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="7c9af-244">보안 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="7c9af-244">Review your security recommendations</span></span>

<span data-ttu-id="7c9af-245">변조 방지는 위협 및 [& 관리 기능과 통합됩니다.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="7c9af-245">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="7c9af-246">[보안 권장 사항에는](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 변조 방지가 설정되어 있는지 확인이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-246">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="7c9af-247">예를 들어 다음 이미지와 같이 변조에서 검색할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7c9af-247">For example, you can search on *tamper*, as shown in the following image:</span></span>

![변조 방지 결과 보안 권장 사항](/images/securityrecs-tamperprotect.jpg)

<span data-ttu-id="7c9af-249">결과에서 변조 보호  켜기 를 선택하여 자세한 내용을 알아보고 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-249">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![변조 방지 켜기](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="7c9af-251">위협 및 취약성 & 자세한 내용은 Microsoft Defender 보안 센터의 위협 & 취약성 관리를 [참조합니다.](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="7c9af-251">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7c9af-252">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="7c9af-252">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="7c9af-253">변조 방지를 구성하는 Windows OS 버전은 어느 것인가요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-253">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="7c9af-254">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)이상과 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="7c9af-254">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="7c9af-255">테넌트 연결과 함께 Configuration Manager 버전 2006을 사용하는 경우 변조 방지를 Windows Server 2019로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-255">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="7c9af-256">테넌트 연결: 관리 센터에서 끝점 보안 바이러스 백신 정책 만들기 및 배포(미리 [보기)를 참조하세요.](/mem/configmgr/tenant-attach/deploy-antivirus-policy)</span><span class="sxs-lookup"><span data-stu-id="7c9af-256">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="7c9af-257">변조 방지는 타사 바이러스 백신 등록에 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-257">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="7c9af-258">아니요.</span><span class="sxs-lookup"><span data-stu-id="7c9af-258">No.</span></span> <span data-ttu-id="7c9af-259">타사 바이러스 백신 제품은 Windows 보안 응용 프로그램에 계속 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-259">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="7c9af-260">장치에서 Microsoft Defender 바이러스 백신이 활성화되지 않은 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-260">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="7c9af-261">끝점용 Microsoft Defender에 온보딩된 장치에는 Microsoft Defender 바이러스 백신이 수동 모드로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-261">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="7c9af-262">변조 보호는 서비스 및 해당 기능을 계속 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-262">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="7c9af-263">변조 보호를 켜고 끄는 방법</span><span class="sxs-lookup"><span data-stu-id="7c9af-263">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="7c9af-264">가정용 사용자인 경우 개별 장치에서 변조 보호 [관리를 참조하세요.](#manage-tamper-protection-on-an-individual-device)</span><span class="sxs-lookup"><span data-stu-id="7c9af-264">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="7c9af-265">끝점용 Microsoft [Defender를](/microsoft-365/security/defender-endpoint)사용하는 조직인 경우 다른 끝점 보호 기능을 관리하는 방법과 유사한 Intune에서 변조 보호를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-265">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="7c9af-266">이 문서의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c9af-266">See the following sections of this article:</span></span> 

- [<span data-ttu-id="7c9af-267">Intune을 사용하여 변조 방지 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-267">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="7c9af-268">Configuration Manager, 버전 2006을 사용하여 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-268">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- <span data-ttu-id="7c9af-269">[Microsoft Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 보안 센터를 사용하여 변조 보호 관리(현재 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7c9af-269">[Manage tamper protection using the Microsoft Defender Security Center](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) (currently in preview)</span></span>

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="7c9af-270">Intune에서 변조 보호를 구성하면 그룹 정책을 통해 Microsoft Defender 바이러스 백신을 관리하는 방법에 어떤 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-270">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="7c9af-271">일반 그룹 정책은 변조 방지에 적용되지 않습니다. 변조 방지가 설정될 때 Microsoft Defender 바이러스 백신 설정에 대한 변경 내용은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-271">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="7c9af-272">끝점용 Microsoft Defender의 경우 전체 조직을 대상으로 하는 Intune에서 변조 보호를 구성하고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="7c9af-272">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="7c9af-273">Intune 또는 Microsoft Endpoint Manager에서 변조 보호 구성은 전체 조직 및 특정 장치 및 사용자 그룹을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-273">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="7c9af-274">Microsoft Endpoint Configuration Manager에서 변조 보호를 구성할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-274">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="7c9af-275">테넌트 첨부를 사용하는 경우 Microsoft Endpoint Configuration Manager를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-275">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="7c9af-276">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c9af-276">See the following resources:</span></span>
- [<span data-ttu-id="7c9af-277">Configuration Manager 버전 2006을 사용하여 조직의 변조 보호 관리</span><span class="sxs-lookup"><span data-stu-id="7c9af-277">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="7c9af-278">기술 커뮤니티 블로그: Configuration Manager 테넌트 연결 클라이언트에 대한 변조 방지 발표</span><span class="sxs-lookup"><span data-stu-id="7c9af-278">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="7c9af-279">Windows E3 등록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-279">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="7c9af-280">Intune에서 변조 보호 구성을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-280">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="7c9af-281">현재 Intune에서 변조 보호를 구성하는 것은 [끝점용 Microsoft Defender가 있는 고객만 사용할 수 있습니다.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="7c9af-281">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="7c9af-282">장치에서 변조 방지를 사용하도록 설정한 경우 Intune, Microsoft Endpoint Configuration Manager 및 Windows Management Instrumentation에서 끝점용 Microsoft Defender 설정을 변경하려고 할 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-282">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="7c9af-283">변조 방지로 보호되는 기능은 변경할 수 없습니다. 이러한 변경 요청은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-283">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="7c9af-284">엔터프라이즈 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-284">I’m an enterprise customer.</span></span> <span data-ttu-id="7c9af-285">로컬 관리자가 장치에서 변조 보호를 변경할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-285">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="7c9af-286">아니요.</span><span class="sxs-lookup"><span data-stu-id="7c9af-286">No.</span></span> <span data-ttu-id="7c9af-287">로컬 관리자는 변조 방지 설정을 변경하거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-287">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="7c9af-288">장치가 끝점용 Microsoft Defender를 사용하여 온보딩된 후 오프보드 상태로 넘어가면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-288">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="7c9af-289">장치가 끝점용 Microsoft Defender에서 오프보딩된 경우 변조 방지가 켜져 있습니다. 이는 관리되지 않는 장치의 기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-289">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="7c9af-290">Microsoft Defender 보안 센터에서 변조 보호 상태 변경에 대한 경고가 있나요?</span><span class="sxs-lookup"><span data-stu-id="7c9af-290">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="7c9af-291">예.</span><span class="sxs-lookup"><span data-stu-id="7c9af-291">Yes.</span></span> <span data-ttu-id="7c9af-292">경고는 경고 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7c9af-292">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="7c9af-293">보안 운영 팀은 다음 예와 같은 헌팅 쿼리를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9af-293">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="7c9af-294">[변조 시도에 대한 정보를 을 를 으로 본다.](#view-information-about-tampering-attempts)</span><span class="sxs-lookup"><span data-stu-id="7c9af-294">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c9af-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c9af-295">See also</span></span>

[<span data-ttu-id="7c9af-296">Microsoft Intune용 Endpoint Protection을 통해 Windows PC 보안 지원</span><span class="sxs-lookup"><span data-stu-id="7c9af-296">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="7c9af-297">끝점용 Microsoft Defender 개요 보기</span><span class="sxs-lookup"><span data-stu-id="7c9af-297">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="7c9af-298">함께 사용: Microsoft Defender 바이러스 백신 및 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7c9af-298">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)