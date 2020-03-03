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
ms.openlocfilehash: 2e2cbc9d6d966a9858fafb62f08d26893c9f4353
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361179"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="a105e-103">Office 365 배포의 다단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="a105e-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="a105e-p101">다단계 인증(MFA)은 두 가지 이상의 확인 방법을 사용해야 하고 사용자 로그인 및 트랜잭션에 두 번째 보안 레이어를 추가하는 인증 방법입니다. 이 작업에는 다음 확인 방법 중 두 가지 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p101">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions. It works by requiring any two or more of the following verification methods:</span></span>
  
- <span data-ttu-id="a105e-106">임의로 생성된 암호</span><span class="sxs-lookup"><span data-stu-id="a105e-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="a105e-107">전화 통화</span><span class="sxs-lookup"><span data-stu-id="a105e-107">A phone call</span></span>
    
- <span data-ttu-id="a105e-108">스마트 카드(가상 또는 실제)</span><span class="sxs-lookup"><span data-stu-id="a105e-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="a105e-109">생체 인식 장치</span><span class="sxs-lookup"><span data-stu-id="a105e-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-office-365"></a><span data-ttu-id="a105e-110">Office 365에서의 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="a105e-110">Multi-factor authentication in Office 365</span></span>

<span data-ttu-id="a105e-111">Office 365에서는 multi-factor authentication을 사용 하 여 추가 보안을 제공 하 고 Microsoft 365 관리 센터에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-111">Office 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="a105e-112">Office 365는 구독의 일부로 Azure 다단계 인증 기능의 다음 하위 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-112">Office 365 offers the following subset of Azure multi-factor authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="a105e-113">최종 사용자에 대한 다단계 인증을 활성화 및 적용하는 기능</span><span class="sxs-lookup"><span data-stu-id="a105e-113">The ability to enable and enforce multi-factor authentication for end users</span></span>
    
