---
title: 'Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 인증서 기반 인증에 Microsoft 365 클라이언트 앱 지원에 대한 세부 정보를 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905000"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a><span data-ttu-id="1164f-103">Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증</span><span class="sxs-lookup"><span data-stu-id="1164f-103">Microsoft 365 Client App Support: Certificate-based Authentication</span></span>

<span data-ttu-id="1164f-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="1164f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1164f-105">최신 인증은 인증 및 권한 부여 방법의 조합을 위한 우산 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-105">Modern authentication is an umbrella term for a combination of authentication and authorization methods.</span></span> <span data-ttu-id="1164f-106">이러한 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-106">These methods include:</span></span>

- <span data-ttu-id="1164f-107">**인증 방법:** 다단계 인증 클라이언트 인증서 기반 인증.</span><span class="sxs-lookup"><span data-stu-id="1164f-107">**Authentication methods**: Multi-factor Authentication; Client Certificate-based authentication.</span></span>
- <span data-ttu-id="1164f-108">**권한 부여 방법:** Microsoft의 OAuth(Open Authorization) 구현</span><span class="sxs-lookup"><span data-stu-id="1164f-108">**Authorization methods**: Microsoft's implementation of Open Authorization (OAuth).</span></span>

<span data-ttu-id="1164f-109">ADAL(Active Directory 인증 라이브러리) 또는 MSAL(Microsoft 인증 라이브러리)과 같은 인증 라이브러리를 사용하여 최신 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-109">Modern authentication is enabled by using an authentication library, like Active Directory Authentication Library (ADAL) or Microsoft Authentication Library (MSAL).</span></span> <span data-ttu-id="1164f-110">최신 인증은 클라이언트가 리소스에 대한 액세스 권한을 인증하고 권한을 부여하는 Microsoft 365 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-110">Modern authentication is what clients use to authenticate and authorize access to Microsoft 365 resources.</span></span> <span data-ttu-id="1164f-111">최신 인증은 OAuth를 사용하며 클라이언트가 사용자 자격 증명에 액세스하지 않고도 Microsoft 365 서비스에 액세스할 수 있는 보안 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-111">Modern authentication uses OAuth and provides a secure mechanism for clients to access Microsoft 365 services, without requiring access to user credentials.</span></span> <span data-ttu-id="1164f-112">로그인 시 사용자는 로그인 시 직접 인증을 Azure Active Directory 액세스/새로 고침 토큰 쌍을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-112">At sign-in, the user authenticates directly with Azure Active Directory and receives an access/refresh token pair in return.</span></span> <span data-ttu-id="1164f-113">액세스 토큰은 클라이언트에게 테넌트의 적절한 리소스에 대한 Microsoft 365 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-113">The access token grants the client access to the appropriate resources in the Microsoft 365 tenant.</span></span> <span data-ttu-id="1164f-114">새로 고침 토큰은 현재 액세스 토큰이 만료될 때 새 액세스 또는 새로 고침 토큰 쌍을 얻는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-114">A refresh token is used to obtain a new access or refresh token pair when the current access token expires.</span></span>

<span data-ttu-id="1164f-115">최신 인증은 인증서 기반 인증과 같은 다양한 인증 메커니즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-115">Modern authentication supports different authentication mechanisms, like certificate-based authentication.</span></span> <span data-ttu-id="1164f-116">Windows, Android 또는 iOS 장치의 클라이언트는 CBA(인증서 기반 인증)를 사용하여 장치에서 클라이언트 Azure Active Directory 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-116">Clients on Windows, Android, or iOS devices can use certificate-based authentication (CBA) to authenticate to Azure Active Directory using a client certificate on the device.</span></span> <span data-ttu-id="1164f-117">일반적인 사용자 이름/암호 대신 인증서를 사용하여 사용자 이름에서 액세스/새로 고침 토큰 쌍을 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1164f-117">Instead of a typical username/password, the certificate is used to obtain an access/refresh token pair from Azure Active Directory.</span></span>

<span data-ttu-id="1164f-118">인증서 기반 [인증에 대해 자세히 알아보시다.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)</span><span class="sxs-lookup"><span data-stu-id="1164f-118">Learn more about [certificate-based authentication](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="1164f-119">지원되는 & 플랫폼</span><span class="sxs-lookup"><span data-stu-id="1164f-119">Supported clients & platforms</span></span>

<span data-ttu-id="1164f-120">다음 클라이언트 및 플랫폼의 최신 버전은 클라이언트 내의 Azure Active Directory 계정에 로그인할 때(예: 앱에 계정을 추가할 때) 인증서 기반 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-120">The latest versions of the following clients and platforms support certificate-based authentication when signing into Azure Active Directory accounts within the client (for example, when adding an account to the app).</span></span> <span data-ttu-id="1164f-121">Microsoft 365 플랫폼 지원에 대한 자세한 내용은 에 대한 시스템 요구 [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="1164f-121">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
><span data-ttu-id="1164f-122">iOS 및 Android용 Edge는 계정 추가 흐름 중에 인증서 기반 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-122">Edge for iOS and Android supports certificate-based authentication during account add flows.</span></span> <span data-ttu-id="1164f-123">iOS 및 Android용 에지에서는 일반적으로 인트라넷 사이트인 웹 사이트에 대해 인증을 수행할 때 인증서 기반 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-123">Edge for iOS and Android does not support certificate-based authentication when performing authentication against web sites, which are typically intranet sites.</span></span> <br><br>  <span data-ttu-id="1164f-124">이 시나리오에서는 사용자가 웹 사이트(일반적으로 인트라넷)로 이동하여 사용자가 인증서를 통해 인증해야 하는 웹 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-124">In this scenario, a user navigates to a web site (usually on the intranet) where the web site requires the user to authenticate via a certificate.</span></span> <span data-ttu-id="1164f-125">이는 최신 인증과 관련이 없는 것이 아니며 Microsoft 인증 라이브러리를 활용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-125">This does not involve modern authentication at all and does not leverage a Microsoft authentication library.</span></span> <span data-ttu-id="1164f-126">이는 iOS의 제한 때문에: iOS는 타사 앱이 인증서가 저장된 시스템 키채인에 액세스하지 못하게 합니다(Apple 앱과 [Safari webview 컨트롤러만](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 시스템 키체인에 액세스할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="1164f-126">This is due to a limitation with iOS: iOS prevents third-party apps from accessing the system keychain where the certificates are stored (only Apple apps and the [Safari webview controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) can access the system keychain).</span></span> <br><br> <span data-ttu-id="1164f-127">Edge는 웹 사이트 렌더링을 위해 [WebKit](https://developer.apple.com/documentation/webkit) 프레임워크를 사용하게 됐기 때문에 Edge는 시스템 키채인에 액세스하여 사용자에게 인증서를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-127">As Edge relies on the [WebKit](https://developer.apple.com/documentation/webkit) framework for rendering web sites, Edge is unable to access the system keychain and present the user with a certificate choice.</span></span> <span data-ttu-id="1164f-128">안타깝게도 Apple의 아키텍처로 인해 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1164f-128">This, unfortunately, is by design due to Apple's architecture.</span></span>

## <a name="supported-powershell-modules"></a><span data-ttu-id="1164f-129">지원되는 PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="1164f-129">Supported PowerShell modules</span></span>

- [<span data-ttu-id="1164f-130">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="1164f-130">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="1164f-131">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1164f-131">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="1164f-132">SharePoint 온라인 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1164f-132">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

