---
title: 로그인 페이지에 회사 브랜딩 추가
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
ms.assetid: a1229cdb-ce19-4da5-90c7-2b9b146aef0a
description: Azure Active Directory를 사용 하 여 Microsoft 365 로그인 페이지를 사용자 지정 합니다. 로그인 페이지에 그림, 로고 및 텍스트를 추가할 수 있습니다.
ms.openlocfilehash: daf5f9007a297615d04051d3364895053572343a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627633"
---
# <a name="add-your-company-branding-to-the-sign-in-page"></a><span data-ttu-id="2b455-104">로그인 페이지에 회사 브랜딩 추가</span><span class="sxs-lookup"><span data-stu-id="2b455-104">Add your company branding to the Sign In page</span></span>

 <span data-ttu-id="2b455-105">이제 Microsoft 365 구독에 포함 된 Azure AD (Active Directory) 구독을 사용 하 여 사용자에 게 표시 되는 로그인 페이지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-105">You can now use the Azure Active Directory (AD) subscription that is included with your Microsoft 365 subscription to customize the sign-in page your users see.</span></span> 
  
## <a name="add-company-branding-to-your-sign-in-page-and-access-panel-pages"></a><span data-ttu-id="2b455-106">로그인 페이지 및 액세스 패널 페이지에 회사 브랜딩 추가</span><span class="sxs-lookup"><span data-stu-id="2b455-106">Add company branding to your sign in page and Access Panel pages</span></span>

<span data-ttu-id="2b455-107">Microsoft 365 for business, Microsoft Dynamics CRM Online, Enterprise Mobility Suite 또는 기타 Microsoft 서비스에 대 한 유료 구독을 사용 하는 경우 Azure Active Directory에 대 한 무료 구독을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-107">If you have a paid subscription to Microsoft 365 for business, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Azure Active Directory.</span></span> <span data-ttu-id="2b455-108">Azure Active Directory를 사용 하 여 사용자 및 그룹 계정을 만들고 관리 하 고 회사 브랜딩을 페이지에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-108">You can use Azure Active Directory to create and manage user and group accounts, and add company branding to your pages.</span></span> <span data-ttu-id="2b455-109">이 구독을 활성화 하 고 Microsoft Azure 관리 포털에 액세스 하려면 일회성 등록 프로세스를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-109">To activate this subscription and access the Microsoft Azure Management Portal, you have to complete a one-time registration process.</span></span> <span data-ttu-id="2b455-110">나중에이를 사용 하는 Microsoft 서비스에서 Azure Active Directory에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-110">Afterward, you can access Azure Active Directory from your Microsoft service that uses it.</span></span> <span data-ttu-id="2b455-111">Microsoft 365 구독을 등록 하는 방법에 대 한 자세한 내용은 [무료 Azure Active Directory 구독 등록](https://go.microsoft.com/fwlink/p/?LinkID=527966)및 일반 관리 지침에 대 한 [azure에서 microsoft 365 구독에 대 한 디렉터리 관리](https://go.microsoft.com/fwlink/p/?LinkId=620076) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b455-111">For instructions on how to register your Microsoft 365 subscription see [Register your free Azure Active Directory subscription](https://go.microsoft.com/fwlink/p/?LinkID=527966), and see [Manage the directory for your Microsoft 365 subscription in Azure](https://go.microsoft.com/fwlink/p/?LinkId=620076) for general management instructions.</span></span> 
  
<span data-ttu-id="2b455-112">다음 그림에서는 Azure에서 로그인 페이지의 어떤 부분을 수정할 수 있는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-112">The following figure shows which parts of the sign-in page can be modified in Azure.</span></span>
  
![사용자 지정할 수 있는 로그인 페이지 영역입니다.](../../media/screenshotbranding.png)
  
1. <span data-ttu-id="2b455-114">큰 그림 및/또는 배경색</span><span class="sxs-lookup"><span data-stu-id="2b455-114">The large illustration and/or its background color</span></span>
    
2. <span data-ttu-id="2b455-115">배너 로고</span><span class="sxs-lookup"><span data-stu-id="2b455-115">The banner logo</span></span>
    
3. <span data-ttu-id="2b455-116">이 영역에 텍스트를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-116">You can also add text to this area</span></span>
    
<span data-ttu-id="2b455-117">로그인 페이지 외에도 Azure에서 액세스 패널 페이지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-117">In addition to the sign-in page, you can customize the Access Panel page in Azure.</span></span>
  
<span data-ttu-id="2b455-118">브랜딩을 추가할 준비가 되 면 Azure content set의 사용자 지정 옵션 ( [로그인 및 액세스 패널 페이지에 회사 브랜딩 추가)](https://go.microsoft.com/fwlink/p/?LinkId=620077)을 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b455-118">If you are ready to add branding, explore the customization options in the Azure content set: [Add company branding to your Sign-in and Access Panel pages](https://go.microsoft.com/fwlink/p/?LinkId=620077).</span></span>