- <span data-ttu-id="a105e-114">모바일 앱(온라인 및 일회용 암호[OTP])을 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="a105e-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="a105e-115">전화 통화를 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="a105e-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="a105e-116">SMS(문자 서비스) 메시지를 두 번째 인증 요소로 사용</span><span class="sxs-lookup"><span data-stu-id="a105e-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="a105e-117">브라우저 이외의 클라이언트(예: Microsoft Lync 2013 통신 소프트웨어)의 응용 프로그램 암호</span><span class="sxs-lookup"><span data-stu-id="a105e-117">Application passwords for non browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="a105e-118">인증 전화 통화 중의 기본 Microsoft 인사말</span><span class="sxs-lookup"><span data-stu-id="a105e-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="a105e-p103">추가 기능의 전체 목록은 [Azure 다단계 인증 버전 비교](https://go.microsoft.com/fwlink/?LinkId=506927)를 참조하세요. Azure 다단계 인증 서비스를 구입하여 언제든지 모든 기능을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="a105e-121">Office 365에 대한 클라우드 전용 배포 또는 Single Sign-On 및 AD FS(Active Directory Federation Services)에 대한 하이브리드 설치가 있는지에 따라 다른 기능 하위 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Office 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="a105e-122">**Office 365 테넌트를 어디에서 관리하나요?**</span><span class="sxs-lookup"><span data-stu-id="a105e-122">**Where do you manage your Office 365 tenant?**</span></span>|<span data-ttu-id="a105e-123">**MFA 두 번째 요소 옵션**</span><span class="sxs-lookup"><span data-stu-id="a105e-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a105e-124">클라우드만</span><span class="sxs-lookup"><span data-stu-id="a105e-124">Cloud only</span></span>  <br/> |<span data-ttu-id="a105e-125">Azure Active Directory MFA(텍스트 또는 전화 통화)</span><span class="sxs-lookup"><span data-stu-id="a105e-125">Azure Active Directory MFA (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="a105e-126">하이브리드 설치, 관리되는 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="a105e-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="a105e-127">사용자 ID 온-프레미스를 관리하는 경우 다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="a105e-128">실제 또는 가상 스마트 카드(AD FS)</span><span class="sxs-lookup"><span data-stu-id="a105e-128">Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="a105e-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677)(AD FS용 모듈)</span><span class="sxs-lookup"><span data-stu-id="a105e-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="a105e-130">Azure AD MFA</span><span class="sxs-lookup"><span data-stu-id="a105e-130">Azure AD MFA</span></span>  <br/> |
   
  
<span data-ttu-id="a105e-p104">다음 그림에서는 업데이트된 Office 2013 장치 앱(Windows 기반)에서 사용자가 MFA를 사용하여 로그인할 수 있는 방법을 보여줍니다. Office 2013 장치 앱은 [Active Directory 인증 라이브러리(ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) 사용을 통한 다단계 인증을 지원합니다. Azure AD는 사용자가 로그인할 수 있는 웹 페이지를 호스팅합니다. ID 공급자는 Azure AD이거나 AD FS와 같은 페더레이션 ID 공급자일 수 있습니다. 페더레이션 사용자에 대한 인증은 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="a105e-p105">Azure AD는 Office 365 테넌트에 대한 레코드의 ID 공급자가 호스팅하는 로그인 웹 페이지로 사용자를 리디렉션합니다. ID 공급자는 사용자의 로그인 이름에 지정된 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="a105e-138">사용자는 자신의 장치에 표시된 로그인 웹 페이지에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="a105e-139">사용자가 성공적으로 로그인하면 ID 공급자는 Azure AD에 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="a105e-140">Azure AD는 Office 장치 앱에 JSON Web Token(JWT)을 반환하며, 장치 앱은 Office 365에서 JWT를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
<span data-ttu-id="a105e-141">다음 그림에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-141">This is detailed in the following figure:</span></span>
  
![Office 2013 장치 앱용 최신 인증](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a><span data-ttu-id="a105e-143">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a105e-143">Software requirements</span></span>

<span data-ttu-id="a105e-144">Office 2013 클라이언트 앱용 MFA를 활성화하려면 [간편 실행 기반 설치](#click-to-run-based-installations) 또는 [MSI 기반 설치](#msi-based-installations)가 있는지에 따라 다음 소프트웨어(아래 나열한 버전 이상)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-144">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="a105e-145">Office 설치가 간편 실행 기반인지 MSI 기반인지 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="a105e-145">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="a105e-146">Outlook 2013을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-146">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="a105e-147">**파일** 메뉴에서 **Office 계정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-147">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="a105e-p106">Outlook 2013 간편 실행 설치의 경우 **업데이트 옵션** 항목이 표시됩니다. MSI 기반 설치의 경우 **업데이트 옵션** 항목이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="a105e-151">간편 실행 기반 설치</span><span class="sxs-lookup"><span data-stu-id="a105e-151">Click-to-run based installations</span></span>

<span data-ttu-id="a105e-p107">간편 실행 기반 설치의 경우 아래 나열한 파일 버전 이상으로 다음 소프트웨어를 설치해야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 아래 단계에 따라 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p107">For Click-to-run based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="a105e-154">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="a105e-154">**File name**</span></span>|<span data-ttu-id="a105e-155">**컴퓨터의 설치 경로**</span><span class="sxs-lookup"><span data-stu-id="a105e-155">**Install path on your computer**</span></span>|<span data-ttu-id="a105e-156">**파일 버전**</span><span class="sxs-lookup"><span data-stu-id="a105e-156">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a105e-157">MSO. DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-157">MSO.DLL</span></span>  <br/> |<span data-ttu-id="a105e-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="a105e-159">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="a105e-159">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="a105e-160">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-160">CSI.DLL</span></span>  <br/> |<span data-ttu-id="a105e-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="a105e-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="a105e-162">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="a105e-162">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="a105e-163">Groove</span><span class="sxs-lookup"><span data-stu-id="a105e-163">Groove.EXE</span></span>  <br/> |<span data-ttu-id="a105e-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="a105e-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="a105e-165">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="a105e-165">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="a105e-166">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="a105e-166">Outlook.exe</span></span>  <br/> |<span data-ttu-id="a105e-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="a105e-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="a105e-168">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="a105e-168">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="a105e-169">ADAL. DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-169">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="a105e-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="a105e-171">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="a105e-171">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="a105e-172">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="a105e-172">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="a105e-173">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a105e-173">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="a105e-174">일정하지 않음</span><span class="sxs-lookup"><span data-stu-id="a105e-174">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="a105e-175">MSI 기반 설치</span><span class="sxs-lookup"><span data-stu-id="a105e-175">MSI-based installations</span></span>

<span data-ttu-id="a105e-p108">MSI 기반 설치의 경우 아래 나열한 파일 버전 이상으로 다음 소프트웨어를 설치해야 합니다. 나열된 파일 버전과 같거나 높지 않은 파일 버전인 경우 업데이트 KB 문서 열에 있는 링크를 사용하여 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="a105e-178">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="a105e-178">**File name**</span></span>|<span data-ttu-id="a105e-179">**컴퓨터의 설치 경로**</span><span class="sxs-lookup"><span data-stu-id="a105e-179">**Install path on your computer**</span></span>|<span data-ttu-id="a105e-180">**업데이트를 다운로드할 위치**</span><span class="sxs-lookup"><span data-stu-id="a105e-180">**Where to get the update**</span></span>|<span data-ttu-id="a105e-181">**버전**</span><span class="sxs-lookup"><span data-stu-id="a105e-181">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a105e-182">MSO. DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-182">MSO.DLL</span></span>  <br/> |<span data-ttu-id="a105e-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="a105e-184">KB3085480</span><span class="sxs-lookup"><span data-stu-id="a105e-184">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="a105e-185">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="a105e-185">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="a105e-186">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-186">CSI.DLL</span></span>  <br/> |<span data-ttu-id="a105e-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="a105e-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="a105e-188">KB3085504</span><span class="sxs-lookup"><span data-stu-id="a105e-188">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="a105e-189">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="a105e-189">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="a105e-190">Groove</span><span class="sxs-lookup"><span data-stu-id="a105e-190">Groove.exe</span></span>  <br/> |<span data-ttu-id="a105e-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="a105e-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="a105e-192">KB3085509</span><span class="sxs-lookup"><span data-stu-id="a105e-192">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="a105e-193">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="a105e-193">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="a105e-194">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="a105e-194">Outlook.exe</span></span>  <br/> |<span data-ttu-id="a105e-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="a105e-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="a105e-196">KB3085495</span><span class="sxs-lookup"><span data-stu-id="a105e-196">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="a105e-197">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="a105e-197">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="a105e-198">ADAL. DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-198">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="a105e-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="a105e-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="a105e-200">KB3055000</span><span class="sxs-lookup"><span data-stu-id="a105e-200">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="a105e-201">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="a105e-201">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="a105e-202">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="a105e-202">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="a105e-203">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a105e-203">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="a105e-204">MS14-052</span><span class="sxs-lookup"><span data-stu-id="a105e-204">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="a105e-205">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="a105e-205">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="a105e-206">MFA 설정</span><span class="sxs-lookup"><span data-stu-id="a105e-206">Enable MFA</span></span>

<span data-ttu-id="a105e-207">MFA를 설정하려면 다음을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-207">To enable MFA, you have to complete the following:</span></span>
  
1. <span data-ttu-id="a105e-208">최신 인증을 위해 클라이언트 설정:</span><span class="sxs-lookup"><span data-stu-id="a105e-208">Enable clients for modern authentication:</span></span>
    
  - <span data-ttu-id="a105e-209">[Windows 장치에서 Office 2013에 대한 최신 인증을 설정합니다](enable-modern-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="a105e-209">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md) .</span></span> 
    
  - <span data-ttu-id="a105e-210">타사 디렉터리 서비스에 Azure MFA를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-210">Set up Azure MFA with third-party directory services.</span></span>
    
    <span data-ttu-id="a105e-211">이 프로그램에 수락 된 특정 id 공급자에 대 한 정보를 보려면 [Azure Multi-factor Authentication 및 타사 VPN 솔루션을 포함 하는 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a105e-211">See the [Advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="a105e-212">Office 365에 대한 다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="a105e-212">Set up multi-factor authentication for Office 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="a105e-213">MFA로 로그인하는 방법을 개별 사용자에게 알림: [2단계 확인을 통해 Office 365에 로그인합니다](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span><span class="sxs-lookup"><span data-stu-id="a105e-213">Tell individual users how to sign in by MFA: [Sign in to Office 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="a105e-p109">Azure AD MFA에 대해 사용자를 설정했고 사용자가 최신 인증을 사용하도록 설정하지 않은 Office 2013을 실행하는 장치를 사용 중인 경우 해당 장치에서 AppPasswords를 사용해야 합니다. AppPasswords 및 이 항목을 언제 어디서 어떻게 사용해야 하는지에 대한 자세한 내용은 다음을 참조하세요. [Azure 다단계 인증의 앱 암호](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span><span class="sxs-lookup"><span data-stu-id="a105e-p109">If you have enabled your users for Azure AD MFA and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices. More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="faq"></a><span data-ttu-id="a105e-216">자주 묻는 질문(FAQ)</span><span class="sxs-lookup"><span data-stu-id="a105e-216">FAQ</span></span>

[<span data-ttu-id="a105e-217">최신 인증 Wiki 문서에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="a105e-217">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 <span data-ttu-id="a105e-218">**알려진 문제점:**</span><span class="sxs-lookup"><span data-stu-id="a105e-218">**Known issues:**</span></span>
  
[<span data-ttu-id="a105e-219">Office 2013 및 Office 365 ProPlus 최신 인증: 온보딩하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="a105e-219">Office 2013 and Office 365 ProPlus modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="a105e-220">**Azure 다단계 인증 문제 해결:**</span><span class="sxs-lookup"><span data-stu-id="a105e-220">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="a105e-221">[Azure MFA 문제 해결](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a105e-221">See [Troubleshoot Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="a105e-222">AD FS를 사용하는 경우 Office 2013 최신 인증의 로그인 문제를 해결하는 방법</span><span class="sxs-lookup"><span data-stu-id="a105e-222">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="a105e-223">**대체 ID가 작동하지 않는 경우:**</span><span class="sxs-lookup"><span data-stu-id="a105e-223">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="a105e-224">PowerShell을 사용하여 중복된 UPN을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="a105e-224">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
<span data-ttu-id="a105e-225">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)(중복된 사용자 계정 이름을 수정하기 위한 스크립트)</span><span class="sxs-lookup"><span data-stu-id="a105e-225">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)</span></span>
  
 <span data-ttu-id="a105e-226">**클라이언트 액세스 필터링:**</span><span class="sxs-lookup"><span data-stu-id="a105e-226">**Client access filtering:**</span></span>
  
[<span data-ttu-id="a105e-227">Office 2013 및 Office 365 ProPlus 최신 인증 및 클라이언트 액세스 필터링 정책: 온보딩하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="a105e-227">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="a105e-228">**어떤 앱이 MFA를 지원하나요?**</span><span class="sxs-lookup"><span data-stu-id="a105e-228">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="a105e-229">**Windows**</span><span class="sxs-lookup"><span data-stu-id="a105e-229">**Windows**</span></span>|<span data-ttu-id="a105e-230">**Mac**</span><span class="sxs-lookup"><span data-stu-id="a105e-230">**Mac**</span></span>|<span data-ttu-id="a105e-231">**iOS**</span><span class="sxs-lookup"><span data-stu-id="a105e-231">**iOS**</span></span>|<span data-ttu-id="a105e-232">**Android 휴대폰**</span><span class="sxs-lookup"><span data-stu-id="a105e-232">**Android phone**</span></span>|<span data-ttu-id="a105e-233">**Android 태블릿**</span><span class="sxs-lookup"><span data-stu-id="a105e-233">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a105e-234">이 릴리스에서는 Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 및 비즈니스용 Skype에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-234">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="a105e-235">이 릴리스에서는 Mac용 Word 2016, Mac용 Excel 2016 및 Mac용 PowerPoint 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-235">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="a105e-236">이 릴리스에서는 iPad용 Word, iPad용 Excel 및 iPad용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-236">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="a105e-237">이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="a105e-238">이 릴리스에서는 Android용 Word, Android용 Excel 및 Android용 PowerPoint에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-238">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="a105e-239">이 릴리스에서는 Outlook 2013 및 Outlook 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-239">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="a105e-240">이 릴리스에서는 Mac용 Outlook 2016에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-240">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="a105e-241">이 릴리스에서는 iPad용 Outlook에 대한 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a105e-241">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

