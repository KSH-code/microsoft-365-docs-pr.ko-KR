---
title: 사례 닫기 또는 삭제
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
description: EDiscovery 사례에서 지 원하는 조사 또는 법적 사례가 종료 되거나 삭제 된 경우 수행 되는 작업에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f91755e6d2aeba89e795a623cd1268af0a53e675
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035640"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="5962c-103">사례 닫기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="5962c-103">Close or delete a case</span></span>

<span data-ttu-id="5962c-104">EDiscovery 사례에서 지 원하는 법적 사례 또는 조사가 완료 되 면 사례를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-104">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="5962c-105">사례를 닫을 때 수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-105">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="5962c-106">대/소문자에 보류 중인 콘텐츠 위치가 포함 되어 있으면 해당 보류를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-106">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="5962c-107">이로 인해 사용자 또는 자동화 된 프로세스 (예: 삭제 정책)에 의해 콘텐츠가 영구적으로 삭제 되거나 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-107">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="5962c-108">사례를 닫으면 해당 사례와 연결 된 보류만 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-108">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="5962c-109">다른 보류가 콘텐츠 위치 (예: 소송 보존)에 배치 되는 경우</span><span class="sxs-lookup"><span data-stu-id="5962c-109">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="5962c-110">보존 정책 또는 다른 eDiscovery 사례의 보류는 계속 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-110">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="5962c-111">이 사례는 보안 & 준수 센터의 eDiscovery 페이지에 계속 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-111">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="5962c-112">닫힌 사례에 대 한 세부 정보, 보류, 검색 및 구성원은 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-112">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="5962c-113">해당 사례가 닫힌 후에 대/소문자를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-113">You can edit a case after it's closed.</span></span> <span data-ttu-id="5962c-114">예를 들어 고급 eDiscovery에서 구성원을 추가 하거나 제거 하 고, 검색을 만들고, 검색 결과를 내보내고, 검색 결과를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-114">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="5962c-115">활성 사례와 닫힌 사례의 주요 차이점은 사례를 닫을 때 보류가 해제 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-115">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="5962c-116">사례를 닫으려면:</span><span class="sxs-lookup"><span data-stu-id="5962c-116">To close a case:</span></span>

1. <span data-ttu-id="5962c-117">**고급 eDiscovery** 페이지에서 닫으려는 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-117">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="5962c-118">**설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-118">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="5962c-119">**대/소문자 닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-119">Click **Close case**.</span></span>

<span data-ttu-id="5962c-120">사례를 삭제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-120">To delete a case:</span></span>

1. <span data-ttu-id="5962c-121">**고급 eDiscovery** 페이지에서 삭제할 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-121">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="5962c-122">**설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-122">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="5962c-123">**대/소문자 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5962c-123">Click **Delete case**.</span></span> 
