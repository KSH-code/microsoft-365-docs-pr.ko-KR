---
title: 사용자의 앱 시작 관리자에 앱 고정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: 전역 관리자는 최대 3 개의 앱을 사용자의 앱 시작 관리자에 게 고정할 수 있습니다.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310878"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="b1486-103">사용자의 앱 시작 관리자에 앱 고정</span><span class="sxs-lookup"><span data-stu-id="b1486-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="b1486-104">Azure Active Directory 포털의 컨트롤을 사용 하 여 Office.com에 최대 3 개의 앱을 고정 하 고 조직의 모든 사용자에 대 한 앱 시작 관리자를 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="b1486-105">응용 프로그램 그룹을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-105">You can also organize groups of applications.</span></span> <span data-ttu-id="b1486-106">나중에 추가 하는 앱은 사용자가 언제 든 지 고정이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="b1486-107">사용자에 대해 앱을 고정 하려면 클라우드 응용 프로그램 관리자 이거나, Azure Active Directory의 응용 프로그램 관리자 이거나, Office 365의 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="b1486-108">관리자 역할에 대 한 자세한 내용은 [Microsoft 365의](../add-users/about-admin-roles.md) [Azure Active Directory 및 관리자 역할에서 관리자 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1486-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="b1486-109">앱 시작 관리자 및 Office.com에 대 한 자세한 내용은 [모임 시작 관리자](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 및 [업데이트를 Office.com 및-Office 365 앱 시작 관리자](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 블로그 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1486-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="b1486-110">Azure Active Directory 포털을 사용 하 여 앱 고정</span><span class="sxs-lookup"><span data-stu-id="b1486-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="b1486-111">Microsoft 365 관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="b1486-112">왼쪽 탐색 창에서 **모두 표시**를 선택 하 고 **관리 센터**에서 **Azure Active Directory**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b1486-113">**Azure Active Directory**에서 **엔터프라이즈 응용 프로그램**  >  **사용자 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="b1486-114">**Office 365 설정** 섹션에서 **응용 프로그램 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="b1486-115">사용자의 앱 시작 관리자에 게 고정할 응용 프로그램을 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 앱 고정 설정":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="b1486-117">사용자 지정 앱 고정</span><span class="sxs-lookup"><span data-stu-id="b1486-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="b1486-118">사용자 인터페이스는이 기능을 사용 하기 위해 추가 Azure AD 라이선스를 구입 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="b1486-119">자세한 내용은 [Azure Active Directory 가격 책정](https://azure.microsoft.com/pricing/details/active-directory/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1486-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="b1486-120">**Azure Active Directory**의 **Enterprise applications**  >  **모든 응용 프로그램** 페이지 위쪽에서 엔터프라이즈 응용 프로그램**새 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="b1486-121">**응용 프로그램 추가** 페이지에서 **비 갤러리 응용 프로그램** 을 선택 하거나 미리 보기 버전의 Azure Active Directory에 있는 경우 **고유한 응용 프로그램을 만듭니다** .</span><span class="sxs-lookup"><span data-stu-id="b1486-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="b1486-122">응용 프로그램의 이름을 입력 하 고 사용자 **및 그룹** 탭에서 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="b1486-123">**속성** 탭을 사용 하 여 앱에 대 한 아이콘을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="b1486-124">앱에 URL을 할당 하려면 **Single sign-on** 탭에서 **연결** 됨을 선택 하 고 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="b1486-125">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="b1486-126">응용 프로그램 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="b1486-126">Create application collections</span></span>

<span data-ttu-id="b1486-127">조직의 사용자에 대 한 응용 프로그램 모음을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1486-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="b1486-128">자세한 내용은 [Azure portal의 내 앱 포털에서 모음 만들기](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1486-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>