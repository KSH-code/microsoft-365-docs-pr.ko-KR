---
title: Office 365 배포의 다단계 인증 계획
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365의 다단계 인증 및 설정 하기 위해 수행 해야 하는 단계에 대해 알아봅니다.
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503998"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="4d5e5-103">Office 365 배포의 다단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="4d5e5-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="4d5e5-104">다단계 인증(MFA)은 두 가지 이상의 확인 방법을 사용해야 하고 사용자 로그인 및 트랜잭션에 두 번째 보안 레이어를 추가하는 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="4d5e5-105">이는 다음과 같이 사용자 계정 암호를 초과 하는 정보와 함께 추가 확인 단계를 요구 하는 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="4d5e5-106">임의로 생성된 암호</span><span class="sxs-lookup"><span data-stu-id="4d5e5-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="4d5e5-107">전화 통화</span><span class="sxs-lookup"><span data-stu-id="4d5e5-107">A phone call</span></span>
    
- <span data-ttu-id="4d5e5-108">스마트 카드(가상 또는 실제)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="4d5e5-109">생체 인식 장치</span><span class="sxs-lookup"><span data-stu-id="4d5e5-109">A biometric device</span></span> 
    
## <a name="mfa-in-office-365"></a><span data-ttu-id="4d5e5-110">Office 365의 MFA</span><span class="sxs-lookup"><span data-stu-id="4d5e5-110">MFA in Office 365</span></span>

<span data-ttu-id="4d5e5-111">Office 365에서는 MFA를 추가 로그인 보안으로 사용 하며, Microsoft 365 관리 센터에서 개별 사용자 계정 마다이를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-111">Office 365 uses MFA for extra sign-in security and can be managed for each individual user account from the Microsoft 365 admin center.</span></span> <span data-ttu-id="4d5e5-112">Office 365에서는 구독의 일부로 Azure Multi-factor Authentication 기능의 다음과 같은 하위 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-112">Office 365 offers the following subset of Azure Multi-Factor Authentication capabilities as a part of your subscription:</span></span> 
  
- <span data-ttu-id="4d5e5-113">최종 사용자에 대해 MFA를 사용 하도록 설정 하 고 적용 하는 기능</span><span class="sxs-lookup"><span data-stu-id="4d5e5-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="4d5e5-114">모바일 앱(온라인 및 일회용 암호[OTP])을 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="4d5e5-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="4d5e5-115">전화 통화를 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="4d5e5-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="4d5e5-116">SMS(문자 서비스) 메시지를 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="4d5e5-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="4d5e5-117">비 브라우저 클라이언트용 응용 프로그램 암호 (예: Microsoft Lync 2013 communications software)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="4d5e5-118">인증 전화 통화 중의 기본 Microsoft 인사말</span><span class="sxs-lookup"><span data-stu-id="4d5e5-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="4d5e5-p103">추가 기능의 전체 목록은 [Azure 다단계 인증 버전 비교](https://go.microsoft.com/fwlink/?LinkId=506927)를 참조하세요. Azure 다단계 인증 서비스를 구입하여 언제든지 모든 기능을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="4d5e5-121">Office 365에 대 한 클라우드 전용 또는 하이브리드 id가 있는지 또는 AD FS (Active Directory Federation Services)에 페더레이션 인증을 사용 하는지에 따라 다른 기능 하위 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-121">You get a different subset of capabilities depending on whether you have a cloud-only or hybrid identity for Office 365 or federated authentication with Active Directory Federation Services (AD FS).</span></span> 
  
<span data-ttu-id="4d5e5-122">|**Office 365 테 넌 트는 어디에서 관리 하나요?** | **MFA 두 번째 요소 옵션**|</span><span class="sxs-lookup"><span data-stu-id="4d5e5-122">|**Where do you manage your Office 365 tenant?**|**MFA second factor options**|</span></span>

