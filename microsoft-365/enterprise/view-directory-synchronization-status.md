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
description: 이 문서에서는 Office 365에서 디렉터리 동기화 상태를 확인할 수 있는 방법을 알아보십시오.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924663"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="9c170-103">Microsoft 365에서 디렉터리 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="9c170-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="9c170-104">Microsoft 365와 사내 환경을 동기화하여 AD DS(Active Directory 도메인 서비스)를 Azure AD(Azure Active Directory)와 통합한 경우 동기화 상태를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="9c170-105">디렉터리 동기화 상태 보기</span><span class="sxs-lookup"><span data-stu-id="9c170-105">View directory synchronization status</span></span>

- <span data-ttu-id="9c170-106">[Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인하고 홈 페이지에서 **DirSync** 상태를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="9c170-107">또는 사용자 활성 **사용자로** 이동하여 활성 사용자 페이지에서 더 많은 디렉터리 동기화 \>    \> **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9c170-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="9c170-108">디렉터리 **동기화 창에서** **DirSync 관리로 이동을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="9c170-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="9c170-109">디렉터리 동기화 관리 페이지에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="9c170-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="9c170-110">다음 표에는 페이지에서 정보를 얻을 수 있는 기능이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="9c170-111">디렉터리 동기화에 문제가 있는 경우 이 페이지에도 오류가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="9c170-112">발생할 수 있는 여러 오류에 대한 자세한 내용은 [Microsoft 365에서](identify-directory-synchronization-errors.md)디렉터리 동기화 오류 식별을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c170-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="9c170-113">항목</span><span class="sxs-lookup"><span data-stu-id="9c170-113">Item</span></span>|<span data-ttu-id="9c170-114">용도</span><span class="sxs-lookup"><span data-stu-id="9c170-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="9c170-115">**확인된 도메인**</span><span class="sxs-lookup"><span data-stu-id="9c170-115">**Domains verified**</span></span> | <span data-ttu-id="9c170-116">소유를 확인한 Microsoft 365 테넌트의 도메인 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="9c170-117">**도메인이 확인되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9c170-117">**Domains not verified**</span></span> | <span data-ttu-id="9c170-118">추가했지만 확인되지 않은 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="9c170-119">**디렉터리 동기화 사용**</span><span class="sxs-lookup"><span data-stu-id="9c170-119">**Directory sync enabled**</span></span> |<span data-ttu-id="9c170-120">True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-120">True or False.</span></span> <span data-ttu-id="9c170-121">디렉터리 동기화를 사용하도록 설정하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="9c170-122">**최신 디렉터리 동기화**</span><span class="sxs-lookup"><span data-stu-id="9c170-122">**Latest directory sync**</span></span> | <span data-ttu-id="9c170-123">디렉터리 동기화를 마지막으로 시작한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-123">Last time directory sync ran.</span></span> <span data-ttu-id="9c170-124">마지막 동기화가 3일이 지난 경우 경고와 문제 해결 도구에 대한 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="9c170-125">**암호 동기화 사용**</span><span class="sxs-lookup"><span data-stu-id="9c170-125">**Password sync enabled**</span></span> | <span data-ttu-id="9c170-126">True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-126">True or False.</span></span> <span data-ttu-id="9c170-127">Microsoft의 사내 테넌트와 Microsoft 365 테넌트 간에 암호 해시 동기화가 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="9c170-128">**마지막 암호 동기화**</span><span class="sxs-lookup"><span data-stu-id="9c170-128">**Last Password Sync**</span></span> | <span data-ttu-id="9c170-129">암호 해시 동기화가 마지막으로 시작된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-129">Last time password hash sync ran.</span></span> <span data-ttu-id="9c170-130">마지막 동기화가 3일이 지난 경우 경고와 문제 해결 도구에 대한 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="9c170-131">**디렉터리 동기화 클라이언트 버전**</span><span class="sxs-lookup"><span data-stu-id="9c170-131">**Directory sync client version**</span></span> | <span data-ttu-id="9c170-132">새 버전의 Azure AD Connect가 릴리스된 경우 다운로드 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="9c170-133">**디렉터리 동기화 서비스 계정**</span><span class="sxs-lookup"><span data-stu-id="9c170-133">**Directory sync service account**</span></span> | <span data-ttu-id="9c170-134">Microsoft 365 디렉터리 동기화 서비스 계정의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="9c170-135">동기화 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="9c170-135">Monitor synchronization health</span></span>

<span data-ttu-id="9c170-136">이 섹션에서는 각 온-프레미스 AD DS 도메인 컨트롤러에 Azure AD Connect 상태 에이전트를 설치하여 Azure AD Connect에서 제공하는 ID 인프라 및 동기화 서비스를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="9c170-137">모니터링 정보는 Azure AD Connect Health 포털에서 사용할 수 있습니다. 이 포털에서 경고, 성능 모니터링, 사용 현황 분석, 기타 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="9c170-138">Azure AD Connect Health 사용 방법에 대한 주요 디자인 의사 결정은 Azure AD Connect 사용 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="9c170-139">**관리되는 인증** 옵션을 사용하는 경우 [동기화와 함께 Azure AD Connect Health 사용](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="9c170-140">AD FS(Active Directory Federation Services)에서 **페더레이션 인증** 을 사용하여 계정 및 그룹의 이름만 동기화하는 경우 [AD FS와 함께 Azure AD Connect Health 사용](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)을 시작하여 Azure AD Connect Health를 이해하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="9c170-141">완료되면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="9c170-142">온-프레미스 ID 서버에 Azure AD Connect Health 에이전트가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="9c170-143">Microsoft 365 구독에 대한 Azure AD 테넌트와 함께 온-프레미스 인프라 및 동기화 활동의 현재 상태가 Azure AD Connect Health 포털에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c170-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>