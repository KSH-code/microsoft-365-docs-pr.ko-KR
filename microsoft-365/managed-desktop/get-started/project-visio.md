---
title: Microsoft Project 장치에 Visio 또는 Microsoft Microsoft Managed Desktop 설치
description: Microsoft Project 또는 Microsoft Visio 설치에 대한 Microsoft Managed Desktop 정보
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925542"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="94d7a-104">Microsoft Project 장치에 Visio 또는 Microsoft Microsoft Managed Desktop 설치</span><span class="sxs-lookup"><span data-stu-id="94d7a-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="94d7a-105">Microsoft Project Microsoft Visio 디바이스에 특정 단계를 설치해야 Microsoft Managed Desktop 합니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="94d7a-106">이 항목에서는 이러한 응용 프로그램의 선행 구성 및 설치 프로세스를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94d7a-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="94d7a-107">Prerequisites</span></span>

<span data-ttu-id="94d7a-108">관리자는 다음 선행 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="94d7a-109">**라이선스 수량** - 사용자에게 올바른 Microsoft Project Microsoft Visio 라이선스를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="94d7a-110">Microsoft Managed Desktop 현재 이러한 응용 프로그램의 64비트 버전만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="94d7a-111">**라이선스 이름** - 이러한 응용 프로그램에 적합한 라이선스 이름은:</span><span class="sxs-lookup"><span data-stu-id="94d7a-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="94d7a-112">**Microsoft Project** - Project Online Professional 또는 Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="94d7a-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="94d7a-113">**Microsoft Visio** - Visio Online 계획 2</span><span class="sxs-lookup"><span data-stu-id="94d7a-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="94d7a-114">**회사 포털** - 회사 포털 응용 프로그램을 설치하려면 테넌트에서 이 응용 프로그램을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="94d7a-115">테넌트에 회사 포털 배포되지 않은 경우 [회사 포털.](company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="94d7a-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="94d7a-116">장치용 Project Visio 및 Microsoft Managed Desktop 배포</span><span class="sxs-lookup"><span data-stu-id="94d7a-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="94d7a-117">Microsoft Managed Desktop Microsoft Project Microsoft Visio 두 개의 Win32 응용 프로그램으로 Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="94d7a-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="94d7a-118">또한 "사용 가능한" 의도를 Azure Active Directory 응용 프로그램에 할당되는 두 개의 그룹도 만들 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="94d7a-119">**배포 Project Visio** 해당 그룹에 사용자를 추가하면 응용 프로그램을 해당 그룹에서 사용할 수 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="94d7a-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="94d7a-120">동기화하는 데 몇 분 정도 걸릴 수 있지만 사용자가 앱의 앱을 설치할 수 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="94d7a-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="94d7a-121">Azure AD 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="94d7a-121">Azure AD Group name</span></span> | <span data-ttu-id="94d7a-122">할당할 사용자</span><span class="sxs-lookup"><span data-stu-id="94d7a-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="94d7a-123">최신 Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="94d7a-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="94d7a-124">사용자가 필요한 Project</span><span class="sxs-lookup"><span data-stu-id="94d7a-124">Users needing Project</span></span>
<span data-ttu-id="94d7a-125">최신 Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="94d7a-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="94d7a-126">사용자가 필요한 Visio</span><span class="sxs-lookup"><span data-stu-id="94d7a-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="94d7a-127">변경 내용 전달</span><span class="sxs-lookup"><span data-stu-id="94d7a-127">Communicate changes</span></span>
<span data-ttu-id="94d7a-128">IT 관리자는 IT 관리자에게 설치 방법과 설치 방법을 Project Visio.</span><span class="sxs-lookup"><span data-stu-id="94d7a-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="94d7a-129">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-129">This includes:</span></span> 
- <span data-ttu-id="94d7a-130">이러한 응용 프로그램을 사용할 수 있는 경우 사용자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d7a-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="94d7a-131">설치 프로그램에서 이러한 응용 프로그램을 설치하는 방법에 대한 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="94d7a-131">Instructions on how to install these applications from the Company Portal.</span></span>
