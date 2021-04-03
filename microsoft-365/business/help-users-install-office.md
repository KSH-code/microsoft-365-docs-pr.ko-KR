---
title: 사용자가 Windows 10 장치에 Office를 설치하도록 지원
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 사용자가 Windows 10 디바이스에 Office 앱을 설치하고 Microsoft 365 관리 센터에서 Windows 10 PC에 Office를 쉽게 설치할 수 있도록 합니다.
ms.openlocfilehash: 35588589cf0b816bcbd686c69684d82b62383f17
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580217"
---
# <a name="help-your-users-install-office-on-windows-10-devices"></a><span data-ttu-id="b81b4-103">사용자가 Windows 10 장치에 Office를 설치하도록 지원</span><span class="sxs-lookup"><span data-stu-id="b81b4-103">Help your users install Office on Windows 10 devices</span></span>

<span data-ttu-id="b81b4-104">[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="b81b4-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="b81b4-105">Microsoft 365 관리 센터에서 Windows 10 PC에 빠르고 쉽게 Office를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b81b4-105">You can quickly and easily install Office on Windows 10 PCs from the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="b81b4-106">이전에 설치한 Office 앱에서의 작동 방식을 알아보려면 시작하기 전에 [Office 클라이언트 설치 준비](prepare-for-office-client-deployment.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b81b4-106">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span>

<span data-ttu-id="b81b4-107">Office 앱 설치에 대한 짧은 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="b81b4-107">Watch a short video about installing Office apps.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/acce002c-0756-4b64-ac5d-2198ee96a9b1] 

<span data-ttu-id="b81b4-108">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b81b4-108">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="manage-office-deployments"></a><span data-ttu-id="b81b4-109">Office 배포 관리</span><span class="sxs-lookup"><span data-stu-id="b81b4-109">Manage Office deployments</span></span>

1. <span data-ttu-id="b81b4-110">의 관리 센터로 이동하고 전역 관리자 자격 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b81b4-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>, and sign in with global admin credentials.</span></span> 

2. <span data-ttu-id="b81b4-111">왼쪽 탐색 **창의** 설치로 이동하고  설치 페이지에서 앱 및 업데이트로 **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="b81b4-111">Go to **Setup** in the left navigation pane, and on the **Setup** page, scroll to **Apps and updates**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b81b4-112">모든 사용자가 Office 앱을 설치한 경우 이 카드가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b81b4-112">You might not see this card if all of your  users have installed Office apps.</span></span>
  
3. <span data-ttu-id="b81b4-113">사용자가 **Office 앱 카드를 설치하도록** 지원 카드에서 보기를 선택한 다음 시작 **을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="b81b4-113">On the **Help users install their Office apps** card, choose **View**, and then **Get started**.</span></span>
    
4. <span data-ttu-id="b81b4-114">전자 **메일 사용자에게 Office** 다운로드 링크에서 전자 메일로 보낼 사용자를 선택한 다음 선택한 사용자를 **전자 메일로 보내기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b81b4-114">On the **Email users a link to download Office** panel, select the users you want to email, and then **Email selected users**.</span></span>

   ![Office 다운로드 링크로 전자 메일을 보낼 사용자를 선택합니다.](../media/sendemailtousers.png)

## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="b81b4-116">Microsoft 365 Business Premium 설정 및 사용에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="b81b4-116">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="b81b4-117">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="b81b4-117">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)