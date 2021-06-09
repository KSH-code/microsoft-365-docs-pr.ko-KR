---
title: Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비
description: 인증서 요구 사항 및 Wi-Fi 연결
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574586"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a><span data-ttu-id="1f3cb-104">Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비</span><span class="sxs-lookup"><span data-stu-id="1f3cb-104">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>  
 
<span data-ttu-id="1f3cb-105">인증서 기반 인증은 인증서 기반 인증을 사용하는 고객에게 일반적인 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-105">Certificate-based authentication is a common requirement for customers using Microsoft Managed Desktop.</span></span> <span data-ttu-id="1f3cb-106">인증서를 사용하여 Wi-Fi 또는 LAN에 액세스하거나 VPN 솔루션에 연결하거나 조직의 내부 리소스에 액세스해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-106">You might require certificates to access Wi-Fi or LAN, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>   
 
<span data-ttu-id="1f3cb-107">Microsoft Managed Desktop 장치는 Azure Active Directory(Azure AD)에 가입되고 Microsoft Intune 관리하기 때문에 Intune과 통합된 SCEP(Simple Certificate Enrollment Protocol) 또는 PKCS(공개 키 암호화 표준) 인증서 인프라를 사용하여 이러한 인증서를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-107">Because Microsoft Managed Desktop devices are joined to Azure Active Directory (Azure AD) and are managed by Microsoft Intune, you must deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with Intune.</span></span>    
 
## <a name="certificate-requirements"></a><span data-ttu-id="1f3cb-108">인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f3cb-108">Certificate requirements</span></span> 
 
<span data-ttu-id="1f3cb-109">SCEP 또는 PKCS 인프라를 통해 인증서를 배포하려면 루트 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="1f3cb-110">조직의 다른 응용 프로그램 및 서비스를 사용하려면 루트 인증서를 조직 장치에 배포해야 Microsoft Managed Desktop 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-110">Other applications and services in your organization might require root certificates to be deployed to your Microsoft Managed Desktop devices.</span></span>    
 
<span data-ttu-id="1f3cb-111">SCEP 또는 PKCS 인증서를 배포하기 Microsoft Managed Desktop 조직에 사용자 또는 장치 인증서가 필요한 각 서비스에 대한 요구 사항을 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-111">Before you deploy SCEP or PKCS certificates to Microsoft Managed Desktop, you should gather requirements for each service that requires a user or device certificate in your organization.</span></span> <span data-ttu-id="1f3cb-112">이 활동을 더 쉽게 만들기 위해 다음 계획 템플릿 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-112">To make this activity easier, you can use one of the following planning templates:</span></span>  
 
