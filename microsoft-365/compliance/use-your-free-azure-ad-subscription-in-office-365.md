---
title: Office 365에서 무료 Azure Active Directory 구독 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 조직의 Office 365 유료 구독에 포함되어 있는 Azure Active Directory에 액세스하는 방법을 알아봅니다.
ms.openlocfilehash: 40ed5808f6e921a3649af408ee078dba64167bb3
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610595"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="784f6-103">Office 365에서 무료 Azure Active Directory 구독 사용</span><span class="sxs-lookup"><span data-stu-id="784f6-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="784f6-p101">조직에 Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite 또는 기타 Microsoft 서비스에 대한 유료 구독이 있는 경우 Microsoft Azure Active Directory는 무료 구독이 제공됩니다. 사용자 및 다른 관리자는 Azure AD를 사용하여 사용자 및 그룹 계정을 만들고 관리할 수 있습니다. Azure AD를 사용하려면 Azure Portal로 이동하고 Office 365 계정을 사용하여 로그인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="784f6-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="784f6-107">Before you begin</span></span>

<span data-ttu-id="784f6-p102">비공개 브라우징 세션(일반 세션이 아님)을 사용하여 (아래의 1단계에서) Azure 포털에 액세스하면 현재 로그온한 자격 증명이 Azure에 전달되지 않으므로 비공개 브라우징 세션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="784f6-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this will prevent the credential that you are currently logged on with from being passed to Azure. To open an private browsing session:</span></span>

- <span data-ttu-id="784f6-110">Microsoft Edge(레거시 버전), Internet Explorer 또는 Mozilla FireFox에서 `CTRL+SHIFT+P`을(를) 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-110">In Microsoft Edge (legacy version), Internet Explorer, or Mozilla FireFox, press `CTRL+SHIFT+P`.</span></span>

- <span data-ttu-id="784f6-111">Microsoft Edge (최신 버전) 또는 Google Chrome에서 `CTRL+SHIFT+N`을(를) 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-111">In Microsoft Edge (newest version) or Google Chrome, press `CTRL+SHIFT+N`.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="784f6-112">Azure Active Directory에 액세스</span><span class="sxs-lookup"><span data-stu-id="784f6-112">Access Azure Active Directory</span></span>

1. <span data-ttu-id="784f6-113">[portal.azure.com](https://portal.azure.com)으로 이동한 후 Office 365 회사 또는 학생 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-113">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="784f6-114">Azure Portal의 왼쪽 탐색 창에서 **Azure Active Directory**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-114">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![Azure Portal의 왼쪽 탐색 창에서 Azure Active Directory를 클릭합니다.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="784f6-116">**Azure Active Directory** 관리 센터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-116">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="784f6-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="784f6-117">More information</span></span>

- <span data-ttu-id="784f6-118">무료 Azure Active Directory 구독에는 로그인 활동 보고서가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-118">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="784f6-119">로그인 활동(데이터 위반 시 유용할 수 있음)을 기록하려면 Azure Active Directory Premium을 구독해야 합닌다.</span><span class="sxs-lookup"><span data-stu-id="784f6-119">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="784f6-120">자세한 내용은 [Azure AD는 데이터를 얼마나 오래 저장하나요?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="784f6-120">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="784f6-121">Microsoft 365 관리 센터에서 **Azure Active Directory** 관리 센터에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-121">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="784f6-122">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **관리 센터** \> **Azure Active Directory**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="784f6-122">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="784f6-123">사용자 및 그룹 관리와 기타 디렉터리 관리 작업 수행에 대한 자세한 내용은 [Azure AD 디렉터리 관리](https://docs.microsoft.com/azure/active-directory/active-directory-administer)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="784f6-123">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
