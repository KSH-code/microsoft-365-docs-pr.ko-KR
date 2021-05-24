---
title: 앱에서 앱에 대한 사용자 동의 Microsoft 365
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 앱에 대한 사용자 동의와 타사 앱이 사용자의 앱 정보에 액세스할 수 있도록 앱을 설정하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: b8f65b50e50b0e0b4d978388463bbd380ca60d4e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624504"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="07476-103">앱에서 앱에 대한 사용자 동의 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07476-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="07476-104">이 설정은 사용자가 로그인에 대해 OpenID 커넥트 및 OAuth 2.0을 사용하는 앱에 대해 해당 동의를 부여할 수 있는지 여부와 데이터에 대한 액세스 요청을 허용할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="07476-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="07476-105">앱은 조직 내에서 만들거나 다른 조직이나 타사에서 Office 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07476-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="07476-106">이 설정을 켜면 해당 앱은 사용자에게 조직의 데이터에 액세스할 수 있는 권한을 요청하며 사용자가 이를 허용할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07476-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="07476-107">이 설정을 끄면 관리자가 해당 앱에 동의해야 사용자가 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07476-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="07476-108">이 경우 사용자가 차단된 앱을 사용하기 위한 관리자 승인 요청을 보낼 수 있도록 Azure Portal에서 관리자 동의 워크플로를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="07476-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="07476-109">사용자는 자신이 소유한 앱이 자신의 Office 365 정보에 액세스하는 경우에만 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07476-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="07476-110">다른 사용자의 정보에 대한 액세스 권한은 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07476-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="07476-111">사용자 동의 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="07476-111">Turning user consent on or off</span></span>
<span data-ttu-id="07476-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="07476-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="07476-113">다음은 앱에 대한 사용자 동의를 설정하거나 해제하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="07476-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="07476-114">관리 센터에서 설정  설정 서비스 페이지로 이동한 다음 앱에 대한 사용자 \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) **동의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="07476-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="07476-115">앱에 대한 사용자 동의 **페이지에서** 사용자 동의를 설정하거나 해제하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07476-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="07476-116">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="07476-116">Related content</span></span> 
<span data-ttu-id="07476-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="07476-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="07476-118">[관리자 동의 워크플로](/azure/active-directory/manage-apps/configure-admin-consent-workflow) 구성(문서)</span><span class="sxs-lookup"><span data-stu-id="07476-118">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="07476-119">[응용 프로그램에 대한 동의 관리 및 동의](/azure/active-directory/manage-apps/manage-consent-requests) 요청 평가(문서)</span><span class="sxs-lookup"><span data-stu-id="07476-119">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>