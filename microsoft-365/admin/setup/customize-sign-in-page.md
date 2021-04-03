---
title: 로그인 페이지에 회사 브랜드 추가
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a1229cdb-ce19-4da5-90c7-2b9b146aef0a
description: Azure Active Directory를 사용하여 Microsoft 365 로그인 페이지를 사용자 지정합니다. 로그인 페이지에 그림, 로고 및 텍스트를 추가할 수 있습니다.
ms.openlocfilehash: 9947d57e4bf35ef0a3409db58f2c663959c2dd49
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579125"
---
# <a name="add-your-company-branding-to-the-sign-in-page"></a><span data-ttu-id="c8e37-104">로그인 페이지에 회사 브랜드 추가</span><span class="sxs-lookup"><span data-stu-id="c8e37-104">Add your company branding to the Sign In page</span></span>

 <span data-ttu-id="c8e37-105">이제 Microsoft 365 구독에 포함된 Azure AD(Active Directory) 구독을 사용하여 사용자에게 표시하는 로그인 페이지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-105">You can now use the Azure Active Directory (AD) subscription that is included with your Microsoft 365 subscription to customize the sign-in page your users see.</span></span> 
  
## <a name="add-company-branding-to-your-sign-in-page-and-access-panel-pages"></a><span data-ttu-id="c8e37-106">로그인 페이지 및 액세스 패널 페이지에 회사 브랜드 추가</span><span class="sxs-lookup"><span data-stu-id="c8e37-106">Add company branding to your sign in page and Access Panel pages</span></span>

<span data-ttu-id="c8e37-107">비즈니스용 Microsoft 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite 또는 기타 Microsoft 서비스를 유료로 구독하는 경우 Azure Active Directory를 무료로 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-107">If you have a paid subscription to Microsoft 365 for business, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Azure Active Directory.</span></span> <span data-ttu-id="c8e37-108">Azure Active Directory를 사용하여 사용자 및 그룹 계정을 만들고 관리하고 페이지에 회사 브랜드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-108">You can use Azure Active Directory to create and manage user and group accounts, and add company branding to your pages.</span></span> <span data-ttu-id="c8e37-109">이 구독을 활성화하고 Microsoft Azure 관리 포털에 액세스하려면 일회성 등록 프로세스를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-109">To activate this subscription and access the Microsoft Azure Management Portal, you have to complete a one-time registration process.</span></span> <span data-ttu-id="c8e37-110">이후에 Azure Active Directory를 사용하는 Microsoft 서비스에서 Azure Active Directory에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-110">Afterward, you can access Azure Active Directory from your Microsoft service that uses it.</span></span> <span data-ttu-id="c8e37-111">Microsoft 365 구독을 등록하는 방법에 대한 지침은 무료 [Azure Active Directory](../../compliance/use-your-free-azure-ad-subscription-in-office-365.md)구독 등록을 참조하고 일반 관리 지침은 [Azure에서 Microsoft 365](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) 구독 디렉터리 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8e37-111">For instructions on how to register your Microsoft 365 subscription see [Register your free Azure Active Directory subscription](../../compliance/use-your-free-azure-ad-subscription-in-office-365.md), and see [Manage the directory for your Microsoft 365 subscription in Azure](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) for general management instructions.</span></span> 
  
<span data-ttu-id="c8e37-112">다음 그림에서는 Azure에서 수정할 수 있는 로그인 페이지의 일부를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-112">The following figure shows which parts of the sign-in page can be modified in Azure.</span></span>
  
![사용자 지정할 수 있는 로그인 페이지의 영역입니다.](../../media/screenshotbranding.png)
  
1. <span data-ttu-id="c8e37-114">큰 그림 및/또는 배경색</span><span class="sxs-lookup"><span data-stu-id="c8e37-114">The large illustration and/or its background color</span></span>
    
2. <span data-ttu-id="c8e37-115">배너 로고</span><span class="sxs-lookup"><span data-stu-id="c8e37-115">The banner logo</span></span>
    
3. <span data-ttu-id="c8e37-116">이 영역에 텍스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-116">You can also add text to this area</span></span>
    
<span data-ttu-id="c8e37-117">로그인 페이지 외에도 Azure에서 액세스 패널 페이지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e37-117">In addition to the sign-in page, you can customize the Access Panel page in Azure.</span></span>
  
<span data-ttu-id="c8e37-118">브랜드를 추가할 준비가 되면 Azure 콘텐츠 집합의 사용자 지정 옵션인 로그인 및 액세스 패널 페이지에 회사 브랜드 [추가를 탐색합니다.](/azure/active-directory/fundamentals/customize-branding)</span><span class="sxs-lookup"><span data-stu-id="c8e37-118">If you are ready to add branding, explore the customization options in the Azure content set: [Add company branding to your Sign-in and Access Panel pages](/azure/active-directory/fundamentals/customize-branding).</span></span>