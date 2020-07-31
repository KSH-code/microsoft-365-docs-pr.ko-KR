---
title: 검색 및 분석 설정 구성-데이터 조사
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
description: 데이터 조사를 관리할 때 유사 중복, 전자 메일 스레딩 및 테마와 같은 검색 및 분석 설정을 구성 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3100c83fc027e793f7937a4d27e059ce7e3038a0
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527354"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="48a0d-103">검색 및 분석 설정 구성</span><span class="sxs-lookup"><span data-stu-id="48a0d-103">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="48a0d-104">유사 중복 및 전자 메일 스레딩</span><span class="sxs-lookup"><span data-stu-id="48a0d-104">Near duplicates and email threading</span></span>

<span data-ttu-id="48a0d-105">이 섹션에서는 중복 검색, 중복 검색 및 전자 메일 스레딩에 대 한 매개 변수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="48a0d-106">사용/사용 안 함: 사용 하도록 설정 된 경우 중복 검색, 근접 중복 검색 및 전자 메일 스레딩을 분석 흐름의 일부로 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="48a0d-107">두 사용자는 서로의 상위에 구축 되므로 모든 기능을 사용 하거나 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="48a0d-108">임계값: 두 문서의 유사성 수준이 임계값을 초과 하면 동일한 중복 집합에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="48a0d-109">기본적으로 중복 항목 숨기기:이 설정이 설정 되어 있으면 중복 문서를 숨기는 필터가 기본적으로 작업 집합에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="48a0d-110">필요한 경우 작업 집합에서 필터를 수동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="48a0d-111">최소/최대 단어 수: 중복 및 전자 메일 스레딩은 최소 단어 수와 최대 단어 수를 포함 하는 문서에 대해서만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="48a0d-112">자세한 내용은 [Near 중복 검색](near-duplicates.md) 및 [전자 메일 스레딩](email-threading.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48a0d-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="48a0d-113">테마</span><span class="sxs-lookup"><span data-stu-id="48a0d-113">Themes</span></span>

<span data-ttu-id="48a0d-114">이 섹션에서는 테마에 대 한 매개 변수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="48a0d-115">Enable/disable: 사용 하도록 설정 된 경우 분석 흐름의 일부로 테마 클러스터링을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="48a0d-116">동적으로 최대 테마 수 조정: 경우에 따라 원하는 수의 테마를 만들 수 있는 문서가 충분 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="48a0d-117">이 설정을 사용 하도록 설정 하는 경우 원하는 최대 테마 수를 강제 실행 하는 것이 아니라 시스템에서 최대 테마 수를 동적으로 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="48a0d-118">테마의 최대 수: 원하는 테마 수</span><span class="sxs-lookup"><span data-stu-id="48a0d-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="48a0d-119">테마에 번호 포함: 사용 하도록 설정 하는 경우 테마를 생성할 때 숫자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="48a0d-120">OCR (광학 문자 인식)</span><span class="sxs-lookup"><span data-stu-id="48a0d-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="48a0d-121">이 설정을 사용 하도록 설정 하면 작업 집합으로 ingested는 이미지에서 OCR이 실행 되어 검색이 가능 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="48a0d-122">텍스트 무시</span><span class="sxs-lookup"><span data-stu-id="48a0d-122">Ignore text</span></span>

<span data-ttu-id="48a0d-123">특정 텍스트에는 전자 메일 내용에 관계 없이 특정 전자 메일에 추가 되는 긴 고 지 사항 등의 분석 품질이 감소 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="48a0d-124">이러한 경우를 알고 있는 경우 텍스트 (RegEx가 지원 됨)와 텍스트를 제외 해야 하는 모듈을 지정 하 여 분석에서이 텍스트를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a0d-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
