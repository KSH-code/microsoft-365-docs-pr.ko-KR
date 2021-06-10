---
title: 고가용성 페더타 인증 5단계 고가용성 인증에 대한 페더타 인증 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: '요약: 2016년 커넥트 대한 고가용성 페더전 인증에 대해 Azure AD Microsoft 365 구성하는 Microsoft Azure.'
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929411"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="85157-103">고가용성 페더러타 인증 5단계: 페더러에 대한 페더 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85157-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="85157-104">Azure 인프라 서비스에서 Microsoft 365 대한 고가용성 페더링 인증을 배포하는 이 최종 단계에서는 공용 인증 기관에서 발급한 인증서를 다운로드하여 설치하고 구성을 확인한 다음 디렉터리 동기화 서버에 Azure AD 커넥트 설치 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="85157-105">Azure AD 커넥트 페더화 인증을 위해 Microsoft 365 및 AD FS(Active Directory Federation Services) 및 웹 응용 프로그램 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="85157-106">모든 [단계는 Azure에서](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) 고가용성 Microsoft 365 인증 배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85157-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="85157-107">공용 인증서를 다운로드하여 디렉터리 동기화 서버에 복사</span><span class="sxs-lookup"><span data-stu-id="85157-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="85157-108">다음 속성을 사용하여 공용 인증 기관에서 디지털 인증서를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="85157-109">SSL 연결을 만드는 데 적합한 X.509 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="85157-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="85157-110">SAN(주체 대체 이름) 확장 속성은 페더임 서비스 FQDN(예: fs.contoso.com)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="85157-111">인증서에는 개인 키가 있어야하며 PFX 형식으로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="85157-112">또한 조직 컴퓨터와 장치는 디지털 인증서를 발급하는 공용 인증 기관을 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="85157-113">이 트러스트는 컴퓨터 및 장치의 신뢰할 수 있는 루트 인증 기관 저장소에 공용 인증 기관의 루트 인증서를 설치하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="85157-114">Microsoft Windows 실행하는 컴퓨터에는 일반적으로 일반적으로 사용되는 인증 기관에서 설치되는 이러한 유형의 인증서 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="85157-115">공용 인증 기관의 루트 인증서가 아직 설치되어 있지 않은 경우 이 인증서를 조직의 컴퓨터 및 장치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="85157-116">페더라이트 인증의 인증서 요구 사항에 대한 자세한 내용은 페더전 설치 및 구성에 대한 사전 요구 [사항을 참조하세요.](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)</span><span class="sxs-lookup"><span data-stu-id="85157-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="85157-117">인증서를 받으면 디렉터리 동기화 서버의 C: 드라이브에 있는 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="85157-118">예를 들어 파일 이름을 SSL.pfx로 지정하고 디렉터리 동기화 서버의 C: Certs 폴더에 \\ 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="85157-119">구성 확인</span><span class="sxs-lookup"><span data-stu-id="85157-119">Verify your configuration</span></span>