- [<span data-ttu-id="1f3cb-113">PKCS 인증서 템플릿</span><span class="sxs-lookup"><span data-stu-id="1f3cb-113">PKCS certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [<span data-ttu-id="1f3cb-114">SCEP 인증서 템플릿</span><span class="sxs-lookup"><span data-stu-id="1f3cb-114">SCEP certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="1f3cb-115">Wi-Fi 연결 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f3cb-115">Wi-Fi connectivity requirements</span></span>

<span data-ttu-id="1f3cb-116">엔터프라이즈 네트워크에 대한 필수 Wi-Fi 장치를 자동으로 제공하려면 Wi-Fi 구성 프로필이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-116">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you might need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="1f3cb-117">이러한 프로필을 Microsoft Managed Desktop 배포하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-117">You can configure Microsoft Managed Desktop to deploy these profiles to your devices.</span></span> <span data-ttu-id="1f3cb-118">네트워크 보안에 장치가 로컬 도메인의 일부가 되어야 하는 경우 Wi-Fi 네트워크 인프라를 평가하여 Microsoft Managed Desktop 장치와 호환되는지(Microsoft Managed Desktop 디바이스는 Azure AD 가입만 해당)해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-118">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with Microsoft Managed Desktop devices (Microsoft Managed Desktop devices are Azure AD-joined only).</span></span> 
 
<span data-ttu-id="1f3cb-119">Wi-Fi 구성을 Microsoft Managed Desktop 배포하기 전에 각 Wi-Fi 네트워크에 대한 조직의 요구 사항을 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-119">Before you deploy a Wi-Fi configuration to Microsoft Managed Desktop devices, you will be required to gather your organization’s requirements for each Wi-Fi network.</span></span> <span data-ttu-id="1f3cb-120">이 활동을 더 쉽게 만들 수 있도록 이 WiFi 프로필 템플릿을 [사용할 수 있습니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-120">To make this activity easier, you can use this [WiFi profile template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).</span></span>
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a><span data-ttu-id="1f3cb-121">유선 연결 요구 사항 및 802.1x 인증</span><span class="sxs-lookup"><span data-stu-id="1f3cb-121">Wired connectivity requirements and 802.1x authentication</span></span> 
 
<span data-ttu-id="1f3cb-122">802.1x 인증을 사용하여 장치에서 LAN(Local Area Network)으로의 액세스를 보호하는 경우 필요한 구성 세부 정보를 Microsoft Managed Desktop 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-122">If you use 802.1x authentication to secure access from devices to your local area network (LAN), you will need to push the required configuration details to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="1f3cb-123">Microsoft Managed Desktop 버전 Windows 10 1809 이상을 실행하는 Microsoft Managed Desktop 장치는 WiredNetwork CSP(구성 서비스 공급자)를 통해 802.1x 구성 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-123">Microsoft Managed Desktop devices running Windows 10, version 1809 or later support deploying an 802.1x configuration through the WiredNetwork configuration service provider (CSP).</span></span> <span data-ttu-id="1f3cb-124">자세한 내용은 [WiredNetwork CSP 설명서를 참조하십시오.](/windows/client-management/mdm/wirednetwork-csp)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-124">For more information, see [WiredNetwork CSP](/windows/client-management/mdm/wirednetwork-csp) documentation.</span></span> 
 
<span data-ttu-id="1f3cb-125">유선 네트워크 구성 프로필을 Microsoft Managed Desktop 유선 회사 네트워크에 대한 조직의 요구 사항을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-125">Before you deploy a wired network configuration profile to Microsoft Managed Desktop devices, gather your organization’s requirements for your wired corporate network.</span></span> <span data-ttu-id="1f3cb-126">이렇게 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-126">To do so, follow these steps:</span></span> 
 
 
1. <span data-ttu-id="1f3cb-127">기존 802.1x 프로필이 구성되어 있으며 LAN 네트워크에 연결된 장치에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-127">Sign on to a device that has your existing 802.1x profile configured and is connected to the LAN network.</span></span>  
2. <span data-ttu-id="1f3cb-128">관리 자격 증명을 사용하여 명령 프롬프트를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-128">Open a command prompt with administrative credentials.</span></span> 
3. <span data-ttu-id="1f3cb-129">netsh 인터페이스 표시 인터페이스를 실행하여 LAN **인터페이스 이름을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3cb-129">Find the LAN interface name by running **netsh interface show interface**.</span></span> 
4. <span data-ttu-id="1f3cb-130">**netsh lan export profile folder=를 실행하여 LAN 프로필 XML을 내보낼 수 있습니다.  Interface="interface_name"**.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-130">Export the LAN profile XML by running **netsh lan export profile folder=.  Interface=”interface_name”**.</span></span> 
5. <span data-ttu-id="1f3cb-131">Microsoft Managed Desktop 장치에서 내보낼 프로필을 테스트해야 하는 경우 **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" 를** 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-131">If you need to test your exported profile on Microsoft Managed Desktop device, run **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**.</span></span> 
 
 
## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="1f3cb-132">인증서 인프라 배포</span><span class="sxs-lookup"><span data-stu-id="1f3cb-132">Deploy certificate infrastructure</span></span>  
 
<span data-ttu-id="1f3cb-133">Intune을 사용하는 기존 SCEP 또는 PKCS 인프라가 이미 있으며 이 방식이 요구 사항을 충족하는 경우 기존 SCEP 또는 PKCS 인프라를 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-133">If you already have an existing SCEP or PKCS infrastructure with Intune and this approach meets your requirements, you can also use it for Microsoft Managed Desktop.</span></span> <span data-ttu-id="1f3cb-134">SCEP 또는 PKCS 인프라가 아직 없는 경우 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-134">If no SCEP or PKCS infrastructure already exists, you'll have to prepare one.</span></span>  
 
<span data-ttu-id="1f3cb-135">자세한 내용은 [Configure a certificate profile for your devices in Microsoft Intune.](/intune/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-135">For more information, see [Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure).</span></span> 
 
 
 
## <a name="deploy-a-lan-profile"></a><span data-ttu-id="1f3cb-136">LAN 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="1f3cb-136">Deploy a LAN profile</span></span> 
 
<span data-ttu-id="1f3cb-137">LAN 프로필을 내보낼 때 다음 단계를 수행하여 Microsoft Managed Desktop 정책을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-137">Once your LAN profile has been exported, you can prepare the policy for Microsoft Managed Desktop by following these steps:</span></span>   
 
1. <span data-ttu-id="1f3cb-138">다음 설정을 사용하여 LAN 프로필에 Microsoft Intune 사용자 지정 프로필을 만들 수 [있습니다(Intune에서](/intune/custom-settings-windows-10)Windows 10 사용자 지정 설정 사용 참조).</span><span class="sxs-lookup"><span data-stu-id="1f3cb-138">Create a custom profile in Microsoft Intune for the LAN profile using the following settings (see [Use custom settings for Windows 10 devices in Intune](/intune/custom-settings-windows-10)).</span></span> <span data-ttu-id="1f3cb-139">사용자 **지정 OMA-URI** 설정 에서 추가를 선택하고 다음 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-139">In **Custom OMA-URI Settings**, select **Add**, and then enter the following values:</span></span> 
    - <span data-ttu-id="1f3cb-140">이름: *최신 Workplace-Windows 10 LAN 프로필*</span><span class="sxs-lookup"><span data-stu-id="1f3cb-140">Name: *Modern Workplace-Windows 10 LAN Profile*</span></span> 
    - <span data-ttu-id="1f3cb-141">설명: 설정에 대한 개요와 기타 중요한 세부 정보를 제공하는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-141">Description: Enter a description that gives an overview of the setting, and any other important details.</span></span> 
    - <span data-ttu-id="1f3cb-142">OMA-URI(대/중문자): *./Device/Vendor/MSFT/WiredNetwork/LanXML 입력*</span><span class="sxs-lookup"><span data-stu-id="1f3cb-142">OMA-URI (case sensitive): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*</span></span>
    - <span data-ttu-id="1f3cb-143">데이터 형식: **문자열(XML 파일)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3cb-143">Data type: select **String (XML file)**.</span></span> 
    - <span data-ttu-id="1f3cb-144">사용자 지정 XML: 업로드 XML 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-144">Custom XML: Upload the exported XML file.</span></span>
2. <span data-ttu-id="1f3cb-145">Microsoft Managed Desktop 관리 포털을 사용하여 Microsoft Managed Desktop IT Microsoft Managed Desktop 제출하여 구성 프로필을 검토하고 "최신 작업 공간 장치 - 테스트"에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-145">Submit a Support request to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="1f3cb-146">Microsoft Managed Desktop IT 운영을 통해 관리 포털의 지원 요청을 통해 요청이 완료된 경우를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-146">Microsoft Managed Desktop IT Operations will let you know when the request is completed via the Support request in the Admin portal.</span></span>
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="1f3cb-147">인증서 및 Wi-Fi/VPN 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="1f3cb-147">Deploy certificates and Wi-Fi/VPN profile</span></span> 
 
 
<span data-ttu-id="1f3cb-148">인증서 및 프로필을 배포하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-148">To deploy certificates and profiles, follow these steps:</span></span>

1. <span data-ttu-id="1f3cb-149">각 루트 및 중간 인증서에 대한 프로필을 만들 수 있습니다(신뢰할 수 있는 인증서 프로필 [만들기 참조).](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-149">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles).</span></span> <span data-ttu-id="1f3cb-150">이러한 각 프로필에는 만료 날짜가 DD/MM/YYYY 형식으로 포함된 설명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-150">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="1f3cb-151">**만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3cb-151">**Certificate profiles without an expiration date will not be deployed.**</span></span>
2. <span data-ttu-id="1f3cb-152">각 SCEP 또는 PKCS 인증서에 대한 프로필 [만들기(SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 인증서 프로필 만들기 또는 [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)인증서 프로필 만들기 참조) 이러한 각 프로필에는 만료 날짜가 DD/MM/YYYY 형식으로 포함된 설명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-152">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or [Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="1f3cb-153">**만료 날짜가 없는 인증서 프로필은 배포되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="1f3cb-153">**Certificate profiles without an expiration date will not be deployed.**</span></span>
3. <span data-ttu-id="1f3cb-154">각 회사 WiFi 네트워크에 대한 프로필을 만들 수 있습니다(Windows 10 [장치용 Wi-Fi 설정](/intune/wi-fi-settings-windows)참조).</span><span class="sxs-lookup"><span data-stu-id="1f3cb-154">Create a profile for each corporate WiFi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span>
4. <span data-ttu-id="1f3cb-155">각 회사 VPN에 대한 프로필을 [생성합니다(Intune을](/intune/vpn-settings-windows-10)사용하여 VPN 연결을 Windows 10 Windows 홀로그램 장치 설정 참조).</span><span class="sxs-lookup"><span data-stu-id="1f3cb-155">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/intune/vpn-settings-windows-10)).</span></span>
5. <span data-ttu-id="1f3cb-156">Microsoft Managed Desktop 관리 포털을 사용하여 "인증서 배포" 또는 "Wi-Microsoft Managed Desktop Fi 프로필 배포"라는 지원 요청을 제출하여 Microsoft Managed Desktop 관리 포털을 사용하여 "최신 작업 공간 장치 - 테스트"에 구성 프로필을 검토하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-156">Submit a Support request titled “Certificate Deployment” or “Wi-Fi Profile Deployment” to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="1f3cb-157">Microsoft Managed Desktop IT 작업을 통해 관리 포털의 지원 요청을 통해 요청이 완료된 경우를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f3cb-157">Microsoft Managed Desktop IT Operations will let you know when the request has been completed via the Support request in the Admin portal.</span></span> 
 
## <a name="steps-to-get-ready"></a><span data-ttu-id="1f3cb-158">준비 단계</span><span class="sxs-lookup"><span data-stu-id="1f3cb-158">Steps to get ready</span></span>

1. <span data-ttu-id="1f3cb-159">에 대한 [선행 Microsoft Managed Desktop.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-159">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="1f3cb-160">준비 [평가 도구를 사용합니다.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-160">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="1f3cb-161">게스트 계정에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1f3cb-161">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="1f3cb-162">Microsoft Managed Desktop의 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="1f3cb-162">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. <span data-ttu-id="1f3cb-163">[인증서 및 네트워크](certs-wifi-lan.md) 프로필을 Microsoft Managed Desktop(이 문서)</span><span class="sxs-lookup"><span data-stu-id="1f3cb-163">[Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md) (This article)</span></span>
6. [<span data-ttu-id="1f3cb-164">Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="1f3cb-164">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="1f3cb-165">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="1f3cb-165">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="1f3cb-166">Microsoft Managed Desktop의 매핑된 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="1f3cb-166">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="1f3cb-167">Microsoft Managed Desktop의 인쇄 리소스 준비</span><span class="sxs-lookup"><span data-stu-id="1f3cb-167">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md) 