<span data-ttu-id="4d5e5-123">|:-----|:-----| | 클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="4d5e5-123">|:-----|:-----| |Cloud only</span></span>  <br/> <span data-ttu-id="4d5e5-124">| Azure Multi-factor Authentication (텍스트 또는 전화 통화)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-124">|Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> <span data-ttu-id="4d5e5-125">| | 하이브리드 설치, 관리 되는 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="4d5e5-125">| |Hybrid setup, managed on-premises</span></span>  <br/> <span data-ttu-id="4d5e5-126">| 온-프레미스에서 사용자 id를 관리 하는 경우 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-126">| If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="4d5e5-127">실제 또는 가상 스마트 카드 (AD FS를 사용 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-127">Physical or virtual smart card (when using AD FS)</span></span>  <br/> <span data-ttu-id="4d5e5-128">[Azure Multi-factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (AD FS 용 모듈)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-128">[Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="4d5e5-129">Azure Active Directory (Azure AD) 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="4d5e5-129">Azure Active Directory (Azure AD) Multi-Factor Authentication</span></span>  <br/> |
   
  
<span data-ttu-id="4d5e5-130">다음 그림에서는 업데이트된 Office 2013 장치 앱(Windows 기반)에서 사용자가 MFA를 사용하여 로그인할 수 있는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-130">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA.</span></span> 

![Office 2013 장치 앱용 최신 인증](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

<span data-ttu-id="4d5e5-132">Office 2013 장치 앱은 [액티브 디렉터리 인증 라이브러리 (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684)사용을 통한 다단계 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-132">The Office 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="4d5e5-133">Azure AD는 사용자가 로그인할 수 있는 웹 페이지를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-133">Azure AD hosts a webpage where users can sign in.</span></span> <span data-ttu-id="4d5e5-134">ID 공급자는 Azure AD이거나 AD FS와 같은 페더레이션 ID 공급자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-134">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="4d5e5-135">페더레이션 사용자에 대한 인증은 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-135">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="4d5e5-p105">Azure AD는 Office 365 테넌트에 대한 레코드의 ID 공급자가 호스팅하는 로그인 웹 페이지로 사용자를 리디렉션합니다. ID 공급자는 사용자의 로그인 이름에 지정된 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="4d5e5-138">사용자는 자신의 장치에 표시된 로그인 웹 페이지에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="4d5e5-139">사용자가 성공적으로 로그인하면 ID 공급자는 Azure AD에 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="4d5e5-140">Azure AD는 Office 장치 앱에 JSON Web Token(JWT)을 반환하며, 장치 앱은 Office 365에서 JWT를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="4d5e5-141">Office 2013 클라이언트 앱에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d5e5-141">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="4d5e5-142">Office 2013 클라이언트 앱용 MFA를 활성화하려면 [간편 실행 기반 설치](#click-to-run-based-installations) 또는 [MSI 기반 설치](#msi-based-installations)가 있는지에 따라 다음 소프트웨어(아래 나열한 버전 이상)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-142">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="4d5e5-143">Office 설치가 간편 실행 기반인지 MSI 기반인지 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="4d5e5-143">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="4d5e5-144">Outlook 2013을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-144">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="4d5e5-145">**파일** 메뉴에서 **Office 계정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-145">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="4d5e5-146">Outlook 2013 간편 실행 설치의 경우 **업데이트 옵션** 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-146">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="4d5e5-147">MSI 기반 설치의 경우 **업데이트 옵션** 항목이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-147">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Office 2013 설치가 간편 실행 또는 MSI 기반 인지를 알리는 방법](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="4d5e5-149">Sor [에 대 한 자세한 내용은 최신 인증 wiki 문서에 대 한 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-149">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="4d5e5-150">간편 실행 기반 설치</span><span class="sxs-lookup"><span data-stu-id="4d5e5-150">Click-to-run based installations</span></span>

<span data-ttu-id="4d5e5-151">간편 실행 기반 설치의 경우 아래 나열 된 파일 버전 또는 이후 버전의 파일을 사용 하 여 다음 소프트웨어가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-151">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="4d5e5-152">나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 아래 단계에 따라 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-152">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="4d5e5-153">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-153">**File name**</span></span>|<span data-ttu-id="4d5e5-154">**컴퓨터의 설치 경로**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-154">**Install path on your computer**</span></span>|<span data-ttu-id="4d5e5-155">**파일 버전**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-155">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d5e5-156">MSO. DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-156">MSO.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-158">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="4d5e5-158">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="4d5e5-159">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-159">CSI.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="4d5e5-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="4d5e5-161">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="4d5e5-161">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="4d5e5-162">Groove</span><span class="sxs-lookup"><span data-stu-id="4d5e5-162">Groove.EXE</span></span>  <br/> |<span data-ttu-id="4d5e5-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="4d5e5-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-164">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="4d5e5-164">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="4d5e5-165">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="4d5e5-165">Outlook.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="4d5e5-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-167">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="4d5e5-167">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="4d5e5-168">ADAL. DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-168">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-170">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="4d5e5-170">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="4d5e5-171">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="4d5e5-171">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-172">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="4d5e5-172">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="4d5e5-173">일정하지 않음</span><span class="sxs-lookup"><span data-stu-id="4d5e5-173">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="4d5e5-174">MSI 기반 설치</span><span class="sxs-lookup"><span data-stu-id="4d5e5-174">MSI-based installations</span></span>

<span data-ttu-id="4d5e5-p108">MSI 기반 설치의 경우 아래 나열한 파일 버전 이상으로 다음 소프트웨어를 설치해야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 업데이트 KB 문서 열에 있는 링크를 사용하여 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="4d5e5-177">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-177">**File name**</span></span>|<span data-ttu-id="4d5e5-178">**컴퓨터의 설치 경로**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-178">**Install path on your computer**</span></span>|<span data-ttu-id="4d5e5-179">**업데이트를 다운로드할 위치**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-179">**Where to get the update**</span></span>|<span data-ttu-id="4d5e5-180">**버전**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-180">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d5e5-181">MSO. DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-181">MSO.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="4d5e5-183">KB3085480</span><span class="sxs-lookup"><span data-stu-id="4d5e5-183">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="4d5e5-184">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="4d5e5-184">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="4d5e5-185">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-185">CSI.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="4d5e5-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="4d5e5-187">KB3085504</span><span class="sxs-lookup"><span data-stu-id="4d5e5-187">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="4d5e5-188">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="4d5e5-188">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="4d5e5-189">Groove</span><span class="sxs-lookup"><span data-stu-id="4d5e5-189">Groove.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="4d5e5-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="4d5e5-191">KB3085509</span><span class="sxs-lookup"><span data-stu-id="4d5e5-191">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="4d5e5-192">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="4d5e5-192">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="4d5e5-193">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="4d5e5-193">Outlook.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="4d5e5-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="4d5e5-195">KB3085495</span><span class="sxs-lookup"><span data-stu-id="4d5e5-195">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="4d5e5-196">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="4d5e5-196">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="4d5e5-197">ADAL. DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-197">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="4d5e5-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="4d5e5-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="4d5e5-199">KB3055000</span><span class="sxs-lookup"><span data-stu-id="4d5e5-199">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="4d5e5-200">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="4d5e5-200">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="4d5e5-201">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="4d5e5-201">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="4d5e5-202">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="4d5e5-202">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="4d5e5-203">MS14-052</span><span class="sxs-lookup"><span data-stu-id="4d5e5-203">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="4d5e5-204">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="4d5e5-204">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="4d5e5-205">MFA 설정</span><span class="sxs-lookup"><span data-stu-id="4d5e5-205">Enable MFA</span></span>

<span data-ttu-id="4d5e5-206">Office 365 구독에 대해 MFA를 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-206">To enable MFA for your Office 365 subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="4d5e5-207">필요한 경우 [Windows 장치에서 Office 2013에 대 한 최신 인증을 사용 하도록 설정](enable-modern-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-207">If needed, [enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
2. <span data-ttu-id="4d5e5-208">페더레이션 인증의 경우 타사 디렉터리 서비스를 사용 하 여 Azure Multi-factor Authentication을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-208">For federated authentication, set up Azure Multi-Factor Authentication with your third-party directory service.</span></span>
    
    <span data-ttu-id="4d5e5-209">이 프로그램에 수락 된 특정 id 공급자에 대 한 정보를 보려면 [Azure Multi-factor Authentication 및 타사 VPN 솔루션을 포함 하는 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
3. <span data-ttu-id="4d5e5-210">[Office 365에 대 한 다단계 인증을 설정](set-up-multi-factor-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-210">[Set up multi-factor authentication for Office 365](set-up-multi-factor-authentication.md).</span></span>
    
4. <span data-ttu-id="4d5e5-211">사용자에 게 [Office 365 사용자 계정에 대해 MFA를 설정](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14)하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-211">Tell your users how to [set up MFA for their Office 365 user account](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14).</span></span> <span data-ttu-id="4d5e5-212">보조 인증 방법을 설정한 후에는 다음 로그인 기능에 MFA가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-212">After they set up their secondary authentication method, their future sign-ins will require MFA.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="4d5e5-213">사용자가 Azure Multi-factor Authentication을 사용 하도록 설정한 상태에서 최신 인증을 사용 하도록 설정 되지 않은 Office 2013을 실행 하는 장치가 있으면 앱 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use App Passwords.</span></span> <span data-ttu-id="4d5e5-214">앱 암호에 대 한 자세한 내용 및 사용 방법/위치/방법, 여기서는 [Azure Multi_Factor 인증을 사용 하는 앱 암호](https://go.microsoft.com/fwlink/p/?LinkId=528178)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-214">More information on App Passwords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="known-issues"></a><span data-ttu-id="4d5e5-215">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="4d5e5-215">Known issues</span></span>
  
[<span data-ttu-id="4d5e5-216">Office 2013 및 Office 365 ProPlus 최신 인증: 온 보 딩 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="4d5e5-216">Office 2013 and Office 365 ProPlus modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="4d5e5-217">**Azure 다단계 인증 문제 해결:**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-217">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="4d5e5-218">[Azure Multi-factor Authentication 문제 해결](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-218">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="4d5e5-219">AD FS를 사용하는 경우 Office 2013 최신 인증의 로그인 문제를 해결하는 방법</span><span class="sxs-lookup"><span data-stu-id="4d5e5-219">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="4d5e5-220">**대체 ID가 작동하지 않는 경우:**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-220">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="4d5e5-221">PowerShell을 사용하여 중복된 UPN을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="4d5e5-221">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
<span data-ttu-id="4d5e5-222">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)(중복된 사용자 계정 이름을 수정하기 위한 스크립트)</span><span class="sxs-lookup"><span data-stu-id="4d5e5-222">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)</span></span>
  
 <span data-ttu-id="4d5e5-223">**클라이언트 액세스 필터링:**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-223">**Client access filtering:**</span></span>
  
[<span data-ttu-id="4d5e5-224">Office 2013 및 Office 365 ProPlus 최신 인증 및 클라이언트 액세스 필터링 정책: 온보딩하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="4d5e5-224">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="4d5e5-225">**어떤 앱이 MFA를 지원하나요?**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-225">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="4d5e5-226">**Windows**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-226">**Windows**</span></span>|<span data-ttu-id="4d5e5-227">**Mac**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-227">**Mac**</span></span>|<span data-ttu-id="4d5e5-228">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-228">**iOS**</span></span>|<span data-ttu-id="4d5e5-229">**Android 휴대폰**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-229">**Android phone**</span></span>|<span data-ttu-id="4d5e5-230">**Android 태블릿**</span><span class="sxs-lookup"><span data-stu-id="4d5e5-230">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d5e5-231">이 릴리스에서는 Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 및 비즈니스용 Skype에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-231">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="4d5e5-232">이 릴리스에서는 Mac용 Word 2016, Mac용 Excel 2016 및 Mac용 PowerPoint 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-232">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="4d5e5-233">이 릴리스에서는 iPad용 Word, iPad용 Excel 및 iPad용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-233">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="4d5e5-234">이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-234">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="4d5e5-235">이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-235">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="4d5e5-236">이 릴리스에서는 Outlook 2013 및 Outlook 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-236">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="4d5e5-237">이 릴리스에서는 Mac용 Outlook 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-237">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="4d5e5-238">이 릴리스에서는 iPad용 Outlook에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e5-238">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

