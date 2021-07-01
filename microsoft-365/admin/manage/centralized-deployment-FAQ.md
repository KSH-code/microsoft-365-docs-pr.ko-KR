---
title: 중앙 집중식 배포 FAQ
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 중앙 집중식 배포에 대한 질문과 대답을 검토하여 Microsoft 365 관리 센터.
ms.openlocfilehash: 0da9ec9595fd433abe1e2e2ae3f2e3a0c6b3b9b5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228009"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="36417-103">중앙 집중식 배포 FAQ</span><span class="sxs-lookup"><span data-stu-id="36417-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="36417-104">조직이 이 문서에 설명된 중앙 집중식 배포 사용에 대한 모든 요구 사항을 충족하는 경우 Office 365 관리자는 조직 내의 사용자 및 그룹에 Office 추가 기능(Word, Excel, PowerPoint 및 Outlook)을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="36417-105">조직이 중앙 집중식 배포에 대해 설정되어 있는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="36417-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="36417-106">추가 기능을 중앙 집중식으로 배포하려면 사용자가 조직 엔터프라이즈용 Microsoft 365 앱 자격 증명을 사용하여 Office 로그인된 사서함을 Exchange Online 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36417-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="36417-107">구독 Azure Active Directory 디렉터리는 해당 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36417-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="36417-108">중앙 집중식 배포는 온라인 사서함에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="36417-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="36417-109">사서함에 대한 배포를 지원하지 Exchange 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="36417-110">중앙 집중식 배포 호환성 검사를 [사용하여](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)구독이   적합한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="36417-111">중앙 집중식 배포를 통해 추가 기능 사용자 할당을 대상으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="36417-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="36417-112">중앙 집중식 배포는 테넌트의 개별 사용자, 그룹 및 모든 사용자에게 할당을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="36417-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="36417-113">중앙 집중식 배포는 상위 그룹이 없는 최상위 그룹 또는 그룹의 사용자에 사용할 수 있지만 상위 그룹이 있는 중첩된 그룹 또는 그룹의 사용자에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="36417-114">중앙 집중식 배포는 Azure Active Directory 그룹, 메일 그룹 및 보안 Office 365 그룹과 같은 대부분의 그룹 그룹에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36417-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="36417-115">보다 쉽게 관리하기 위해 개별 사용자 할당 대신 그룹 할당을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="36417-116">자세한 내용은 사용자 및 그룹 [할당을 참조합니다.](./centralized-deployment-of-add-ins.md#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="36417-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="36417-117">추가 기능을 모든 사용자에게 표시하는 데 얼마나 걸릴까요?</span><span class="sxs-lookup"><span data-stu-id="36417-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="36417-118">추가 기능을 모든 사용자에게 표시하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="36417-119">추가 기능 업데이트, 켜기 또는 끄기 변경 또는 추가 기능 제거에 동일한 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="36417-120">관리자는 조직에 대한 추가 기능의 사용자 액세스를 어떻게 관리하나요?</span><span class="sxs-lookup"><span data-stu-id="36417-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="36417-121">사용자, 그룹 또는 전체 조직에 추가 기능을 쉽게 배포할 수 있도록 관리자는 중앙 집중식 배포를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="36417-122">사용자 액세스 관리에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36417-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="36417-123">모든 클라이언트에서 Office Store를 해제하여 추가 기능 다운로드 방지(Outlook)</span><span class="sxs-lookup"><span data-stu-id="36417-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="36417-124">관리자 및 설치 하 고 Outlook 용 추가 기능을 관리할 수 있는 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="36417-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="36417-125">중앙 집중식 배포는 관리자에게 추가 기능의 배포 방법을 선택할 Outlook 제공합니까?</span><span class="sxs-lookup"><span data-stu-id="36417-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="36417-126">예.</span><span class="sxs-lookup"><span data-stu-id="36417-126">Yes.</span></span> <span data-ttu-id="36417-127">중앙 집중식 배포는 관리자에게 추가 기능 배포 중에 추가 Outlook 세 가지 배포 방법 중 하나를 선택할 수 있는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36417-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="36417-128">**고정(기본값)**   추가 기능은 할당된 사용자에게 자동으로 배포되며 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="36417-129">**사용 가능** 사용자는 관리 관리 에서 추가 기능 Outlook 홈을 선택하여 > 추가 기능을 > 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="36417-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="36417-130">**선택 사항** 추가 기능을 할당된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="36417-131">관리자가 LOB(LOB) 추가 기능을 업데이트할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="36417-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="36417-132">예.</span><span class="sxs-lookup"><span data-stu-id="36417-132">Yes.</span></span> <span data-ttu-id="36417-133">관리자는 새 매니페스트 파일을 업로드하여 관리자가 배포한 LOB 추가 기능의 메타데이터 변경을 지원할 수 있습니다. 추가 기능에서 다음에 응용 프로그램을 시작할 Office 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="36417-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="36417-134">웹 응용 프로그램은 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="36417-135">자세한 내용은 업무 추가 [기능을 참조하세요.](./manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="36417-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="36417-136">관리자가 추가 기능을 해제할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="36417-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="36417-137">예.</span><span class="sxs-lookup"><span data-stu-id="36417-137">Yes.</span></span> <span data-ttu-id="36417-138">관리자는 Microsoft 관리 센터에서 모든 사용자에 대해 배포하는 추가 기능을 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="36417-139">자세한 내용은 추가 [기능 상태 를 참조하세요.](./manage-addins-in-the-admin-center.md#add-in-states)</span><span class="sxs-lookup"><span data-stu-id="36417-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="36417-140">관리자가 추가 기능을 삭제하거나 제거할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="36417-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="36417-141">예.</span><span class="sxs-lookup"><span data-stu-id="36417-141">Yes.</span></span> <span data-ttu-id="36417-142">관리자는 Microsoft 관리 센터에서 모든 사용자에 대해 배포한 추가 기능을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="36417-143">자세한 내용은 추가 기능 [삭제를 참조하세요.](./manage-addins-in-the-admin-center.md#delete-an-add-in)</span><span class="sxs-lookup"><span data-stu-id="36417-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="36417-144">관리자가 중앙 집중식 배포를 사용하여 Office 스토어에서 유료 추가 기능을 배포할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="36417-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="36417-145">아니요.</span><span class="sxs-lookup"><span data-stu-id="36417-145">No.</span></span> <span data-ttu-id="36417-146">현재는 중앙 집중식 배포를 사용하여 Office 스토어에서 유료 추가 기능을 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="36417-147">매니페스트 파일 또는 URL을 요청하기 위해 유료 추가 기능을 위해 ISV 개발자에게 요청하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="36417-148">그런 다음 테넌트 관리자는 중앙 집중식 배포를 사용하여 추가 기능을 LOB 추가 기능으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36417-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="36417-149">조직의 추가 기능을 관리하려면 어떤 관리자 역할이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="36417-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="36417-150">전역 관리자는 추가 기능 관리 수명 주기에 대한 모든 액세스 권한을 가진 권장 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="36417-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="36417-151">비즈니스용 구독을 구매한 Microsoft 365 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="36417-151">If you're the person who purchased your Microsoft 365 Business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="36417-152">구독에는 조직의 다른 사용자에게 할당할 수 있는 관리자 역할 집합이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="36417-152">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="36417-153">각 관리자 역할은 일반적인 비즈니스 기능에 매핑되어 있으며 조직의 사용자에게 조직 내 특정 작업을 수행할 수 있는 권한을 Microsoft 365 관리 센터.</span><span class="sxs-lookup"><span data-stu-id="36417-153">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="36417-154">자세한 내용은 관리자 역할 [할당을 참조하세요.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="36417-154">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md).</span></span> 
