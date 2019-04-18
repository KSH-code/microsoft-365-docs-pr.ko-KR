---
title: Microsoft Managed Desktop에 대 한 온-프레미스 리소스 액세스 준비
description: Azure AD가 온-프레미스 AD와 통신 하 여 인증을 제공할 수 있도록 하기 위한 중요 한 단계
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: db52a11eb192a28dbec827c565e36ad4a81d8e3f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901212"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="6f2a1-104">Microsoft Managed Desktop에 대 한 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="6f2a1-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="6f2a1-105">Microsoft Managed Desktop에서 장치는 azure Active Directory (azure AD)에 자동으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6f2a1-106">즉, 온-프레미스 active directory를 사용 하는 경우 Azure AD에 연결 된 장치가 온-프레미스 active directory와 통신할 수 있는지 몇 가지 사항을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="6f2a1-107">*하이브리드* Azure AD 조인은 Microsoft Managed Desktop에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6f2a1-108">사용자는 Azure Active Directory를 사용 하 여 sso (Single sign-on)를 활용할 수 있는데,이는 일반적으로 리소스를 사용할 때마다 자격 증명을 제공 하지 않아도 된다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="6f2a1-109">azure Active Directory에 가입 하는 방법에 대 한 자세한 내용은 [방법: azure AD join 구현 계획](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="6f2a1-110">azure ad에 연결 된 장치에 대 한 sso (Single sign-on)에 대 한 자세한 내용은 [azure ad에 가입 된 장치에서 sso에서 온-프레미스 리소스의 작동 방식을](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="6f2a1-111">이 항목에서는 로컬 Active Directory 연결에 의존 하는 앱 및 기타 리소스가 Microsoft Managed Desktop에서 원활 하 게 작동 하도록 하기 위해 확인 해야 하는 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-111">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="6f2a1-112">온-프레미스 리소스에 대 한 Single sign-on</span><span class="sxs-lookup"><span data-stu-id="6f2a1-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="6f2a1-113">Microsoft Managed Desktop 장치에서 UPN 및 암호를 사용 하 여 sso (Single sign-on)를 기본적으로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="6f2a1-114">그러나 사용자는 비즈니스용 Windows Hello를 사용할 수 있으며,이 경우 몇 가지 추가 설정 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="6f2a1-115">UPN 및 암호를 사용 하 여 Single sign-on</span><span class="sxs-lookup"><span data-stu-id="6f2a1-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="6f2a1-116">대부분의 조직에서는 사용자가 SSO를 사용 하 여 Microsoft Managed Desktop 장치에서 UPN 및 암호를 통해 인증을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="6f2a1-117">그러나이 작업을 제대로 수행 하려면 다음을 두 번 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-117">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="6f2a1-118">Azure AD Connect가 설정 되었으며 Windows server 2008 R2 이상 버전을 실행 하는 온-프레미스 Active Directory 서버를 사용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="6f2a1-119">azure ad Connect가 지원 되는 버전을 실행 하 고 있으며 이러한 세 가지 특성을 Azure ad와 동기화 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="6f2a1-120">온-프레미스 Active Directory의 DNS 도메인 이름 (최종 사용자가 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="6f2a1-120">DNS domain name of the on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="6f2a1-121">온-프레미스 Active Directory의 NetBIOS (최종 사용자가 있는 위치)</span><span class="sxs-lookup"><span data-stu-id="6f2a1-121">NetBIOS of your on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="6f2a1-122">SAM 사용자의 계정 이름</span><span class="sxs-lookup"><span data-stu-id="6f2a1-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="6f2a1-123">비즈니스용 Windows Hello를 사용 하 여 Single sign-on</span><span class="sxs-lookup"><span data-stu-id="6f2a1-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="6f2a1-124">또한 Microsoft Managed Desktop 장치는 비즈니스용 Windows Hello를 채택 하 여 빠르고, 암호를 덜 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="6f2a1-125">사용자가 각 UPN과 암호를 제공 하지 않아도 비즈니스용 Windows hello가 작동 하는지 확인 하려면 [비즈니스용 windows hello를 사용 하 여 온-프레미스 Single sign-on에 대해 Azure AD 조인 장치를 구성](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) 하 여 요구 사항을 확인 한 다음 여기에 나와 있는 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="6f2a1-126">인증을 사용 하는 앱 및 리소스</span><span class="sxs-lookup"><span data-stu-id="6f2a1-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="6f2a1-127">azure Active Directory에서 작동 하도록 앱을 설정 하는 방법에 대 한 전체 지침은 azure content set의 [응용 프로그램 및 리소스에 대 한 고려 사항 이해](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-127">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="6f2a1-128">요약:</span><span class="sxs-lookup"><span data-stu-id="6f2a1-128">In summary:</span></span>


- <span data-ttu-id="6f2a1-129">Azure AD 앱 갤러리에 추가 된 것과 같은 **클라우드 기반 앱**을 사용 하는 경우에는 Microsoft Managed Desktop에서 더 이상 준비할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="6f2a1-130">그러나 WAM (Web Account Manager)를 사용 하지 않는 모든 Win32 앱에서 사용자에 게 인증을 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="6f2a1-131">**온-프레미스에 호스트**되는 앱의 경우 브라우저의 신뢰할 수 있는 사이트 목록에 해당 앱을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="6f2a1-132">이렇게 하면 사용자가 자격 증명을 입력 하 라는 메시지가 표시 되지 않고 Windows 인증이 원활 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-132">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="6f2a1-133">이 작업을 수행 하려면 [구성 가능한 설정 참조](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)에서 [신뢰할 수 있는 사이트](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-133">To do this, refer to [Trusted sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in the [Configurable settings reference](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).</span></span>

- <span data-ttu-id="6f2a1-134">Active Directory 페더레이션 서비스를 사용 하는 경우에는 [AD FS에 대 한 single sign-on 확인 및 관리](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))의 단계를 사용 하 여 SSO가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="6f2a1-135">온 **-프레미스 및 오래 된 프로토콜을 사용**하는 앱의 경우에는 장치에서 인증을 위해 온-프레미스 도메인 컨트롤러에 액세스할 수 있는 한 추가 설치가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="6f2a1-136">그러나 이러한 응용 프로그램에 대 한 보안 액세스를 제공 하려면 Azure AD 응용 프로그램 프록시를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="6f2a1-137">자세한 내용은 [Azure Active Directory의 응용 프로그램 프록시를 통해 온-프레미스 응용 프로그램에 대 한 원격 액세스](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="6f2a1-138">온-프레미스를 실행 하 **고 컴퓨터 인증을 사용** 하는 앱은 지원 되지 않으므로 최신 버전으로 교체 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="6f2a1-139">인증을 사용 하는 네트워크 공유</span><span class="sxs-lookup"><span data-stu-id="6f2a1-139">Network shares that use authentication</span></span>

<span data-ttu-id="6f2a1-140">장치에서 UNC 경로를 사용 하 여 온-프레미스 도메인 컨트롤러에 액세스할 수 있는 한 사용자는 네트워크 공유에 액세스 하는 데 추가 설정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="6f2a1-141">프린터</span><span class="sxs-lookup"><span data-stu-id="6f2a1-141">Printers</span></span>

<span data-ttu-id="6f2a1-142">Microsoft Managed Desktop devices는 [하이브리드 클라우드 인쇄](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 구성 하지 않은 경우 온-프레미스 Active Directory에 게시 된 프린터에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="6f2a1-143">클라우드 전용 환경에서는 프린터를 자동으로 검색할 수 없지만 장치에 온-프레미스 도메인 컨트롤러에 대 한 액세스 권한이 있으면 사용자가 프린터 경로 또는 프린터 큐 경로를 사용 하 여 온-프레미스 프린터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2a1-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