<span data-ttu-id="85157-120">이제 Azure AD 2013에 대해 Azure AD 커넥트 페더러시트 인증을 구성할 준비가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85157-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="85157-121">확인을 위해 검사 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="85157-122">조직의 공용 도메인이 조직 구독에 Microsoft 365 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="85157-123">조직의 Microsoft 365 계정이 조직의 공용 도메인 이름으로 구성되어 성공적으로 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="85157-124">공용 도메인 이름을 기반으로 페더임 서비스 FQDN을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="85157-125">페더ation Service FQDN에 대한 공용 DNS A 레코드는 웹 응용 프로그램 프록시 서버에 대한 인터넷 연결 Azure 부하 균형 조정 서비스의 공용 IP 주소를 지점으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="85157-126">페더ation Service FQDN에 대한 개인 DNS A 레코드는 AD FS 서버에 대한 내부 Azure 부하 관리 서비스의 개인 IP 주소를 지점으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="85157-127">페더ation service FQDN으로 설정된 SAN과의 SSL 연결에 적합한 공용 인증 기관 발급 디지털 인증서는 디렉터리 동기화 서버에 저장된 PFX 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="85157-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="85157-128">공용 인증 기관의 루트 인증서는 컴퓨터 및 장치의 신뢰할 수 있는 루트 인증 기관 저장소에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="85157-129">Contoso 조직의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="85157-130">**Azure의 고가용성 페더타 인증 인프라에 대한 구성 예**</span><span class="sxs-lookup"><span data-stu-id="85157-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Azure의 페더 Microsoft 365 인프라에 대한 고가용성 구성의 예](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="85157-132">Azure AD 커넥트 실행하여 페더타 인증 구성</span><span class="sxs-lookup"><span data-stu-id="85157-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="85157-133">Azure AD 커넥트 도구는 다음 단계를 사용하여 AD FS 서버, 웹 응용 프로그램 프록시 서버 및 Microsoft 365 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="85157-134">로컬 관리자 권한이 있는 도메인 계정을 사용하여 디렉터리 동기화 서버에 대한 원격 데스크톱 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="85157-135">디렉터리 동기화 서버의 바탕 화면에서 를 열고 Internet Explorer 로 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="85157-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="85157-136">Microsoft Azure Active Directory 커넥트 **페이지에서** **다운로드를** 클릭한 다음 실행을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="85157-137">Azure AD 커넥트 페이지에서 **동의를** **클릭하고** 계속을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="85157-138">**기본 설정** 페이지에서 **사용자 지정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="85157-139">**필수 구성 요소 설치** 페이지에서 **설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="85157-140">**사용자 로그인** 페이지에서 **AD FS로 페더레이션** 을 클릭하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="85157-141">Azure **AD 커넥트** 페이지에서 Microsoft 365 전역 관리자 계정의 이름과 암호를 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="85157-142">디렉터리  커넥트 페이지에서 포리스트에서 AD DS(Active Directory 도메인 서비스) 포리스트가 선택되어 있는지 **확인한** 다음 도메인 관리자 계정의 이름과 암호를 입력하고 디렉터리 추가를 클릭한 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="85157-143">Azure **AD 로그인 구성 페이지에서** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="85157-144">도메인 **및 OU 필터링 페이지에서** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="85157-145">고유하게 사용자 **식별 페이지에서** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="85157-146">사용자 **및 장치 필터링 페이지에서** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="85157-147">선택적 **기능 페이지에서** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="85157-148">AD **FS 팜** 페이지에서 새 **AD FS 팜 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="85157-149">**찾아보기를** 클릭하고 공용 인증 기관에서 SSL 인증서의 위치와 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="85157-150">메시지가 표시될 때 인증서 암호를 입력한 다음 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="85157-151">주체  이름 및 페더ation **서비스** 이름이 페더임 서비스 FQDN으로 설정되어 있는지 확인하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="85157-152">AD **FS 서버** 페이지에서 첫 번째 AD FS 서버 이름(테이블 M - 항목 4 - 가상 컴퓨터 이름 열)을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="85157-153">두 번째 AD FS 서버 이름(테이블 M - 항목 5 - 가상 컴퓨터 이름 열)을 입력하고 **추가를** 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="85157-154">웹 **응용 프로그램 프록시** 서버 페이지에서 첫 번째 웹 응용 프로그램 프록시 서버의 이름(테이블 M - 항목 6 - 가상 컴퓨터 이름 열)을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="85157-155">두 번째 웹 응용 프로그램 프록시 서버의 이름(테이블 M - 항목 7 - 가상 컴퓨터 이름 열)을 입력하고 **추가를** 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="85157-156">도메인 **관리자 자격 증명 페이지에서** 도메인 관리자 계정의 사용자 이름과 암호를 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="85157-157">AD **FS 서비스 계정** 페이지에서 엔터프라이즈 관리자 계정의 사용자 이름과 암호를 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="85157-158">Azure **AD 도메인 페이지의** **도메인에서** 조직의 DNS 도메인 이름을 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85157-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="85157-159">**구성 준비 완료** 페이지에서 **설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="85157-160">**설치 완료** 페이지에서 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="85157-161">인트라넷 및 인터넷 구성이 모두 성공적으로 확인되었음을 나타내는 메시지가 두 개 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="85157-162">인트라넷 메시지에는 AD FS 서버에 대한 Azure 내부 부하 균형 조정의 개인 IP 주소가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="85157-163">인터넷 메시지에는 웹 응용 프로그램 프록시 서버에 대한 Azure 인터넷 연결 부하 균형 조정 프로그램의 공용 IP 주소가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="85157-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="85157-164">**설치 완료** 페이지에서 **끝내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85157-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="85157-165">다음은 서버의 자리 holder 이름을 사용 하는 최종 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="85157-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="85157-166">**5단계: Azure의 고가용성 페더전 인증 인프라의 최종 구성**</span><span class="sxs-lookup"><span data-stu-id="85157-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Azure의 페더 Microsoft 365 인프라에 대한 고가용성 구성](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="85157-168">Azure에서 사용할 수 있는 고가용성 페더 Microsoft 365 인프라가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85157-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85157-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85157-169">See Also</span></span>

[<span data-ttu-id="85157-170">Azure에서 Microsoft 365용 고가용성 페더레이션 인증 배포</span><span class="sxs-lookup"><span data-stu-id="85157-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="85157-171">Microsoft 365/테스트 환경에 대한 페더티드 ID</span><span class="sxs-lookup"><span data-stu-id="85157-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="85157-172">Microsoft 365 솔루션 및 아키텍처 센터</span><span class="sxs-lookup"><span data-stu-id="85157-172">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="85157-173">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85157-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)