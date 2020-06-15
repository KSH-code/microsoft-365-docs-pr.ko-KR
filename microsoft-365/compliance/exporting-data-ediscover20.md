---
title: Advanced eDiscovery에서 사례 데이터 내보내기
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
description: 고급 eDiscovery 사례에서 프레젠테이션이나 외부 검토를 위해 검토 집합의 콘텐츠를 내보내거나 다운로드 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726469"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="1b7e2-103">Advanced eDiscovery에서 사례 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="1b7e2-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="1b7e2-104">다음과 같은 세 가지 방법으로 검토 집합에서 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="1b7e2-105">**다운로드:** 브라우저를 사용 하 여 소수의 기본 파일 집합을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="1b7e2-106">이 방법은 작은 데이터 집합을 내보내는 가장 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="1b7e2-107">이 메서드는 네이티브 파일 이름을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-107">This method preserves the native file names.</span></span>

<span data-ttu-id="1b7e2-108">**내보내기:** 내보낼 데이터를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="1b7e2-109">여기에는 PDF 파일에 저장 된 파일 메타 데이터, 네이티브 파일, 텍스트 파일 및 redacted 문서를 내보내는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="1b7e2-110">내보낸 데이터를 Azure 저장소 위치로 업로드 한 후 로컬 컴퓨터에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="1b7e2-111">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-111">For more information, see:</span></span>

- [<span data-ttu-id="1b7e2-112">검토 집합에서 문서 내보내기</span><span class="sxs-lookup"><span data-stu-id="1b7e2-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="1b7e2-113">내보내기 작업 다운로드</span><span class="sxs-lookup"><span data-stu-id="1b7e2-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="1b7e2-114">**다른 검토 집합에 추가:** 한 검토 집합에서 다른 검토 집합으로 데이터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="1b7e2-115">자세한 내용은 [한 검토 집합의 데이터를 다른 검토 집합에 추가](add-data-to-review-set-from-another-review-set.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1b7e2-116">Microsoft 365에서는 데이터가 해시 되며 확인을 위해 이러한 해시가 출력 파일에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="1b7e2-117">이 기능은 수집 통계, 부하 집합 보고서 및 내보내기 보고서 (내보내기 로드 파일 포함)와 같은 감사 로그 및 보고 기능을 통해 보완 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b7e2-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
