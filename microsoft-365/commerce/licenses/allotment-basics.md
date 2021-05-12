---
title: 기본
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
description: 새로운 배정 기능에 대해 자세히 알아보습니다.
ms.date: 03/17/2021
ms.openlocfilehash: 0910673ce54f3f977ed8ecbc3d6c77ac2ebad0cc
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331697"
---
# <a name="allotment-basics"></a><span data-ttu-id="4b4ca-103">기본</span><span class="sxs-lookup"><span data-stu-id="4b4ca-103">Allotment basics</span></span>

<span data-ttu-id="4b4ca-104">라이선스 할당을 통해 라이선스 할당을 선택한 제품 및 라이선스 제한으로만 라이선스 제한 및 라이선스 할당 관리를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="4b4ca-105">할당은 그룹 기반 라이선싱을 사용하여 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="4b4ca-106">라이선스 제한을 통해 그룹의 사용자에게 할당된 라이선스 수에 대한 제어가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="4b4ca-107">따라서 그룹의 사용자 수가 증가하는 경우에도, 사용자가 추가에 대해 설정한 라이선스 제한 내에 유지되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="4b4ca-108">또한 사용권의 관리를 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="4b4ca-109">위임된 할당 소유자는 관리 센터에 액세스할 수 있지만 소유한 할당에서만 라이선스를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="4b4ca-110">이렇게 하면 조직 내에서 라이선스 관리를 보다 세밀하게 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b4ca-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4b4ca-111">Prerequisites</span></span>

<span data-ttu-id="4b4ca-112">그룹 기반 라이선싱에 대한 라이선스 [요구 사항을 충족해야 합니다.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="4b4ca-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="4b4ca-113">사용자가 사용할 수 있는 모든 제품에 대해 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="4b4ca-114">Office 제품군 및 독립 실행형 제품</span><span class="sxs-lookup"><span data-stu-id="4b4ca-114">Office suites and standalone products</span></span>
- <span data-ttu-id="4b4ca-115">Enterprise 및 Mobility 제품</span><span class="sxs-lookup"><span data-stu-id="4b4ca-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="4b4ca-116">Dynamics 365 제품</span><span class="sxs-lookup"><span data-stu-id="4b4ca-116">Dynamics 365 products</span></span>

<span data-ttu-id="4b4ca-117">다음 제품은 사용 시에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="4b4ca-118">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="4b4ca-118">Microsoft Store apps</span></span>
- <span data-ttu-id="4b4ca-119">관련 라이선스가 없는 경우 사용자에게 직접 할당된 소프트웨어 또는 소프트웨어.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="4b4ca-120">Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="4b4ca-120">Azure resources</span></span>

<span data-ttu-id="4b4ca-121">할당을 시작하려면 전역 관리자 또는 라이선스 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="4b4ca-122">시작하기</span><span class="sxs-lookup"><span data-stu-id="4b4ca-122">Getting started</span></span>

<span data-ttu-id="4b4ca-123">전용 미리 보기에서는 소수의 고객만이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b4ca-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="4b4ca-124">가입에 관심이 있는 경우 다음 양식을 [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) 작성합니다. .</span><span class="sxs-lookup"><span data-stu-id="4b4ca-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>