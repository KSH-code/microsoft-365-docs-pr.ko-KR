---
title: 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Microsoft 365 Business에 대 한 다단계 인증을 설정 합니다.
ms.openlocfilehash: 4a201680172653fe5beffe7855fd35d1d395359e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42064536"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="24313-103">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="24313-103">Multi-factor authentication</span></span>

<span data-ttu-id="24313-104">MFA (multi-factor authentication)를 사용 하려면 사용자가 전화 통화 또는 인증자 앱을 사용 하 여 id를 확인 하는 두 번째 방법으로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24313-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="24313-105">Microsoft 365 관리 센터에서 MFA 설정</span><span class="sxs-lookup"><span data-stu-id="24313-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="24313-106">[![관리 센터가 변경되고 있음을 알리는 레이블이며 aka.ms/aboutM365preview에서 자세한 내용을 확인할 수 있습니다.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="24313-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="24313-107">전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24313-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="24313-108">왼쪽 탐색 창에서 **설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24313-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="24313-109">설정 페이지에서 **MFA (다단계 인증 켜기)** 카드에서 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24313-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="24313-110">**Mfa 켜기** 페이지에서 **시작**을 선택 하거나, 이미 MFA를 설정 했으며 변경 작업을 수행 하려는 경우에는 **관리** 합니다.</span><span class="sxs-lookup"><span data-stu-id="24313-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  :::image type="content" source="../media/turnonmfa.png" alt-text="MFA 페이지를 켜는 스크린샷":::

5. <span data-ttu-id="24313-112">**로그온 보안** 패널에서 **관리자에 대 한 다단계 인증 필요**를 확인 하 고 **정책 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24313-112">On the **Strengthen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
