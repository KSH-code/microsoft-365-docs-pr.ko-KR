---
title: 운영 체제 기반 형식으로 된 용어 집합 가져오기
description: 운영 체제 기반 형식으로 된 용어 집합을 가져오는 방법 알아보기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296077"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="28f5a-103">운영 체제 기반 형식으로 된 용어 집합 가져오기</span><span class="sxs-lookup"><span data-stu-id="28f5a-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="28f5a-104">지역 \ 운영 체제 기반 형식을 사용 하 여 용어 집합을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="28f5a-105">형식에 대 한 자세한 내용은 [SharePoint 분류법과 os 형식 참조](skos-format-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28f5a-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="28f5a-106">가져오기 파일을 2만 항 미만으로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="28f5a-107">파일이 크면 유효성 검사 및 가져오기에 소요 되는 시간이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="28f5a-108">SharePoint 관리 센터에서 **콘텐츠 서비스**를 확장 하 고 **용어 저장소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="28f5a-109">용어 집합을 가져올 용어 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="28f5a-110">명령 모음에서 **용어 집합 가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="28f5a-111">서식 파일로 사용할 예제 파일을 다운로드 하려면 **sample-metadata** 를 클릭 하 여 지 하는 os 기반 형식을 사용 하는 예제 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="28f5a-112">가져올 용어 & 용어 집합이 포함 된 가져오기 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="28f5a-113">**파일 형식**에서 이상 **운영 체제 (* ttl)*\* 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="28f5a-114">**찾아보기를** 클릭 하 고 가져오기 파일을 찾아 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="28f5a-115">**가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-115">Click **Import**.</span></span> <span data-ttu-id="28f5a-116">가져오기가 완료 될 때까지 패널을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="28f5a-117">파일 가져오기가 성공적으로 완료 되 면 성공 메시지가 표시 되 고 용어 저장소가 새로 고쳐지고 새로 만든 용어 집합으로 이동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28f5a-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="28f5a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28f5a-118">See also</span></span>

[<span data-ttu-id="28f5a-119">관리되는 메타데이터 소개</span><span class="sxs-lookup"><span data-stu-id="28f5a-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="28f5a-120">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="28f5a-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="28f5a-121">용어 집합 가져오기 (사이트 수준)</span><span class="sxs-lookup"><span data-stu-id="28f5a-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)