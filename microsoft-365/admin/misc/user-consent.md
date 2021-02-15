---
title: Microsoft 365에서 앱에 대한 사용자 동의 관리
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
description: 앱에 대한 사용자 동의 및 타사 앱이 사용자의 Microsoft 365 정보에 액세스할 수 있도록 앱을 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999586"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="84783-103">Microsoft 365에서 앱에 대한 사용자 동의 관리</span><span class="sxs-lookup"><span data-stu-id="84783-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="84783-104">이 설정은 사용자가 로그인 및 데이터 액세스 요청에 OpenID Connect 및 OAuth 2.0을 사용하는 앱에 동의할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="84783-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="84783-105">앱은 사용자 조직 내에서 만들 수도, 다른 Office 365 조직이나 타사에서 앱을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84783-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="84783-106">이 설정을 켜면 해당 앱은 사용자에게 조직의 데이터에 액세스할 수 있는 권한을 요청하며 사용자는 이를 허용할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84783-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="84783-107">이 설정을 끄면 사용자가 앱을 사용하기 전에 관리자가 해당 앱에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84783-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="84783-108">이 경우 사용자가 차단된 앱을 사용하기 위한 관리자 승인 요청을 보낼 수 있도록 Azure Portal에서 관리자 동의 워크플로를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84783-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="84783-109">사용자는 자신이 소유한 앱이 자신의 Office 365 정보에 액세스하는 경우에만 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84783-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="84783-110">다른 사용자의 정보에 대한 액세스 권한은 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84783-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="84783-111">사용자 동의 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="84783-111">Turning user consent on or off</span></span>
<span data-ttu-id="84783-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="84783-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="84783-113">다음은 앱에 대한 사용자 동의를 설정하거나 해제하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="84783-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="84783-114">관리 센터에서 설정  Org 설정 서비스 페이지로 이동한 다음 앱에 대한 사용자 \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) **동의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="84783-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="84783-115">앱에 **대한 사용자** 동의 페이지에서 사용자 동의를 설정하거나 해제하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84783-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="84783-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="84783-116">More info</span></span>
<span data-ttu-id="84783-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="84783-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="84783-118">Azure Active Directory에서 동의 설정을 구성하는 방법에 대한 자세한 내용은 관리자 동의 워크플로 [구성을 읽어 읽습니다.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)</span><span class="sxs-lookup"><span data-stu-id="84783-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="84783-119">앱에 대한 사용자 동의 관리에 대한 자세한 내용은 응용 프로그램에 대한 동의 관리 및 동의 요청 [평가를 읽어야 합니다.](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)</span><span class="sxs-lookup"><span data-stu-id="84783-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>