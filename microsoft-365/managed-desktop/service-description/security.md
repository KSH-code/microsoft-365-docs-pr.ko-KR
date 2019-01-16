---
title: Microsoft Managed Desktop의 보안
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870344"
---
# <a name="security-in-microsoft-managed-desktop"></a><span data-ttu-id="e1083-103">Microsoft Managed Desktop의 보안</span><span class="sxs-lookup"><span data-stu-id="e1083-103">Security in Microsoft Managed Desktop</span></span>

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

<span data-ttu-id="e1083-p101">Microsoft 관리 되는 데스크톱 표준 정책 집합을 적용 하는 및 보안 Microsoft 관리 되는 데스크톱 장치, 회사의 저장 된 데이터 등을 위해 많은 Microsoft 기술을 활용 하 여 합니다. 아래에 나열 된 영역 더 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-p101">Microsoft Managed Desktop applies a standard set of policies and utilizes many Microsoft technologies to help secure Microsoft Managed Desktop devices, stored company data, and more. The areas listed below are detailed further:</span></span>  

- <span data-ttu-id="e1083-106">[데이터 보안](#data-security) -Microsoft 관리 되는 데스크톱 및 안전 하 게 저장 되는 위치에서 수집 된 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e1083-106">[Data security](#data-security) - types of data collected by Microsoft Managed Desktop and where it's securely stored</span></span>
- <span data-ttu-id="e1083-107">[장치 보안](#device-security) -보안 및 보호 Microsoft 관리 되는 데스크톱 장치에서</span><span class="sxs-lookup"><span data-stu-id="e1083-107">[Device security](#device-security) – security and protection on Microsoft Managed Desktop devices</span></span>
- <span data-ttu-id="e1083-108">Azure Active Directory id 서비스를 통해 장치 사용 하 여 [id 및 액세스 관리](#identity-and-access-management) -보안 관리</span><span class="sxs-lookup"><span data-stu-id="e1083-108">[Identity and Access Management](#identity-and-access-management) – managing secure use of devices through Azure Active Directory identity services</span></span>
- <span data-ttu-id="e1083-109">[네트워크 보안](#network-security) – VPN 정보 및 데스크톱을 관리 하는 Microsoft 권장 되는 솔루션 및 설정</span><span class="sxs-lookup"><span data-stu-id="e1083-109">[Network security](#network-security) – VPN information and Microsoft Managed Desktop recommended solution and settings</span></span>
- <span data-ttu-id="e1083-110">[정보 보안](#information-security) – 더 중요 한 정보를 보호 하기 위해 사용할 수 있는 선택적 서비스</span><span class="sxs-lookup"><span data-stu-id="e1083-110">[Information security](#information-security) – optional available services to further protect sensitive information</span></span> 

## <a name="data-security"></a><span data-ttu-id="e1083-111">데이터 보안</span><span class="sxs-lookup"><span data-stu-id="e1083-111">Data security</span></span>

<span data-ttu-id="e1083-112">(활성화 하는 Microsoft 관리 되는 데스크톱 IT 서비스 및 운영) 고객 테 넌 트에서 수집한 데이터는 미국에서 호스팅되는 Microsoft 테 넌 트의 Azure SQL 데이터베이스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-112">Data collected from customer tenants (which enables Microsoft Managed Desktop IT services and operations) is stored in Azure SQL databases in the Microsoft tenant hosted in the United States of America.</span></span>

<span data-ttu-id="e1083-113">자세한 내용은 [Microsoft Azure 보안](https://docs.microsoft.com/azure/security/azure-database-security-overview)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1083-113">For more information, see [Microsoft Azure security](https://docs.microsoft.com/azure/security/azure-database-security-overview).</span></span>

<span data-ttu-id="e1083-114">테 넌 트에서 전송 되는 데이터의 형식을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-114">Listed below are the types of data transmitted from your tenant:</span></span>

- <span data-ttu-id="e1083-115">장치 업데이트, 사용 현황 및 안정성 데이터</span><span class="sxs-lookup"><span data-stu-id="e1083-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="e1083-116">응용 프로그램 배포 및 안정성 데이터</span><span class="sxs-lookup"><span data-stu-id="e1083-116">App deployment and reliability data</span></span>
- <span data-ttu-id="e1083-117">업데이트 및 보안 정책 배포 데이터</span><span class="sxs-lookup"><span data-stu-id="e1083-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="e1083-118">장치에 할당 된 사용자</span><span class="sxs-lookup"><span data-stu-id="e1083-118">Users assigned to devices</span></span>



## <a name="device-security"></a><span data-ttu-id="e1083-119">장치 보안</span><span class="sxs-lookup"><span data-stu-id="e1083-119">Device security</span></span>

<span data-ttu-id="e1083-120">Microsoft 관리 되는 데스크톱을 통해 모든 관리 되는 장치 보호 된 하 고, 보호 및 다음 서비스를 사용 하 여 최대한 일찍 위협 요소를 검색:</span><span class="sxs-lookup"><span data-stu-id="e1083-120">Microsoft Managed Desktop ensures all managed devices are secured and protected, and detects threats as early as possible using the following services:</span></span>

<span data-ttu-id="e1083-121">서비스</span><span class="sxs-lookup"><span data-stu-id="e1083-121">Service</span></span> | <span data-ttu-id="e1083-122">설명</span><span class="sxs-lookup"><span data-stu-id="e1083-122">Description</span></span>
--- | ---
<span data-ttu-id="e1083-123">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="e1083-123">Antivirus</span></span> | <span data-ttu-id="e1083-124">Windows Defender AV 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="e1083-124">Windows Defender AV is installed and configured</span></span><br><span data-ttu-id="e1083-125">Windows Defender AV 정의 최신 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-125">Windows Defender AV definitions are up to date</span></span>
<span data-ttu-id="e1083-126">전체 볼륨 암호화</span><span class="sxs-lookup"><span data-stu-id="e1083-126">Full Volume Encryption</span></span> |    <span data-ttu-id="e1083-127">Windows BitLocker는 Microsoft 관리 되는 데스크톱 장치에 대 한 볼륨 암호화 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-127">Windows BitLocker is the volume encryption solution for Microsoft Managed Desktop devices.</span></span><br><br><span data-ttu-id="e1083-128">조직에는 서비스로 onboarded 되 면 장치가 절전 모드에서 하거나 해제 하는 경우 로컬 데이터에 무단으로 액세스를 방지 하기 위해 함께 기본 제공 신뢰 플랫폼 모듈 (TPM) Windows BitLocker을 사용 하 여 장치 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-128">Once an organization is onboarded into the service, devices will be encrypted using Windows BitLocker with built-in Trust Platform Module (TPM) to prevent unauthorized access to local data when the device is in sleep mode, or off.</span></span> 
<span data-ttu-id="e1083-129">모니터링</span><span class="sxs-lookup"><span data-stu-id="e1083-129">Monitoring</span></span> |    <span data-ttu-id="e1083-p102">Windows Defender 고급 위협 보호 (Windows Defender ATP)는 모든 Microsoft 관리 되는 데스크톱 장치에 대해 보안 위협 모니터링에 사용 됩니다. Windows Defender ATP 기업 고객을 감지, 조사, 및가 회사 네트워크의 고급 위협에 응답할 수 있습니다. 자세한 내용은 참조 [Windows Defender 고급 위협 보호.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="e1083-p102">Windows Defender Advanced Threat Protection (Windows Defender ATP) is used for security threat monitoring across all Microsoft Managed Desktop devices. Windows Defender ATP allows enterprise customers to detect, investigate, and respond to advanced threats in their corporate network. For more information, see [Windows Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span></span> 
<span data-ttu-id="e1083-133">소프트웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="e1083-133">Software updates</span></span> |  <span data-ttu-id="e1083-134">Microsoft 관리 되는 데스크톱 장치는 항상 최신 보안 업데이트를 사용 하 여 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-134">Microsoft Managed Desktop devices are always secured with the latest security updates.</span></span>
<span data-ttu-id="e1083-135">보안 장치 구성</span><span class="sxs-lookup"><span data-stu-id="e1083-135">Secure Device Configuration</span></span> |   <span data-ttu-id="e1083-p103">Microsoft 관리 되는 데스크톱 Microsoft 보안 초기 계획을 구현합니다. 자세한 내용은 참조 [Windows 보안 기준선.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="e1083-p103">Microsoft Managed Desktop implements the Microsoft Security Baseline. For more information, see [Windows security baselines.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span></span>



## <a name="identity-and-access-management"></a><span data-ttu-id="e1083-138">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="e1083-138">Identity and access management</span></span>

<span data-ttu-id="e1083-p104">회사 자산 및 업무에 중요 한 데이터를 보호 하는 id 및 액세스 관리 합니다. 데스크톱을 관리 하는 Microsoft Azure Active Directory (Azure AD)와 보안 사용 관리 id가 되도록 장치를 구성 합니다. 것은 자신의 Azure AD 테 넌 트에 정확한 정보를 유지 하는 고객의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-p104">Identity and access management protects corporate assets and business-critical data. Microsoft Managed Desktop configures devices to ensure secure use with Azure Active Directory (Azure AD) managed identities. It is the customer's responsibility to maintain accurate information in their Azure AD tenant.</span></span> 

<span data-ttu-id="e1083-142">서비스</span><span class="sxs-lookup"><span data-stu-id="e1083-142">Service</span></span> | <span data-ttu-id="e1083-143">설명</span><span class="sxs-lookup"><span data-stu-id="e1083-143">Description</span></span>
--- | ---
<span data-ttu-id="e1083-144">생체 인식 인증</span><span class="sxs-lookup"><span data-stu-id="e1083-144">Biometric Authentication</span></span> |  <span data-ttu-id="e1083-p105">Windows Hello 사용자가 자신의 얼굴 또는 암호를 잊어버리거나 훔쳐 하기 어렵습니다 되도록 설정 하는 PIN을 사용 하 여 로그인 합니다. 자세한 내용은 참조 [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span><span class="sxs-lookup"><span data-stu-id="e1083-p105">Windows Hello allows users to login using their face or a PIN, making passwords harder to forget or steal. For more information, see [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span></span>
<span data-ttu-id="e1083-147">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="e1083-147">Multi-factor authentication</span></span> | <span data-ttu-id="e1083-148">Azure 다단계 인증 더 밀접 하 게는 더 높은 수준의 웰 같이 셀프서비스 암호 재설정으로는 휴대폰을 사용 하 여 인증을 제공 하 여 데스크톱을 관리 하는 Microsoft 서비스의 중요 한 기능에 대 한 액세스를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-148">Azure multi-factor authentication more tightly controls access to sensitive functions of the Microsoft Managed Desktop service by providing an additional level of authentication using a mobile phone, as well as self-service password reset.</span></span> 
<span data-ttu-id="e1083-149">표준 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="e1083-149">Standard user permission</span></span> |  <span data-ttu-id="e1083-p106">시스템을 보호 하 고 더욱 안전 하 게 하려면 사용자 표준 사용자 권한 할당 됩니다. 이 Windows 작업을 자동화할 즉시의 환경에서의 일부분으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-p106">To protect the system and make it more secure, the user will be assigned Standard User Permissions. This is assigned as part of the Windows Autopilot out-of-box experience.</span></span>



## <a name="network-security"></a><span data-ttu-id="e1083-152">네트워크 보안</span><span class="sxs-lookup"><span data-stu-id="e1083-152">Network security</span></span>

<span data-ttu-id="e1083-153">고객에 게는 네트워크 보안에 대 한 책임을 집니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-153">Customers are responsible for network security.</span></span> 

<span data-ttu-id="e1083-154">서비스</span><span class="sxs-lookup"><span data-stu-id="e1083-154">Service</span></span> | <span data-ttu-id="e1083-155">설명</span><span class="sxs-lookup"><span data-stu-id="e1083-155">Description</span></span>
--- | ---
<span data-ttu-id="e1083-156">VPN</span><span class="sxs-lookup"><span data-stu-id="e1083-156">VPN</span></span> | <span data-ttu-id="e1083-157">고객 소유가 VPN 인프라 확인 인트라넷 외부의 제한 된 회사 리소스를 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-157">Customers own their VPN infrastructure, to ensure limited corporate resources can be exposed outside the intranet.</span></span><br><br><span data-ttu-id="e1083-p107">최소 요구 사항: Microsoft 관리 되는 데스크톱 Windows 10 호환 되는 및 지원 되는 VPN 솔루션 필요 합니다. 조직에서 VPN 솔루션을 필요로 하는 경우 Windows 10 지원과 패키지화 되 고 Intune를 통해 배포 될 수 있어야 합니다. 자세한 내용은 소프트웨어 게시자에 게 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-p107">Minimum requirement: Microsoft Managed Desktop requires a Windows 10 compatible and supported VPN solution. If your organization needs a VPN solution, it needs to support Windows 10 and be packaged and deployable through Intune. Contact your software publisher for more information.</span></span><br><br><span data-ttu-id="e1083-161">권장 사항:</span><span class="sxs-lookup"><span data-stu-id="e1083-161">Recommendation:</span></span><br><span data-ttu-id="e1083-p108">Microsoft 푸시 VPN 프로필에 Intune를 통해 쉽게 배포할 수 있는 최신 VPN 솔루션을 권장 합니다. 이 회사 네트워크에 액세스 하는 항상-에, 원활 하 게, 안정적이 고 안전한 방법을 제공 합니다. 자세한 내용은 [[Intune의 VPN 설정]을](https://docs.microsoft.com/intune/vpn-settings-configure)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1083-p108">- Microsoft recommends a modern VPN solution that could be easily deployed through Intune to push VPN profiles. This provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see [[VPN settings in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).</span></span><br><span data-ttu-id="e1083-165">-굵은 VPN 클라이언트 또는 레거시 VPN 클라이언트는 최종 사용자 환경에 영향을 줄 수 있는 것 처럼 Microsoft 관리 되는 데스크톱을 사용 하는 동안 Microsoft에서 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-165">- Thick VPN clients, or legacy VPN clients, are not recommended by Microsoft while using Microsoft Managed Desktop as it can impact the end-user environment.</span></span><br><span data-ttu-id="e1083-166">Microsoft는 성능 문제를 방지 하기 위해 VPN을 거치지 않고 보내는 웹 트래픽을 인터넷에 직접 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-166">- Microsoft recommends that the outgoing web traffic goes directly to Internet without going through the VPN to avoid any performance issues.</span></span><br><span data-ttu-id="e1083-167">-원칙적으로, Microsoft Azure Active Directory 응용 프로그램 프록시를 VPN 하는 대신 사용할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-167">- Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</span></span>


## <a name="information-security"></a><span data-ttu-id="e1083-168">정보 보안 적용</span><span class="sxs-lookup"><span data-stu-id="e1083-168">Information security</span></span>

<span data-ttu-id="e1083-169">고객 회사 중요 한 자산을 보호 하려면 이러한 선택적 서비스를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-169">Customers may configure these optional services to help protect corporate high-value assets.</span></span> 

<span data-ttu-id="e1083-170">서비스</span><span class="sxs-lookup"><span data-stu-id="e1083-170">Service</span></span> | <span data-ttu-id="e1083-171">설명</span><span class="sxs-lookup"><span data-stu-id="e1083-171">Description</span></span>
--- | ---
<span data-ttu-id="e1083-172">데이터 복구</span><span class="sxs-lookup"><span data-stu-id="e1083-172">Data recovery</span></span>  | <span data-ttu-id="e1083-p109">장치에서 주요 폴더에 저장 된 정보는 다음과 같은 비즈니스용 OneDrive에 백업 됩니다. Microsoft 관리 되는 데스크톱 비즈니스용 OneDrive와 동기화 되지 않은 데이터에 대 한 책임을 집니다있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-p109">Information stored in key folders on the device is backed up to OneDrive for Business. Microsoft Managed Desktop is not responsible for data that isn’t synchronized with OneDrive for Business.</span></span> 
<span data-ttu-id="e1083-175">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="e1083-175">Windows Information Protection</span></span> |    <span data-ttu-id="e1083-176">높은 수준의 정보 보안을 필요로 하는 기업에 대 한 것이 좋습니다 [Windows 정보 보호](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) 및 [Azure 정보 보호.](https://www.microsoft.com/cloud-platform/azure-information-protection)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1083-176">For companies that require high levels of information security, we recommend [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection).</span></span> 

