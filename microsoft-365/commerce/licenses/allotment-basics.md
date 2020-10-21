---
title: 서비스 기본 사항
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: 새 서비스 구성 기능에 대해 알아봅니다.
ms.openlocfilehash: 2ab8efd637bb278faf6065559cab26cb7016975b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638234"
---
# <a name="allotment-basics"></a><span data-ttu-id="f1b7a-103">서비스 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f1b7a-103">Allotment basics</span></span>

<span data-ttu-id="f1b7a-104">라이선스 할당을 사용 하면 라이선스 제한을 설정 하 고 사용자가 선택한 제품 및 라이선스 제한에 맞게 라이선스 지정 관리를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="f1b7a-105">서비스 그룹 기반 라이선싱을 사용 하 여 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="f1b7a-106">라이선스 제한을 사용 하면 그룹의 사용자에 게 할당 된 라이선스 수를 보다 강력 하 게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="f1b7a-107">따라서 그룹의 사용자 수가 늘어나면 해당 할당에 대해 설정한 라이선스 제한 범위 내에서 유지 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="f1b7a-108">또한 서비스의 관리를 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="f1b7a-109">위임 된 서비스 소유자는 관리 센터에 대 한 액세스 권한을 얻게 되지만 자신이 소유한 사용자의 라이선스를 보고 관리할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="f1b7a-110">이렇게 하면 조직 내에서 더 세분화 된 라이선스 관리 위임이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1b7a-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f1b7a-111">Prerequisites</span></span>

<span data-ttu-id="f1b7a-112">[그룹 기반 라이선싱](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)에 대 한 라이선스 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="f1b7a-113">사용자가 사용할 수 있는 모든 제품과 함께 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="f1b7a-114">Office 제품군 및 독립 실행형 제품</span><span class="sxs-lookup"><span data-stu-id="f1b7a-114">Office suites and standalone products</span></span>
- <span data-ttu-id="f1b7a-115">엔터프라이즈 및 모바일 제품</span><span class="sxs-lookup"><span data-stu-id="f1b7a-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="f1b7a-116">Dynamics 365 제품</span><span class="sxs-lookup"><span data-stu-id="f1b7a-116">Dynamics 365 products</span></span>

<span data-ttu-id="f1b7a-117">다음 제품은 서비스 사용과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="f1b7a-118">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="f1b7a-118">Microsoft Store apps</span></span>
- <span data-ttu-id="f1b7a-119">라이선스가 없는 경우 사용자에 게 직접 할당 되는 정품 소프트웨어 또는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="f1b7a-120">Azure 리소스</span><span class="sxs-lookup"><span data-stu-id="f1b7a-120">Azure resources</span></span>

<span data-ttu-id="f1b7a-121">할당을 시작 하려면 전역 또는 라이선스 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="f1b7a-122">TVM을 간편하게</span><span class="sxs-lookup"><span data-stu-id="f1b7a-122">Getting started</span></span>

<span data-ttu-id="f1b7a-123">서비스 구성 기능은 소수의 고객 에게만 전용 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="f1b7a-124">참석 하려는 경우이 양식을 작성 [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1b7a-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
