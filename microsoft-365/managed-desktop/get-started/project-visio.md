---
title: Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치
description: Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치에 대 한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126830"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="cd3be-104">Microsoft Managed Desktop 장치에 Microsoft Project 또는 Microsoft Visio 설치</span><span class="sxs-lookup"><span data-stu-id="cd3be-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="cd3be-105">Microsoft Managed Desktop 장치에 특정 단계를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="cd3be-106">이 항목에서는 이러한 응용 프로그램의 필수 구성 요소 및 설치 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd3be-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cd3be-107">Prerequisites</span></span>

<span data-ttu-id="cd3be-108">관리자는 다음과 같은 필수 구성 요소를 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="cd3be-109">**라이선스 수량** -사용자가 올바른 microsoft Project 및 microsoft Visio 라이선스를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="cd3be-110">Microsoft Managed Desktop은 현재 이러한 응용 프로그램의 64 비트 버전만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="cd3be-111">**라이선스 이름** -이러한 응용 프로그램에 해당 하는 라이선스 이름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="cd3be-112">**Microsoft project** -Project online Professional 또는 Project online Premium</span><span class="sxs-lookup"><span data-stu-id="cd3be-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="cd3be-113">**Microsoft visio** -Visio Online 계획 2</span><span class="sxs-lookup"><span data-stu-id="cd3be-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="cd3be-114">**회사 포털** -사용자가 이러한 응용 프로그램을 설치 하려면 테 넌 트에서 회사 포털을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="cd3be-115">회사 포털이 테 넌 트에 배포 되어 있지 않으면 [회사 포털](company-portal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3be-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="cd3be-116">Microsoft Managed Desktop devices 프로젝트 및 Visio 배포</span><span class="sxs-lookup"><span data-stu-id="cd3be-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="cd3be-117">Microsoft Managed Desktop은 microsoft Project 및 Microsoft Visio를 Microsoft Intune에 두 개의 Win32 응용 프로그램으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="cd3be-118">또한 "사용 가능" 의도로 해당 응용 프로그램에 할당 될 두 개의 그룹을 Azure Active Directory에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="cd3be-119">**프로젝트 및 Visio를 배포 하려면** 사용자를 적절 한 그룹에 추가 하면 회사 포털에서 응용 프로그램을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="cd3be-120">동기화 하는 데 몇 분 정도 걸릴 수 있지만 사용자가 회사 포털에서 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="cd3be-121">Azure AD 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="cd3be-121">Azure AD Group name</span></span> | <span data-ttu-id="cd3be-122">어떤 사용자를 지정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="cd3be-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="cd3be-123">현대 회사-사무실-Project_Install</span><span class="sxs-lookup"><span data-stu-id="cd3be-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="cd3be-124">Project가 필요한 사용자</span><span class="sxs-lookup"><span data-stu-id="cd3be-124">Users needing Project</span></span>
<span data-ttu-id="cd3be-125">현대 회사-사무실-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="cd3be-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="cd3be-126">Visio가 필요한 사용자</span><span class="sxs-lookup"><span data-stu-id="cd3be-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="cd3be-127">변경 내용 전달</span><span class="sxs-lookup"><span data-stu-id="cd3be-127">Communicate changes</span></span>
<span data-ttu-id="cd3be-128">IT 관리자는 사용자에 게 프로젝트 및 Visio 설치 방법을 알려 주는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="cd3be-129">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-129">This includes:</span></span> 
- <span data-ttu-id="cd3be-130">사용자에 게 이러한 응용 프로그램을 사용할 수 있는 시기를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="cd3be-131">회사 포털에서 이러한 응용 프로그램을 설치 하는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="cd3be-131">Instructions on how to install these applications from the Company Portal.</span></span>
