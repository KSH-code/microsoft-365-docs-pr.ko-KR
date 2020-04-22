---
title: Microsoft 365 배포에 대 한 다단계 인증 계획
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
description: Microsoft 365의 다단계 인증 및이를 설정 하기 위해 수행 해야 하는 단계에 대해 알아봅니다.
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665671"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a><span data-ttu-id="fd019-103">Microsoft 365 배포에 대 한 다단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="fd019-103">Plan for multi-factor authentication for Microsoft 365 deployments</span></span>

<span data-ttu-id="fd019-104">다단계 인증(MFA)은 두 가지 이상의 확인 방법을 사용해야 하고 사용자 로그인 및 트랜잭션에 두 번째 보안 레이어를 추가하는 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="fd019-105">이는 다음과 같이 사용자 계정 암호를 초과 하는 정보와 함께 추가 확인 단계를 요구 하는 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="fd019-106">사용자의 smart 전화로 전송 되는 임의로 생성 되는 확인 코드</span><span class="sxs-lookup"><span data-stu-id="fd019-106">A randomly generated verification code sent to your smart phone</span></span>
    
- <span data-ttu-id="fd019-107">전화 통화</span><span class="sxs-lookup"><span data-stu-id="fd019-107">A phone call</span></span>
    
- <span data-ttu-id="fd019-108">스마트 카드(가상 또는 실제)</span><span class="sxs-lookup"><span data-stu-id="fd019-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="fd019-109">생체 인식 장치</span><span class="sxs-lookup"><span data-stu-id="fd019-109">A biometric device</span></span> 
    
## <a name="mfa-in-microsoft-365"></a><span data-ttu-id="fd019-110">Microsoft 365의 MFA</span><span class="sxs-lookup"><span data-stu-id="fd019-110">MFA in Microsoft 365</span></span>

