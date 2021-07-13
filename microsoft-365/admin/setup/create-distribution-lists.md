---
title: 메일 그룹 만들기
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b1ffe755-59e5-4369-826d-825f145a8400
ms.custom:
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
description: 각 받는 사람 이름을 입력하지 않고도 Microsoft 365 관리 센터 전자 메일을 보낼 수 있도록 메일 그룹 또는 목록을 만들 수 있습니다.
ms.openlocfilehash: 87b3f375f5e90ec7fc97332abb801d814bf4939b
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393574"
---
# <a name="create-distribution-groups-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d9f28-103">메일 그룹에서 Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="d9f28-103">Create distribution groups in the Microsoft 365 admin center</span></span>
  
<span data-ttu-id="d9f28-104">개별 받는 사람의 이름을 입력하지 않고도 사용자 그룹에 전자 메일을 보내려면 메일 그룹(메일 그룹)이 특정 토론 주체(예: "마케팅")나 자주 통신해야 하는 공통 작업을 공유하는 사용자가 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-104">Used when you want to send email to group of people without having to type each individual recipient's name, distribution groups (distribution lists) are organized by a particular discussion subject (such as "Marketing") or by users who share common work that requires them to communicate frequently.</span></span> <span data-ttu-id="d9f28-105">또한 전자 메일을 여러 전자 메일 주소로 자동으로 전달하는 방법도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-105">They also provide a way for you to automatically forward email to multiple email addresses.</span></span>

<span data-ttu-id="d9f28-106">메일 그룹을 메일 그룹이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-106">Distribution groups are sometimes called distribution lists.</span></span>
  
## <a name="create-a-distribution-group-list"></a><span data-ttu-id="d9f28-107">메일 그룹 만들기(목록)</span><span class="sxs-lookup"><span data-stu-id="d9f28-107">Create a distribution group (list)</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="d9f28-108"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="d9f28-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="d9f28-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.</span></span>

::: moniker-end

1. <span data-ttu-id="d9f28-111">앱 시작 관리자 아이콘 을 선택하고 **관리자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-111">Select the app launcher icon and choose **Admin**.</span></span>
    
    <span data-ttu-id="d9f28-112">찾고자 하는 앱을 찾을 수 없나요?</span><span class="sxs-lookup"><span data-stu-id="d9f28-112">Can't find the app you're looking for?</span></span> <span data-ttu-id="d9f28-113">앱 시작 앱에서 모든  앱을 선택하여 사용할 수 있는 앱의 사전순 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-113">From the app launcher, select **All apps** to see an alphabetical list of the apps available to you.</span></span> <span data-ttu-id="d9f28-114">거기에서 특정 앱을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f28-114">From there, you can search for a specific app.</span></span> 
    
2. <span data-ttu-id="d9f28-115">왼쪽 **탐색 창에서** 그룹을 선택한 다음 그룹 추가 \>  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9f28-115">Select **Groups** \> **Groups** in the left navigation pane, and then select **Add a group**.</span></span> 
      
3. <span data-ttu-id="d9f28-116">그룹 **유형 선택 필드에서** 배포를 **선택하고** 다음 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9f28-116">On the **Choose a group type** field, choose **Distribution**, and then choose **Next**.</span></span>
  
4. <span data-ttu-id="d9f28-117">새 그룹의 이름, 설명 및 전자 메일 별칭을 입력하고 조직 외부의 사람이 그룹에 전자 메일을 보낼 수 있도록 할지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9f28-117">Enter a name, description, and email alias for your new group, and choose whether you want people outside your organization to send email to the group.</span></span> 
    
5. <span data-ttu-id="d9f28-118">추가를 눌러 그룹을 만든 다음 그룹을 검토하고 닫기 를 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="d9f28-118">Press **Add** to create a group, and then review your group and choose **Close**.</span></span> 
    
6. <span data-ttu-id="d9f28-119">메일 그룹에 사용자를 추가하는 경우 메일 그룹에 사용자 또는 [연락처 추가를 참조하세요.](../email/add-user-or-contact-to-distribution-list.md)</span><span class="sxs-lookup"><span data-stu-id="d9f28-119">To add users to your distribution list, see [Add a user or contact to a distribution group](../email/add-user-or-contact-to-distribution-list.md).</span></span>
    
<span data-ttu-id="d9f28-120">Outlook 2016 및 에서 웹용 Outlook 그룹(이전의 메일 [그룹)](https://support.microsoft.com/office/1c97fcb2-0ed4-41e6-b401-58f9d7d40e39)사용에서 그룹을 사용하는 Outlook.</span><span class="sxs-lookup"><span data-stu-id="d9f28-120">Check out how to use group in Outlook 2016 and Outlook on the web in [Use contact groups (formerly distribution lists) in Outlook](https://support.microsoft.com/office/1c97fcb2-0ed4-41e6-b401-58f9d7d40e39).</span></span> 
  
<span data-ttu-id="d9f28-121">메일 그룹 [문제에 대한 도움말은](/office365/troubleshoot/groups/distribution-list-issues) 메일 그룹 문제를 확인해 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f28-121">Check out [Distribution group issues](/office365/troubleshoot/groups/distribution-list-issues) for help with distribution list issues.</span></span> 

## <a name="related-content"></a><span data-ttu-id="d9f28-122">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d9f28-122">Related content</span></span>

<span data-ttu-id="d9f28-123">[사용자 전자 메일](../email/office-365-user-email-settings.md) 설정(문서)</span><span class="sxs-lookup"><span data-stu-id="d9f28-123">[User email settings](../email/office-365-user-email-settings.md) (article)</span></span>\
<span data-ttu-id="d9f28-124">[보안 그룹에서](../email/create-edit-or-delete-a-security-group.md) 보안 그룹 만들기, 편집 또는 Microsoft 365 관리 센터(문서)</span><span class="sxs-lookup"><span data-stu-id="d9f28-124">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="d9f28-125">[공유 사서함 만들기](../email/create-a-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="d9f28-125">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>
