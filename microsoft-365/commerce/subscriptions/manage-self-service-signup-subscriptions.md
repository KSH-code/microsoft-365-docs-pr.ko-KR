---
title: 셀프 서비스 등록 구독 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: 조직에 대 한 무료 셀프 서비스 등록 구독을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 056ae95f9f5067ea3fa86164b620c72c84e3aad4
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43154139"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="7e369-103">셀프 서비스 등록 구독 관리</span><span class="sxs-lookup"><span data-stu-id="7e369-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="7e369-104">셀프 서비스 등록 구독은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="7e369-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="7e369-105">조직의 사용자가 등록할 수 있는 제한 된 수의 무료 셀프 서비스 등록 구독이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="7e369-106">사용자는 자체적으로 셀프 서비스 등록 구독을 등록 하 고 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="7e369-107">이러한 구독은 **Products & services** 페이지에 나타나며, **무료로**표시 되며, "이 제품은 회사의 사용자가 사용 하 여 무료 구독을 활성화 했습니다." 라는 메모를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-107">These subscriptions appear on the **Products & services** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="7e369-108">사용자가 등록을 차단 하 고 사용자가 등록 한 무료 구독을 삭제 하 여 셀프 서비스 등록 구독을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="7e369-109">셀프 서비스 등록 및 사용 가능한 구독에 대 한 자세한 내용은 [조직에서 셀프 서비스 등록 사용](../../admin/misc/self-service-sign-up.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e369-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="7e369-110">이러한 구독은 셀프 서비스 구매 구독과 어떤 차이가 있나요?</span><span class="sxs-lookup"><span data-stu-id="7e369-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="7e369-111">셀프 서비스 등록 구독은 무료 이며 셀프 서비스 구매 구독 보다 더 큰 제품 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="7e369-112">사용자가 셀프 서비스 구매 구독을 등록 하는 경우이에 대 한 지불을 담당 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="7e369-113">또한 셀프 서비스 구매 구독은 전원 플랫폼 제품 (Power BI, Power Apps 및 파워 자동화)에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="7e369-114">자세한 내용은 [셀프 서비스 구매 FAQ](self-service-purchase-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e369-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="7e369-115">사용자의 등록 차단</span><span class="sxs-lookup"><span data-stu-id="7e369-115">Block users from signing up</span></span>

<span data-ttu-id="7e369-116">**AllowAdHocSubscriptions** 매개 변수와 함께 [**set-msolcompanysettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet을 사용 하 여 사용자가 셀프 서비스 등록 구독에 등록할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="7e369-117">자세한 내용은 [How to control services settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e369-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="7e369-118">셀프 서비스 등록 구독 삭제</span><span class="sxs-lookup"><span data-stu-id="7e369-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e369-119">셀프 서비스 등록 구독을 삭제 하면 모든 사용자가 해당 데이터 및 전자 메일에 액세스할 수 없도록 차단 되며 모든 데이터 및 전자 메일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="7e369-120">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품 & 서비스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
2. <span data-ttu-id="7e369-121">삭제 하려는 셀프 서비스 등록 구독을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="7e369-122">**& 작업 설정** 섹션에서 **구독 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="7e369-123">**구독 삭제** 창에서 확인란을 선택 하 고 **구독 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="7e369-124">디렉터리 삭제를 차단 하는 셀프 서비스 등록 구독을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="7e369-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="7e369-125">개별 사용자가 등록할 수 있는 셀프 서비스 등록 제품은 Azure AD 디렉터리에서 인증을 위한 게스트 사용자도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="7e369-126">데이터 손실을 방지 하기 위해 이러한 셀프 서비스 제품은 디렉터리 삭제를 중단 하 고 디렉터리가 완전히 삭제 될 때까지이를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e369-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="7e369-127">Azure AD 관리자만 삭제할 수 있습니다. 자세한 내용은 [Azure Active directory에서 디렉터리 삭제](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e369-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>