---
title: Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비
description: Azure AD가 인증을 제공하기 위해 Azure AD와 통신할 수 있도록 하는 중요한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841414"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="32e6d-104">Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="32e6d-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="32e6d-105">Microsoft Managed Desktop에서 장치는 Azure AD(Azure Active Directory)에 자동으로 가입됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="32e6d-106">이러한 이유로, On-premises Active Directory를 사용하는 경우 Azure AD에 가입된 장치가 On-premises Active Directory와 통신할 수 있도록 몇 가지를 점검해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-106">For this reason, if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="32e6d-107">*하이브리드* Azure AD 가입은 Microsoft Managed Desktop에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="32e6d-108">Azure Active Directory를 사용하면 사용자가 SSO(Single Sign-On)를 활용할 수 있습니다. 즉, 일반적으로 리소스를 사용할 때마다 자격 증명을 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="32e6d-109">Azure Active Directory에 가입하는 방법에 대한 자세한 내용은 방법: Azure AD 조인 구현 [계획.을 참조하세요.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="32e6d-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="32e6d-110">Azure AD에 가입된 Sign-On SSO(Single Sign-On)에 대한 배경 정보는 Azure AD 가입 장치에서 [SSO와의 SSO가](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)작동하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e6d-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="32e6d-111">이 문서에서는 로컬 Active Directory 연결에 종속된 앱 및 기타 리소스가 Microsoft Managed Desktop에서 원활하게 작동하도록 보장하기 위해 확인해야 하는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-111">This article explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="32e6d-112">Sign-On 리소스에 대한 단일 리소스</span><span class="sxs-lookup"><span data-stu-id="32e6d-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="32e6d-113">UPN 및 암호를 Sign-On SSO(Single Sign-On)는 Microsoft Managed Desktop Devices에서 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="32e6d-114">그러나 사용자는 비즈니스용 Windows Hello를 사용할 수도 있습니다. 이 경우 몇 가지 추가 설정 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="32e6d-115">UPN 및 Sign-On 사용하여 단일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="32e6d-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="32e6d-116">대부분의 조직에서 사용자는 SSO를 사용하여 Microsoft Managed Desktop Devices에서 UPN 및 암호로 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="32e6d-117">그러나 이 함수가 작동할 수 있도록 다음을 다시 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-117">However, to make sure this function will work, you should double-check the following things:</span></span>

- <span data-ttu-id="32e6d-118">Azure AD Connect가 설정되어 있으며 Windows Server 2008 R2 이상을 실행하는프레미스 Active Directory 서버를 사용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="32e6d-119">Azure AD Connect가 지원되는 버전을 실행하고 있으며 Azure AD와 이러한 세 가지 특성을 동기화할 수 있는 것으로 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="32e6d-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="32e6d-120">사용자 위치의 Dns 도메인 이름(사용자가 있는 경우)의 DNS 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="32e6d-120">DNS domain name of the on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="32e6d-121">사용자 위치의 NetBIOS(On-premises Active Directory)</span><span class="sxs-lookup"><span data-stu-id="32e6d-121">NetBIOS of your on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="32e6d-122">사용자의 SAM 계정 이름</span><span class="sxs-lookup"><span data-stu-id="32e6d-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="32e6d-123">비즈니스용 Windows Hello를 사용하여 단일 Sign-On 사용</span><span class="sxs-lookup"><span data-stu-id="32e6d-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="32e6d-124">또한 Microsoft Managed Desktop 장치는 비즈니스용 Windows Hello를 사용하여 사용자에게 빠르고 암호 없는 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="32e6d-125">사용자가 각 UPN 및 암호를 제공할 필요 없이 비즈니스용 Windows Hello가 작동하도록 보장하기 위해, 비즈니스용 Windows Hello를 사용하여 요구 사항을 확인한 다음, 비즈니스용 [Windows Hello를](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) 사용하여 Single-Sign에 대한 Azure AD 가입 장치 구성을 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="32e6d-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="32e6d-126">인증을 사용하는 앱 및 리소스</span><span class="sxs-lookup"><span data-stu-id="32e6d-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="32e6d-127">Azure [](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) Active Directory에서 작동할 앱을 설정하는 방법에 대한 전체 지침은 Azure 콘텐츠 집합의 응용 프로그램 및 리소스에 대한 고려 사항 이해를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e6d-127">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="32e6d-128">요약하면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-128">In summary:</span></span>


- <span data-ttu-id="32e6d-129">Azure AD 앱 갤러리에 추가된 앱과 같은 클라우드 기반 앱을 사용하는 경우 Microsoft Managed Desktop을 사용하기 위해 추가 준비를 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="32e6d-130">그러나 WAM(웹 계정 관리자)을 사용하지 않는 Win32 앱은 사용자에게 인증을 요청하는 메시지가 계속 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="32e6d-131">**On-premises에서** 호스팅하는 앱의 경우 브라우저의 신뢰할 수 있는 사이트 목록에 해당 앱을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="32e6d-132">이 단계를 통해 사용자에게 자격 증명을 입력하라는 메시지가 표시되지 않고도 Windows 인증이 원활하게 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-132">This step will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="32e6d-133">앱을 추가하려면 구성 [](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) 가능한 설정 참조에서 신뢰할 수 있는 [사이트를 참조하세요.](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)</span><span class="sxs-lookup"><span data-stu-id="32e6d-133">To add apps, refer to [Trusted sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in the [Configurable settings reference](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).</span></span>

- <span data-ttu-id="32e6d-134">Active Directory Federated Services를 사용하는 경우 [AD FS에서 Single Sign-On](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))확인 및 관리 단계를 사용하여 SSO가 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="32e6d-135">장치가 인증을 위해온-프레미스 도메인 컨트롤러에 액세스할 수 있는 한,온-프레미스에 있으며 이전 프로토콜을 사용하는 앱의 경우 추가 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="32e6d-136">그러나 이러한 응용 프로그램에 대한 보안 액세스를 제공하기 위해 Azure AD 응용 프로그램 프록시를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="32e6d-137">자세한 내용은 Azure Active Directory의 응용 프로그램 프록시를 통해 프레미스 응용 프로그램에 대한 원격 [액세스를 참조하세요.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)</span><span class="sxs-lookup"><span data-stu-id="32e6d-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="32e6d-138">시스템 인증을 사용하는 앱은 지원되지 않습니다. 따라서 이를 최신 버전으로 바꾸는 것이 고려해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="32e6d-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing them with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="32e6d-139">인증을 사용하는 네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="32e6d-139">Network shares that use authentication</span></span>

<span data-ttu-id="32e6d-140">장치가 UNC 경로를 사용하여 인터넷 공유에 액세스할 수 있는 경우 추가 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="32e6d-141">프린터</span><span class="sxs-lookup"><span data-stu-id="32e6d-141">Printers</span></span>

<span data-ttu-id="32e6d-142">하이브리드 클라우드 인쇄를 구성하지 않은 경우 Microsoft Managed Desktop 장치는 사용자가 하이브리드 클라우드 인쇄를 구성하지 않은 경우, 사용자의 On-프레미스 Active Directory에 게시된 프린터에 연결할 [수 없습니다.](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)</span><span class="sxs-lookup"><span data-stu-id="32e6d-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="32e6d-143">클라우드 전용 환경에서는 프린터를 자동으로 검색할 수 없는 반면, 디바이스에서 프린터가 On-premises 도메인 컨트롤러에 액세스할 수 있는 한 사용자는 프린터 경로 또는 프린터 큐 경로를 사용하여 프레미스 프린터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6d-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
