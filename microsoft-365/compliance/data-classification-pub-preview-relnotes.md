---
title: 데이터 분류 릴리스 정보
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 데이더 분류에 대한 릴리스 정보입니다.
ms.openlocfilehash: 2b9302cfa49f9445d3cbeb5109aef70e0c8d8f7f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663043"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="a6562-103">데이터 분류 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="a6562-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="a6562-104">Exchange 사서함 수</span><span class="sxs-lookup"><span data-stu-id="a6562-104">Exchange mailbox count</span></span>

<span data-ttu-id="a6562-105">Exchange 사서함을 드릴 다운하면 작은 도구 설명이 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="a6562-106">중요한 정보 유형, 민감도 레이블 및 보존 레이블에 대해 표시되는 집계 수가 사서함 내에서 찾을 수 있는 항목 수와 정확히 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="a6562-107">이는 폴더로 드릴다운하면 집계된 수가 계산되는 동안 분류된 콘텐츠의 라이브 뷰를 가져오기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="a6562-108">암호화된 문서 렌더링</span><span class="sxs-lookup"><span data-stu-id="a6562-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="a6562-109">암호화되는 SharePoint, Exchange 및 OneDrive 파일은 콘텐츠 탐색기에서 렌더링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="a6562-110">이는 콘텐츠 탐색기에서 파일 콘텐츠를 확인할 필요와 콘텐츠를 암호화된 상태로 유지할 필요 사이에 균형을 요구하는 중요한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="a6562-111">**콘텐츠 탐색기 목록 뷰어** 및 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹에서 부여한 권한으로 파일, 파일, 메타 데이터, 웹 클라이언트를 통해 컨텐츠에 액세스하는 데 사용할 수 있는 링크의 목록 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="a6562-112">SharePoint 검색의 보존 레이블 이름에 지원되는 문자</span><span class="sxs-lookup"><span data-stu-id="a6562-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="a6562-113">SharePoint 검색은 `-` 또는 `_`가 포함된 보존 레이블 이름을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="a6562-114">예를 들어 `Label-MIP` 및 `Label_MIP`은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="a6562-115">SharePoint 검색에서는 민감도 레이블 이름 및 중요한 정보 유형 이름의 문자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="a6562-116">OneDrive가 미리 보기에 남아 있음</span><span class="sxs-lookup"><span data-stu-id="a6562-116">OneDrive remains in preview</span></span>

<span data-ttu-id="a6562-117">미리 보기 프로그램 중 OneDrive 통합에 대한 유용한 피드백에 대해 감사드립니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="a6562-118">세부 사항을 통해 작업할 때 일치하지 않는 데이터/흐름이 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="a6562-119">모든 수정 사항이 적용될 때까지 OneDrive를 미리 보기로 계속해서 제공할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="a6562-120">귀하의 지속적인 지원에 감사드립니다.</span><span class="sxs-lookup"><span data-stu-id="a6562-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="a6562-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6562-121">See also</span></span>

- [<span data-ttu-id="a6562-122">데이터 분류 시작(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a6562-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="a6562-123">레이블 활동 보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a6562-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a6562-124">레이블이 지정된 콘텐츠 보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a6562-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="a6562-125">민감도 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="a6562-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a6562-126">보존 정책 및 보존 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="a6562-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="a6562-127">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="a6562-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)