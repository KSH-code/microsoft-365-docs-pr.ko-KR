---
title: Microsoft 365에서 디렉터리 동기화 상태 보기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 이 문서에서는 Office 365에서 디렉터리 동기화 상태를 확인 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326952"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="c0a08-103">Microsoft 365에서 디렉터리 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="c0a08-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="c0a08-104">온-프레미스 환경을 Microsoft 365와 동기화 하 여 Azure Active Directory (Azure AD)와 함께 온-프레미스 AD DS (Active Directory 도메인 서비스)를 통합 한 경우 동기화 상태를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="c0a08-105">디렉터리 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="c0a08-105">View directory synchronization status</span></span>

- <span data-ttu-id="c0a08-106">[Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 하 고 홈 페이지에서 **DirSync 상태** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="c0a08-107">또는 **사용자** \> **활성 사용자**로 이동 하 여 **활성 사용자** 페이지에서 **더 많은** \> **디렉터리 동기화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="c0a08-108">**디렉터리 동기화** 창에서 **DirSync 관리로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="c0a08-109">디렉터리 동기화 관리 페이지에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="c0a08-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="c0a08-110">다음 표에서는 페이지에 대 한 정보를 얻을 수 있는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="c0a08-111">디렉터리 동기화에 문제가 있으면 오류가이 페이지에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="c0a08-112">발생할 수 있는 다양 한 오류에 대 한 자세한 내용은 [Microsoft 365에서 디렉터리 동기화 오류 파악](identify-directory-synchronization-errors.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0a08-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="c0a08-113">항목</span><span class="sxs-lookup"><span data-stu-id="c0a08-113">Item</span></span>|<span data-ttu-id="c0a08-114">용도</span><span class="sxs-lookup"><span data-stu-id="c0a08-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0a08-115">**확인 된 도메인**</span><span class="sxs-lookup"><span data-stu-id="c0a08-115">**Domains verified**</span></span> | <span data-ttu-id="c0a08-116">사용자가 본인을 확인 한 Microsoft 365 테 넌 트의 도메인 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="c0a08-117">**도메인이 확인 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="c0a08-117">**Domains not verified**</span></span> | <span data-ttu-id="c0a08-118">추가한 도메인 (확인 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c0a08-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="c0a08-119">**디렉터리 동기화 사용**</span><span class="sxs-lookup"><span data-stu-id="c0a08-119">**Directory sync enabled**</span></span> |<span data-ttu-id="c0a08-120">True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-120">True or False.</span></span> <span data-ttu-id="c0a08-121">디렉터리 동기화를 사용 하도록 설정 했는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="c0a08-122">**최신 디렉터리 동기화**</span><span class="sxs-lookup"><span data-stu-id="c0a08-122">**Latest directory sync**</span></span> | <span data-ttu-id="c0a08-123">디렉터리 동기화를 마지막으로 실행 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-123">Last time directory sync ran.</span></span> <span data-ttu-id="c0a08-124">마지막 동기화가 3 일 전까지 경고 및 문제 해결 도구에 대 한 링크를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="c0a08-125">**암호 동기화 사용**</span><span class="sxs-lookup"><span data-stu-id="c0a08-125">**Password sync enabled**</span></span> | <span data-ttu-id="c0a08-126">True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-126">True or False.</span></span> <span data-ttu-id="c0a08-127">온-프레미스와 Microsoft 365 테 넌 트 간에 암호 해시 동기화가 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="c0a08-128">**마지막 암호 동기화**</span><span class="sxs-lookup"><span data-stu-id="c0a08-128">**Last Password Sync**</span></span> | <span data-ttu-id="c0a08-129">암호 해시 동기화를 마지막으로 실행 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-129">Last time password hash sync ran.</span></span> <span data-ttu-id="c0a08-130">마지막 동기화가 3 일 전까지 경고 및 문제 해결 도구에 대 한 링크를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="c0a08-131">**디렉터리 동기화 클라이언트 버전**</span><span class="sxs-lookup"><span data-stu-id="c0a08-131">**Directory sync client version**</span></span> | <span data-ttu-id="c0a08-132">새 버전의 Azure AD Connect가 릴리스되면 다운로드 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="c0a08-133">**디렉터리 동기화 서비스 계정**</span><span class="sxs-lookup"><span data-stu-id="c0a08-133">**Directory sync service account**</span></span> | <span data-ttu-id="c0a08-134">Microsoft 365 디렉터리 동기화 서비스 계정의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="c0a08-135">동기화 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="c0a08-135">Monitor synchronization health</span></span>

<span data-ttu-id="c0a08-136">이 섹션에서는 각 온-프레미스 AD DS 도메인 컨트롤러에 Azure AD Connect 상태 에이전트를 설치하여 Azure AD Connect에서 제공하는 ID 인프라 및 동기화 서비스를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="c0a08-137">모니터링 정보는 Azure AD Connect Health 포털에서 사용할 수 있습니다. 이 포털에서 경고, 성능 모니터링, 사용 현황 분석, 기타 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="c0a08-138">Azure AD Connect Health 사용 방법에 대한 주요 디자인 의사 결정은 Azure AD Connect 사용 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="c0a08-139">**관리되는 인증** 옵션을 사용하는 경우 [동기화와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="c0a08-140">AD FS(Active Directory Federation Services)에서 **페더레이션 인증**을 사용하여 계정 및 그룹의 이름만 동기화하는 경우 [AD FS와 함께 Azure AD Connect Health 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="c0a08-141">완료 되 면 다음이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="c0a08-142">온-프레미스 ID 서버에 Azure AD Connect Health 에이전트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="c0a08-143">Microsoft 365 구독에 대한 Azure AD 테넌트와 함께 온-프레미스 인프라 및 동기화 활동의 현재 상태가 Azure AD Connect Health 포털에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a08-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

