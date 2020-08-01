---
title: 관리 포털 액세스
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530226"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="1d1c1-103">관리 포털 액세스</span><span class="sxs-lookup"><span data-stu-id="1d1c1-103">Access the admin portal</span></span>

<span data-ttu-id="1d1c1-104">Microsoft Managed Desktop service에 대 한 게이트웨이는 Microsoft [Azure portal](https://portal.azure.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="1d1c1-105">Azure portal 환경을 사용 하 고 사용자 지정 하는 방법에 대 한 자세한 내용은 [azure portal 설명서](https://docs.microsoft.com/azure/azure-portal/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> <span data-ttu-id="1d1c1-106">지금 미리 보기에서 사용할 수 있음 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)에서 Microsoft Managed Desktop도 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-106">Available in preview now, you can also find Microsoft Managed Desktop in the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="1d1c1-107">장치 관리에 대 한이 포털의 기능에 익숙하지 않은 경우 [Microsoft Endpoint Manager 설명서](https://docs.microsoft.com/mem/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-107">If you are unfamiliar with the capabilities of this portal for device management see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

<span data-ttu-id="1d1c1-108">관리 계정에는 Microsoft Managed Desktop Admin 포털에 액세스 하기 위한 특정 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-108">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="1d1c1-109">RBAC (역할 기반 액세스 제어)를 사용 하 여 조직 내에서 이러한 기능에 대 한 관리자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-109">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="1d1c1-110">Azure Active Directory 역할에 대 한 자세한 내용은 [Azure Active directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-110">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="1d1c1-111">관리자 사용자 계정에 다음 역할을 할당 하 여 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-111">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="1d1c1-112">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="1d1c1-112">Azure AD role</span></span>  |<span data-ttu-id="1d1c1-113">Microsoft Managed Desktop 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1d1c1-113">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="1d1c1-114">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="1d1c1-114">Global Administrator</span></span>     | <span data-ttu-id="1d1c1-115">이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 및 쓰기 권한이** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-115">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="1d1c1-116">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="1d1c1-116">Global Reader</span></span>     | <span data-ttu-id="1d1c1-117">이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 전용 권한이** 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-117">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="1d1c1-118">Intune 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="1d1c1-118">Intune Service Administrator</span></span>     |  <span data-ttu-id="1d1c1-119">이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 및 쓰기 권한이** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="1d1c1-120">서비스 지원 관리자</span><span class="sxs-lookup"><span data-stu-id="1d1c1-120">Service Support Administrator</span></span>     | <span data-ttu-id="1d1c1-121">이 역할을 가진 관리자에 게는 Microsoft Managed Desktop Admin 포털의 모든 기능에 대 한 **읽기 및 쓰기 권한이** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-121">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="1d1c1-122">전역 관리자 역할에만 Microsoft Managed Desktop에서 조직을 *등록* 하는 데 필요한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-122">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1d1c1-123">Azure Active Directory 역할은 다양 한 Microsoft 서비스에서 사용자 계정 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-123">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="1d1c1-124">Microsoft Managed Desktop을 사용한 등록을 완료 한 후에는 항상 다른 작업을 수행 하는 데 필요한 *최소* 권한으로 역할을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-124">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="1d1c1-125">관리자에 게 역할 할당</span><span class="sxs-lookup"><span data-stu-id="1d1c1-125">Assigning roles to administrators</span></span>

<span data-ttu-id="1d1c1-126">Azure Active Directory 역할을 할당 하는 데 도움이 필요한 경우 [Azure Active directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1c1-126">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
