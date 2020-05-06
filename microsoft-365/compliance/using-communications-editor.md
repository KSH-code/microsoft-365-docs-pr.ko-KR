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
description: 콘텐츠 서식을 설정할 때 통신 편집기를 사용 하 여 텍스트 및 병합 필드 변수를 변경 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034480"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="31a7f-103">커뮤니케이션 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="31a7f-103">Use the communications editor</span></span>

<span data-ttu-id="31a7f-104">포털 콘텐츠, 법적 보존 알림 및 관련 미리 알림/에스컬레이션의 콘텐츠를 정의할 때 통신 편집기를 활용 하 여 콘텐츠를 포맷 하 고 동적으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="31a7f-105">서식 있는 텍스트 편집기</span><span class="sxs-lookup"><span data-stu-id="31a7f-105">Rich text editor</span></span> 

<span data-ttu-id="31a7f-106">사용자는 통신 편집기를 사용 하 여 편집기 옵션을 통해 텍스트를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="31a7f-107">예를 들어 사용자는 글꼴 종류를 변경 하 고, 글머리 기호 목록을 만들고, 콘텐츠를 강조 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="31a7f-108">병합 필드 변수</span><span class="sxs-lookup"><span data-stu-id="31a7f-108">Merge field variables</span></span>

<span data-ttu-id="31a7f-109">통신 편집기에서 전자 메일 병합 변수를 활용 하 여 사용자 지정 된 custodian 특성을 통신의 본문 텍스트에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="31a7f-110">Custodian로 전송 되 면 병합 필드에 해당 하는 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="31a7f-111">예를 들어 custodian John Smith에 게 보내면 병합 필드 [Custodian Name]은 해당 이름으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="31a7f-112">서식 있는 텍스트 편집기 컨트롤 위쪽에서 **병합 필드** 아이콘을 선택 하 여 전자 메일 병합 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="31a7f-113">사용자 커서 위치에 따라 자리 표시 자가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="31a7f-114">병합 필드 변수 목록</span><span class="sxs-lookup"><span data-stu-id="31a7f-114">List of merge field variables</span></span>

| <span data-ttu-id="31a7f-115">필드 이름</span><span class="sxs-lookup"><span data-stu-id="31a7f-115">Field name</span></span>                  | <span data-ttu-id="31a7f-116">필드 세부 정보</span><span class="sxs-lookup"><span data-stu-id="31a7f-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="31a7f-117">표시 이름</span><span class="sxs-lookup"><span data-stu-id="31a7f-117">Display Name</span></span>  | <span data-ttu-id="31a7f-118">Custodian의 성과 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="31a7f-119">승인 링크</span><span class="sxs-lookup"><span data-stu-id="31a7f-119">Acknowledgement Link</span></span> | <span data-ttu-id="31a7f-120">각 custodian의 승인을 기록 하기 위한 사용자 지정 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="31a7f-121">포털 링크</span><span class="sxs-lookup"><span data-stu-id="31a7f-121">Portal Link</span></span>     | <span data-ttu-id="31a7f-122">Custodian 준수 포털에 대 한 사용자 지정 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="31a7f-123">관리자 발급</span><span class="sxs-lookup"><span data-stu-id="31a7f-123">Issuing Officer</span></span>                   | <span data-ttu-id="31a7f-124">지정한 발급 관리자의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="31a7f-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="31a7f-125">발급 날짜</span><span class="sxs-lookup"><span data-stu-id="31a7f-125">Issuing Date</span></span>                   | <span data-ttu-id="31a7f-126">확인이 실행 된 날짜입니다 (UTC).</span><span class="sxs-lookup"><span data-stu-id="31a7f-126">The date that the notice was issued (UTC).</span></span>              |
