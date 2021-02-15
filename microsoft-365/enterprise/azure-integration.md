---
title: Microsoft 365와 Azure 통합
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: 암호 동기화 또는 Single Sign-On을 원하는 경우 Azure AD와 Microsoft 365를 통합합니다.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384740"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="d92d0-103">Microsoft 365와 Azure 통합</span><span class="sxs-lookup"><span data-stu-id="d92d0-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="d92d0-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d92d0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d92d0-105">Microsoft 365는 Azure AD(Azure Active Directory)를 사용하여 장면 뒤에서 사용자 ID를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="d92d0-106">Microsoft 365 구독에는 무료 Azure AD 구독이 포함되어 있으므로 사용자 계정 및 암호를 동기화하거나 Single Sign-On을 설정할 수 있도록 AD DS(Active Directory 도메인 서비스)를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="d92d0-107">고급 기능을 구입하여 계정을 보다 효율적으로 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="d92d0-108">Azure AD는 Microsoft 365 구독을 확장하고 사용자 지정하는 데 사용할 수 있는 통합 앱 관리와 같은 다른 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="d92d0-109">Microsoft 365 관리 센터에서 Azure AD 배포 관리자를 사용하여 안내 설치 및 구성 환경을 사용할 수 있습니다(Microsoft 365에 로그인해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="d92d0-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="d92d0-110">Azure AD Connect 어드바이저</span><span class="sxs-lookup"><span data-stu-id="d92d0-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="d92d0-111">AD FS 배포 고문</span><span class="sxs-lookup"><span data-stu-id="d92d0-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="d92d0-112">Azure AD 설정 가이드</span><span class="sxs-lookup"><span data-stu-id="d92d0-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="d92d0-113">Azure AD 버전 및 Microsoft 365 ID 관리</span><span class="sxs-lookup"><span data-stu-id="d92d0-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="d92d0-114">Microsoft 365에 대한 유료 구독이 있는 경우 무료 Azure AD 구독도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="d92d0-115">Azure AD를 사용하여 사용자 및 그룹 계정을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="d92d0-116">이 구독을 활성화하려면 일회성 등록을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="d92d0-117">이후에 Microsoft 365 관리 센터에서 Azure AD에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="d92d0-118">무료 Azure AD 구독을 등록하는 지침은 무료 Azure AD 구독을 [참조하세요.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d92d0-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="d92d0-119">등록하기 위해 직접 이동하지 azure.microsoft.com Microsoft 365를 통해 무료 Azure AD 구독과는 별개인 Microsoft Azure에 대한 평가판 또는 유료 구독이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="d92d0-120">무료 구독을 사용하면 모든 서비스 응용 프로그램(예: Salesforce, DropBox 등)과 동기화하고, Single Sign-On을 설정하고, 여러 소프트웨어와 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="d92d0-121">향상된 AD DS 기능, 양방향 동기화 및 기타 관리 기능을 원하는 경우 무료 구독을 유료 프리미엄 구독으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="d92d0-122">자세한 내용은 Azure [Active Directory 에디션을 참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="d92d0-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="d92d0-123">Microsoft 365 및 Azure AD에 대한 자세한 내용은 [Microsoft 365 ID 모델을 참조하세요.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="d92d0-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="d92d0-124">Microsoft 365 테넌트의 기능 확장</span><span class="sxs-lookup"><span data-stu-id="d92d0-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="d92d0-125">**기능**</span><span class="sxs-lookup"><span data-stu-id="d92d0-125">**Feature**</span></span>|<span data-ttu-id="d92d0-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="d92d0-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d92d0-127">통합 앱</span><span class="sxs-lookup"><span data-stu-id="d92d0-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="d92d0-128">메일, 일정, 연락처, 사용자, 그룹, 파일 및 폴더와 같은 Microsoft 365 데이터에 대한 액세스 권한을 개별 앱에 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="d92d0-129">또한 전역 관리자 수준에서 이러한 앱을 승인하고 Azure AD에 앱을 등록하여 전체 회사에서 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="d92d0-130">Formore 정보는 [Microsoft 365](integrated-apps-and-azure-ads.md)관리자를 위한 통합 앱 및 Azure AD를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d92d0-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="d92d0-131">Single [Sign-On도 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=698604)</span><span class="sxs-lookup"><span data-stu-id="d92d0-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="d92d0-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="d92d0-132">PowerApps</span></span>  <br/> | <span data-ttu-id="d92d0-133">Power Apps는 SharePoint 목록 및 기타 데이터 앱과 같은 기존 데이터 원본에 연결할 수 있는 모바일 장치용 포커스가 있는 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="d92d0-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="d92d0-134">자세한 [내용은 SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 및 [PowerApps](https://powerapps.microsoft.com/) 페이지에서 목록에 대한 PowerApp 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d92d0-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d92d0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d92d0-135">See also</span></span>

[<span data-ttu-id="d92d0-136">Microsoft 365 Enterprise 개요</span><span class="sxs-lookup"><span data-stu-id="d92d0-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
