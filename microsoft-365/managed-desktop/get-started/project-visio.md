---
title: microsoft Managed Desktop 장치에 microsoft Project 또는 microsoft Visio 설치
description: microsoft Managed Desktop 장치에 microsoft Project 또는 microsoft Visio 설치에 대 한 정보
keywords: microsoft Managed Desktop, microsoft 365, microsoft Project, microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288999"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="9037a-104">microsoft Managed Desktop 장치에 microsoft Project 또는 microsoft Visio 설치</span><span class="sxs-lookup"><span data-stu-id="9037a-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="9037a-105">microsoft Managed Desktop 장치에 특정 단계를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9037a-106">이 항목에서는 이러한 응용 프로그램의 필수 구성 요소 및 설치 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9037a-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9037a-107">Prerequisites</span></span>

<span data-ttu-id="9037a-108">관리자는 다음과 같은 필수 구성 요소를 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="9037a-109">**라이선스 수량** -사용자가 올바른 microsoft Project 및 microsoft Visio 라이선스를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="9037a-110">Microsoft Managed Desktop은 현재 이러한 응용 프로그램의 64 비트 버전만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="9037a-111">**라이선스 이름** -이러한 응용 프로그램에 해당 하는 라이선스 이름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="9037a-112">**Microsoft project** -project online Professional 또는 Project online Premium</span><span class="sxs-lookup"><span data-stu-id="9037a-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="9037a-113">**Microsoft visio** -visio Online 계획 2</span><span class="sxs-lookup"><span data-stu-id="9037a-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="9037a-114">**회사 포털** -사용자가 이러한 응용 프로그램을 설치 하려면 테 넌 트에서 회사 포털을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="9037a-115">회사 포털이 테 넌 트에 배포 되어 있지 않으면 [회사 포털](company-portal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9037a-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="9037a-116">Microsoft Managed Desktop devices 프로젝트 및 Visio 배포</span><span class="sxs-lookup"><span data-stu-id="9037a-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="9037a-117">지원 요청을 제출 하면 microsoft Managed Desktop이 microsoft Intune을 통해 3 개의 Azure AD 그룹 및 세 개의 응용 프로그램 배포를 만들어 테 넌 트에 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="9037a-118">**프로젝트 및 Visio를 배포 하려면**</span><span class="sxs-lookup"><span data-stu-id="9037a-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="9037a-119">**지원 요청 파일** IT 관리자는 이러한 응용 프로그램을 사용자에 게 제공 하기 위해 지원 요청을 파일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="9037a-120">microsoft managed desktop에 연결 하는 방법에 대 한 자세한 내용은 [microsoft managed desktop의 관리자 지원을](../working-with-managed-desktop/admin-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9037a-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="9037a-121">**새 Azure AD 그룹에 사용자 할당** Microsoft Managed Desktop은 테 넌 트에 3 개의 Azure AD 그룹을 만들고 해당 응용 프로그램 배포를 3 개 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="9037a-122">IT 관리자는 사용자를 적절 한 그룹에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="9037a-123">사용자를 다음 Azure AD 그룹 중 하나에만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="9037a-124">Azure AD 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="9037a-124">Azure AD Group name</span></span> | <span data-ttu-id="9037a-125">어떤 사용자를 지정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9037a-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="9037a-126">Microsoft-Office-Project-설치</span><span class="sxs-lookup"><span data-stu-id="9037a-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="9037a-127">프로젝트만 필요한 사용자</span><span class="sxs-lookup"><span data-stu-id="9037a-127">Users needing only Project</span></span>
<span data-ttu-id="9037a-128">Microsoft-Office-Visio 설치</span><span class="sxs-lookup"><span data-stu-id="9037a-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="9037a-129">Visio만 필요한 사용자</span><span class="sxs-lookup"><span data-stu-id="9037a-129">Users needing only Visio</span></span>
<span data-ttu-id="9037a-130">Microsoft-Office-프로젝트 및 Visio 설치</span><span class="sxs-lookup"><span data-stu-id="9037a-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="9037a-131">프로젝트 및 Visio가 필요한 사용자</span><span class="sxs-lookup"><span data-stu-id="9037a-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="9037a-132">이러한 그룹에 할당 되 면 회사 포털에서 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="9037a-133">동기화 하는 데 몇 분 정도 걸릴 수 있지만 사용자가 회사 포털에서 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="9037a-134">변경 내용 전달</span><span class="sxs-lookup"><span data-stu-id="9037a-134">Communicate changes</span></span>
<span data-ttu-id="9037a-135">it 관리자는 사용자에 게 프로젝트 및 Visio 설치 방법을 알려 주는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="9037a-136">성능 저하를 줄여주는 방법에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-136">This includes:</span></span> 
- <span data-ttu-id="9037a-137">사용자에 게 이러한 응용 프로그램을 사용할 수 있는 시기를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="9037a-138">회사 포털에서 이러한 응용 프로그램을 설치 하는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="9037a-139">사용자는 회사 포털에서 microsoft Project 또는 microsoft Visio를 설치 하기 전에 모든 Office 응용 프로그램을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9037a-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
