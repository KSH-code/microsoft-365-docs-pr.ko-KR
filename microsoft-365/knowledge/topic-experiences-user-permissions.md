---
title: Microsoft Viva 항목의 항목 사용 권한 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva 항목에서 항목 사용 권한을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 6592103526a86671a3ff42c698c1243f63be7fef
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107392"
---
# <a name="manage-topic-permissions-in-microsoft-viva-topics"></a><span data-ttu-id="3d05e-103">Microsoft Viva 항목의 항목 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="3d05e-103">Manage topic permissions in Microsoft Viva Topics</span></span>

<span data-ttu-id="3d05e-104">[Microsoft 365](https://admin.microsoft.com)관리 센터에서 항목 사용 권한 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-104">You can manage topic permissions settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="3d05e-105">이러한 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

<span data-ttu-id="3d05e-106">항목 사용 권한 설정을 사용하여 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-106">With topic permissions settings you can choose:</span></span>

- <span data-ttu-id="3d05e-107">항목을 만들고 편집할 수 있는 사용자: 검색 중에 찾을 수 없는 새 항목을 만들거나 기존 항목 세부 정보를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-107">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic details.</span></span>
- <span data-ttu-id="3d05e-108">항목을 관리할 수 있는 사용자: 항목 관리 센터에 액세스하고 항목에 대한 피드백을 보고 수명 주기를 통해 항목을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-108">Which users can manage topics: Access the topic management center and view feedback on topics as well as move topics through the lifecycle.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="3d05e-109">항목 관리 설정에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="3d05e-109">To access topics management settings:</span></span>

1. <span data-ttu-id="3d05e-110">Microsoft 365 관리 센터에서 설정, Org 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d05e-110">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="3d05e-111">서비스 **탭에서** 항목 **환경을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d05e-111">On the **Services** tab, click **Topic experiences**.</span></span>

    ![지식에 사람 연결](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="3d05e-113">항목 사용 **권한 탭을** 선택합니다. 각 설정에 대한 자세한 내용은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d05e-113">Select the **Topic permissions** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-permissions.png) 

## <a name="change-who-has-permissions-to-update-topic-details"></a><span data-ttu-id="3d05e-115">항목 세부 정보를 업데이트할 권한이 있는 사용자 변경</span><span class="sxs-lookup"><span data-stu-id="3d05e-115">Change who has permissions to update topic details</span></span>

<span data-ttu-id="3d05e-116">항목을 만들고 편집할 수 있는 권한이 있는 사용자 업데이트:</span><span class="sxs-lookup"><span data-stu-id="3d05e-116">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="3d05e-117">항목 사용 **권한** 탭의 **항목을** 만들고 편집할 수 있는 사용자 아래에서 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d05e-117">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span>
2. <span data-ttu-id="3d05e-118">항목을 **만들고 편집할 수** 있는 사용자 페이지에서 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-118">On the **Who can create and edit topics** page, you can select:</span></span>
    - <span data-ttu-id="3d05e-119">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="3d05e-119">**Everyone in your organization**</span></span>
    - <span data-ttu-id="3d05e-120">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="3d05e-120">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="3d05e-121">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="3d05e-121">**No one**</span></span>

    ![항목 만들기 및 편집](../media/k-manage-who-can-create-and-edit.png)  

3. <span data-ttu-id="3d05e-123">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-123">Select **Save**.</span></span>

<span data-ttu-id="3d05e-124">항목을 관리할 수 있는 권한이 있는 사용자 업데이트:</span><span class="sxs-lookup"><span data-stu-id="3d05e-124">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="3d05e-125">항목 사용 **권한 탭의** 항목을 관리할 수 **있는 사용자** 아래에서 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d05e-125">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span>
2. <span data-ttu-id="3d05e-126">항목을 **관리할 수 있는 사용자 페이지에서** 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-126">On the **Who can manage topics** page, you can select:</span></span>
    - <span data-ttu-id="3d05e-127">**조직의 모든 사람**</span><span class="sxs-lookup"><span data-stu-id="3d05e-127">**Everyone in your organization**</span></span>
    - <span data-ttu-id="3d05e-128">**선택한 사용자 또는 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="3d05e-128">**Selected people or security groups**</span></span>

    ![항목 관리](../media/k-manage-who-can-manage-topics.png)  

3. <span data-ttu-id="3d05e-130">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d05e-130">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d05e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d05e-131">See also</span></span>

[<span data-ttu-id="3d05e-132">Microsoft Viva 항목에서 항목 검색 관리</span><span class="sxs-lookup"><span data-stu-id="3d05e-132">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="3d05e-133">Microsoft Viva 항목의 항목 표시 여부 관리</span><span class="sxs-lookup"><span data-stu-id="3d05e-133">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="3d05e-134">Microsoft Viva 항목에서 항목 센터의 이름 변경</span><span class="sxs-lookup"><span data-stu-id="3d05e-134">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)
