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
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695270"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="a24f5-103">보존 레이블을 사용하여 레코드 선언</span><span class="sxs-lookup"><span data-stu-id="a24f5-103">Declare records by using retention labels</span></span>

><span data-ttu-id="a24f5-104">*[보안 및 규정 준수에 대한 Microsoft 365 라이센스 지침](https://aka.ms/ComplianceSD)입니다.*</span><span class="sxs-lookup"><span data-stu-id="a24f5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a24f5-105">[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 레코드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="a24f5-106">사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="a24f5-107">레코드를 선언하도록 보존 레이블을 구성 중</span><span class="sxs-lookup"><span data-stu-id="a24f5-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="a24f5-108">[보존 레이블](retention.md#retention-labels)을(를) 생성할 때 내용을 레코드로 표시하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="a24f5-109">Microsoft 365 규정 준수 센터의 **정보 거버넌스**에서 보존 레이블을 생성하거나 구성하는 경우에는 내용을 레코드로 표시하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a24f5-110">대신 **레코드 관리**를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="a24f5-111">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에서 **관리 기록** \> **파일 계획**(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="a24f5-112">**파일 계획** 페이지에서 **레이블 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="a24f5-113">마법사의 **레이블 설정** 페이지에서 콘텐츠를 레코드로 분류하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![레이블을 사용하여 콘텐츠를 레코드로 분류 확인란을 클릭합니다.](../media/recordversioning6.png)

3. <span data-ttu-id="a24f5-115">필요에 따라 SharePoint 또는 OneDrive 문서와 Exchange 전자 메일에 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="a24f5-116">해당 지침은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a24f5-116">For instructions:</span></span>
    
    - [<span data-ttu-id="a24f5-117">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="a24f5-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="a24f5-118">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="a24f5-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="a24f5-119">콘텐츠에 구성된 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="a24f5-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="a24f5-120">콘텐츠를 레코드로 표시하는 보존 레이블을 사용자가 앱에 적용할 수 있도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="a24f5-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="a24f5-121">Exchange의 경우 사서함에 대한 쓰기 권한이 있는 사용자는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="a24f5-122">SharePoint 및 OneDrive의 경우 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24f5-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="a24f5-123">보존 레이블을 사용하여 레코드로 표시된 문서 예제:</span><span class="sxs-lookup"><span data-stu-id="a24f5-123">Example of a document marked as record by using a retention label:</span></span>

![레코드로 태그가 지정된 문서에 대한 세부 정보 창](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="a24f5-125">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a24f5-125">Next steps</span></span>

<span data-ttu-id="a24f5-126">레코드에 해당 하는 문서를 업데이트 해야 하는 경우 레코드 버전 관리를 사용하여 SharePoint 또는 [OneDrive에 저장된 레코드를 업데이트](record-versioning.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a24f5-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="a24f5-127">레코드 처리에 대한 자세한 내용은 [콘텐츠 삭제](disposition.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a24f5-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
