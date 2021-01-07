---
title: 커뮤니케이션 편집기 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 커뮤니케이션 편집기를 사용하여 콘텐츠 서식을 지정하는 경우 텍스트를 변경하고 필드 변수를 병합합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769163"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="10e9d-103">커뮤니케이션 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="10e9d-103">Use the communications editor</span></span>

<span data-ttu-id="10e9d-104">포털 콘텐츠, 법적 보유 알림 및 관련 미리 알림/에스컬레이터의 콘텐츠를 정의할 때 통신 편집기를 사용하여 콘텐츠의 형식을 지정하고 동적으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="10e9d-105">텍스트 편집기</span><span class="sxs-lookup"><span data-stu-id="10e9d-105">Rich text editor</span></span>

<span data-ttu-id="10e9d-106">통신 편집기를 사용하면 편집기 옵션을 사용하여 텍스트를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="10e9d-107">예를 들어 사용자는 글꼴 유형을 변경하고 글머리 기호 목록을 만들고 콘텐츠를 강조 표시하는 등 다양한 작업도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="10e9d-108">필드 변수 병합</span><span class="sxs-lookup"><span data-stu-id="10e9d-108">Merge field variables</span></span>

<span data-ttu-id="10e9d-109">통신 편집기에서 전자 메일 병합 변수를 사용하여 사용자 지정된 속성이 통신 본문 텍스트에 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="10e9d-110">양도인에게 보내면 병합 필드가 해당 필드로 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="10e9d-111">예를 들어 조지민 님에게 보내면 병합 필드 [Custodian Name]이 해당 이름으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="10e9d-112">텍스트가 있는 편집기 컨트롤  위쪽에 있는 병합 필드 아이콘을 선택하여 전자 메일 병합 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="10e9d-113">자리 표시자는 사용자 커서의 위치에 따라 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="10e9d-114">병합 필드 변수 목록</span><span class="sxs-lookup"><span data-stu-id="10e9d-114">List of merge field variables</span></span>

| <span data-ttu-id="10e9d-115">필드 이름</span><span class="sxs-lookup"><span data-stu-id="10e9d-115">Field name</span></span>                  | <span data-ttu-id="10e9d-116">필드 세부 정보</span><span class="sxs-lookup"><span data-stu-id="10e9d-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="10e9d-117">표시 이름</span><span class="sxs-lookup"><span data-stu-id="10e9d-117">Display Name</span></span>  | <span data-ttu-id="10e9d-118">양도자 이름과 성입니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="10e9d-119">Acknowledgment Link</span><span class="sxs-lookup"><span data-stu-id="10e9d-119">Acknowledgment Link</span></span> | <span data-ttu-id="10e9d-120">각 보금주의 확인을 기록하기 위한 사용자 지정 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="10e9d-121">포털 링크</span><span class="sxs-lookup"><span data-stu-id="10e9d-121">Portal Link</span></span>     | <span data-ttu-id="10e9d-122">관리인 준수 포털에 대한 사용자 지정된 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="10e9d-123">Issuing Officer</span><span class="sxs-lookup"><span data-stu-id="10e9d-123">Issuing Officer</span></span>                   | <span data-ttu-id="10e9d-124">지정한 발행 담당자의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="10e9d-125">발행 날짜</span><span class="sxs-lookup"><span data-stu-id="10e9d-125">Issuing Date</span></span>                   | <span data-ttu-id="10e9d-126">알림이 발행된 날짜(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="10e9d-126">The date that the notice was issued (UTC).</span></span>              |
|||
