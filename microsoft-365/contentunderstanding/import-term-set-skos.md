---
title: SKOS 기반 형식을 사용하여 용어 집합 가져오기
description: SKOS 기반 형식을 사용하여 용어 집합 가져오는 방법 알아보기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288518"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="2404a-103">SKOS 기반 형식을 사용하여 용어 집합 가져오기</span><span class="sxs-lookup"><span data-stu-id="2404a-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="2404a-104">SKOS 기반 형식을 사용하여 용어 집합을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="2404a-105">형식에 대한 자세한 내용은 [SharePoint 분류로 된 SKOS 형식 참조](skos-format-reference.md) 보기</span><span class="sxs-lookup"><span data-stu-id="2404a-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="2404a-106">이 기능을 사용하려면 [SharePoint Syntex](index.md) 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="2404a-107">가져오는 파일의 용어가 20,000개 이하인 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="2404a-108">파일이 커지면 유효성 검사와 가져오기에 걸리는 시간이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="2404a-109">SharePoint 관리 센터에서 **콘텐츠 서비스** 를 확장하고 **용어 저장소** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="2404a-110">용어 집합을 가져올 용어 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="2404a-111">명령 모음에서 **용어 집합 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-111">In the command bar, click **Import term set**.</span></span>

4. <span data-ttu-id="2404a-112">서식 파일로 사용 할 샘플 파일을 다운로드 하려는 경우 **sample-metadata.ttl** 을 클릭하여 SKOS 기반 형식을 사용하는 샘플 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>

5. <span data-ttu-id="2404a-113">가져올 용어 및 용어 집합이 포함 된 가져오기 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6. <span data-ttu-id="2404a-114">**파일 형식** 에서 **SKOS(\*.ttl)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7. <span data-ttu-id="2404a-115">**찾아보기** 를 클릭하여 가져오기 파일을 탐색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-115">Click **Browse** and navigate to and add your import file.</span></span>

8. <span data-ttu-id="2404a-116">**가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-116">Click **Import**.</span></span> <span data-ttu-id="2404a-117">가져오기가 완료 될 때까지 패널을 닫지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2404a-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="2404a-118">파일 가져오기가 완료되면 성공 메시지가 표시되고, 용어 저장소가 새로고침 되면 새로 만들어진 용어 집합으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2404a-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="2404a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2404a-119">See also</span></span>

[<span data-ttu-id="2404a-120">관리되는 메타데이터 소개</span><span class="sxs-lookup"><span data-stu-id="2404a-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="2404a-121">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="2404a-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="2404a-122">용어 집합 가져오기(사이트 수준)</span><span class="sxs-lookup"><span data-stu-id="2404a-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