<span data-ttu-id="fd019-111">Microsoft 365에서는 MFA를 사용 하 여 추가 보안을 제공 하 고 Microsoft 365 관리 센터에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-111">Microsoft 365 uses MFA to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="fd019-112">Microsoft 365에서는 구독의 일부로 [Azure Multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) 기능의 다음과 같은 하위 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-112">Microsoft 365 offers the following subset of [Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="fd019-113">최종 사용자에 대해 MFA를 사용 하도록 설정 하 고 적용 하는 기능</span><span class="sxs-lookup"><span data-stu-id="fd019-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="fd019-114">모바일 앱(온라인 및 일회용 암호[OTP])을 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="fd019-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="fd019-115">전화 통화를 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="fd019-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="fd019-116">SMS (Short Message Service) 텍스트 메시지를 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="fd019-116">The use of a Short Message Service (SMS) text message as a second authentication factor</span></span>
    
- <span data-ttu-id="fd019-117">비 브라우저 클라이언트용 응용 프로그램 암호 (예: Microsoft Lync 2013 communications software)</span><span class="sxs-lookup"><span data-stu-id="fd019-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="fd019-118">인증 전화 통화 중의 기본 Microsoft 인사말</span><span class="sxs-lookup"><span data-stu-id="fd019-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="fd019-119">추가 된 기능의 전체 목록은 [Azure Multi-factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd019-119">For the full list of added features, see [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927).</span></span> <span data-ttu-id="fd019-120">[Azure Multi-factor Authentication 라이선스](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)를 구입 하 여 언제 든 지 모든 기능을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-120">You can always get the full functionality by purchasing [Azure Multi-Factor Authentication licenses](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing).</span></span> 
  
<span data-ttu-id="fd019-121">Microsoft 365에서 사용자 계정이 있는 경우 클라우드 전용 id를 사용 하는지 또는 single sign-on 및 AD FS (Active Directory Federation Services)로 하이브리드를 설정 했는지에 따라 다른 기능 하위 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-121">You get a different subset of capabilities depending on whether you use cloud-only identity where the user accounts on exist in Microsoft 365, or hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="fd019-122">**어디에서 Microsoft 365를 관리 하나요?**</span><span class="sxs-lookup"><span data-stu-id="fd019-122">**Where do you manage Microsoft 365?**</span></span>|<span data-ttu-id="fd019-123">**MFA 두 번째 요소 옵션**</span><span class="sxs-lookup"><span data-stu-id="fd019-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fd019-124">클라우드만</span><span class="sxs-lookup"><span data-stu-id="fd019-124">Cloud only</span></span>  <br/> | <span data-ttu-id="fd019-125">Azure Multi-factor Authentication (텍스트 또는 전화 통화)</span><span class="sxs-lookup"><span data-stu-id="fd019-125">Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="fd019-126">하이브리드 설치, 관리되는 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="fd019-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="fd019-127">사용자 ID 온-프레미스를 관리하는 경우 다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/> <span data-ttu-id="fd019-128">-실제 또는 가상 스마트 카드 (AD FS)</span><span class="sxs-lookup"><span data-stu-id="fd019-128">-  Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="fd019-129">-Azure Multi-factor Authentication (AD FS 용 모듈)</span><span class="sxs-lookup"><span data-stu-id="fd019-129">- Azure Multi-Factor Authentication (module for AD FS)</span></span>  <br/>  <span data-ttu-id="fd019-130">-Azure Multi-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="fd019-130">- Azure Multi-Factor Authentication</span></span>  <br/> |
   
<span data-ttu-id="fd019-131">Office 2013 장치 앱은 [ADAL (Active Directory 인증 라이브러리)](https://go.microsoft.com/fwlink/p/?LinkId=526684)사용을 통해 MFA를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-131">The Office 2013 device apps support MFA through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="fd019-132">Azure AD (Active Directory)는 사용자가 로그인 할 수 있는 웹 페이지를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-132">Azure Active Directory (Azure AD) hosts a web page where users can sign in.</span></span> <span data-ttu-id="fd019-133">ID 공급자는 Azure AD이거나 AD FS와 같은 페더레이션 ID 공급자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-133">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="fd019-134">페더레이션 사용자에 대한 인증은 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-134">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="fd019-135">Azure AD는 사용자를 조직의 레코드 id 공급자가 호스팅하는 로그인 웹 페이지로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-135">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the organization.</span></span> <span data-ttu-id="fd019-136">ID 공급자는 사용자의 로그인 이름에 지정된 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-136">The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="fd019-137">사용자는 자신의 장치에 표시된 로그인 웹 페이지에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-137">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="fd019-138">사용자가 성공적으로 로그인하면 ID 공급자는 Azure AD에 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-138">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="fd019-139">Azure AD는 Office 장치 앱에 대 한 JWT (JSON Web Token)를 반환 하며, 장치 앱은 Microsoft 365에서 JWT를 사용 하 여 인증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-139">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Microsoft 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="fd019-140">Office 2013 클라이언트 앱에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd019-140">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="fd019-141">Office 2013 클라이언트 앱용 MFA를 활성화하려면 [간편 실행 기반 설치](#click-to-run-based-installations) 또는 [MSI 기반 설치](#msi-based-installations)가 있는지에 따라 다음 소프트웨어(아래 나열한 버전 이상)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-141">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="fd019-142">Office 설치가 간편 실행 기반인지 MSI 기반인지 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="fd019-142">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="fd019-143">Outlook 2013을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-143">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="fd019-144">**파일** 메뉴에서 **Office 계정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-144">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="fd019-145">Outlook 2013 간편 실행 설치의 경우 **업데이트 옵션** 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-145">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="fd019-146">MSI 기반 설치의 경우 **업데이트 옵션** 항목이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-146">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Office 2013 설치가 간편 실행 또는 MSI 기반 인지를 알리는 방법](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="fd019-148">Sor [에 대 한 자세한 내용은 최신 인증 wiki 문서에 대 한 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=530064)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd019-148">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="fd019-149">간편 실행 기반 설치</span><span class="sxs-lookup"><span data-stu-id="fd019-149">Click-to-run based installations</span></span>

<span data-ttu-id="fd019-150">간편 실행 기반 설치의 경우 아래 나열 된 파일 버전 또는 이후 버전의 파일을 사용 하 여 다음 소프트웨어가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-150">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="fd019-151">나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 아래 단계에 따라 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-151">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="fd019-152">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="fd019-152">**File name**</span></span>|<span data-ttu-id="fd019-153">**컴퓨터의 설치 경로**</span><span class="sxs-lookup"><span data-stu-id="fd019-153">**Install path on your computer**</span></span>|<span data-ttu-id="fd019-154">**파일 버전**</span><span class="sxs-lookup"><span data-stu-id="fd019-154">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd019-155">MSO. DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-155">MSO.DLL</span></span>  <br/> |<span data-ttu-id="fd019-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="fd019-157">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="fd019-157">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="fd019-158">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-158">CSI.DLL</span></span>  <br/> |<span data-ttu-id="fd019-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="fd019-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="fd019-160">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="fd019-160">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="fd019-161">Groove</span><span class="sxs-lookup"><span data-stu-id="fd019-161">Groove.EXE</span></span>  <br/> |<span data-ttu-id="fd019-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="fd019-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="fd019-163">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="fd019-163">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="fd019-164">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="fd019-164">Outlook.exe</span></span>  <br/> |<span data-ttu-id="fd019-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="fd019-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="fd019-166">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="fd019-166">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="fd019-167">ADAL. DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-167">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="fd019-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="fd019-169">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="fd019-169">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="fd019-170">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="fd019-170">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="fd019-171">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="fd019-171">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="fd019-172">일정하지 않음</span><span class="sxs-lookup"><span data-stu-id="fd019-172">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="fd019-173">MSI 기반 설치</span><span class="sxs-lookup"><span data-stu-id="fd019-173">MSI-based installations</span></span>

<span data-ttu-id="fd019-p108">MSI 기반 설치의 경우 아래 나열한 파일 버전 이상으로 다음 소프트웨어를 설치해야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 업데이트 KB 문서 열에 있는 링크를 사용하여 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="fd019-176">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="fd019-176">**File name**</span></span>|<span data-ttu-id="fd019-177">**컴퓨터의 설치 경로**</span><span class="sxs-lookup"><span data-stu-id="fd019-177">**Install path on your computer**</span></span>|<span data-ttu-id="fd019-178">**업데이트를 다운로드할 위치**</span><span class="sxs-lookup"><span data-stu-id="fd019-178">**Where to get the update**</span></span>|<span data-ttu-id="fd019-179">**버전**</span><span class="sxs-lookup"><span data-stu-id="fd019-179">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd019-180">MSO. DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-180">MSO.DLL</span></span>  <br/> |<span data-ttu-id="fd019-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="fd019-182">KB3085480</span><span class="sxs-lookup"><span data-stu-id="fd019-182">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="fd019-183">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="fd019-183">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="fd019-184">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-184">CSI.DLL</span></span>  <br/> |<span data-ttu-id="fd019-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="fd019-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="fd019-186">KB3085504</span><span class="sxs-lookup"><span data-stu-id="fd019-186">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="fd019-187">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="fd019-187">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="fd019-188">Groove</span><span class="sxs-lookup"><span data-stu-id="fd019-188">Groove.exe</span></span>  <br/> |<span data-ttu-id="fd019-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="fd019-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="fd019-190">KB3085509</span><span class="sxs-lookup"><span data-stu-id="fd019-190">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="fd019-191">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="fd019-191">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="fd019-192">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="fd019-192">Outlook.exe</span></span>  <br/> |<span data-ttu-id="fd019-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="fd019-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="fd019-194">KB3085495</span><span class="sxs-lookup"><span data-stu-id="fd019-194">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="fd019-195">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="fd019-195">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="fd019-196">ADAL. DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-196">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="fd019-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="fd019-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="fd019-198">KB3055000</span><span class="sxs-lookup"><span data-stu-id="fd019-198">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="fd019-199">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="fd019-199">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="fd019-200">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="fd019-200">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="fd019-201">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="fd019-201">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="fd019-202">MS14-052</span><span class="sxs-lookup"><span data-stu-id="fd019-202">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="fd019-203">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="fd019-203">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="fd019-204">MFA 설정</span><span class="sxs-lookup"><span data-stu-id="fd019-204">Enable MFA</span></span>

<span data-ttu-id="fd019-205">구독에 대해 MFA를 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-205">To enable MFA for your subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="fd019-206">필요한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-206">If needed:</span></span> 

  - <span data-ttu-id="fd019-207">[Windows 장치에서 Office 2013에 대 한 최신 인증을 사용 하도록 설정](enable-modern-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-207">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
  - <span data-ttu-id="fd019-208">타사 디렉터리 서비스를 사용 하 여 Azure Multi-factor Authentication을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-208">Set up Azure Multi-Factor Authentication with third-party directory services.</span></span>
    
    <span data-ttu-id="fd019-209">이 프로그램에 수락 된 특정 id 공급자에 대 한 정보를 보려면 [Azure Multi-factor Authentication 및 타사 VPN 솔루션을 포함 하는 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd019-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. <span data-ttu-id="fd019-210">[Microsoft 365에 대해 MFA를 설정](set-up-multi-factor-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-210">[Set up MFA for Microsoft 365](set-up-multi-factor-authentication.md).</span></span>
    
3. <span data-ttu-id="fd019-211">개별 사용자에 게 MFA로 로그인 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-211">Tell individual users how to sign in by MFA.</span></span> <span data-ttu-id="fd019-212">[MFA를 사용 하 여 Microsoft 365에 로그인을](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd019-212">See [Sign in to Microsoft 365 with MFA](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd019-213">사용자가 Azure Multi-factor Authentication을 사용 하도록 설정한 상태에서 최신 인증을 사용 하도록 설정 되지 않은 모든 장치를 Office 2013를 실행 하는 경우 해당 장치에서 AppPasswords를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices.</span></span> <span data-ttu-id="fd019-214">AppPasswords에 대 한 자세한 내용은 [Azure 다단계 인증을 사용 하는 앱 암호](https://go.microsoft.com/fwlink/p/?LinkId=528178)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd019-214">More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span>
  
## <a name="faq"></a><span data-ttu-id="fd019-215">FAQ</span><span class="sxs-lookup"><span data-stu-id="fd019-215">FAQ</span></span>

[<span data-ttu-id="fd019-216">최신 인증 Wiki 문서에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="fd019-216">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a><span data-ttu-id="fd019-217">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="fd019-217">Known issues</span></span>

[<span data-ttu-id="fd019-218">엔터프라이즈 최신 인증용 Office 2013 및 Microsoft 365 앱: 온 보 딩 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="fd019-218">Office 2013 and Microsoft 365 Apps for enterprise modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="fd019-219">**Azure 다단계 인증 문제 해결:**</span><span class="sxs-lookup"><span data-stu-id="fd019-219">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="fd019-220">[Azure Multi-factor Authentication 문제 해결](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd019-220">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="fd019-221">AD FS를 사용하는 경우 Office 2013 최신 인증의 로그인 문제를 해결하는 방법</span><span class="sxs-lookup"><span data-stu-id="fd019-221">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="fd019-222">**대체 ID가 작동하지 않는 경우:**</span><span class="sxs-lookup"><span data-stu-id="fd019-222">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="fd019-223">PowerShell을 사용하여 중복된 UPN을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="fd019-223">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
<span data-ttu-id="fd019-224">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)(중복된 사용자 계정 이름을 수정하기 위한 스크립트)</span><span class="sxs-lookup"><span data-stu-id="fd019-224">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)</span></span>
  
 <span data-ttu-id="fd019-225">**클라이언트 액세스 필터링:**</span><span class="sxs-lookup"><span data-stu-id="fd019-225">**Client access filtering:**</span></span>
  
[<span data-ttu-id="fd019-226">엔터프라이즈 최신 인증 및 클라이언트 액세스 필터링 정책에 대 한 Office 2013 및 Microsoft 365 앱: 온 보 딩 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="fd019-226">Office 2013 and Microsoft 365 Apps for enterprise modern authentication and client access filtering policies: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="fd019-227">**어떤 앱이 MFA를 지원하나요?**</span><span class="sxs-lookup"><span data-stu-id="fd019-227">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="fd019-228">**Windows**</span><span class="sxs-lookup"><span data-stu-id="fd019-228">**Windows**</span></span>|<span data-ttu-id="fd019-229">**Mac**</span><span class="sxs-lookup"><span data-stu-id="fd019-229">**Mac**</span></span>|<span data-ttu-id="fd019-230">**iOS**</span><span class="sxs-lookup"><span data-stu-id="fd019-230">**iOS**</span></span>|<span data-ttu-id="fd019-231">**Android 휴대폰**</span><span class="sxs-lookup"><span data-stu-id="fd019-231">**Android phone**</span></span>|<span data-ttu-id="fd019-232">**Android 태블릿**</span><span class="sxs-lookup"><span data-stu-id="fd019-232">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd019-233">이 릴리스에서는 Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 및 비즈니스용 Skype에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-233">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="fd019-234">이 릴리스에서는 Mac용 Word 2016, Mac용 Excel 2016 및 Mac용 PowerPoint 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-234">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="fd019-235">이 릴리스에서는 iPad용 Word, iPad용 Excel 및 iPad용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-235">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="fd019-236">이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-236">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="fd019-237">이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="fd019-238">이 릴리스에서는 Outlook 2013 및 Outlook 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-238">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="fd019-239">이 릴리스에서는 Mac용 Outlook 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-239">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="fd019-240">이 릴리스에서는 iPad용 Outlook에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd019-240">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

