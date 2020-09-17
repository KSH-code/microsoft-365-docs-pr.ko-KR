---
title: 보존 레이블을 사용하여 레코드 선언
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 사용하여 레코드 선언
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817111"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="c7ea0-103">보존 레이블을 사용하여 레코드 선언</span><span class="sxs-lookup"><span data-stu-id="c7ea0-103">Declare records by using retention labels</span></span>

><span data-ttu-id="c7ea0-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c7ea0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c7ea0-105">문서 및 전자 메일을 레코드로 선언하려면 항목을 레코드로 표시하는 [보존 레이블](retention.md#retention-labels)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-105">To declare documents and emails as a record, you use [retention labels](retention.md#retention-labels) that mark items as a record.</span></span> <span data-ttu-id="c7ea0-106">사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="c7ea0-107">레코드를 선언하도록 보존 레이블을 구성 중</span><span class="sxs-lookup"><span data-stu-id="c7ea0-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="c7ea0-108">보존 레이블을 생성하거나 구성할 때 콘텐츠를 레코드로 표tl하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-108">When you create or configure a retention label, select the option to mark items as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="c7ea0-109">Microsoft 365 규정 준수 센터의 **정보 거버넌스**에서 보존 레이블을 생성하거나 구성하는 경우에는 내용을 레코드로 표시하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c7ea0-110">대신 **레코드 관리**를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="c7ea0-111">콘텐츠를 레코드로 표시하는 새 보존 레이블을 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="c7ea0-112">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에서 **관리 기록** \> **파일 계획**(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="c7ea0-113">**파일 계획** 페이지에서 **레이블 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="c7ea0-114">**보존 설정 정의** 페이지에서 다음을 선택하여 항목을 레코드로 표시하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-114">On the **Define retention settings** page in the wizard, choose the option to mark items as records:</span></span>
    
   ![보존 설정을 선택하여 항목을 레코드로 표시합니다.](../media/recordversioning6.png)

3. <span data-ttu-id="c7ea0-116">필요에 따라 SharePoint 또는 OneDrive 문서와 Exchange 전자 메일에 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="c7ea0-117">해당 지침은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-117">For instructions:</span></span>
    
    - [<span data-ttu-id="c7ea0-118">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="c7ea0-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="c7ea0-119">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="c7ea0-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="c7ea0-120">콘텐츠에 구성된 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="c7ea0-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="c7ea0-121">콘텐츠를 레코드로 표시하는 보존 레이블을 사용자가 앱에 적용할 수 있도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="c7ea0-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="c7ea0-122">Exchange의 경우 사서함에 대한 쓰기 권한이 있는 사용자는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="c7ea0-123">SharePoint 및 OneDrive의 경우 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="c7ea0-124">보존 레이블을 사용하여 레코드로 표시된 문서 예제:</span><span class="sxs-lookup"><span data-stu-id="c7ea0-124">Example of a document marked as record by using a retention label:</span></span>

![레코드로 태그가 지정된 문서에 대한 세부 정보 창](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="c7ea0-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c7ea0-126">Next steps</span></span>

<span data-ttu-id="c7ea0-127">레코드 관리에서 지원되는 기타 시나리오 목록은 [레코드 관리에 대한 일반적인 시나리오](get-started-with-records-management.md#common-scenarios-for-records-management)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7ea0-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
